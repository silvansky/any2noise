# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

any2noise — browser tool that reinterprets raw file bytes as PCM audio samples. Single-file vanilla JS app (`index.html`), no dependencies, no build step. Deployed as GitHub Pages at silvansky.github.io/any2noise/.

## Development

No build, lint, or test commands. Open `index.html` in a browser to run. Everything (HTML, CSS, JS) lives in the single file.

## Architecture

User uploads file → FileReader reads as ArrayBuffer → raw bytes converted to float samples based on settings (channels, sample rate, bit depth, signed/unsigned) → stored in Web Audio API AudioBuffer → playback via AudioContext with GainNode (volume) and AnalyserNode (visualization) → Canvas draws frequency spectrum. WAV export encodes the AudioBuffer as 16-bit PCM with proper RIFF headers.

Key globals: `audioContext`, `audioBuffer`, `sourceNode`, `analyser`, `gainNode`, `isPlaying`. Settings changes during playback trigger re-read of the file and auto-restart.
