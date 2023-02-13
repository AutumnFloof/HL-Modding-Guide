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
![AppScreenshot](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/2.png)

Use a blank template as we won't actually be using anything in the scene
![AppScreenshot](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/3.png)

Finally, under project settings ensure you have no starter content selected. Name your project, and create project
![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/4.png)

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

Next we'll parent the armature to the mesh and weight paint it that way the new model can move in game

The first thing is `Select Only Your New Mesh` then `Hold Shift` -> `Click One Of The Bones` -> Press `Ctrl P` -> `Select Armature Deform`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/Parenting.gif)

The new mesh should now be under the armature

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/29.png)

Next is to do the opposit and `Select Only The One Of The Bones` then `Hold Shift` -> `Click The Mesh` -> `Switch From Object Mode To Weight Paint`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/WeightMode.gif)

`Control Click` the top bone to select it and then make sure the entire mesh is `Blue`, Press `R` to rotate the bone and make sure NOTHING moves and then press `Escape` to cancel the rotation

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/Rotation.gif)

If anything moves with the top bone, change the brush to `subtract` and remove any `Red/Orange/Yellow` color on your mesh

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/Subtract.gif)

Now `Control Click` the second bone and make sure your brush is on `Add` and paint the entire mesh `Red`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/Painting.gif)

*Keep adding until your entire mesh looks red*

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/30.png)

Switch Back To `Object Mode` and select ``Only The Armature``

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/ObjectMode.gif)

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/31.png)

Then to `Pose Mode`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/PoseMode.gif)

Click `The Top Bone` then press `R` to rotate the bone, if done correctly, *nothing* should move. press `Escape` to cancel rotation

Click `The Bottom Bone` then press `R` to rotate the bone, if done correctly, *everything* should move. press `Escape` to cancel rotation

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/TopBone.gif)

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/BottomBone.gif)

Congrats! You have weight painted your new mesh to the wand's armature so it can actually move in game!

## Exporting The Model

Once all the steps are done, and your mesh looks good, go to `File -> Export -> FBX`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/Export.gif)

Before clicking export, make sure to UNCHECK `Bake Animation` and UNCHECK `Add Leaf Bones`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/Settings.gif)

## Unreal Folder Structure And Importing

Back in unreal engine, make sure you are in the `content` folder, and make a new folder called `Cinematics`

Inside `Cinematics`, new folder called `Props`

Inside `Props`, new folder called `Materials` and one called `Textures`

your structure should look like this

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/Structure.png)

This next bit is a bit complex so I won't go into too much detail, but basically, we're gonna tell our custom wand to use the material from Ollivander's Wand Box from the start of the game. In order to do that, we're gonna tell our model to use that material by creating a "Dummy" reference.

In the `Materials` folder, `Right Click`, create a material called `MI_CCL_OlivandersWandBox02B`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/Mat.gif)

Now in the textures folder, Import all your model's `Color` and `Normal` texture by dragging and dropping them

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/Text.gif)

Finally go back to content and we're gonna make some new folders

Next to the `Cinematics` folder, make one called `RiggedObjects`

Inside `RiggedObjects`, make one called `Props`

Inside `Props`, make one called `Wands`

Inside `Wands`, make one called `Wands_Customizable`

Inside `Wands_Customizable`, make one called `Meshes`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/Structure.gif)

Finally, drag and drop your fbx into the `Meshes Folder`

![](https://github.com/AutumnFloof/HL-Modding-Guide/blob/main/Img/FBX.gif)
