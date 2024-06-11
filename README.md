
# Blasphemous port for PS VITA

This repos contains patch you can apply on Blasphemous Steam data files in order to get the game running on PS VITA.
**Please read carefully following sections before going on with the patching procedure**

## Functional notes

On a functional point of view, despites compromises listed below, this port comes up with latest version, all DLC's are so part of the port.
You shouldn't face any blocking issues, I've completed the game will all 3 endings, 100% in NG, more than 100% in NG+, all boss fights achievable as well as all game modes (boss rush, demake).

## Technical notes

Here is a video showcasing what you can expect from a technical point of view if you set up your Vita following instructions below :
[![Showcase video](https://img.youtube.com/vi/wdu1oQsovBY/0.jpg)](https://www.youtube.com/watch?v=wdu1oQsovBY)

Porting this game to PS Vita was a real challenge and comes therefore with some issues and some compromises in order to fit the console technical specifications.
It is not perfect, and will probably never be, but it's decent enough to enjoy this amazing game.

## Compromises

- FPS is capped at 30 (can be less in big scenes with few enemies - until they die)
- A few textures were downsized to fit in PS VITA RAM
- Voices were ripped off
- Videos were replaced by sprites slide shows (loss of quality for a few seconds in the game, allowing to benefit from significant more memory for the entire gameplay experience)
- Sound can be glitchy in the first minutes of game session (then, you are good) and sample rate was reduced to 8k
- Credits were ripped off (the way it was implemented was too heavy for VITA's RAM), but I strongly recommend you to have a look at all the people involved in this amazing game, and support their work.
- Main menu face & background selection is disabled 
- Skin selection is disabled
- Initial load of the app can take up to 2 minutes in order for FMOD Studio to start and load all the sound banks

## Known issues

BETA.1 version comes up with some known issues, none being Blocking or High :

- Some areas have lower fps when there are a lot of enemies.
- The port has became quite stable but crash could still happen after long game session.
- Reducing the size of the textures led to small gaps between some textures in game, and some pixelated sprites.
- Shaders are not implemented.
- One elevator is locking the camera below the player when going up. When the elevator stops, simply go left to another screen and come back to have the camera focusing the player again.
- Buttons icons are not displayed in some UI popups and are replaced by their text label.
- Interaction icon can sometimes appear even if there is nothing to interact with.
- Visual glitches during Sierpes boss fight.

## Controls

Controls are based on the PS4 version of the game (as well as buttons icons displayed in game).
- L2 is replaced by left side of the touch screen.
- R2 is replaced by right side of the touch screen.
  
## PS VITA Set up

In order to have the best possible experience, I recommend you to use following plugins (that you should be able to find somewhere on the net) :
- ioplus.skprx
- iostaging.skprx
- (ThreadOptimizer) => Optional, requires configuration, and can have negative impact if not correctly done

**+ Full CPU Overclock (500Mhz)**

## Patching procedure

- Download Blasphemous vpk from vitadb and install it.
- Go to the Release page and download ``BlasphemousVitaSteam.zip``.
- Extract it.
- Put the game's data folder(```../steamapps/common/Blasphemous/Blasphemous_Data```) inside the extracted folder (Should be Steam version, make sure there is no Config.ini file in files. if there is one, just delete it.)
- Launch ``ApplyPatch.bat`` and wait.
- Let it finish and there should be a .ZIP file named ``BlasphemousVITA.zip``.
- Open VitaShell, connect your PS Vita to your PC and copy the contents of the .ZIP file```(Zip file should be around 500MB before unpacking)``` over to ``ux0:app/BLPM12345/``.
- Click on "Replace the files in destination" when it asks you to.
- Launch the game and have fun!
