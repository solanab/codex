# Self release (fork)

This repo includes a lightweight GitHub Actions workflow to publish `codex` binaries to **GitHub Releases** for personal use.

## Create a release

1. Ensure `main` has the commits you want.
2. Create and push an annotated tag:

   ```bash
   git tag -a self-v0.0.1 -m "self release"
   git push origin self-v0.0.1
   ```

3. Wait for the `self-release` workflow to finish. It will create a GitHub Release for that tag and upload assets.

## Install locally

1. Download the asset that matches your platform:
   - `aarch64-unknown-linux-gnu`
   - `aarch64-apple-darwin`
2. Extract and install:

   ```bash
   tar -xzf codex-<tag>-<target>.tar.gz
   install -m 0755 codex ~/.local/bin/codex
   ```

3. Verify which binary you are running:

   ```bash
   command -v codex
   codex --version || true
   ```

If you still have an npm-installed wrapper, make sure `~/.local/bin` appears before npm’s bin directory in your `PATH`.
