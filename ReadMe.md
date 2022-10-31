# TwitchVault
Simplified tool to automatically archive VODs, clips, highlights, including associated chat logs for specified Twitch channels
***
## Concept
My personal goal has been to find or develop a tool that can not only automate archiving the latest VODs, clips, and highlights from selected Twitch channels, but also archiving the chat logs as they are available for each medium.

### Known Issues
* VTT render produces files with a single word displayed at a time (at least as played via VLC). This needs to be fixed. I may just switch this to SRT as Vosk can natively output this and hopefully it outputs correctly. More testing needed here...

## Credit & Attribution

This repo has been heavily modified from [goldbattle's](https://github.com/goldbattle) [Twitch VOD Creator](https://github.com/goldbattle/twitch_vod_creator) - All credit and attribution as well as a huge amount of thanks goes out to them for creating the core functionality of automatically retrieving the requisite content from Twitch.