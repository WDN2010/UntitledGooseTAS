# Intro
This repository contains movie archive (in [Releases section](https://github.com/WDN2010/UntitledGooseTAS/releases)) and it's contents required for Tool Assistant Speedrun of Untitled Goose Game in Any% category performed with libTAS tool.
It was created for fun and as a PoC that it's possible to finish the Untitled Goose Game in less than 2 minutes. First released version time is exactly 1:59. 
- Recorded movie is available via link https://youtu.be/H8gu9nLgwOc
- Process of first release version enconding is available via link https://youtu.be/xhrI-Fea4l0
# Technical setup
- Ubuntu 20.04.3 LTS (native)
- Nouveau display driver (required for savestates)
- [libTAS](https://github.com/clementgallet/libTAS/releases) v.1.4.2
- Non-official native port of Untitled Goose Game v. 1.0.8 (pre-multiplayer patch). General information about porting Unity games on Linux platform is available in [English]( https://www.gamingonlinux.com/wiki/Unity_Games_Working_On_Linux_(User_Ported)) and [Russian](https://rutracker.org/forum/viewtopic.php?t=5026239)
	- In-game settings: Graphics low, resolution 720p during development and 1080p for final recording
# libTAS settings
- Video
	- Force software rendering: enabled. Required for savestates. Affects FPS during working with game via TAS, but resulting video will be in 60 FPS
	- Toggle performance tweaks: disabled. Minor FPS boost, but significant graphics degradation
- Sound
	- Mute: enabled. 
	- Disable: disabled. Doesn't affect encoded video, but enabled audio during working with TAS might be glitchy and affects FPS
- Runtime
	- Savestates
		- Backtrack savestates might be useful to have a savestate after moving to another area of the game
	- Prevent writing to disk doesn't crash the game, so can be enabled
	- Virtual Steam client is not required
- Tools 
	- Configure encode...
		- Video codec: FFmpeg video codec #1
		- Video bitrate: 4000
		- Audio codec: AAC (Advanced Audio Config)
		- Audio bitrate: 128
		- ffmpeg options  `-c:v ffv1 -b:v 4000k -c:a aac -b:a 128k`
	- **Start encode**
		- It's recommecded to launch released movie with started encode only as it affects game behavior. Run will be not finished without encoding enabled from the start!
	- Slow motion
		- One of the main tools for TAS development. Locks FPS on the required speed. For final rendering recommended to set normal speed
	- Input
		- Mouse support is optional. If you make TAS with gamepad inputs (as this one), disabling it will decrease number of recorded inputs 

# Tips for TAS newbies from TAS newbie
- Main available tools are:
	- **Main window -> General options -> Pause** - Freezes game at any point of time
	- **Savestates** - Shift + F1-F11 to create savestate, F1-F11 to load savestate. F12 to load Backtrack Savestate if you've moved to new area
	- **Movie -> Input editor...** - Window with frame-by-frame inputs which can be fine-tuned and optimized for performing skips. Savestates are marked on the left
	- **Input -> Joystick inputs...** - Window with controller inputs. Note that buttons are performed as checkboxes, so clicking a button fast is like `Pause -> check the box -> Unpause -> Pause -> uncheck the box -> Unpause`
- From time to time it might be a good idea to check your progress by launching full run. Behavior can be changed from launching part of game (like performing hard skip) using savestate. In case of success you can save current movie or even save it to another file with **Export Movie** option
# Additional information
- If you want to add any honking not required for run, it's better to make it during TAS creation in the same frame (and 5-10 frames around) with grabbing or turning might change goose position and affect following inputs. Be careful!