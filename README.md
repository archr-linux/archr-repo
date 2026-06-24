# archr-repo

ArchR pacman repository. The actual package data lives in GitHub
Releases, not in the git tree, because pacman fetches assets over
HTTPS from `https://github.com/archr-linux/archr-repo/releases/download/repo-<channel>/`.

This repository exists primarily as a coordinate for the release
tags and as a place to publish the mirror's `README` and policy.
The package build pipeline that produces each release lives in
[archr-linux/Arch-R](https://github.com/archr-linux/Arch-R)
under `scripts/repo/gen-pacman-repo`.

## Channels

| Tag          | Audience    | Cadence |
|--------------|-------------|---------|
| `repo-stable`| end users   | monthly snapshot, validated |
| `repo-next`  | testers     | promoted from dev after CI window |
| `repo-dev`   | maintainers | rolling, may break |

The ArchR system selects the channel from `system.cfg "updates.branch"`;
`archr-update` rewrites `/etc/pacman.d/mirrorlist` accordingly.

## Verification

Packages and the repo `.db` are signed with the ArchR master subkey.
The public key ships with the `archr-keyring` package on every ArchR
system. Manual verification:

```sh
gpg --verify archr.db.sig archr.db
gpg --verify <package>.pkg.tar.zst.sig <package>.pkg.tar.zst
```

Master key fingerprint:

    0CB28237 9EBB394E F380AEB9 8A762D57 06C602A1

