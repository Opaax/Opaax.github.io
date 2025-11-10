---
layout: project
title: Bet'N'Die
description: Game/UI Programmer
date: 2022/06/13
image: /assets/img/Projects/BND/BetNDie_Thumbnail.jpg
tags: [Unreal, C++, Blueprint, Perforce, UI, AWS, Online, FPS]
website: https://isart-digital.itch.io/betndie
github: 
demo: 
---

![BND_Banner](/assets/img/Projects/BND/BND_Banner_NoText.png)

### Context

**Bet’N’Die** was my graduation project at Isart Digital.<br>
It was developed on a **custom version of Unreal Engine 4.26**. We built this custom version to **allow deployment on AWS**, as our servers were hosted there thanks to a partnership between AWS and Isart Digital.<br>
For version control, we used **Perforce**. The project was structured like a small studio production and lasted about 10 months, with clear milestones:

- POC
- 3C
- Alpha
- Beta
- Gold

---

### Tech

- **Unreal 4** - Engine
- **C++ - Blueprint** - Language
- **Figma** - Screen references
- **Perforce** - versionning
- **AWS** - Servers
- **Wwise** - Sound Engine

---

### Team

- **Gameplay Programmers and Pitchers** -  Clément VIEILLY, Enguerran COBERT, Joël VOIGNIER
- **Engine Programmers** - Adel HALES, Baptiste RIMETZ, Nathan LEPEC, Théophile SCHAFFNER
- **Music & Sound Design** - Baptiste DENOUX, Mattéo SISCARO
- **Game Design** - Jean CHOUPAY, Jonathan BERGOZ, Martin ROSSEL, Natacha LEONARD
- **Game Art** - Edwin VORNG, Marion BLIN, Roman DUVIVIER, Victor LOPEZ, Zoë CHAPLAIN
- **Producer** - Tristan DEROCHE, Maxime PERRIN
- **Voice Actors** - Pierre-Alain de GARRIGUES (FR), Lemmy CONSTANTINE (EN)
- **Musicians** - Thilo GOLUZA (Piano / Keyboard), Régis MOREAU (Saxophone)

---

### Screenshoot

<div class="row g-3">
    <div class="col-md-6">
        <img src="/assets/img/Projects/BND/BND_Screen_1.png" alt="Bnd" class="img-fluid rounded">
    </div>
	<div class="col-md-6">
        <img src="/assets/img/Projects/BND/BND_Screen_2.png" alt="bet" class="img-fluid rounded">
    </div>
	<div class="col-md-6">
        <img src="/assets/img/Projects/BND/BND_Screen_3.png" alt="betwon" class="img-fluid rounded">
    </div>
	<div class="col-md-6">
        <img src="/assets/img/Projects/BND/BND_Screen_4.png" alt="bet2" class="img-fluid rounded">
    </div>
</div>

---

### Trailer

<div class="ratio ratio-16x9 my-4">
    <iframe src="https://youtu.be/FxrSrZTVpUA?si=-MNufNYp0P3uy9x8" allowfullscreen></iframe>
</div>

---

### Gameplay

The initial idea was to **merge poker with a first-person shooter**. Over time, the poker aspect faded, but the casino theme remained. In this game, simply eliminating opponents does not provide much reward; it is mainly a strategic way to slow opponents token progression.<br>

The **real key to victory lies in bets**, such as:<br>
- All opponents die within X time (kills from any player count).
- Find the watermelon: a watermelon spawns in the arena, and players must shoot it. Others can destroy it to force it to respawn elsewhere.
- And more...

To win, players must accumulate tokens and **deposit them in the vault**, a shared location accessible to all. Tokens kept in your pocket don’t count! But since the vault is a high-risk spot, eliminations there are frequent.

---

### My Role

I was part of the team that **originally pitched the project**.<br>
Between June and September 2021, we explored the idea of **merging betting mechanics with FPS gameplay**. Our **USP (Unique Selling Point) became the Bet Shot**, a feature allowing players to place bets during matches. I developed the prototype for the [Bet Shot](https://www.youtube.com/watch?v=FAA6zQfjZm4), which was later expanded by other programmers for networking and additional parameters.

At the same time, I was **responsible for the game flow**, including:
- From the main menu to the start of the match.
- Waiting for all players via networking.
- Lobby system.
- Triggering cinematics at the right time.

I also created our debug menu, a user-friendly alternative to console commands. This tool allowed us to restart matches, swap weapons, adjust runtime parameters, and more. It became widely used by the entire team, and I later reused some of its features in the final game options menu.

Most of **my contribution** was focused on [menus and UI](https://www.youtube.com/watch?v=PeeU5teId58), such as:
- A fully **3D main menu**.
- A **Fortnite-style lobby**.
- The **betting machine interfaces**.
- For UI, I worked closely with a small team of 3: an UI artist, an UX designer, and myself as the programmer.

Unfortunately, the game is no longer playable since the servers are no longer available.

### Links

- [Trailer](https://www.youtube.com/watch?v=FxrSrZTVpUA)
- [Walkthrough](https://www.youtube.com/watch?v=iQB3cvAuf4o)
- [Menu Focus](https://www.youtube.com/watch?v=PeeU5teId58)
- [Prototype Betshot](https://www.youtube.com/watch?v=FAA6zQfjZm4)
- [LinkedIn](https://www.linkedin.com/company/bet-n-die/?originalSubdomain=fr)
- [itch.io](https://isart-digital.itch.io/betndie)

---

### Conclusion

This project is still the most meaningful one for me.<br>
It reminds me that my true goal is to create games as part of a team, not alone.
I also learned a lot about myself, especially how I communicate with others. My approach wasn’t always the best, but through this project, I learned to let go, trust my teammates, and collaborate more openly.<br>
It wasn’t just a graduation project, it was a human experience that forged lasting friendships and taught me what true teamwork means.<br>
Thank you to my team for believing in this project when we first pitched it, and for all the dedicated work we accomplished together.