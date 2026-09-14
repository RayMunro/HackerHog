# HackerHog

Ray Munro's Community Applications feed for Unraid: a collection of Docker apps and plugins, each maintained in its own repository. This repo holds only the Community Applications metadata (`ca_profile.xml`, `templates/*.xml`, `plugins/*.xml`) that Unraid's Community Applications plugin reads to list them - the source code, `.plg` files, and Dockerfiles for each app live in their own linked repository.

## Docker apps (`templates/`)

| App | Template | Source |
| --- | --- | --- |
| Dockyard | [`templates/dockyard.xml`](templates/dockyard.xml) | [RayMunro/dockyard](https://github.com/RayMunro/dockyard) |
| Docker Safeguard | [`templates/docker-safeguard.xml`](templates/docker-safeguard.xml) | [RayMunro/docker-safeguard](https://github.com/RayMunro/docker-safeguard) |

## Plugins (`plugins/`)

| Plugin | Entry | Source |
| --- | --- | --- |
| Share Name Normalizer | [`plugins/share-name-normalizer.xml`](plugins/share-name-normalizer.xml) | [RayMunro/unraid-share-name-normalizer](https://github.com/RayMunro/unraid-share-name-normalizer) |
| Bulk Share Toggle | [`plugins/bulk-share-toggle.xml`](plugins/bulk-share-toggle.xml) | [RayMunro/unraid-bulk-share-toggle](https://github.com/RayMunro/unraid-bulk-share-toggle) |
| SMB Bulk Share Control | [`plugins/smb-bulk-share.xml`](plugins/smb-bulk-share.xml) | [RayMunro/unraid-smb-bulk-share](https://github.com/RayMunro/unraid-smb-bulk-share) |
| Parity Spot Check | [`plugins/parity-spotcheck.xml`](plugins/parity-spotcheck.xml) | [RayMunro/unraid-parity-spotcheck](https://github.com/RayMunro/unraid-parity-spotcheck) |
| Boot Ready Notify | [`plugins/boot.ready.warning.xml`](plugins/boot.ready.warning.xml) | [RayMunro/unraid-boot-ready-notify](https://github.com/RayMunro/unraid-boot-ready-notify) |
| Mains Power Monitor | [`plugins/mains-power-monitor.xml`](plugins/mains-power-monitor.xml) | [RayMunro/unraid-mains-power-monitor](https://github.com/RayMunro/unraid-mains-power-monitor) |
| Cache / Array Share Control | [`plugins/cache-array-share.xml`](plugins/cache-array-share.xml) | [RayMunro/unraid-cache-array-share](https://github.com/RayMunro/unraid-cache-array-share) |

## Adding a new app or plugin

1. Build and publish the app/plugin as usual in its own repository.
2. Add a `<Repository>`/`<Container>` XML template (Docker apps) under `templates/`, or a `<Plugin>` wrapper under `plugins/`, following the existing files as a pattern.
3. Point `TemplateURL`/`PluginURL`, `Project`, `ReadMe`, and `Icon` at the raw GitHub URLs of the source repo (except `TemplateURL`, which points back at this repo).
4. Commit and push, then run **Validate** and **Scan** in the Community Applications submit flow.

## Files

- `ca_profile.xml`: repository overview and support metadata shown in Community Applications.
- `icon.svg`: repository icon referenced by `ca_profile.xml`.
- `templates/`: one Docker app template per file.
- `plugins/`: one plugin wrapper per file.
