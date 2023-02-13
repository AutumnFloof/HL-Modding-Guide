# Autumn's Hogwarts Legacy Modding Guide

A (hopefully) comprehensive guide to get you started on modding Hogwarts Legacy.

## Getting Started
In order to get started modding the game you'll need a few tools which will be linked:

Unreal Engine 4.27.2: as of the time of writing, this can be found in the [Epic Games Launcher](https://www.unrealengine.com/en-US/download)

Simply click "+" next to engine version and find 4.27.2

![AppScreenshot](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/1.png)

[Fmodel](https://fmodel.app/) For Viewing And Extracting Game Assets/Paths

[Blender 2.83](https://download.blender.org/release/) For Mesh Swaps *I am unsure if newer versions of blender work with the addons needed*

[Blender PSK/PSA Importer](https://github.com/Befzz/blender3d_import_psk_psa/)


## Creating A New Project

Start by launching unreal engine and making a new `Games` project
![AppScreenshot]([https://i.postimg.cc/xCz3QL4C/image.png](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/2.png))

Use a blank template as we won't actually be using anything in the scene
![AppScreenshot]([https://i.postimg.cc/L5vYFX25/image.png](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/3.png))

Finally, under project settings ensure you have no starter content selected. Name your project, and create project
![]([https://i.postimg.cc/1Rg39JBM/image.png](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/4.png))

## Configuring Unreal Engine

Once your project has loaded up there are a few settings you want to change
In the top top bar above the scene view, click on `Settings -> Project Settings`
![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/5.png)

Under the project tab on the left, select packaging and make sure the following boxes are checked
``Use Pak File``
``Use IO Store``
``Generate Chunks``

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/6.png)

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/7.png)

You can close out of the `project settings` window

Lastly head over to edit on the top left corner next to file, and click ``Edit -> Editor Preferences`` 

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/8.png)

Under the ``Experimental`` tab, check the box that says ``Allow ChunkID Assignments``

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/9.png)

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/10.png)

## Setting Up And Loading FModel

Start by opening FModel. You should be greeted with a window that looks like this

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/11.png)

Click the arrows above ``Add Undetected Game`` and fill in whatever name you like, and then add the path to your game's PAK folder
*generally `C:\Program Files (x86)\Steam\steamapps\common\Hogwarts Legacy\Phoenix\Content\Paks`*

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/12.png)

Click the blue `+` button and it should move to the top, then press ok. The FModel window will now open

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/13.png)

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/14.png)

On the top left of FModel make sure the box next to `Loading Mode` is set to `All` and then click load

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/15.png)

## Extracting Wand Mesh

In Fmodel navigate your way down by double clicking the folders and go all the way down to `Phoenix/Content/RiggedObjects/Props/Wands/Wands_Customizable/Meshes`
*Note that the paths are in alphabetical order*

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/16.png)

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/17.png)

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/18.png)

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/19.png)

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/20.png)

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/21.png)

Double click on `Meshes` and you should see something like this

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/22.png)

Right click on `SK_T000` then select `Save Model (psk)`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/23.png)

## Swapping The Mesh In Blender

Open up blender and ensure you have the PSK Importer installed. Link for the download and install instructions are at the [start](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/README.md#getting-started) of the guide.
In Blender go to delete everything in your scene and import the psk file
`File -> Import -> Sekelton Mesh (psk)`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/24.png)

Your PSK file will be located where you selected to save it in FModel: {yourlocation}\Game\RiggedObjects\Props\Wands\Wands_Customizable\Meshes\SK_T000_LOD0.psk

The Wand WILL be small, this is normal, and you will want to scale your custom model downto the size of the wand to get it somewhat proportional to the player model

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/25.png)

The next step is to import your own custom model. This can be whatever your imagination can think of ;)

Make sure to scale it down move, rotate it to roughly match the wand mesh size

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/26.png)

The top bone is from where the spell casts originate from, and the bottom bone is the handle. *Untested, but perhaps moving the top bone will allow you to change the spell cast positions for odd shaped items like guns?*

Next step is to delete the original wand mesh and add your new mesh to the wand's armature.

In the top right of blender you have your `Scene Collection/Hierarchy`

Drop down SK_T000 

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/27.png)

`Right Click -> Delete` on `SK_T000_LOD0.mo`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/28.png)

## Parenting The Armature And Weight Painting The Mesh

Next well parent the armature to the mesh and weight paint it that way the new model can move in game

The first thing is select only your new mesh then `Hold Shift` -> `Click One Of The Bones` -> Press `Ctrl P` -> `Select Armature Deform`

[]()
