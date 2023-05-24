---
title: 'Forest House'
subtitle: 'Spooky Woods'
date: 2022-07-30 00:00:00
description: Forest House is custom mod map for Ready or Not in UE4. 
featured_image: '/images/ronforesthouse/foresthouse_feature.jpg'
---

<div class="gallery" data-columns="1">
    <img src="/images/ronforesthouse/1235-1674881882-2019931607.jpeg">
    <img src="/images/ronforesthouse/1235-1674881882-1057211206.jpeg">
</div>

## About  
<a href="https://www.nexusmods.com/readyornot/mods/1235" class="button button--large" style="padding:0px,10px;">Nexus Mods</a> <a href="https://mod.io/g/readyornot/m/foresthouse" class="button button--large" style="padding:0px,10px;">mod.io</a>
  
This is a sample map [marketplace asset](https://www.unrealengine.com/marketplace/en-US/product/atmospheric-house-modular) which I prepared for Ready or Not.  
I created the landscaping and surrounding structures using marketplace or game assets.  
Gameplay elements were added by me. Collision was edited where needed.  
  
---
  
### Lighting and optimisation

Lighting was reworked for Ready or Not and a blueprint based switcher is included for a "dawn" lighting preset chosen by the host.  
An optimisation trigger blueprint was created to disable lights that are out of sight from the player such as when the player is on a different floor.
I optimised the file size by replacing "clean" referenced textures in master materials and applying size limits and lossy compression.  

<div class="gallery" data-columns="1">
    <img src="/images/ronforesthouse/UE4Editor_0cTEAHVoqq.jpg">
</div> 

### Doors and glass

I took the included marketplace door assets and adjusted and remodelled them to be destructible and utilise Ready or Not's door interaction system.  
Each door is "pre" destroyed into a 3x3 grid of chunks with the splinters hidden within.

<div class="gallery" data-columns="1">
    <img src="/images/ronforesthouse/UE4Editor_zqkXYm5Ogm.jpg">
</div> 

A custom blueprint system also allowed for an additional glass destruction layer for each chunk,  
with the gibs pre modeled from vornoii or glass impact cells.  
  
The glass system was copied into a standalone blueprint to enable breakable glass for the windows and non-opening doors.  
  
Materials were adjusted for increased grime and a spiral blur was applied to glass to obstruct player and ai vision.  
  
<video width="100%" preload="auto" muted controls loop>
    <source type="video/mp4" src="/images/ronforesthouse/fh_glassbreak.mp4" />
</video>
  
<img style="float:right; padding:20px;" width=500 src="/images/ronforesthouse/UE4Editor_s5xySdxkIe.jpg" /> 
  
### Audio

A blueprint system was created to fade between two FMOD events based on distance and on which side of the trigger the player was standing.  
This allowed me to reuse Ready or Not's sounds to add ambiance for the outdoors, interior and basement of the level.  
  
Additionally if the Dawn lighting scenario is chosen the audio is switched out to match the theme.
  
  
### Gallery

<div class="gallery" data-columns="2">
    <img src="/images/ronforesthouse/1235-1674881888-1007423891.jpeg">
    <img src="/images/ronforesthouse/1235-1654850589-483640929.webp">
	<img src="/images/ronforesthouse/1235-1654850587-2030358324.jpeg">
	<img src="/images/ronforesthouse/highresscreenshot00011.jpg">
	<img src="/images/ronforesthouse/HighresScreenshot00037.jpg">
	<img src="/images/ronforesthouse/HighresScreenshot00039.jpg">
	<img src="/images/ronforesthouse/HighresScreenshot00040.jpg">
	<img src="/images/ronforesthouse/HighresScreenshot00041.jpg">
	<img src="/images/ronforesthouse/HighresScreenshot00042.jpg">
	<img src="/images/ronforesthouse/HighresScreenshot00038.jpg">
</div>

