# GTA 6 Latest Leaks Forensic & Provenance Investigation (August 2026)

A technical forensic breakdown and provenance verification of the latest August 2026 *Grand Theft Auto VI* leaked gameplay clips and maps distributed through decentralized storage and the "Cyberleek" portal.

---

## Executive Summary

In mid-August 2026, new footage and map assets claiming to be from *Grand Theft Auto VI* surfaced online across decentralized hosting networks (Arweave, IPFS, Upload.ee, Transfiles).

This investigation examines the underlying smart contracts, blockchain transaction blocks, container codec metadata, in-game HUD systems, and cartographic layers to determine the **true origin and creation timeline** of each file rather than simply reporting when they were uploaded.

### Quick Findings:
1. **Gameplay Videos (`output.mp4` & `video2.mp4`)**: Authentic internal development footage from a modern PlayStation 5 milestone build (estimated capture: mid-2025 to mid-2026). Re-encoded using FFmpeg 6.1 with custom promotional watermarks added prior to Arweave distribution.
2. **Map Images (`full_map.png` & Sneak Peeks)**: Not internal Rockstar Games assets. These are community-created vector maps from the public **GTA VI Community Mapping Project** (2024–2025) cropped and watermarked.

---

## 1. Investigative Methodologies

| # | Methodology | Tooling & Approach | Objective |
| :--- | :--- | :--- | :--- |
| **1** | **dApp Reverse Engineering** | Static AST analysis of client bundle (`assets/index-CE2GuztQ.js`). | Extracted Solana Program ID, token mint address, and content seeds. |
| **2** | **Solana RPC State Extraction** | `getProgramAccounts` across mainnet RPC nodes. | Discovered on-chain accounts holding active titles, Arweave IDs, and mirrors. |
| **3** | **Arweave GraphQL Forensics** | Queried `https://arweave.net/graphql` for block height & timestamp. | Retrieved immutable ledger upload timestamps and uploader wallet. |
| **4** | **Codec & Atom Inspection** | `ffprobe` stream parser & MP4 atom inspection (`mvhd`, `tkhd`). | Extracted resolution, frame rates, HEVC profiles, and FFmpeg encoder signatures. |
| **5** | **Visual & HUD Analysis** | Keyframe extraction via `ffmpeg`. | Verified in-game mechanics (aiming rings, stamina, bank/cash HUD, road signs). |
| **6** | **Cartographic Comparison** | Layer comparison against GTA VI Mapping Community GIS assets. | Proved origin of map assets vs proprietary development material. |

---

## 2. On-Chain Contracts & Media Endpoints

* **Solana Program ID**: `7rAgHPLDc9NryZmNdeEzyDui6D9PHkvTxMjKhNSa7w3a`
* **Token Mint ($CYBERLEEK)**: `ApZuxdpzMrbEYTGEzeY9afh5pj9d6qPRJCTgQYiipbKg`
* **Arweave Uploader Wallet**: `7gFAEaOIEHNhx2BqiVtpCgF_7HUePnN8E2aejRR6vTE`

### Media Endpoints Table

