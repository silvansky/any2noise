# any2noise

Turn any file into audio. Treat raw bytes as audio samples and play them back.

**[→ Launch App](https://silvansky.github.io/any2noise/)**

## What is this?

Like `cat file > /dev/dsp` on Linux, but in your browser. Upload any file (`.exe`, `.dat`, `.bin`, whatever) and it gets reinterpreted as raw audio data.

## Usage

1. **Upload a file** — drag & drop or click to browse
2. **Adjust settings** (optional):
   - **Channels**: Mono / Stereo
   - **Sample Rate**: 8 kHz – 96 kHz
   - **Bytes per Sample**: 8-bit, 16-bit, 24-bit, 32-bit
   - **Interpretation**: Signed / Unsigned
3. **Play** — hear your file as audio

Settings can be changed mid-playback; audio restarts automatically with new parameters.

## Default Settings

- **8 kHz** sample rate
- **Mono** channel
- **16-bit** (2 bytes)
- **Unsigned**

## How it Works

- Files are read as raw `ArrayBuffer` in the browser
- Bytes are reinterpreted as PCM audio samples based on your settings
- Playback uses the Web Audio API — no server processing, everything is client-side

## Examples to Try

- **Executable files** — often contain interesting noise patterns
- **Image files** — headers and data create distinct sounds
- **Compressed archives** — structured data produces rhythmic patterns
- **Other audio files** — with wrong settings, they sound like alien transmissions

## Tech

- Vanilla JavaScript
- Web Audio API
- Single HTML file, no dependencies
- Works offline after initial load

## License

MIT
