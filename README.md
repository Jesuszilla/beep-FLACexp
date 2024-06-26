# Beep [![GoDoc](https://godoc.org/github.com/faiface/beep?status.svg)](https://godoc.org/github.com/faiface/beep) [![Go Report Card](https://goreportcard.com/badge/github.com/faiface/beep)](https://goreportcard.com/report/github.com/faiface/beep) [![Discord Chat](https://img.shields.io/discord/699679031603494954)](https://discord.gg/q2DK4MP)

A little package that brings sound to any Go application. Suitable for playback and audio-processing.

```cmd
go get -u github.com/samhocevar/beep
```

This is a fork of the [original Beep](https://github.com/faiface/beep) which has not been updated since March 2022.

## ✨ New features

## 🛠 Fixed issues

- [`81a81132`](https://github.com/samhocevar/beep/commit/81a811327e2e631134893fc7f7cb67d710e2392e): fix a freeze when seeking into Ogg/Vorbis files
- [`c9d71576`](https://github.com/samhocevar/beep/commit/c9d71576f54ad5ec7e0f6794944265373e2a37f0): fix wrong playback speed for mono and 5.1 Ogg/Vorbis files  ([`#154`](https://github.com/faiface/beep/pull/154), [`#139`](https://github.com/faiface/beep/pull/139))
- [`1a828691`](https://github.com/samhocevar/beep/commit/1a82869175674f6be990b726c669b027e6858d51): fix incorrect WAV header when writing to file ([`#144`](https://github.com/faiface/beep/pull/144))

## Features

Beep is built on top of its [Streamer](https://godoc.org/github.com/samhocevar/beep#Streamer) interface, which is like [io.Reader](https://golang.org/pkg/io/#Reader), but for audio. It was one of the best design decisions I've ever made and it enabled all the rest of the features to naturally come together with not much code.

- **Decode and play WAV, MP3, OGG, and FLAC.**
- **Encode and save WAV.**
- **Very simple API.** Limiting the support to stereo (two channel) audio made it possible to simplify the architecture and the API.
- **Rich library of compositors and effects.** Loop, pause/resume, change volume, mix, sequence, change playback speed, and more.
- **Easily create new effects.** With the `Streamer` interface, creating new effects is very easy.
- **Generate completely own artificial sounds.** Again, the `Streamer` interface enables easy sound generation.
- **Very small codebase.** The core is just ~1K LOC.

## Tutorial

The [Wiki](https://github.com/faiface/beep/wiki) contains a handful of tutorials for you to get started. They teach the fundamentals and advanced topics alike. **Read them especially if you call `speaker.Init` every time you play something.**

- [Hello, Beep!](https://github.com/faiface/beep/wiki/Hello,-Beep!)
- [Composing and controlling](https://github.com/faiface/beep/wiki/Composing-and-controlling)
- [To buffer, or not to buffer, that is the question](https://github.com/faiface/beep/wiki/To-buffer,-or-not-to-buffer,-that-is-the-question)
- [Making own streamers](https://github.com/faiface/beep/wiki/Making-own-streamers)

## Examples

| [Speedy Player](https://github.com/samhocevar/beep/tree/master/examples/speedy-player) | [Doppler Stereo Room](https://github.com/samhocevar/beep/tree/master/examples/doppler-stereo-room) |
| --- | --- |
| ![Speedy Player](https://github.com/samhocevar/beep/blob/master/examples/speedy-player/screenshot.png) | ![Doppler Stereo Room](https://github.com/samhocevar/beep/blob/master/examples/doppler-stereo-room/screenshot.png) |

## Dependencies

For playback, Beep uses [Oto](https://github.com/hajimehoshi/oto) under the hood. Check its requirements to see what you need to install for building your application.

Running an already built application should work with no extra dependencies.

## Licence

[MIT](https://github.com/samhocevar/beep/blob/master/LICENSE)

## Projects using beep

- [Mifasol music server](https://github.com/jypelle/mifasol)
