# audio - Official Wyn Package

Audio utilities for Wyn: format detection and audio math. Pure Wyn, no system
dependency. (Decode/encode/playback via C bindings is future work.)

## Install

```bash
wyn pkg install github.com/wynlang/audio
```

## Usage

```wyn
import audio

// Format detection from file extension
print(audio.audio_format("song.mp3"))            // mp3
print(audio.audio_format("voice.flac"))          // flac
print(audio.audio_is_supported("clip.ogg"))      // true
print(audio.audio_is_supported("notes.txt"))     // false

// Audio math: CD-quality stereo = 176400 bytes/sec
var bps = audio.audio_bytes_per_second(44100, 2, 16)
print(bps)                                       // 176400

// Estimate duration of a 10 MB file in seconds
print(audio.audio_duration_estimate(10485760, bps))  // 59
```

## API

| Function | Description |
|----------|-------------|
| `audio_format(path)` | Detect format from extension: `wav`, `mp3`, `ogg`, `flac`, or `unknown` |
| `audio_is_supported(path)` | True if the extension is a known audio format |
| `audio_bytes_per_second(sample_rate, channels, bits_per_sample)` | Uncompressed data rate |
| `audio_duration_estimate(file_bytes, bytes_per_sec)` | Estimated duration in whole seconds |
