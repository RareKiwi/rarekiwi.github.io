---
title: 'In Game Menu'
subtitle: 'Level Selector, Mod Configuration & Loading + More'
date: 2022-05-30 00:00:00
description: Unofficial debug menu for Ready or Not.  
featured_image: '/images/roningamemenu/igm_feature.webp'
---

<div class="gallery" data-columns="1">
    <img src="/images/roningamemenu/igm_level.webp">
</div>

<a href="https://mod.io/g/readyornot/m/igm" class="button button--large" style="padding:0px,10px;">mod.io</a>

## About

This is an unofficial debug menu I have been using to load and test stuff within Ready or Not.  
The menu is fairly generic and could be added to other UE4 projects.
In it's initial incarnation, this was simply a way to display levels from the asset registry and construct unreal engine travel commands.   
This was to assist players in loading custom maps before official loading support was added to the game.  
  
With version 2, the widget was expanded to include blueprint loading, a config menu and and a session browser.  
Other mod creators have access to blueprint based DataAsset types for adding mods and levels to the menu.  

### Level Selector

A vertical list of levels which can be expanded to also choose the desired gamemode.  
Using a Data Asset, users can add a feature image, list of gamemodes, titles, descriptions and mod URLs.  
A debug option can be enabled to show the behind the scenes travel URL and allow unsupported gamemodes.  
Unsupported map mods have an entry automatically added as a QOL feature.

### Config

Provides options for the IGM menu itself, but can also have entries added via the mod Data Asset for other modders to utilize.  
Configuration widgets are not loaded until the tab is selected.  

<div class="gallery" data-columns="1">
    <img src="/images/roningamemenu/igm_config.webp">
</div>

### Status

An included modification exposes the Advanced Sessions blueprints to optionally increase multiplayer lobby sizes.  
Here you can see the current session details and a kick player feature was added before it was officially added to the game.  
Mods from the IGM mods tab can optionally be shared here to see what other mods players are using.

<div class="gallery" data-columns="1">
    <img src="/images/roningamemenu/igm_status.webp">
</div>

### Mod Menu

Mod creators can add their own data assets to this menu in order to provide a title, description, urls, blueprint loading and widget loading.

<div class="gallery" data-columns="1">
    <img src="/images/roningamemenu/igm_mods.webp">
</div>

### Servers
This menu uses Advanced Sessions to scan the the available public sessions in a player's region. They can then choose to join an open lobby.

<div class="gallery" data-columns="1">
    <img src="/images/roningamemenu/igm_server.webp">
</div>