# Centralized Ad Configuration for All Craftisle Projects

This JSON file controls ad settings across all Craftisle projects.
Changes here take effect within 5 minutes (cache TTL).

## Usage

1. Edit `enabled` to turn ads on/off for ALL projects at once
2. Commit and push to GitHub
3. All projects will read this file automatically (5min cache)

## Configuration

```json
{
  "enabled": true,
  "monetag": true,
  "adsense": false,
  "updatedAt": "2026-06-23T10:00:00.000Z",
  "note": "Set enabled to false to disable all ads. Set monetag/adsense to control per-platform."
}
```

## Fields

- `enabled`: Master switch. If `false`, no ads load in any project.
- `monetag`: Control Monetag ads only. If `false`, Monetag won't load even if `enabled` is `true`.
- `adsense`: Control AdSense only. If `false`, AdSense won't load even if `enabled` is `true`.
- `updatedAt`: Timestamp of last update (for cache busting).
- `note`: Optional note for humans.

## Project-specific config

Each project has its own `src/lib/config/ads.ts` for:
- AdSense client ID
- AdSense slot IDs
- Monetag zone ID
- etc.

Edit those files in each project to update ad platform details.
