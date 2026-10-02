# Orbit Store

### A modern, no-BS download manager for PS5.

Your console. Your collection. One clear download queue.

Orbit brings a cinematic, controller-friendly storefront to PS5 homebrew. Browse on the TV, or manage the same console from your phone. Downloads travel directly from third-party hosts to your PS5 and the drive attached to it.

![Orbit Store desktop preview](assets/orbit-preview.jpg)

## Built around the console

- **Direct to PS5.** The console handles the transfer. No Motrix or computer download relay.
- **A focused collection.** Five curated titles to start, with format and source shown clearly.
- **Storage you choose.** Prefer an attached external drive's `homebrew` folder, or select internal storage.
- **A queue that remembers.** Pause, resume, retry, and recover interrupted work.
- **One interface, everywhere.** Controller on the TV; touch or keyboard on your local network.
- **No account. No telemetry.** Pair your local device with the code shown on your console.

## Development status

**This is an early development build. There is no public payload release yet.**

The interface and backend have been built and tested locally, and the main payload and optional launcher cross-compile. **Actual PS5 testing is still pending.** Firmware 12.60 / Relapse is the first intended target; compatibility has not been established.

The initial five entries are Cyberpunk 2077, Elden Ring Nightreign, Sifu, Ghostrunner 2, and Prince of Persia: The Lost Crown. Their direct Archive.org sources pass desktop metadata checks. This does not establish that the files will launch, that every edition includes DLC, or that a full console transfer has been tested.

The source repository is private. This public repository is the home for documentation, issues, screenshots, and future release downloads. Public binary distribution remains subject to the SDK and dependency licence review.

## How it will work

Once a tested release is available:

1. Download `orbit_store.elf` from this repository's **Releases** page and verify its published SHA-256 checksum.
2. Start it with your supported PS5 payload loader.
3. Open Orbit in the console browser, or visit `http://<ps5-ip>:6971/` from a phone or computer on the same network.
4. Pair remote devices using the console's six-digit code.
5. Choose a game, choose storage, and select **Download to PS5**.

Keep the PS5 awake and the payload running. The control browser can close while downloads continue. After a payload restart, interrupted active transfers become paused so you can review and resume them.

An optional home-screen shortcut is being developed separately. Its installer changes console app metadata; it will remain separate from the main payload and needs firmware validation before release.

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
- **Cannot connect:** check that the payload is running and your device is on the same local network. Do not expose port 6971 to the internet.

## Roadmap

Console validation → dependency clearance → first payload release → more verified direct-file sources. Archive extraction, installation, and additional providers are future work, not advertised as finished features.

---

## IMPORTANT — THIRD-PARTY CONTENT & DOWNLOAD DISCLAIMER

**Orbit Store is an independent download-management application. This project does not host, upload, mirror, or bundle the game files referenced by its catalogue.** File transfers happen directly between third-party providers and the user's selected device. This repository hosts Orbit's documentation and, when released, Orbit's own application files.

Catalogue entries reference publicly accessible third-party URLs. **Publicly accessible does not mean authorised, licensed, or free to redistribute.** Use Orbit only for material you have permission to obtain and use, in accordance with applicable law, relevant licences, and the provider's terms. Owning a game does not, by itself, establish permission to obtain any copy found online.

**Third-party files are outside this project's control.** Their hosts and uploaders control availability and contents. Orbit does not guarantee ownership, authenticity, completeness, safety, compatibility, or continued availability. Download completion, a matching file size, or a matching checksum is a technical result—not a licence or a guarantee that the file is safe to run.

All game names, artwork, trademarks, and other third-party materials belong to their respective owners. Orbit is **not affiliated with or endorsed by** Sony Interactive Entertainment, PlayStation, game publishers, or download providers. The app does not supply accounts, credentials, purchase entitlements, or permission to bypass access restrictions.

To report an incorrect entry or a rights concern, open an issue with the affected title, URL, and sufficient information to identify the concern. Do not post private personal information. The underlying hosting provider is responsible for files it hosts; Orbit's maintainers can review catalogue references controlled by this project.

**This notice explains the project's role. It does not override applicable law, third-party licences, or anyone's legal responsibilities.** For background, see the [U.S. Copyright Office's information on copyright and digital files](https://www.copyright.gov/help/faq/faq-digital.html).
