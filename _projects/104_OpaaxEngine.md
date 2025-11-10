---
layout: project
title: Opaax Engine
description: My custom game engine (wip)
date: 2025/04
image: /assets/img/Projects/OpaaxEngine/OPE_Thumbnail.png
tags: [C++, Vulkan, Engine]
github: https://github.com/Opaax/OpaaxEngine/tree/dev/OpaaxGameEngine
github:
demo:
---

![OpaaxEngine_Banner](/assets/img/Projects/OpaaxEngine/OPE_Banner_NoText.png)

### Context

I started this project because I wanted to better understand low-level **game engine programming**. 
Until now, I mostly **developed games** using existing engines like **Unity and Unreal Engine**. 
This project isn’t meant to “compete” with those engines, but rather to **improve my technical knowledge** about how game engines work under the hood.
I began by following Dave Churchill’s game engine programming course to build a strong foundation. 
Then, I used **SFML** for the graphics side and developed a small Geometry Wars–style game.
After that, I added support for **sprites and animations**.
Wanting to go deeper technically, I **implemented Vulkan** and moved to a modern rendering pipeline.

To keep progressing, I studied advanced resources such as:
- **Esoterica** Prototype Game Engine by Bobby Anguelov
- **Enigine** by furkansarihan
- The book **Game Engine Architecture** by Jason Gregory

This helped me structure and build my own engine step by step.

---

### Tech

- **Vulkan** - Rendering
- **SDL** - Abstracting
- **C++** - Language

---

### Screenshoot

<div class="row g-3">
    <div class="col-md-6">
        <img src="/assets/img/Projects/OpaaxEngine/OPE_Vulkan.gif" alt="Vulkan" class="img-fluid rounded">
    </div>
</div>

---

### Code

Entry point:
```c++
#pragma once
#include "Log/OPLogMacro.h"

#ifdef OPAAX_PLATFORM_WINDOWS
extern OPAAX::OpaaxApplication* OPAAX::CreateApplication();

inline int main(int argc, char** argv)
{
	OPAAX_VERBOSE("======================= Entry point =======================")
	
	auto lApp = OPAAX::CreateApplication();
	OPAAX_LOG("[OpaaxGameEntryPoint], created Application: %1%", %typeid(*lApp).name())
	
	lApp->Initialize();
	lApp->Run();
	// lApp Shutting down it-self.
	
	delete lApp;
	return 0;
}
#else
#error Opaax Game Engine only supports Windows!
#endif
```

Engine flow:
```c++
void OpaaxApplication::Initialize()
{
	OPAAX_VERBOSE("======================= Application Initialize =======================")

	//Loading base config for the engine
	OpaaxEngine::Get().LoadConfig();
	CreateInitMainWindow();
	OpaaxEngine::Get().Initialize(*m_opaaxWindow);
	
	bIsInitialize = true;
	
	OPAAX_VERBOSE("======================= Application End Initialize =======================")
}

void OpaaxApplication::Run()
{
	bIsRunning = true;
	
	while (bIsRunning)
	{
		// Handle events on queue
		SDL_Event lEvent;
		while (m_opaaxWindow->PollEvents(lEvent))
		{
			OpaaxEngine::Get().PollEvents(lEvent);
		}

		//The app will close
		if(m_opaaxWindow->ShouldClose())
		{
			//TODO Close event to make some save or other stuff
			bIsRunning = false;
			break;
		}

		if(m_opaaxWindow->IsMinimized())
		{
			//TODO Stop rendering
			//TODO Make a save?
			//std::this_thread::sleep_for(std::chrono::milliseconds(100));
		}

		OpaaxEngine::Get().PreUpdate();
		OpaaxEngine::Get().Update();
		OpaaxEngine::Get().PostUpdate();
	}
	
	Shutdown();
}

void OpaaxApplication::Shutdown()
{
	OPAAX_VERBOSE("======================= Application Shutting down =======================")
	
	bIsRunning = false;
	
	OpaaxEngine::Get().Shutdown();
	m_opaaxWindow->Shutdown();
	
	OPAAX_VERBOSE("======================= Application Shutting down End =======================")
}
```

Init the triangle pipepline:

```c++
void OpaaxVulkanRenderer::InitTrianglePipeline()
{
    VkShaderModule lTriangleFragShader;

    if (!VULKAN_HELPER::LoadShaderModule("Shaders/Triangle.frag.spv", m_vkDevice, &lTriangleFragShader))
    {
        OPAAX_ERROR("Error when building the triangle fragment shader module")
    }
    else
    {
        OPAAX_LOG("Triangle fragment shader successfully loaded")
    }

    VkShaderModule lTriangleVertexShader;

    if (!VULKAN_HELPER::LoadShaderModule("Shaders/Triangle.vert.spv", m_vkDevice, &lTriangleVertexShader))
    {
        OPAAX_ERROR("Error when building the triangle vertex shader module")
    }
    else
    {
        OPAAX_LOG("Triangle vertex shader successfully loaded")
    }

    //build the pipeline layout that controls the inputs/outputs of the shader
    //we are not using descriptor sets or other systems yet, so no need to use anything other than empty default
    VkPipelineLayoutCreateInfo lPipelineLayoutInfo = VULKAN_HELPER::PipelineLayoutCreateInfo();
    VK_CHECK(vkCreatePipelineLayout(m_vkDevice, &lPipelineLayoutInfo, nullptr, &m_trianglePipelineLayout));

    OpaaxVKPipelineBuilder lPipelineBuilder;

    //use the triangle layout we created
    lPipelineBuilder.PipelineLayout = m_trianglePipelineLayout;
    //connecting the vertex and pixel shaders to the pipeline
    lPipelineBuilder.SetShaders(lTriangleVertexShader, lTriangleFragShader);
    //it will draw triangles
    lPipelineBuilder.SetInputTopology(VK_PRIMITIVE_TOPOLOGY_TRIANGLE_LIST);
    //filled triangles
    lPipelineBuilder.SetPolygonMode(VK_POLYGON_MODE_FILL);
    //no backface culling
    lPipelineBuilder.SetCullMode(VK_CULL_MODE_NONE, VK_FRONT_FACE_CLOCKWISE);
    //no multisampling
    lPipelineBuilder.SetMultisamplingNone();
    //no blending
    lPipelineBuilder.DisableBlending();
    //no depth testing
    lPipelineBuilder.DisableDepthTest();

    //connect the image format we will draw into, from draw image
    lPipelineBuilder.SetColorAttachmentFormat(m_drawImage.ImageFormat);
    lPipelineBuilder.SetDepthFormat(VK_FORMAT_UNDEFINED);

    //finally build the pipeline
    m_trianglePipeline = lPipelineBuilder.BuildPipeline(m_vkDevice);

    //clean structures
    vkDestroyShaderModule(m_vkDevice, lTriangleFragShader, nullptr);
    vkDestroyShaderModule(m_vkDevice, lTriangleVertexShader, nullptr);

    m_mainDeletionQueue.PushFunction([&]()
    {
        vkDestroyPipelineLayout(m_vkDevice, m_trianglePipelineLayout, nullptr);
        vkDestroyPipeline(m_vkDevice, m_trianglePipeline, nullptr);
    });
}
```

--- 

### Links

- [Github](https://github.com/Opaax/OpaaxEngine/tree/dev/OpaaxGameEngine)

---