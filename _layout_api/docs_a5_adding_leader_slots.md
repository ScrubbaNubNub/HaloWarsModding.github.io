## **EDITING THE LEADERPICKER.GFX FILE + Tips .gfx file editing in general**

This guide is a runthrough on the `leaderpicker.gfx` file. This controls the leader selection menu and can be modified to reposition and modify the menu to look wildly different from what it normally does.

**Quick Tip:** You can edit most `.gfx` files while *Halo Wars Definitive Edition* is open, and see those changes without reloading the game entirely. To do this, all you need to do is refresh the piece of UI that you are currently editing.  To do this, simply exit the leader selection menu (if it is already opened), and then go back into it.

1. You will need a flash editor (https://github.com/jindrapetrik/jpexs-decompiler is the one this guide will use)

2. You will also need the `leaderpicker.gfx` file. For your convenience, a baseline one with 6 extra slots has been uploaded and will be used for this guide. ([leaderpicker.zip](https://github.com/HaloWarsModding/HaloWarsModding.github.io/files/14397490/leaderpicker.zip)) This file will need to be placed in the following directory within the mod folder: (`art\ui\flash\pregame\leaderpicker\leaderpicker.gfx`)
 
3. Open the `leaderpicker.gfx` file with the editor. In the top right of your tools at the top of the application, select Tag List (this will make it easier to follow the guide)
![image](https://github.com/HaloWarsModding/HaloWarsModding.github.io/assets/37745702/6e44d553-ccb3-4e89-83f5-fde0bca89080)

4. Click `frame 1` on the left side to expand the list of options within, then scroll down to `PlaceObject (45) Depth: 80 (leader5INST)`

5. Right-Click That `PlaceObject`, and click `clone` from the list of options.  Right under `PlaceObject (45) Depth: 80 (leader5INST)`, there should be a `PlaceObject (45) Depth: 80 (leader5INST) [2]`

6. Right-Click the new object and select `Raw edit`.  At the bottom of this text, change `leader5INST` --> `leader__INST`
The underscores will be whatever number is next in the sequence of the `leader_INST` series. For the file provided, 15 would be the next number.  So, the new string will be `leader15INST`

![image](https://github.com/HaloWarsModding/HaloWarsModding.github.io/assets/37745702/ad964477-378e-4d03-8d82-218117f15ce3)

7. After this is done, you should have a completely new leader slot in the `.gfx` file. To reposition this slot, expand the `matrix: MATRIX` tab in the `Raw edit`, and edit the `translateX` & `translateY` values to move the new slot around the UI.

![image](https://github.com/HaloWarsModding/HaloWarsModding.github.io/assets/37745702/bafd9024-a2a5-4dfe-bda5-1bf1c740927e)

8. Last thing that will need to be edited is directly at the top of the list of options in `frame 1`. That is the `DoAction ActionScript` source script.  Click this tab, scroll down to line 114 and change `while(i < 15)` to `while(i < 16)`.  You should increase this by one for every additional leader slot you add.

![image](https://github.com/HaloWarsModding/HaloWarsModding.github.io/assets/37745702/66304cb1-716c-4c70-b2bc-e34bfde5c5f8)
![image](https://github.com/HaloWarsModding/HaloWarsModding.github.io/assets/37745702/b75700e0-1c17-45fd-a6f3-b44b39c25580)

If you've done everything correctly and remembered to save your changes, then you changes should now be visible ingame!
