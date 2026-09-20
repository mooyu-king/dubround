# DubRound — Turn Every Line into Your Voice Challenge

![DubRound](dubround-logo-3.webp)

**Official website: [dubround.com](https://dubround.com/)** · [Play Now](https://dubround.com/games/dub-round/) · [Community Packs](https://dubround.com/packs/community/) · [Create a Pack](https://dubround.com/create/from-video/)

DubRound is a browser-based voice game platform where you listen, dub, and compare performances. Pick a familiar line, enable your microphone, and perform your own version: practice solo or take turns challenging friends.

## One Line, Many Ways to Play

![Game menu and multiplayer options](dubround-game.webp)

- **Instant dubbing**: Listen, record, play back, and compare vocal features such as rhythm. Scores are for entertainment and do not verify identity or dialogue accuracy.
- **Play with friends**: Share a device for a local party. Online rooms support 2–4 players taking turns, matching Packs, and synchronizing scores, with a separate room service required.
- **Community library**: Browse Packs with source attribution, download supported resources, load them into the game, and track actual download and processing status. Upstream resources may change or become unavailable.
- **Custom video Packs**: Split videos you have the right to use into voice clips, preview them, and export a replayable ZIP Pack.
- **Keep your performances**: Basic recording and scoring run locally, with saving and export available. You are responsible for backing up browser data.

## From Listening to Your Own Version

![Reference dialogue preview](dubround-game-2.webp)

1. Choose a sample or community Pack, or import your own material.
2. Grant microphone access and say a few words to check the input.
3. Listen to the reference clip and record your own performance.
4. Compare performances, try again, or pass the microphone to the next player.

![Live recording waveform](showcase/live-waveform.png)

Online rooms synchronize players, rounds, and scores. They do not provide live voice calls or automatically distribute private Pack audio.

## Explore dubround.com

| What You Want to Do | Page |
| --- | --- |
| Play the dubbing game | [DubRound](https://dubround.com/games/dub-round/) |
| Challenge friends | [Multiplayer](https://dubround.com/multiplayer/) |
| Find material | [Community Packs](https://dubround.com/packs/community/) |
| Turn a video into a game | [Pack Creator](https://dubround.com/create/from-video/) |
| Troubleshoot your setup | [Microphone Test](https://dubround.com/tools/mic-test/) |
| Read the policies | [Terms](https://dubround.com/terms/) · [Privacy](https://dubround.com/privacy/) |

## Local Development and Static Deployment

Built with Next.js, React, TypeScript, browser audio APIs, and Workbox. The GitHub deployment repository contains the **static output from out**, not the source project needed to run npm commands.

Run these commands in the local source project:

```bash
npm run dev
npm run typecheck
npm run build-preserve-git
```

The build runs in an isolated directory within the project and updates out only after success. Existing out/.git and all README variants are preserved. The first build creates the deployment README from the source README and adjusts relative image paths. The initial remote URL is https://github.com/mooyu-king/dubround.git; the script does not automatically commit, push, or overwrite an existing origin.

Deployment workflow: build locally → review changes in out → manually commit the static repository → deploy with Cloudflare Pages. The static repository is already compiled, so Cloudflare does not need to run another Next.js build. Keep the root _headers file to enforce same-origin embedding restrictions. The production domain is **dubround.com**.

**Service requirements**: out does not include a running room service or Pack download proxy. These must be deployed, configured, and verified separately. A successful build does not confirm that online multiplayer or remote downloads work in production. Do not upload .env files, service secrets, source dependencies, or the isolated build directory.

The website uses data.1back.link for traffic analytics; see the privacy policy for details. Microphone access requires HTTPS or a local development environment, along with user permission.

## Copyright and Contact

Public access to DubRound does not grant permission to redistribute its original code, interface, or branding. Third-party games, Packs, images, and audio belong to their respective rights holders; availability for download does not imply permission to republish. Use the creator only with material you created, licensed, or are otherwise legally allowed to use. Public browser resources cannot be guaranteed to remain impossible to download.

Contact: [mooyuking@gmail.com](mailto:mooyuking@gmail.com) · [dubround.com/contact](https://dubround.com/contact/)
