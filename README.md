# Autumn's Hogwarts Legacy Modding Guide

A (hopefully) comprehensive guide to get you started on modding Hogwarts Legacy.

## Getting Started
In order to get started modding the game you'll need a few tools which will be linked:

Unreal Engine 4.27.2: as of the time of writing, this can be found in the [Epic Games Launcher](https://www.unrealengine.com/en-US/download)

Simply click "+" next to engine version and find 4.27.2

![AppScreenshot](https://i.postimg.cc/dtJhB8wY/image.png)

[Fmodel](https://fmodel.app/) For Viewing And Extracting Game Assets/Paths

[Blender 2.83](https://download.blender.org/release/) For Mesh Swaps *I am unsure if newer versions of blender work with the addons needed*

[Blender PSK/PSA Importer](https://github.com/Befzz/blender3d_import_psk_psa/)


# Creating A New Project

Start by launching unreal engine and making a new `Games` project
![AppScreenshot](https://i.postimg.cc/xCz3QL4C/image.png)

Use a blank template as we won't actually be using anything in the scene
![AppScreenshot](https://i.postimg.cc/L5vYFX25/image.png)

Finally, under project settings ensure you have no starter content selected. Name your project, and create project
![](https://i.postimg.cc/1Rg39JBM/image.png)

# Configuring Unreal Engine

Once your project has loaded up there are a few settings you want to change
In the top top bar above the scene view, click on `Settings -> Project Settings`
![](https://i.postimg.cc/wTtGwbHK/image.png)

Under the project tab on the left, select packaging and make sure the following boxes are checked
``Use Pak File``
``Use IO Store``
``Generate Chunks``

![](https://i.postimg.cc/ZqgcvJBC/image.png)

![](https://i.postimg.cc/mg92WwYJ/image.png)

You can close out of the `project settings` window

Lastly head over to edit on the top left corner next to file, and click ``Edit -> Editor Preferences`` 

![](https://i.postimg.cc/cJqzP7hD/image.png)

Under the ``Experimental`` tab, check the box that says ``Allow ChunkID Assignments``

![](https://i.postimg.cc/m2vVrL9k/image.png)

![](https://i.postimg.cc/KvMrw6W2/image.png)

# Using FModel To Extract Base Wand Meshes

