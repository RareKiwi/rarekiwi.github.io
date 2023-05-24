---
title: 'Custom Scenarios'
subtitle: 'New game-mode layouts for Insurgency: Sandstorm'
date: 2021-01-30 00:00:00
description: Additional scenarios for Insurgency Sandstorm in UE4.
featured_image: '/images/customscenarios/insurgencyclient-win64-shipping_2021-03-03_17-17-27.jpg'
---

![](/images/customscenarios/insurgencyclient-win64-shipping_2021-03-03_17-17-27.jpg)

<a href="https://www.artstation.com/artwork/b5o2Xn" class="button button--large" style="padding:0px,10px;">Art Station</a>
<a href="https://mod.io/g/insurgencysandstorm/m/customscenarios" class="button button--large" style="padding:0px,10px;">mod.io</a>

<!-- ## About

This is a mod for Insurgency: Sandstorm made in UE4 via the game's SDK. The aim was to add re-playability and to reuse the existing levels of the game.  

The game utilizes blueprint streamed sublevels for each gamemode scenario, so a solution was needed in order to add my own additional content. 
To get around this, I created an empty new persistent level and re-added the original sublevels in addition to the original persistent level. 
Through some weird quirk of UE4 and because the baked lighting was stored in separate lighting sublevels, this solution worked perfectly, which the exception of precomputed visibility volumes. 
This allowed me to add new sublevels and content freely.
  
To modify the maps where needed I formed a number of reusable blueprints. 
One notable one was an actor with a soft reference list to hide and disable the collision of certain pieces of architecture + blocking volumes. 
This allowed me to extend and modify the levels bounds with objects lit by the direct light and volume sample grid of the static baked lighting.
Another blueprint was used in places to modify the static nav mesh data. 
This was used to make AI avoid new objects or even per active objective to direct AI flow into fair positions for the players.  
  
This mod also contains two experimental gamemodes.
The 1st is an extensive experiment to make the base "Checkpoint" game mode use a randomized set of objectives instead of a pre-determined editor defined route.
The second is backboned on the "Survival" gamemode and has the players searching possible locations marked on the map in order to find caches or trucks. -->