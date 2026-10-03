# Orbit Store

### A modern, no-BS download manager for PS5.

Orbit brings a cinematic, controller-friendly storefront to PS5 homebrew. Browse on the TV, or manage the same console from your phone. Downloads travel directly from third-party hosts to your PS5 and the drive attached to it.

![Orbit Store desktop preview](assets/orbit-preview.jpg)

## Built around the console

- **Direct to PS5.** Files travel directly from the download provider to your console's selected storage.
- **A focused collection.** Five curated titles to start, with format and source shown clearly.
- **Storage you choose.** Prefer an attached external drive's `homebrew` folder, or select internal storage.
- **A queue that remembers.** Pause, resume, retry, and recover interrupted work.
- **One interface, everywhere.** Controller on the TV; touch or keyboard on your local network.
- **No account. No telemetry.** Pair your local device with the code shown on your console.

## Development status

**This is an early development build. There is no public payload release yet.**

The interface and backend have been built and tested locally. First-run home-screen icon setup is integrated into the development payload. **Actual PS5 testing is still pending.** Firmware 12.60 / Relapse is the first intended target; compatibility has not been established.

The initial five entries are Cyberpunk 2077, Elden Ring Nightreign, Sifu, Ghostrunner 2, and Prince of Persia: The Lost Crown. Their direct Archive.org sources pass desktop metadata checks.

## How it will work

**The ELF is not available for download yet.** Download instructions and a SHA-256 checksum will be added when the first tested release is published.

The planned setup and everyday workflow is:

1. **Run it once.** Add `orbit_store.elf` to Payload Manager and run it. Orbit starts in the background and adds the **Orbit Store** home-screen icon on its first successful run.
2. **Start Orbit each session.** Set it to autoload in Payload Manager, or run the same ELF manually whenever needed. The existing icon is retained.
3. **Open the icon.** Once Orbit is running, select its home-screen icon to open the storefront.
4. **Download on the console.** Choose a game, choose storage, and select **Download to PS5**.
5. **Use your phone if you want.** While Orbit is running, visit `http://<ps5-ip>:34177/` on the same network and pair using the console's six-digit code.

After a reboot, activate your supported homebrew environment and let Payload Manager start Orbit, automatically or manually. The icon opens the running storefront; Payload Manager handles starting the payload. This workflow is awaiting console validation.

Keep the PS5 awake while downloading. Closing the storefront leaves downloads running. After an Orbit restart, interrupted transfers become paused so you can review and resume them.

## Controls and formats

| Control | Action |
|---|---|
| D-pad / arrow keys | Move focus |
| Cross / Enter | Select |
| Circle / Escape | Back or close details |
| Touch / mouse | Select visible controls |

The initial catalogue uses direct **FFPFSC** files. The downloader also accepts curated direct **exFAT** variants when supplied. Vikingfile support will be enabled only after automatic direct-link resolution works on the console.

V1 does **not** extract RAR/7z archives, install or launch games, or download in rest mode. “Complete” means the file was saved and passed available validation. Size-only checks are labelled separately from checksum verification.

## When something needs attention

- **No storage:** attach a writable drive to the PS5 and refresh storage. A drive connected to your computer is not PS5 storage.
- **Drive disconnected:** reconnect the original destination. Orbit will not silently switch to internal storage.
- **Not enough space:** free space on the selected destination before retrying.
- **Source changed:** preserve the partial file until you decide to remove it and restart. Orbit will not append a different file to it.
- **Provider throttling:** let the retry delay finish. Orbit respects the provider's `Retry-After` response.
- **Icon does not open Orbit:** start Orbit through Payload Manager, then open the icon again.
- **Cannot connect:** check that the payload is running and your device is on the same local network. Orbit uses TCP port **34177**.
- **Port already in use:** Orbit reports the port in its startup error. Check which service is using it before retrying.

## Roadmap

Console validation of first-run icon setup and Payload Manager startup → dependency clearance → first payload release → more verified direct-file sources. Archive extraction, game installation, and additional providers are future work, not advertised as finished features.

---

## IMPORTANT — THIRD-PARTY CONTENT & DOWNLOAD DISCLAIMER

**Orbit Store is an independent download-management application. This project does not host, upload, mirror, or bundle the game files referenced by its catalogue.** File transfers happen directly between third-party providers and the user's selected device. This repository hosts Orbit's documentation and, when released, Orbit's own application files.

Catalogue entries reference publicly accessible third-party URLs. **Publicly accessible does not mean authorised, licensed, or free to redistribute.** Use Orbit only for material you have permission to obtain and use, in accordance with applicable law, relevant licences, and the provider's terms. Owning a game does not, by itself, establish permission to obtain any copy found online.

**Third-party files are outside this project's control.** Their hosts and uploaders control availability and contents. Orbit does not guarantee ownership, authenticity, completeness, safety, compatibility, or continued availability. Download completion, a matching file size, or a matching checksum is a technical result—not a licence or a guarantee that the file is safe to run.

All game names, artwork, trademarks, and other third-party materials belong to their respective owners. Orbit is **not affiliated with or endorsed by** Sony Interactive Entertainment, PlayStation, game publishers, or download providers. The app does not supply accounts, credentials, purchase entitlements, or permission to bypass access restrictions.

To report an incorrect entry or a rights concern, open an issue with the affected title, URL, and sufficient information to identify the concern. Do not post private personal information. The underlying hosting provider is responsible for files it hosts; Orbit's maintainers can review catalogue references controlled by this project.
