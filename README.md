# Blasphemous port for PS VITA

This repos contains patch you can apply on Blasphemous Steam data files in order to get the game running on PS VITA.
**Please read carefully following sections before going on with the patching procedure**


## Technical notes

First, let's clear one thing up: 
Keep your expectations low with this port !
You will encounter issues, and a lot of crashes (due to memory issues).

Porting this game was (is still, and will always be) a real challenge because of multiple reasons :
- The game is huge in a lot of aspects
- It makes use of FMOD Studio for audio (which consumes half of the available resource of the VITA)
- It was not really optimized in a few aspects (a lot of effects were drawn by hand in pixel art instead of using particles or shaders, a lot of blank spaces in spritesheets, tons of scenes loaded at the same time leading to tons of textures loaded in memory at the same time, ...)
- There is at least one memory leak I've not been able to identify yet, which will lead you for sure in some crashes during your game sessions.
  This memory leak is also part of the retail versions but less noticeable because more memory margin

In order to keep the experience viable, the port comes up with some "restricted modes" that will restrict some functionalities (videos or sound fx) to spare some memory (see below).


## Functional notes

On a functional point of view, despites concessions listed below, this port comes up with latest version, all DLC's are so part of the port.
You shouldn't face any blocking issues, I've completed the game with all 3 endings, 100% in NG, more than 100% in NG+, all boss fights achievable as well as all game modes (boss rush, demake).


## Concessions

Some concessions were made to make the game fit in PS VITA.

- Textures were downsized to fit in PS VITA RAM (I could have named the port "Blasphemous LD")
- Some textures set down to 16-bits color instead of 32-bits
- Sound is sometimes glitchy and sample rate was reduced to 8k (I had to find some balance between quality and memory, more quality led to more memory usage and so, more crashes)
- Voices were ripped off
- Credits were ripped off (the way it was implemented was too heavy for VITA's RAM)
- Main menu face & background selection is disabled 

Don't expect these concessions to be changed in a later version (if any).


## Known issues

ALPHA version comes up with some known issues :

- Game will crash for sure because of VITA's memory full (beginning of the game is quite stable, crashes will occur the more you will progress in the map).
  Most of the time, simply relaunch the game, go back to your last save and continue progressing to go further.
  Sometimes, rebooting via Safe Mode (hold standby button for 10 seconds) and restarting the VITA will be needed. You won't lose anything with that process.
- It always takes some time to FMOD to synchronize sound with game when you enter a new area. It should be good after a few seconds.
- Reducing the size of the textures led to gaps between textures in game, and some trembling sprites.
- Some areas have low fps when there are a lot of enemies.
- Shaders are not yet implemented in ALPHA version (which means skin selection won't change the Penitent appearance).
- Scroll down via right stick in inventory is not working. To scroll down, use the bottom of the touch screen. 
  This will lock the item selection. In order to unlock it, press TRIANGLE to see the Lore description or press L/R to change inventory menu and go back.
- Bell carrier enemy behaviour is bugged.
- One dialogue line or animation were ripped off here and there because some were causing issues.
- One elevator is locking the camera below the player when going up. When the elevator stops, simply go left to another screen and come back to have the camera focusing the player again.
- Buttons icons are not displayed in some UI popups and are replaced by their text label.


## Restricted modes

Port comes up with 3 game modes, some with restrictions to spare some memory usage :
- Full Experience = All cinematics and sounds (except voices) are played.
- NO SFX = Sounds are restricted to only ambient background and musics.
- NO VIDEO = Some cinematics are not played.

Selection of the restricted modes is done at the landing screen (when app is loaded, on the black screen with the big red "Blasphemous") :
- Press L to enable "NO SFX" mode
- Press R to enable "NO VIDEO" mode 
- Press any other key to go with Full experience mode

Remarks :
- Modes can only be selected at the landing screen and cannot be rollbacked
- When either "NO SFX" or "NO VIDEO" mode is enabled, a red label appears on the top right of the screen to inform the player which mode is enabled.
- When going with Full Experience mode, if at some point, the game is starting to get out of memory, it can automatically enable "NO VIDEO" mode first (except if player is in the last scenes, before the endings videos) and then the "NO SFX" mode.
  This is not 100% reliable, as the game is sometimes increasing memory usage too much too fast and the restricted modes are not enabled in time.
  
Recommendations :
- Beginning of the game is quite stable, don't hesitate to run the game will the full experience mode, you should be safe for some time.
- Most of the videos are at the beginning of the game, so don't hesitate to go directly with "NO VIDEO" mode between beginning and end of the game.
- When at the end of the game, I recommend playing with Full experience mode in order to see the endings cinematics.
- When going for the 100% with a lot of backtracking, I recommend starting directly with both "NO VIDEO" and "NO SFX" modes.


## Controls

Controls are taken from PS4 versions (as well as buttons icons displayed in game).
- L2 is replaced by left side of the touch screen.
- R2 is replaced by right side of the touch screen.
- Scroll down via right stick in inventory is not working. To scroll down, use the bottom of the touch screen. 
  This will lock the item selection. In order to unlock it, press TRIANGLE to see the Lore description or press L/R to change inventory menu and go back.

## Patching procedure

- Download Blasphemous vpk from vitadb and install it.
- Go to the Release page and download ``BlasphemousVitaSTEAM.zip``.
- Extract it.
- Put the game's data folder(```../steamapps/common/Blasphemous/Blasphemous_Data```) inside the extracted folder (Should be Steam version, make sure there is no Config.ini file in files. if there is one, just delete it.)
- Launch ``ApplyPatch.bat`` and wait.
- Let it finish and there should be a .ZIP file named ``BlasphemousVITA.zip``.
- Open VitaShell, connect your PS Vita to your PC and copy the contents of the .ZIP file```(Zip file should be around 500MB before unpacking)``` over to ``ux0:app/BLPM12345/``.
- Click on "Replace the files in destination" when it asks you to.
- Launch the game and have fun!

**Full CPU Overclock is a must !**