| Media Item | Title & Description | Arweave TX ID | Mirror & Download Endpoints | File Type & Size |
| :--- | :--- | :--- | :--- | :--- |
| **`MEDIA-01`** | **GTA 6: basketball video**<br>Jason playing basketball at stilt house | `3XQv_9ndgQ48DAZTeEYqRdVFryunBb0tI4gEVQpTJUs` | [Arweave Gateway](https://arweave.net/3XQv_9ndgQ48DAZTeEYqRdVFryunBb0tI4gEVQpTJUs)<br>[Turbo Gateway](https://turbo-gateway.com/3XQv_9ndgQ48DAZTeEYqRdVFryunBb0tI4gEVQpTJUs)<br>[Upload.ee Direct](https://www.upload.ee/download/19658673/ca588c03820c230b5ec7/output.mp4) | MP4 (HEVC)<br>35.75 MB |
| **`MEDIA-02`** | **GTA 6: random video 1**<br>Jason driving Picador past Goose Key sign | `hhOoYZtHBqQi3d-dmxcGooXKTbiT3HJ2-eNsE7HNtKg` | [Arweave Gateway](https://arweave.net/hhOoYZtHBqQi3d-dmxcGooXKTbiT3HJ2-eNsE7HNtKg)<br>[Turbo Gateway](https://turbo-gateway.com/hhOoYZtHBqQi3d-dmxcGooXKTbiT3HJ2-eNsE7HNtKg)<br>[Upload.ee Direct](https://www.upload.ee/download/19662951/7f826eda5700230b5ec9/video2.mp4) | MP4 (HEVC)<br>36.40 MB |
| **`MEDIA-03`** | **GTA 6: map sneak peek 1**<br>Dalton Island (Fisher Island) crop | `MyMFWWJkSuOoi2MehJ1TDC2kSLk_Twwl57WdPe5ceGg` | [Arweave Gateway](https://arweave.net/MyMFWWJkSuOoi2MehJ1TDC2kSLk_Twwl57WdPe5ceGg)<br>[Turbo Gateway](https://turbo-gateway.com/MyMFWWJkSuOoi2MehJ1TDC2kSLk_Twwl57WdPe5ceGg) | PNG Image<br>787.1 KB |
| **`MEDIA-04`** | **GTA 6: map sneak peek 2**<br>Catalan Key / Gloriana Key crop | `zbfExgTitr6LZ9Cu8lv3P8hjDr56uYyEIVkYU1OdZ-0` | [Arweave Gateway](https://arweave.net/zbfExgTitr6LZ9Cu8lv3P8hjDr56uYyEIVkYU1OdZ-0)<br>[Turbo Gateway](https://turbo-gateway.com/zbfExgTitr6LZ9Cu8lv3P8hjDr56uYyEIVkYU1OdZ-0) | PNG Image<br>922.5 KB |
| **`MEDIA-05`** | **GTA 6: full map**<br>Complete Leonida county map | `GVTWJUbg27XLsFEMctFUL45Z3beIyDWfKuhTe3Sp_w0` | [Arweave Gateway](https://arweave.net/GVTWJUbg27XLsFEMctFUL45Z3beIyDWfKuhTe3Sp_w0)<br>[Turbo Gateway](https://turbo-gateway.com/GVTWJUbg27XLsFEMctFUL45Z3beIyDWfKuhTe3Sp_w0)<br>[Upload.ee Direct](https://www.upload.ee/download/19662855/bf9597c60d99230b5ecd/full_map.png) | PNG Image<br>3.71 MB |

---

## 3. Cryptographic Hashes & Technical Data

| File Name | SHA-256 Hash | Resolution | Video / Audio Specifications | Encoder Signature |
| :--- | :--- | :--- | :--- | :--- |
| **`output.mp4`** | `bbcb8f662b8f973e6c59a0a2c98c9cd361eee67bc7593eeada9a43f6211eab82` | 2560 × 1440 (1440p) | HEVC Main @ L5.0 • 30fps<br>AAC Stereo 48kHz | `Lavf60.16.100`<br>`libx265` |
| **`video2.mp4`** | `c2a2284d8b83b28f4fa4919e99b5f903bbea3925a35177357fe398a861a9a638` | 1920 × 1080 (1080p) | HEVC Main @ L4.0 • 30fps<br>AAC Stereo 48kHz | `Lavf60.16.100`<br>`libx265` |
| **`full_map.png`** | `c5a07256f62f3ae37904540621f2b07d2f647fd10867b620622b3471910563f6` | 2590 × 3240 px | PNG (RGBA) 8-bit depth | Community Vector Export |
| **`map_sneak_peek_1.png`** | `0d1f9f522b7cd5ac4e4b9702a73e1b7aaac86b3cbd4befb725c488fa4ff9bb12` | 1110 × 880 px | PNG (RGB) 8-bit depth | Image Crop |
| **`map_sneak_peek_2.png`** | `b223c52138bc03a6fc4f27ab0dd58f95cf7ae173efb948a452ea7bf5b552cbac` | 1140 × 907 px | PNG (RGB) 8-bit depth | Image Crop |

---

## 4. Visual Analysis & Content Breakdown

### `output.mp4` — Basketball Minigame
* **Scene**: Protagonist Jason is on the deck of a waterfront stilt house in Leonida. He interacts with a basketball hoop on the side of the house.
* **Mechanics Observed**:
  * Action prompt: *"To shoot, aim with and hold until the rings overlap, then release."*
  * Eye/focus stamina meter at top left.
  * Currency display: `$39` cash, `$1,643` bank balance.
  * PlayStation gamepad controls: `AIM (L2)`, `THROW (Cross/Square)`.

### `video2.mp4` — Highway Driving & Delivery Van
* **Scene**: Jason drives a vintage Declasse Picador pickup along a coastal highway.
* **Key Landmarks & Signage**:
  * Overhead highway sign: `← Goose Key (US 1)`, `↗ Hamlet (US 82)`, `↗ Vice City (Airport / Hwy 97)`.
  * Brown `SCOOP` delivery truck with pelican logo.
  * Vice City high-rise skyline visible across the bay.
  * GPS mini-map with route line and `1.04 mi` distance counter.

### Maps — GTA VI Community Mapping Project
* **Content**: The full map displays the state of Leonida with community-named counties (`LUMMOX`, `KELLY`, `LEONARD`, `VICE-DALE`, `MARIANA`).
* **Origin Confirmation**: The artwork matches the public collaborative vector map maintained on GTAForums and Reddit since 2024.

---

## 5. Master Timeline & Dates Summary

| Media Asset | Arweave Block / Ledger Upload Date | Earliest Known Online Appearance | Estimated True Creation Date | Provenance & Authenticity Determination |
| :--- | :--- | :--- | :--- | :--- |
| **`output.mp4`** (Basketball) | **2026-08-17 18:27:16 UTC**<br>*(Block #1982091)* | August 17, 2026 | **Mid 2025 – Mid 2026** | **Authentic GTA VI Footage**<br>Internal Rockstar PS5 Build |
| **`video2.mp4`** (Highway) | **2026-08-18 16:25:56 UTC**<br>*(Block #1982709)* | August 18, 2026 | **Mid 2025 – Mid 2026** | **Authentic GTA VI Footage**<br>Internal Rockstar PS5 Build |
| **`full_map.png`** (Leonida Map) | **2026-08-18 14:48:34 UTC**<br>*(Block #1982664)* | Aug 18, 2026 *(Watermarked)*<br>2024–2025 *(Original)* | **2024 – 2025** | **Community Re-creation**<br>GTA VI Community Mapping Project |
| **`map_sneak_peek_1.png`** | **2026-08-17 18:27 UTC** | August 17, 2026 | **2024 – 2025** | **Community Re-creation**<br>Cropped from Community Map |
| **`map_sneak_peek_2.png`** | **2026-08-16 10:24:11 UTC**<br>*(Block #1981170)* | August 16, 2026 | **2024 – 2025** | **Community Re-creation**<br>Cropped from Community Map |

---

## License & Disclaimer

This repository is for educational and archival research purposes. All trademarks and game content belong to Take-Two Interactive and Rockstar Games.
