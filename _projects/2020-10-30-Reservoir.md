---
title: 'Reservoir'
subtitle: 'Quixel Remake'
date: 2020-10-30 00:00:00
description: Reservoir is custom mod map for Insurgency Sandstorm in UE4.
featured_image: '/images/reservoir/reservoir_feature.jpg'
---

![](/images/reservoir/reservoir_feature.jpg)


<a href="https://www.artstation.com/artwork/14PzPZ" class="button button--large" style="padding:0px,10px;">Art Station</a>

<!-- ## About

Reservoir was something I worked on for a few weeks in my spare time. At the end of 2020 for a modding competition. Shelved due to a discussion about when the project started, just to be safe.
The setting is the out of bounds area of a map called Power Plant in the game Insurgency: Sandstorm. The level was created in UE4 on the Insurgency: Sandstorm mod tools, utilizing the modular models and texture sets provided rather than assembling custom assets for a change of pace.
A big goal of this project was to try to first form a meaningful gameplay design from what was a low poly structure at the edge of the original maps that the community would recognize. I also wanted to try use natural light as much as possible within the interiors and add a lot of verticality wherever possible.
I began this project by exporting the original level's nature geometry (massive rocks etc) and landscape so I could bake it into a combined landscape heightmap within Marmoset toolbag. This would allow me to sculpt and extend the cliffs which were originally formed of meshes. Additionally using a combination of buffer views, photoshop I exported the base texture of the landscape, cliffs and any background mountains as a single diffuse 4k x 8k texture that matched my intended new landscape size, more on that later.
To start in UE4 I setup my new level area with the baked and extended landscape to match the same world space of the original level, then made a copy of the original levels HLOD meshes for the structures to my project so that there was something to recognize outside of the play space.
The landscape utilizes two main materials.
The first is a modification of the SDK content to allow the slope based cliff textures to be triplanar projected.
I utilized an amazing 1 texture sample, UV based triplanar method that I came across for that (I now use this in all my projects, it's amazing!) https://blueprintue.com/blueprint/eb4yb3c9/
The second was applied to landscape components just outside of my intended play area and used the 4k x 8k texture to vastly simplify the shader instructions of the out of bounds areas, while preserving the original paint layers when viewed at a distance. A static switch materials instance with the triplanar cliff textures were layered on top for the component sections that contained cliffs.
From there the rest of the project and level in pictures is mostly from my own blocking and kitbashing of the SDK assets. I came back to the project later to experiment with lighting. -->