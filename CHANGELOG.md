# Changelog

All notable changes to the UnixMC Brand Kit. Format: [Keep a Changelog](https://keepachangelog.com/); versioning: `MAJOR.MINOR.PATCH` (see [guidelines §9](docs/BRAND_GUIDELINES.md#9-file-naming-and-versioning)).

## [2.0.0]

Full rework of the brand kit. The former `assets/` folder is merged into the new root layout; no files were renamed or removed.

### Added
- Kit folders at the repository root: `logo/`, `avatar/`, `colors/`, `fonts/`, `source/` and `socials/` (`youtube/`, `instagram/`, `x/`, `bluesky/`) with logo sizes 16–2048 px, avatars, platform banners, colours, fonts and source files.
- `docs/BRAND_GUIDELINES.md`: full brand overview (name, logo system, colour, typography, imagery, do/don't, platform reference).
- `docs/USAGE_POLICY.md`: what is allowed, what needs permission, what is never allowed, attribution wording, how to ask.
- `docs/LICENSING.md`: licence map for every folder and the bundled fonts.
- `docs/ASSET_INDEX.md`: every file, and which logo size to use.
- `NOTICE.md`: copyright, trademark, Minecraft/Mojang disclaimer and third-party notices.
- Palette exports: `unixmc_palette.css`, `.json`, `.gpl`, `.hex` (generated from the original 16 sampled colours).
- Website UI palette audit (489 colours, Overworld/The End themes) in `colors/website-ui/`.
- `licenses/third-party/`: SIL OFL texts for Press Start 2P and Silkscreen (single copy; the duplicates that sat next to the fonts were removed).
- `MANIFEST.sha256`: checksums for integrity checks.

### Changed
- `README.md` rewritten as an index with licence summary and contacts.
- `LICENSE` replaced with the full **CC BY-NC-ND 4.0** legal code. It previously contained CC0 1.0 (public-domain dedication), which contradicted the README and copyright notice.

### Removed (byte-identical duplicates)
- Per-platform avatar copies (`youtube_avatar_800x800`, `instagram_avatar_320x320`, `tiktok_avatar_400x400`, `x_avatar_400x400`, `bluesky_avatar_1000x1000`). Use `avatar/unixmc_avatar_<size>.png`.
- `source/Clock512_original.png` (identical to `logo/Clock512.png`).
- `fonts/OFL_*.txt` (identical to `licenses/third-party/OFL_*.txt`).

### Moved
- `assets/banner/*` → `banner/*`
- `assets/logo/Clock512.*` → `logo/`
- `assets/logo/` badges (`logo_cartoon.png`, `logo_mentor.png`, `logo_moderation.png`, `kawaii_logo.webp`) → `logo/characters/`

### Unchanged
- All file names and contents of the moved assets.
- `colors/unixmc_colors.txt` (original names/CSS variables)

## [1.x]

Earlier repository state: logos and banners under `assets/`, README with a CC BY-NC-ND notice and a copyright notice (see git history).
