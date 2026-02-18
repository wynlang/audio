# audio — Official Wyn Package

Cross-platform audio playback. Wraps miniaudio (single-header C library).

## Install

```bash
wyn pkg install github.com/wynlang/audio
```

## Usage

```wyn
Audio_init()
var sound = Audio_load("sound.wav")
Audio_play(sound)
Audio_close()
```

No system dependency — miniaudio is bundled.
