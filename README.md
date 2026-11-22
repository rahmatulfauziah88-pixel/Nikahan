# Nikahan — DXV conversion workflow

This repository contains a GitHub Actions workflow to fetch videos from the shared Google Drive folder and convert them to Resolume DXV.

## Source folder
Google Drive folder ID: `17qj8tTGCiiNdMVh1WLxICbHh2m2ivrvJ`

## Important access requirement
The Google Drive folder must be shared as **Anyone with the link — Viewer** so a GitHub-hosted runner can download it. Do not put Google passwords, OAuth tokens, or private keys in this public repository.

## Run
1. Open the **Actions** tab in this repository.
2. Select **Convert Nikahan videos to DXV**.
3. Press **Run workflow**.
4. When it finishes, open the run and download the artifact named **Nikahan-DXV-Output**.

## Output details and limitations
- Output container: MOV, video codec: DXV DXT1.
- DXT1 is the FFmpeg DXV encoder's **Normal Quality, no-alpha** format.
- Source resolution is retained; audio is kept by encoding it as AAC.
- This is not the full official Resolume DXV3 exporter: FFmpeg's encoder only supports DXT1 / Normal Quality / no alpha. It cannot produce DXV HQ or DXV with alpha.
- This workflow downloads from Drive and returns a GitHub Actions artifact. It does not write files back into Google Drive automatically.

Original files in Drive are not changed.
