---
layout: project
title: Eden Creative
description: C++ Unreal Developer
date: 2025-11-01
image: /assets/img/Projects/EdenCreative/Eden_Thumbnail.png
tags: [Unreal, C++, Diversion]
website: https://www.edencreative.ca/exodia-irpg
github:
demo:
---

![EdenCreative_Banner](/assets/img/Projects/EdenCreative/Eden_Banner_NoText.png)

### Context

I started at Eden Creative in November 2025 on a contract, which later transitioned into a full-time position.

The studio is composed primarily of artists who use technology to create immersive experiences where humans come first. My role was not only to build the combat system for their immersive game, but also to help the team improve their coding skills.

## The Game

The game takes place in an unconventional environment. It uses an internal technology called Unibox, which allows players to stand and move within a physical play area. Players are tracked using trackers, without any buttons or controllers.

This meant the challenge was not only technical, but also involved significant game design considerations.

Unfortunately, this “honeymoon” period was cut short when my visa was not approved.

### Tech

- **Unreal 5** - Engine
- **C++** - Language
- **Blueprint** - Integration
- **Miro** - Documentations
- **Monday** - tasks
- **Diversion** - Versioning


### My Job

My role was to create a turn-based combat system supporting up to five players and AI. I also provided coding guidance and Unreal Engine best practices to help the team improve their technical skills.

I started by developing a studio plugin for Unreal Engine to support future projects. 
This plugin includes, for example:
- **Messaging System**: Simple, but leveraging Unreal’s Gameplay Tags and optional UObject payloads.
- **Sparse Graph**: A base graph system using nodes to generate different types of grids (the project extends it for a hexagonal grid), with a robust A* pathfinding implementation.
- **Blueprint Library**: Exposes functions that are not normally accessible in Blueprints.

For the combat system, I created a Combat Director responsible for managing the overall flow. The logic is broken down into a simple state machine, keeping the director code relatively lightweight.

The AI is built using State Trees, which allowed me to define reusable base tasks and extend them for more specialized behaviors (such as a healer, for example).

### Conclusion

Thank you to the entire **Enden Creative Studio** for giving me the opportunity to work on such an exciting project.