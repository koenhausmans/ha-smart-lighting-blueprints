# Smart Motion Lights (Home Assistant Blueprint)

Motion-activated lights for multiple sensors per room, with sun-elevation–based
brightness (sine curve, separate morning/evening minimums, optional auto-scaling
to today's peak sun), a cancellable off-delay, periodic brightness refresh while
occupied, and optional manual-override protection.

> **Note:** HACS has no "blueprint" category, so this is *not* installed as a HACS
> repository. Use the native blueprint import below. No `hacs.json` is needed.

## Repository layout

```
.
├── README.md
└── motion_light_multisensor.yaml   # the blueprint
```

## Install (one-click import)

Click the badge (replace `<you>`/`<repo>` and branch if needed):

[![Open your Home Assistant instance and show the blueprint import dialog.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fraw.githubusercontent.com%2F<you>%2F<repo>%2Fmain%2Fmotion_light_multisensor.yaml)

Or manually: **Settings → Automations & Scenes → Blueprints → Import Blueprint**,
and paste the raw URL of `motion_light_multisensor.yaml`.

Native import is a one-time copy — to update, re-import the same URL (it overwrites
the existing blueprint of the same name).

## Optional: update tracking

For HACS-style "new version available" notifications, install a blueprint-updater
integration (e.g. `blueprints-updater`) — added to HACS as a custom repository with
category **Integration** — which adds native update entities for blueprints.

## Versioning

Version = the GitHub release tag, e.g. `v0.1.0`:

```bash
git tag v0.1.0
git push --tags
```

Then publish it as a Release on GitHub.

## Requirements

- A `sun.sun` entity (default in HA).
- For per-room manual-override protection: one `input_number` helper per room.
