# Cyberleek GTA 6 Leaks Investigation & Proof

A complete breakdown of the August 2026 GTA 6 leaks found on the Cyberleek site (`leek.vilenarios.com`). This report explains step by step how I found all the hidden video and map links, how to prove where the files came from, and how to verify their real creation dates.

---

## 1. How I Found All The Hidden Links

When you visit `https://leek.vilenarios.com`, the main website page has zero direct video links in its HTML source code. 

Here is the exact method I used to uncover every file:

1. **Inspected the website scripts**:
   I opened the main JavaScript file used by the site:
   `https://leek.vilenarios.com/assets/index-CE2GuztQ.js`
   Looking through the code, I noticed the site was built as a Web3 app on Solana that fetches its content dynamically from a smart contract.
2. **Found the smart contract address**:
   The script contained the Solana Program ID `7rAgHPLDc9NryZmNdeEzyDui6D9PHkvTxMjKhNSa7w3a` and the token mint `ApZuxdpzMrbEYTGEzeY9afh5pj9d6qPRJCTgQYiipbKg`.
   * You can check the program on [Solscan](https://solscan.io/account/7rAgHPLDc9NryZmNdeEzyDui6D9PHkvTxMjKhNSa7w3a) or [Solana Explorer](https://explorer.solana.com/address/7rAgHPLDc9NryZmNdeEzyDui6D9PHkvTxMjKhNSa7w3a).
   * You can check the token on [DexScreener](https://dexscreener.com/solana/ApZuxdpzMrbEYTGEzeY9afh5pj9d6qPRJCTgQYiipbKg).
3. **Queried the blockchain directly**:
   I made an RPC call (`getProgramAccounts`) to Solana mainnet to read all 8 data accounts owned by that program.
4. **Decoded the hidden data**:
   Inside the accounts, I found the titles, mirror download links, and permanent Arweave storage hashes for all 5 leaked media files:
   * Account `FSKYZHqq...` had the Basketball video (`3XQv_9nd...`)
   * Account `9pUqCNKg...` had the Driving video (`hhOoYZt...`)
   * Account `9qjyztEy...` had the Map Peek 1 (`MyMFWWJ...`)
   * Account `3k3DqRCT...` had the Map Peek 2 (`zbfExgT...`)
   * Account `GwrASq3d...` had the Full Map (`GVTWJUb...`)
5. **Downloaded the original files**:
   I downloaded the files directly from the Arweave blockchain storage gateway and backup servers.

---

## 2. All Sources, Proof Links & Media Endpoints

### On-Chain Smart Contracts
* **Solana Program**: [`7rAgHPLDc9NryZmNdeEzyDui6D9PHkvTxMjKhNSa7w3a`](https://solscan.io/account/7rAgHPLDc9NryZmNdeEzyDui6D9PHkvTxMjKhNSa7w3a)
* **Token Mint ($CYBERLEEK)**: [`ApZuxdpzMrbEYTGEzeY9afh5pj9d6qPRJCTgQYiipbKg`](https://dexscreener.com/solana/ApZuxdpzMrbEYTGEzeY9afh5pj9d6qPRJCTgQYiipbKg)
* **Arweave Uploader Wallet**: `7gFAEaOIEHNhx2BqiVtpCgF_7HUePnN8E2aejRR6vTE`

### All Media Download Links

| File ID | Content Title | Permanent Arweave Link | Backup Mirrors | Resolution & Size |
| :--- | :--- | :--- | :--- | :--- |
| **`01`** | **GTA 6: Basketball Video**<br>Jason playing basketball at stilt house | [Arweave Gateway Link](https://arweave.net/3XQv_9ndgQ48DAZTeEYqRdVFryunBb0tI4gEVQpTJUs) | [Turbo Gateway](https://turbo-gateway.com/3XQv_9ndgQ48DAZTeEYqRdVFryunBb0tI4gEVQpTJUs)<br>[Upload.ee Mirror](https://www.upload.ee/download/19658673/ca588c03820c230b5ec7/output.mp4) | 2560 × 1440 (1440p)<br>35.75 MB |
| **`02`** | **GTA 6: Driving Video**<br>Jason driving Picador past Goose Key sign | [Arweave Gateway Link](https://arweave.net/hhOoYZtHBqQi3d-dmxcGooXKTbiT3HJ2-eNsE7HNtKg) | [Turbo Gateway](https://turbo-gateway.com/hhOoYZtHBqQi3d-dmxcGooXKTbiT3HJ2-eNsE7HNtKg)<br>[Upload.ee Mirror](https://www.upload.ee/download/19662951/7f826eda5700230b5ec9/video2.mp4) | 1920 × 1080 (1080p)<br>36.40 MB |
| **`03`** | **GTA 6: Map Peek 1**<br>Dalton Island crop | [Arweave Gateway Link](https://arweave.net/MyMFWWJkSuOoi2MehJ1TDC2kSLk_Twwl57WdPe5ceGg) | [Turbo Gateway](https://turbo-gateway.com/MyMFWWJkSuOoi2MehJ1TDC2kSLk_Twwl57WdPe5ceGg) | 1110 × 880 px<br>787 KB |
| **`04`** | **GTA 6: Map Peek 2**<br>Catalan Key and Gloriana Key crop | [Arweave Gateway Link](https://arweave.net/zbfExgTitr6LZ9Cu8lv3P8hjDr56uYyEIVkYU1OdZ-0) | [Turbo Gateway](https://turbo-gateway.com/zbfExgTitr6LZ9Cu8lv3P8hjDr56uYyEIVkYU1OdZ-0) | 1140 × 907 px<br>922 KB |
| **`05`** | **GTA 6: Full Map**<br>Complete Leonida county map | [Arweave Gateway Link](https://arweave.net/GVTWJUbg27XLsFEMctFUL45Z3beIyDWfKuhTe3Sp_w0) | [Turbo Gateway](https://turbo-gateway.com/GVTWJUbg27XLsFEMctFUL45Z3beIyDWfKuhTe3Sp_w0)<br>[Upload.ee Mirror](https://www.upload.ee/download/19662855/bf9597c60d99230b5ecd/full_map.png) | 2590 × 3240 px<br>3.71 MB |

---

## 3. How We Know Where The Footage Came From (Detailed Proof)

### The 2 Videos Are Real GTA 6 Gameplay
Here is the visual and technical evidence proving what these videos are:

1. **Video 1 (`output.mp4`) — Basketball Minigame**:
   * **The Scene**: Jason is standing on the back deck of a house on the water in Leonida. He walks over to a basketball hoop and shoots a basketball into the hoop.
   * **In-Game Systems**: 
     * The game gives an on screen prompt: *"To shoot, aim with and hold until the rings overlap, then release."*
     * You can see circular aiming rings on screen that shrink and line up.
     * In the bottom right corner, PlayStation button icons appear: `AIM (L2)`, `THROW (Cross / Square)`.
     * In the top right corner, there is a currency display showing `$39` in cash and `$1,643` in the bank.
     * In the top left corner, there is an eye stamina focus meter.
2. **Video 2 (`video2.mp4`) — Road Driving & Vice City Skyline**:
   * **The Scene**: Jason drives an old blue Declasse Picador pickup along a highway near the coast.
   * **Road Signage**: An overhead green highway sign clearly shows three locations:
     * `← Goose Key (US 1)`
     * `↗ Hamlet (US 82)`
     * `↗ Vice City (Airport / Hwy 97)`
   * **Other Details**: A brown `SCOOP` delivery truck with a pelican logo is parked by the side of the road. Across the water, you can see the Vice City skyline with high rise buildings. In the bottom left, the mini map shows the road curve with a distance marker (`1.04 mi`).
3. **Proof the Videos Were Re-Encoded**:
   If you check the technical file tags using `ffprobe`:
   * Video format: HEVC (H.265)
   * Tool tags: `Lavf60.16.100` and `Lavc60.31.102 libx265`
   * This proves the Cyberleek operators took the original raw PS5 clips and ran them through FFmpeg to stamp their QR codes and mascot on top before uploading.

### The 3 Maps Are Community Made (NOT Rockstar Leaks)
* **Proof**:
  The full map image (`full_map.png`) shows the state of Leonida with made up county names: `Lummox County`, `Kelly County`, `Leonard County`, `Vice-Dale County`, and `Mariana County`.
* **Where it really came from**:
  This is the famous map drawn by the **GTA VI Community Mapping Project** on Reddit (`r/GTA6`) and GTAForums. Fan cartographers (like DuPz0r and rollos) spent 2024 and 2025 building this exact vector map by piecing together landmarks from Trailer 1 and 2022 leaks.
* Cyberleek simply took the community map image, cropped two islands (`Dalton Island` and `Catalan Key`), added a blue box with their URL, and claimed it was a leak.

---

## 4. How We Know The Exact Dates & Timestamps

We have two distinct date categories: the blockchain upload date, and the true original creation date.

### 1. Blockchain Upload Dates (100% Verified on Arweave)
Arweave is an immutable blockchain. When a file is uploaded, the block timestamp cannot be changed or faked by anyone.

You can verify these block timestamps directly on any Arweave explorer:

* **Map Peek 2 (`zbfExgT...`)**:
  * **Date**: **August 16, 2026 at 10:24:11 UTC**
  * **Block Height**: #1981170
  * **Proof Link**: [View on Viewblock](https://viewblock.io/arweave/tx/zbfExgTitr6LZ9Cu8lv3P8hjDr56uYyEIVkYU1OdZ-0)
* **Basketball Video (`3XQv_9n...`)**:
  * **Date**: **August 17, 2026 at 18:27:16 UTC**
  * **Block Height**: #1982091
  * **Proof Link**: [View on Viewblock](https://viewblock.io/arweave/tx/3XQv_9ndgQ48DAZTeEYqRdVFryunBb0tI4gEVQpTJUs)
* **Full Map (`GVTWJUb...`)**:
  * **Date**: **August 18, 2026 at 14:48:34 UTC**
  * **Block Height**: #1982664
  * **Proof Link**: [View on Viewblock](https://viewblock.io/arweave/tx/GVTWJUbg27XLsFEMctFUL45Z3beIyDWfKuhTe3Sp_w0)
* **Driving Video (`hhOoYZt...`)**:
  * **Date**: **August 18, 2026 at 16:25:56 UTC**
  * **Block Height**: #1982709
  * **Proof Link**: [View on Viewblock](https://viewblock.io/arweave/tx/hhOoYZtHBqQi3d-dmxcGooXKTbiT3HJ2-eNsE7HNtKg)

### 2. True Creation Dates (Before Upload)
* **The Gameplay Videos (`output.mp4` & `video2.mp4`)**:
  * These clips are **not** from the 2022 leaks. The 2022 leaks were early debug builds with code text all over the screen.
  * These two clips show a finished PlayStation 5 build with complete lighting, clean interface, final sound effects, and no debug lines.
  * **Estimated True Date**: Captured between **Mid 2025 and Mid 2026** during internal testing at Rockstar.
* **The Map Images**:
  * Drawn by community artists and published on Reddit / GTAForums between **2024 and 2025**.

---

## 5. Master Dates & Hashes Summary Table

| File Name | SHA-256 Hash | Blockchain Upload Date (Arweave) | Estimated True Creation Date | Provenance & What It Is |
| :--- | :--- | :--- | :--- | :--- |
| **`output.mp4`** | `bbcb8f662b8f973e6c59a0a2c98c9cd361eee67bc7593eeada9a43f6211eab82` | **August 17, 2026**<br>(18:27:16 UTC) | **Mid 2025 – Mid 2026** | **Real GTA 6 Gameplay**<br>Internal PS5 build with added watermarks |
| **`video2.mp4`** | `c2a2284d8b83b28f4fa4919e99b5f903bbea3925a35177357fe398a861a9a638` | **August 18, 2026**<br>(16:25:56 UTC) | **Mid 2025 – Mid 2026** | **Real GTA 6 Gameplay**<br>Internal PS5 build with added watermarks |
| **`full_map.png`** | `c5a07256f62f3ae37904540621f2b07d2f647fd10867b620622b3471910563f6` | **August 18, 2026**<br>(14:48:34 UTC) | **2024 – 2025** | **Community Fan Map**<br>GTA VI Community Mapping Project |
| **`map_sneak_peek_1.png`** | `0d1f9f522b7cd5ac4e4b9702a73e1b7aaac86b3cbd4befb725c488fa4ff9bb12` | **August 17, 2026**<br>(18:27 UTC) | **2024 – 2025** | **Community Fan Map**<br>Cropped section of Dalton Island |
| **`map_sneak_peek_2.png`** | `b223c52138bc03a6fc4f27ab0dd58f95cf7ae173efb948a452ea7bf5b552cbac` | **August 16, 2026**<br>(10:24:11 UTC) | **2024 – 2025** | **Community Fan Map**<br>Cropped section of Catalan Key |

---

## License

MIT License. For educational and research purposes only. All GTA game assets belong to Rockstar Games and Take-Two Interactive.
