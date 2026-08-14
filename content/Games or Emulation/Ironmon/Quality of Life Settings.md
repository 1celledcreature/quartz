These settings/methods really help when playing modes like kaizo due to the continual resets.

The 1st one is a big one. 

*Patching the game*
**NOTE - THIS ONLY WORKS WITH VERSION 1.1**
Yes, after going through all that effort to get the ROM and the tracker working in unison, we're now going to update the ROM (Trust me its worth it).

Patching the game does the following:

- Shortens the intro (skips to gender, naming player, naming rival)
- Talk to mom to skip to the lab
- Shorter lab text
- Oak talks less in the first battle
- When you reach the top of route 1 automatically receive package.
- running back into pallet turns in package and gets pokeballs (This allows access to the pokecenter in viridian, and doesn't skip any grass patches)
- Prompts re-use for repels

The intro won't matter too much as there's an easy way round that which i'll talk about later.

First, download the file *pokefirered_7.6.bps* (7.6 is current version at time of making) [here](https://github.com/DrSeil/FireRed-Intro-Patch/blob/main/pokefirered_7.6.bps)

Then head to https://www.marcrobledo.com/RomPatcher.js/

On the webpage, upload your ROM (version 1.1) and the file we just downloaded into the designated slots (ROM file & Patch file) as seen below and hit *'Apply patch'*

![[Pasted image 20250105231937.png]]

This will generate a new file that will be downloaded. This is your new ROM which you'll need to load into the emulator.
**Also note** - The rom will need to be changed in the tracker settings 'new runs' section (see set up process page)

*Loading quick when initially opening BizHawk*
Once your ROM with the randomiser and tracker settings has been set up and opened once, it's easy to open again.
Opening from scratch, you can hit **File -- Recent ROM -- select the ROM**. The AutoRandomized one is the one to select.
![[Pasted image 20250105233456.png]]
You can see my kaizo randomised game as the top one.

*Lua console (Tracker) opens with the emulator*
When opening the emulator we want to ensure the console opens with it. This means that when opening the ROM, the tracker will automatically open.
In the 'Lua console' window, head to the settings tab and toggle the 'Autoload with EmuHawk' on. 
See my settings below.
![[Pasted image 20250106221246.png]]

Now when opening the emulator, the Lua console should automatically load with the tracker script already there. The Lua console can essentially now be ignored.

*EmuHawk Settings*
**Controller - mapping**
In the emulator taskbar, go to **config -- controllers**
![[Pasted image 20250106230432.png]]
Click on the text in the box (up,J1 ect) then tap the input on the controller plugged into the PC. The input option will automatically descend to the next after inputting.

**Controller - Hotkeys**
My opinion is you should have a button mapped for a reset. Then, as soon as runs end, you can reset the ROM immediately. As i use a PS4 pad, i mapped this to the PS button itself.