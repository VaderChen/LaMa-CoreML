# LaMa Core ML backup

Backup of the exact Core ML package used by [FilmDevelop](https://github.com/VaderChen/FilmDevelop).

## Download

Download `LaMa.mlpackage.zip` and `SHA256SUMS` from [Releases](https://github.com/VaderChen/LaMa-CoreML/releases), verify the archive with SHA-256, then unzip it. The archive contains the complete package including the 215,544,960-byte model weights. Large model files are stored as release assets, not Git LFS pointers.

## Provenance and license

- Source: https://huggingface.co/mlboydaisuke/LaMa-CoreML
- Pinned source revision: `5ed76e3799ab4cad31381750d29880c267477e18`
- Original research/code: https://github.com/advimman/lama
- Core ML conversion credited upstream to john-rocky (Daisuke Majima).
- License: Apache-2.0; see LICENSE and the preserved UPSTREAM_MODEL_CARD.md.
- Model bytes are unmodified. Only the ZIP packaging is new; its hash differs from upstream ZIP archives.
- This is an independent backup mirror, not a GitHub fork or an upstream-endorsed release.

`SHA256SUMS` records the archive and each extracted package file. FilmDevelop independently checks each package file against the same pinned hashes before loading.
