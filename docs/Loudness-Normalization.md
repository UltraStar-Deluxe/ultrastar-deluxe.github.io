## Introduction to ReplayGain
It is desirable for each song in USDX to have equal loudness, so the audio volume does not need to be frequently adjusted while playing. However, the loudness of audio files may vary significantly.

To solve this problem, USDX supports ReplayGain during playback of a song's `#MP3`/`#AUDIO` file. ReplayGain works by scanning a file ahead of time and "tagging" it with metadata that contains a volume adjustment. During playback, USDX will read the file's tag and apply the requested volume adjustment automatically. This ensures that all files play back at the same perceived volume.

ReplayGain is not enabled by default in USDX. To enable it, navigate to Tools->Options->Sound, and set the ReplayGain setting to 'On'.

## Adding ReplayGain Tags to Your UltraStar Library
USDX will read the ReplayGain tags of your audio files, but it won't write them. This means you will need another program to scan your audio files and write the ReplayGain tags, so they can later be read by USDX.

### USDB Syncer
Recent versions of the [USDB Syncer](https://github.com/bohning/usdb_syncer) support ReplayGain tag writing. However, ReplayGain is not enabled by default. To enable it, navigate to Tools->Settings, and set the "Normalization" setting to "ReplayGain".

When enabled, the Syncer will automatically scan downloaded audio files for loudness and write the ReplayGain tags.

### Full Library Scanning
For ReplayGain to work properly, your *entire* library needs to have tags. It's not good enough to write ReplayGain tags to newly added songs only. If you already have a large existing UltraStar library, you will need to write ReplayGain tags to those files too.

One way to accomplish a full library scan is with [rsgain](https://github.com/complexlogic/rsgain), a cross-platform ReplayGain scanning utility. It can be installed via the [instructions on the README](https://github.com/complexlogic/rsgain?tab=readme-ov-file#installation).

A comptibility preset is needed for `rsgain` to have consistency with USDB Syncer. Open a text editor of your choice, and paste the following into it:

```ini
[Global]
Album=false
TruePeak=true
ClipMode=n
OpusMode=s
```

Save this file as `usdb_syncer.ini` in the following folder depending on your platform (you will need to create this folder if it doesn't already exist):
- Windows: `%USERPROFILE%\.rsgain\presets` (typically `C:\Users\<your username>\.rsgain\presets`)
- macOS: `~/Library/rsgain/presets`
- Linux: `~/.config/rsgain/presets`

Execute the full library scan with the following command:
```shell
rsgain easy -p usdb_syncer -m MAX <path to ultrastar library>
```
Replace `<path to ultrastar library>` with the actual path to your UltraStar library on your filesystem. Use quotation marks if the path contains spaces.

The full library scan only needs to be performed once. In the future, when you add new songs to your UltraStar library, the Syncer will handle ReplayGain for you automatically.
