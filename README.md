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


## Creating A New Project

Start by launching unreal engine and making a new `Games` project
![AppScreenshot](https://i.postimg.cc/xCz3QL4C/image.png)

Use a blank template as we won't actually be using anything in the scene
![AppScreenshot](https://i.postimg.cc/L5vYFX25/image.png)

Finally, under project settings ensure you have no starter content selected. Name your project, and create project
![](https://i.postimg.cc/1Rg39JBM/image.png)

## Configuring Unreal Engine

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

## Setting Up And Loading FModel

Start by opening FModel. You should be greeted with a window that looks like this

![](https://i.postimg.cc/1zq83Spm/image.png)

Click the arrows above ``Add Undetected Game`` and fill in whatever name you like, and then add the path to your game's PAK folder
*generally `C:\Program Files (x86)\Steam\steamapps\common\Hogwarts Legacy\Phoenix\Content\Paks`*

![](https://i.postimg.cc/XJx4V1DN/image.png)

Click the blue `+` button and it should move to the top, then press ok. The FModel window will now open

![](https://i.postimg.cc/PfpdGyQH/image.png)

![](https://i.postimg.cc/sXWHmM7k/image.png)

On the top left of FModel make sure the box next to `Loading Mode` is set to `All` and then click load

![](https://i.postimg.cc/XY3Z7msd/image.png)

## Extracting Wand Mesh

In Fmodel navigate your way down by double clicking the folders and go all the way down to `Phoenix/Content/RiggedObjects/Props/Wands/Wands_Customizable/Meshes`
*Note that the paths are in alphabetical order*

![](https://i.postimg.cc/xdfsr9hZ/image.png)

![](https://i.postimg.cc/bYDmfCVq/image.png)

![](https://i.postimg.cc/Nf87QW6v/image.png)

![](https://i.postimg.cc/k4tKzZJZ/image.png)

![](https://i.postimg.cc/TYcmznxR/image.png)

![](https://i.postimg.cc/FHRfwqGZ/image.png)

Double click on `Meshes` and you should see something like this

![](https://i.postimg.cc/fLwQr4fW/image.png)

Right click on `SK_T000` then select `Save Model (psk)`

![](https://i.postimg.cc/9QYhtFyg/image.png)

## Swapping The Mesh In Blender

Open up blender and ensure you have the PSK Importer installed. Link for the download and install instructions are at the [start](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/README.md#getting-started) of the guide.
In Blender go to delete everything in your scene and import the psk file
`File -> Import -> Sekelton Mesh (psk)`

![](https://i.postimg.cc/1z0b1WvW/image.png)
