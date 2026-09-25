# LaMa Core ML backup

Source, license, model card and file checksums for the Core ML model used by [FilmDevelop](https://github.com/VaderChen/FilmDevelop). The complete model package, including weights, is backed up as a GitHub Release asset.

## Backup download

Download `LaMa.mlpackage.zip` and `SHA256SUMS` from [the backup release](https://github.com/VaderChen/LaMa-CoreML/releases/tag/lama-5ed76e3). The ZIP contains the complete package with unmodified model files; only the archive packaging is new. Verify its SHA-256 before extracting.

## Application download source

FilmDevelop continues downloading from Hugging Face, using the pinned revision below. No GitHub Release download or fallback is configured.

- Model: https://huggingface.co/mlboydaisuke/LaMa-CoreML
- Pinned revision: `5ed76e3799ab4cad31381750d29880c267477e18`
- Package: https://huggingface.co/mlboydaisuke/LaMa-CoreML/tree/5ed76e3799ab4cad31381750d29880c267477e18/LaMa.mlpackage
- Original research/code: https://github.com/advimman/lama
- Core ML conversion credited upstream to john-rocky (Daisuke Majima).
- License: Apache-2.0; see LICENSE and preserved UPSTREAM_MODEL_CARD.md.

`SHA256SUMS` records the backup ZIP and the three original package files verified against FilmDevelop's pinned hashes. The upstream model card is preserved as historical source material; its ZIP references describe the upstream project, not assets hosted here.

This is an independent backup mirror, not a GitHub fork or an upstream-endorsed release. GitHub hosts a recovery copy only; FilmDevelop continues using the original Hugging Face URLs.
