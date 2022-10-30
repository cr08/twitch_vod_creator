# Twitch VOD Creator

The goal of these scripts is to enable the automatic downloading of Twitch VODs, Highlights, Clips, and associated chat transcripts.

At the core we leverage lay295's [TwitchDownload](https://github.com/lay295/TwitchDownloader) utility to download both complete vods, highlights, clips, and chats.

Additionally, a transcript of the video can be generated using [vosk](https://github.com/alphacep/vosk-api).

### Dependencies & Config

We leverage [python-twitch-client](https://github.com/tsifrer/python-twitch-client) library which recently added oauth support.
You will need at least version 0.7.1 installed to have the correct api support functions.

`python -m pip install -r requirements.txt`

You will need to make a copy of *[config/auth_example.yaml](config/auth_example.yaml)* and rename it to `config/auth.yaml`.
This should be fill out with a twitch app client information which can be generated from the twitch [developer center](https://dev.twitch.tv/console/apps).

If you are running this on a linux machine, you will need the ffmpeg binary for your system.
Try to download from the official website as your machine repositories will be too far out of date.
From there, ensure you have Python 3.6 installed, and that you have correct paths to the TwitchDownload CLI and ffmpeg.
See the commented out examples in the top of each script file.
Additionally, one can use the `crontab_script_launcher.sh` script to run script automatically on a cronjob.

```
sudo crontab -e
*/25 * * * * /path/to/repo/crontab_script_launcher.sh 0_main_videos.py
*/15 * * * * /path/to/repo/crontab_script_launcher.sh 1_render_segments.py
* */12 * * * /path/to/repo/crontab_script_launcher.sh 0_main_clips.py
```
### Credits & Attribution

This repo has been heavily modified from [goldbattle's](https://github.com/goldbattle) [Twitch VOD Creator](https://github.com/goldbattle/twitch_vod_creator) - All credit and attribution as well as a huge amount of thanks goes out to them for creating the core functionality of automatically retrieving the requisite content from Twitch.