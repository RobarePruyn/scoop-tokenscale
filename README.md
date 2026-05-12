# scoop-tokenscale

[Scoop](https://scoop.sh/) bucket for [tokenscale](https://github.com/RobarePruyn/tokenscale).

## Install

```powershell
scoop bucket add tokenscale https://github.com/RobarePruyn/scoop-tokenscale
scoop install tokenscale
```

Then `tokenscale init && tokenscale serve` gets the dashboard running on `http://127.0.0.1:8787`.

## Updating

The manifest has Scoop's `autoupdate` block configured against the tokenscale repo's GitHub Releases. `scoop update` picks up new versions automatically — no manual intervention here when a new tokenscale release ships.

## Why a separate repo?

Scoop expects buckets to be Git repos with manifests at the root or under `bucket/`. Mixing the bucket with the main tokenscale source tree would force users to clone all of tokenscale just to install the binary. Separate repo = `scoop bucket add` works with no options + the bucket stays tiny.

## Distribution path

`dist` (the release-pipeline tool) doesn't have native Scoop support as of v0.31.0 (its installer options are `shell` / `powershell` / `npm` / `homebrew` / `msi`). The manifest in this repo is hand-maintained but auto-updates through Scoop's own update mechanism, so the maintenance cost is essentially zero per release. If/when `dist` adds Scoop support, the bucket migrates to automated publish.
