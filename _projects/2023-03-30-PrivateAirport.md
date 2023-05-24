---
title: 'Private Airport'
subtitle: 'UE4 remake of a Classic'
date: 2023-03-30 00:00:00
description: "Private Airport is custom mod map for Ready or Not in UE4."
featured_image: '/images/ronprivateairport/privateairport_feature2.webp'
---
<div class="gallery" data-columns="1">
	<img src="/images/ronprivateairport/privateairport_23.jpeg">
	<img src="/images/ronprivateairport/privateairport_10.jpeg">
	<img src="/images/ronprivateairport/privateairport_07.jpeg">
</div>

---

<a href="https://www.nexusmods.com/readyornot/mods/2458" class="button button--large" style="padding:0px,10px;">Nexus Mods</a> <a href="https://mod.io/g/readyornot/m/privateairport" class="button button--large" style="padding:0px,10px;">mod.io</a>
## About

Remaster of Private Airport (AKA Operation Falcon Hour and Operation Talon Steel) from Tom Clancy's Rainbow Six 3: Raven Shield  
No original assets are used, all level geometry is remodelled and decorated with Megascans, UE Marketplace or created assets.
<!-- 
After Forest House I was looking for a level design project to work on in my free time and in between coding projects. 
I had just done a lot of reverse work in order to examine the Ready Or Not game maps in UE4 and recently as a part of that included a few weeks of automating a way to import the textures correctly and assign them to materials and material instances and ultimately create references of all the static meshes used in the game.  
   -->
At this point I wanted a project to improve my skills in terms of level art, so I was ideally looking for an existing layout to use as a base. 
<!-- Rainbow Six 3 maps were still fresh in my mind from some modding experiments I did in the Insurgency Sandstorm SDK for implementing a T-Hunt gamemode.  -->
When scoping out the work, 
I sifted through the levels picking out the ones that were most memorable to me, but also pre-planned what additional assets I would need to remake or source which I already had in my EGL library or that I could find on marketplaces.  
  
I enjoy nature and tropical style themes and with the Jungle Asset Pack in my library I was keen for a project to use them in, 
so Private Airport seemed like a good fit with a mix of industrial metal work which could be made with some Ready Or Not and marketplace assets.

<div class="gallery" data-columns="1">
    <img src="/images/ronprivateairport/privateairport_21.jpeg">
	<img src="/images/ronprivateairport/privateairport_17.jpeg">
	<img src="/images/ronprivateairport/privateairport_09.jpeg">
	<img src="/images/ronprivateairport/privateairport_05.jpeg">
	<img src="/images/ronprivateairport/privateairport_11.jpeg">
</div>

---

## T3D Reference

A major timesaver along with all my other conversion projects is that the original game includes a level editor with source map files and a method for exporting textures and models.  
  
My initial hurdle was finding a good method for converting those from UE2 to UE4 to use as reference. 
Having mesh references directly in Maya would save me time, so this is where a lot of my initial time is usually spent.   
  
