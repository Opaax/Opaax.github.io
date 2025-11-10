---
layout: project
title: School project - Plum's Odyssey
description: Gameplay Programmer - Game Designer
date: 2020-03-25
image: /assets/img/projects/Plum/Plum_Thumbnail.png
tags: [Unity, C#, Git, Gameplay, Design]
website: https://yaysimbi.itch.io/plums-odyssey
---

![Plum_Banner](/assets/img/Projects/Plum/Plum_Banner_No_Text.png)

### Context

This project was a **multidisciplinary collaboration** involving **programmers - designers, artists, and sound designers**.

The goal was to create a 2-level platformer featuring:
- **Cross-platform compatibility** (PC and mobile)
- **Online leaderboard integration**
- A **unique gameplay twist** around a **custom gravity system**, where each platform has its own gravity.

---

### Tech

- **Unity** - Engine
- **C#** - language
- **Git** - Versionning

---

### Team

- **Programmer / Game Designer**: Rain Simbi,  Mattéo, Samuel, Enguerran
- **Art**: Nolwenn, Eleonor, Helena, Aurelie, Hugo, Vassili
- **Music & Sound**: Kevin, Henri

---

### Screenshoot

<div class="row g-3">
    <div class="col-md-6">
        <img src="/assets/img/Projects/Plum/Plum_Screen_1.jpg" alt="scr1" class="img-fluid rounded">
    </div>
	<div class="col-md-6">
        <img src="/assets/img/Projects/Plum/Plum_Screen_2.jpg" alt="scr2" class="img-fluid rounded">
    </div>
	<div class="col-md-6">
        <img src="/assets/img/Projects/Plum/Plum_Screen_3.jpg" alt="scr3" class="img-fluid rounded">
    </div>
	<div class="col-md-6">
        <img src="/assets/img/Projects/Plum/Plum_Thumbnail.png" alt="scr4" class="img-fluid rounded">
    </div>
</div>

---

### Video

<div class="ratio ratio-16x9 my-4">
    <iframe src="https://www.youtube.com/watch?v=0X-m7WTply8" allowfullscreen></iframe>
</div>

---

### My Work

I **worked closely** with the sound design team.<br>
We have to use **Unity’s built-in audio system** instead of third-party tools like FMOD or Wwise, which meant our sound designers needed custom tools to manage their **workflow efficiently**.<br>

I **developed a tool** that allowed them to define sound data, which automatically generated a list of sound names (as enums).<br>
This made it easy for gameplay programmers to simply attach a Sound Play component and reference a sound by name, the system handled all the logic behind the scenes.

I also **created the input interface** to support both PC and mobile controls.

As a designer, I contributed to level design and **built editor tools** to quickly place interactive elements such as coins and collectibles.

---

### Conclusion

It was a truly rewarding experience, especially working side by side with sound designers to create tools tailored to their needs.<br>
Even though the tools weren’t extremely advanced, they were efficient, practical, and fit perfectly within the project’s scope and timeline.