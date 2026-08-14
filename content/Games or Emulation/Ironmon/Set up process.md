Assets needed to run Ironmon:

- The game ROM for emulation
- Java installed
- The Emulator
- The Tracker
- Universal Pokemon Randomiser
- C++ Database update (possibly)

Do note, these files/folders should be kept organised and in folders that won't be interfered with. (eg: don't just extract them to the 'downloads' folder and let them sit)
Note also, some of the folders will be downloaded as 'zip' folders and will need to be extracted to a location.

*The ROM*
For this we'll be using 'Fire Red'. However, any Pokemon game can be used depending on the challenge you're wanting to do.
A download for the Fire Red ROM (version 1.1 recommended) can be found [here](https://archive.org/download/pokemon-fire-red-version-english-rom-v-1.1)

*Java installed*
The latest version of Java should be installed. The download can be found [here](https://www.java.com/en/download/)

*The Emulator*
The one to use as i've had no issues with is BizHawk. The download for the windows and linux based OS's can be found [here](https://github.com/TASEmulators/BizHawk/releases/tag/2.9.1)

*The tracker*
The tracker is essential for any ironmon run and is generally and i think it's just a nice piece of software. It tracks and saves pokemon move lists/data in the current seed. Shows your current mon's stats, as well as being able to provide tons of information about your current seed.
The tracker can be found [here](https://github.com/besteon/Ironmon-Tracker/releases/tag/v8.9.0) Just extract the folder somewhere for now.

*The Randomiser*
This is what is going to make each run a 'seed'. The game is completely randomised dependant on the settings you choose. Trainers/move sets/items/spawn locations for mons, the whole lot.
Download is found [here](https://github.com/Ajarmar/universal-pokemon-randomizer-zx/releases)

*c++*
This is needed for to run the emulator BizHawk efficiently/at all. To update fully, the download is free for windows and can be found [here](https://www.techpowerup.com/download/visual-c-redistributable-runtime-package-all-in-one/)
The download on the page will look like this:
![[Pasted image 20250105132316.png]]

It will download a zip while which the files will need to be extracted from (To anywhere).
You will see this file in the folder thats extracted.
![[Pasted image 20250105132541.png]]
After running this, a command prompt window will open and will start the installation. It will prompt once the installation is complete.



Once everything is downloaded, we can go ahead and set up the game.



*Setting up the game*

The first thing we need to do, is to attach the randomiser into the ROM. 

From the files download earlier in the section "randomiser" select the java file
![[Pasted image 20250105133045.png]]
This will then open this interface: (ignore any warnings/prompts)

![[Pasted image 20250105132939.png]]

The first step is to open the ROM. Once clicking on 'open ROM' a window will appear where you can navigate to where you saved the downloaded ROM. Select it and hit open.

![[Pasted image 20250105133315.png]]

Once open, you'll see the interface change slightly.

The next step is to load the 'string'. This is essentially the type of randomiser you're wanting to use, depending on the game style you're playing. As we're setting up the Kaizo IronMon, we're going to use the string specifically for that. 
Strings for all game types and rules can be found [here](https://gist.github.com/UTDZac/a147c497424dfbd537d8c4b0c22b5621) 

The string for Kaizo is seen below:
321WRIEEjIBAAQABwCRAAKeBhsECQEAFAACCQAuEgAAAAAABRi45ATkAYYICTIGBAIyAAUYEEZpcmUgUmVkIChVKSAxLjF0u1o648M4ig==

Click the settings icon (top right) and select *Get/load settings string*. 
This box will then appear:
![[Pasted image 20250105134401.png]]

In the load section, copy and past the FULL string seen above, then click load. This will change all the settings in the interface (ignore any pop ups).
Our randomiser is now loaded.

Next up, *installing the tracker.*

There is a fair bit of installation when it comes to the tracker. There are two ways of doing it but i always find the manual installation better as you have more control over whats happening. Then, if anything goes wrong, it's easy to take back steps.

Open the emuhawk emulator we download earlier (It's a good idea to create a shortcut/taskbar icon)
![[Pasted image 20250105135606.png]]
Once open, proceed to open the ROM. 
*File -- open ROM -- select ROM from wherever you saved it*

![[Pasted image 20250105220025.png]]

Once opened and the ROM has loaded, in the taskbar, head to *tools -- Lua console*
You will be presented with the following:

![[Pasted image 20250105140107.png]]

Go to *Script -- open script* then in the open window, locate the ironmon-tracker folder we downloaded earlier. In here, you'll see a *ironmon-tracker.lua* file. This is what we want to open. 

![[Pasted image 20250105215314.png]]

After opening, the game screen will look as follows:

![[Pasted image 20250105140920.png]]

Once open, there's a couple more vital steps.
In the tracker, you can see a small cog which is for the settings of the tracker. 
Go into that and select the *'new runs'* option

![[Pasted image 20250105220438.png]]

Ensure you are using the *'Generate ROM each time'*.
This means we don't have to constantly generate new seeds. 

![[Pasted image 20250105220657.png]]

We do need to set the 3 settings seen currently with an X.

*Randomiser JAR*
This is the Java file we opened earlier and loaded the 'string' into
![[Pasted image 20250105221221.png]]

*Source ROM*
This is the original ROM we downloaded (the game, essentially)

![[Pasted image 20250105221428.png]]
(either one of these)

*Settings file*
When hitting set, a file explorer window should open in the correct folder location to select your game type (we're playing FRLG Kaizo).

![[Pasted image 20250105222856.png]]

If for some reason you're not taken straight here, you can follow the file path seen in the image above (starting with 'Ironmon-tracker)

The game window should now look as follows

![[Pasted image 20250105223547.png]]

The game is now set. Every time you reset the game a new seed will be generated. 

There are MANY quality of life settings which i heavily advise to go through to improve the experience and the fluidity of runs, especially if streaming. 