After a few weeks of digging through old forums and software, 
and not being satisfied with a complete process, I ended up making my own helper scripts and documented guide to help others <!-- (and my forgetful future self) --> for converting UE2 maps such as from RSix3 or Swat4 to UE4.
Available on GitHub as [T3D_UE4Importer](https://github.com/RareKiwi/T3D_UE4Importer.)  
  
At this stage I had the original map geometry in the form of editable UE4 brushes along with any relevant level actors such as static meshes and lights and transform data for everything else.  

<div class="gallery" data-columns="2">
    <img src="/images/ronprivateairport/breakdown/UE4Editor_76DcFn5b3p.jpg">
	<img src="/images/ronprivateairport/breakdown/UE4Editor_WoVl0Od4BK.jpg">
</div>

I added minimal gameplay systems to a few areas such as spawns, doors, ai navmesh and baked lighting and exported the map to the game. 
My intentions were to check the gameplay and scale of the map (conversions can have issues) as well as get movement timings.



---
<img style="float:right; padding:20px;" src="/images/ronprivateairport/breakdown/image9.jpg" >
### Arch Reference


I used UE4’s brush to static mesh conversion to export an fbx of the level geometry into a maya scene. 
This model is triangulated and also subtractive so it can be a little bit difficult to work with, however, selections were made easier because I had done the work to get correct materials assigned earlier.  
  
First the skybox faces were removed and I began work on separating the level into individual models. Ultimately I was planning how I wanted to re import the level once remodelled back into UE4.
I also merged all the original Static Mesh Actors into a single Static Mesh in UE4 and exported this with no materials into Maya.
I set this as a reference layer that I can toggle if needed.  
  
I split each ground piece by material or by how large the lightmap uvs would be. I didn’t want anything too big so the lighting quality would suffer.  
From here I could isolate each building and separate the walls by individual floors and any roofing elements so I could hide them individually later when working on the interiors for example. 
<!-- After grouping and naming everything I moved onto the interiors. I sped up my selections by separating alternating rooms, which allowed me to select the remaining disconnected rooms by their now separate polygon islands.  -->
<!-- I kept each of my interior rooms floors, walls and ceilings in a single mesh each, finding the lightmap density adequate.   -->
  
I had just over 100 separate meshes so I used a maya script to export the meshes as FBX back to UE4 with the folder structure intact.  
  
I bulk imported these “Arch” meshes into UE4 with default lightmap generation and material lookup. Each mesh’s pivot point is located at the world origin, so all can be added to the level and be automatically aligned. 
The original level’s BSP brush geo from T3D importing is removed. For collision, complex collision is used as simple collision for now.
This now allows me to quickly iterate my changes into UE4 by simply pushing a button in maya with my Arch piece selected<!-- , then in UE4 right-clicking that part of the level in the content browser and reimporting it. -->

### Reference and Experiments.
A lot of my early time is spent on the exterior theme of the level, as this is the most limited of the original and is seen through a lot of the level. Just beyond the playable space, the original level features a flat sky box with jungle trees and a blurry mountain range.  
I gathered reference from similiar locations and for the interiors of buildings matching the original theme. I import Quixel materials that match those of the original or my reference images.  
A few trips around Grand Cayman airport (and smaller nearby islands) in Maps Street View help me get an idea of road to grass texture blending, rooftop materials and colours as well as tropical island roadside gardens and planting.
  
![](/images/ronprivateairport/breakdown/PrivateAirportReference.jpg)  
  
---
<img style="float:right; padding:20px;" width=400 src="/images/ronprivateairport/breakdown/image8.jpg" >
  
### Terrain  
  
I started with the main car park because I want to reuse my process developed here across all the outdoor areas.
I didn’t want the overhead of a UE4 landscape and wanted to experiment with tessellation instead for the terrain.  
  
I created a tessellation vertex paint material for the sandy grass and remodelled the asphalt and grass Arch meshes to smooth out the BSP’s curbs and provide enough polygons for tessellation and vertex painting in UE4.
I create lightmaps for each and iterate between Maya and UE4 until I’m happy with seams etc.  
  
Some mega scans grass is added and sand decals are colour adjusted to provide some transition blending onto other materials.
A 3-way asphalt material from Megascans is created for roads to break up the large surfaces from the original design.  
  
  
---
  
<div class="gallery" data-columns="1">
	<img src="/images/ronprivateairport/breakdown/terrain_b.webp">
	<img src="/images/ronprivateairport/breakdown/terrain_a.webp">
</div>
  
---
<img style="float:right; padding:20px;" width=400 src="/images/ronprivateairport/breakdown/image19.jpg" >
### Exterior Walls
The original hangar walls are simple flat geo with cinder and sheet metal and a blend texture in between.
I remodeled this as seperated and baked a tiled corrugated material based on a megascans material. This tiling template is copied and vertex merged around the exterior of the Hangar.  
  
The dimension of the metalwork is extended over the brickwork to add depth and allow for decals blending.
The metal panels are split into North, East, South and West sections to allow for culling and optimal lightmap utilisation.  

### Pre-displaced Geometry
This is one of my favourite workflows I developed for this project.
My steps generally involved; 
* Create a base UVed mesh in Maya  
* Export that as FBX (with quads)  
* Import into blender  
* Perform subdivision, displacement, simplification and solidify.  
  
Through FBX, the result was brought back into Maya for lightmaps and collision hull creation. <!-- This effect was developed initially for the corners for the light hangar brick work, but is also used and refined for the cobble walls, corrugated metal roofs, and corrugated metal walls of the garage and out of bounds hangar. -->
For the linear corrugated walls I further optimised, by removing horizontal subdivision edge-loops first, resulting in high quality displaced meshes with less than 10k tris for the whole out-of-bounds hangar.

<div class="gallery" data-columns="5">
    <img src="/images/ronprivateairport/breakdown/image4.jpg">
	<img src="/images/ronprivateairport/breakdown/image21.jpg">
	<img src="/images/ronprivateairport/breakdown/image12.jpg">
	<img src="/images/ronprivateairport/breakdown/image15.jpg">
	<img src="/images/ronprivateairport/breakdown/image23.jpg">
</div>
  
---
<img style="float:right; padding:20px;" width=800 src="/images/ronprivateairport/breakdown/image18.jpg" >

### Out-Of-Bounds
For the new out of bounds I sampled low resolution height maps from islands like Vanuatu to generate the mountain ranges as a single low-poly mesh and used Google Earth samples of runways to use as mask samples in a large scale blend material on planar geometry.  
  
I didn’t want to place forests of trees out of bounds (for time and optimisation), so I created a row of jungle meshes and merged it using UE4’s toolset into a single material blobby, opaque mesh.  
This mesh is used just past the real trees to fill the depth. I created and used spline mesh blueprints with a decal material a for runway details and linework  
  
### Arch Modelling  
<img style="float:right; padding:20px;" width=550 src="/images/ronprivateairport/breakdown/image1.jpg" >  
  
Arch models are what I call the base level geometry of terrain, walls, floors, ceilings, roofs etc.
<img style="float:left; padding:20px;" width=300 src="/images/ronprivateairport/breakdown/image10and13.webp" />  
  
Modelling was done generally building by building throughout the project. Generally the original mesh was renamed or placed in an “original” folder in Maya.  
A new mesh was then box modelled retaining clean quads to make UVing later easier. The floors, walls and ceiling were vertex separated but kept within the same object to help with further modelling or UV generation.  

  
A generic Floor(green), Wall (grey or yellow), Ceiling (pink) and door frame (blue) checker-board material was assigned to each and the UV's are unwrapped to a default texel size across the whole map by default.  
Seams are minimised in the texture UVs to start, then the uv set is duplicated and lightmap UVs are cut and auto-layouted to maximise texel space.  
Most rooms have lightmaps of 256x256 with sizes adjusted and checked in UE4’s debug views.  
  
Some rooms and walls are deleted in favour of using kitbashed UE4 assets which are exported to maya, combined, booled and vertex merged. Lightmaps are generated to remove seams.  
Some material base colours are imported into Maya to align their UVs better.  

### Weighted Normals and Smooth Edges

<!-- Learning the technique of faking round edges is probably my biggest improvement to come out of this project.  -->
Generally any edge that comes to a point has some form of smooth edge modelled in order to break up the sharp rendering of the CGI.  
  
Some models have bevels but most are smooth shade based by using supporting hard edge loops (<2-5 cm usually). 
This helps the illusion of a high-poly rounded corner edge. The prior separation of the floor and mesh polys makes this a generally quick refinement to each mesh which is done after an initial UV unwrap.  
  
Lightmap seams are avoided on these corner edge loops which results in a smooth, very high quality light bake. <!-- This softening of edges that often catch highlights, results in probably the best looking lighting I’ve ever produced. --> 
Additional layering of vertex wear or decal plaster cracks further enhances these details.  
  
<div class="gallery" data-columns="4">
	<img src="/images/ronprivateairport/breakdown/image16.jpg">
    <img src="/images/ronprivateairport/breakdown/image6.jpg">
	<img src="/images/ronprivateairport/breakdown/image5.jpg">
	<img src="/images/ronprivateairport/breakdown/image3.jpg">
</div>
  
---

### Kitbashing

In many cases where I was lacking detail I experimented with kitbashing walls from existing UE4 assets or Ready Or Not examples.  
Brick walls were laid out in UE4 and exported to Maya where I used planar face cuts to nudge the bricks into the required dimensions and also culled any back faces, unseen by the player.   
Lightmaps were packed and whole assemblies were exported back into UE4 for a great look and clean Lightmass bake.  
  
Another area kitbashed was the lobby and waiting area walls and recessed ceiling.  
I studied the hallways meshes from the Penthouse level within Ready or Not as I had similar wall lighting that I wanted to achieve in this area.  
I copied the wall profile into my arch modelling, and left holes where the static meshes from the game files would stick through, although this time in plaster-white rather than dark veneered wood.  
  
Each hut within the main hangar space has its own unique look kitbashed from asset packs, which helps differentiate each area compared to the original map. 

<div class="gallery" data-columns="4">
	<img src="/images/ronprivateairport/breakdown/image17.jpg">
    <img src="/images/ronprivateairport/breakdown/image11.jpg">
	<img src="/images/ronprivateairport/breakdown/image7.jpg">
	<img src="/images/ronprivateairport/breakdown/image20.jpg">
	<img src="/images/ronprivateairport/breakdown/image2.jpg">
</div>

---

<img style="float:right; padding:20px;" width=500 src="/images/ronprivateairport/breakdown/napkin.png" />  
### Audio
Following some experiments into modding new audio into FMOD with VOIDs sound team, we as modders were given access to a system normally reserved for dialogue and voice lines within FMOD.
This opened the way for me to implement the tropical custom sounds I'd need in my map to give it life.   
  
To support environment transitions I created a system of blueprint trigger boxes which output a value of -1 to +1 based on the players location to an opening such as a door or threshold. 
Curves are then used to provide a configurable transition value for volume, occlusion and direction which are then stored within a main blueprint map variable against a key value.  
  
This key to float variable is then read by one or more FMOD sound players within the map in order to control their volume, occlusion parameter or even their location.  
  
Some position features include attaching an environment sound to the player, then transiting it to attach to the threshold of a door way once inside.  
Another is to provide sound wrapping for certain sounds such as cicadas. Put simply as you move inside, the sound will come from the door threshold, rather than the actual outdoor 3d position.
  
The whole system was made in about a day following a few napkin sketches for the features I had been thinking about.
  
---
  
### Gallery

<div class="gallery" data-columns="2">
    <img src="/images/ronprivateairport/privateairport_01.jpeg">
	<img src="/images/ronprivateairport/privateairport_02.jpeg">
	<img src="/images/ronprivateairport/privateairport_03.jpeg">
	<img src="/images/ronprivateairport/privateairport_04.jpeg">
</div>

<div class="gallery" data-columns="3">
    <img src="/images/ronprivateairport/privateairport_06.jpeg">
	<img src="/images/ronprivateairport/privateairport_08.jpeg">
	<img src="/images/ronprivateairport/privateairport_12.jpeg">
	<img src="/images/ronprivateairport/privateairport_13.jpeg">
	<img src="/images/ronprivateairport/privateairport_14.jpeg">
	<img src="/images/ronprivateairport/privateairport_15.jpeg">
	<img src="/images/ronprivateairport/privateairport_16.jpeg">
	<img src="/images/ronprivateairport/privateairport_17.jpeg">
	<img src="/images/ronprivateairport/privateairport_18.jpeg">
	<img src="/images/ronprivateairport/privateairport_19.jpeg">
	<img src="/images/ronprivateairport/privateairport_20.jpeg">
	<img src="/images/ronprivateairport/privateairport_22.jpeg">
</div>

---
