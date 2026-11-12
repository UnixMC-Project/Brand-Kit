# Asset Index

Every file in the kit, where it lives and what it is for. For the rules read the [Brand Guidelines](BRAND_GUIDELINES.md); for what you may do with the files read the [Usage Policy](USAGE_POLICY.md).

> © UnixMC · CC BY-NC-ND 4.0 · use the files **unmodified** and give attribution. Fonts are under SIL OFL 1.1.

## Folders

| Folder | Contents |
|---|---|
| [`logo/`](../logo) | The Clock mark: `unixmc_logo_native_16x16.png` (original grid) and nearest-neighbour enlargements at 64, 128, 256, 512, 1024, 2048 px, all with transparent background. Also `Clock512.png` and the animated `Clock512.gif`. |
| [`logo/characters/`](../logo/characters) | Character and staff badges: `logo_cartoon.png`, `logo_mentor.png`, `logo_moderation.png`, `kawaii_logo.webp` |
| [`banner/`](../banner) | 3D title renders (`unixmc_title.png`, `_alpha`, `_beta`, `_release`, `_lostsoul`), `unixmc_banner_big.png`, and the Blockbench model `title_model.bbmodel` |
| [`avatar/`](../avatar) | Square avatar on the blurred in-game backdrop: 320, 400, 800, 1000 px. One copy per size; every platform uses these (see table below) |
| [`socials/`](../socials) | Banners, headers, covers and watermark per platform (see below) |
| [`colors/`](../colors) | Palette sheet (`unixmc_palette.png`), data files (`.css .json .gpl .hex .txt`), and `website-ui/` (unixmc.com UI palette audit) |
| [`fonts/`](../fonts) | `PressStart2P-Regular.ttf`, `Silkscreen-Regular.ttf` (licence texts are in [`licenses/third-party/`](../licenses/third-party)) |
| [`source/`](../source) | Original screenshot: `unixmc_screenshot_2555x480.png` |

## Platform files

| Folder | Files |
|---|---|
| `socials/youtube/` | `youtube_banner_2560x1440.png` · `youtube_watermark_150x150.png` |
| `socials/instagram/` | `instagram_highlight_cover_1080x1920.png` |
| `socials/x/` | `x_header_1500x500.png` |
| `socials/bluesky/` | `bluesky_banner_1500x500.webp` |

### Which avatar goes where

| Platform | Upload | Size |
|---|---|---|
| YouTube | `avatar/unixmc_avatar_800x800.png` | 800 × 800 |
| Instagram | `avatar/unixmc_avatar_320x320.png` | 320 × 320 |
| TikTok | `avatar/unixmc_avatar_400x400.png` | 400 × 400 |
| X | `avatar/unixmc_avatar_400x400.png` | 400 × 400 |
| Bluesky | `avatar/unixmc_avatar_1000x1000.png` | 1000 × 1000 |

The kit contains no duplicate files: each image exists once.

## Which logo size should I use?

| Need | File |
|---|---|
| Favicon, tiny UI | `logo/unixmc_logo_native_16x16.png` or `_64x64` |
| Discord/Slack emoji, forum avatar | `_128x128` / `_256x256` |
| Website header, article inline | `_512x512` |
| Video overlay, print up to ~10 cm | `_1024x1024` |
| Large print, posters | `_2048x2048` |

Use `image-rendering: pixelated` (CSS) or "nearest neighbour" in editors if the size you need isn't provided.

## Verify your copy

`MANIFEST.sha256` in the repository root lists a SHA-256 checksum for every asset file.

```bash
sha256sum -c MANIFEST.sha256     # macOS: shasum -a 256 -c MANIFEST.sha256
```
