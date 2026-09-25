---
license: apache-2.0
library_name: coreml
pipeline_tag: image-to-image
tags:
  - coreml
  - core-ml
  - ios
  - macos
  - apple
  - on-device
  - inpainting
  - fourier-convolution
  - arxiv:2109.07161
---

# LaMa — Core ML

*Image Inpainting, 2022*

Resolution-robust large mask inpainting. Draw over unwanted objects to remove them. Fast Fourier convolutions for global context. 800×800 input.

<p><img src="https://huggingface.co/mlboydaisuke/LaMa-CoreML/resolve/main/media/f5af3cfcc7.gif" alt="LaMa demo"></p>

Core ML conversion of [advimman/lama](https://github.com/advimman/lama) for on-device inference on iPhone, iPad and Mac. Converted with `coremltools`; the packages are stateless, so all sequencing and buffering lives in your Swift code.

| | |
|---|---|
| Task | image to image |
| Upstream | [advimman/lama](https://github.com/advimman/lama) |
| Packages | 1 |
| Download size | 187 MB |
| Minimum iOS | 17.0 |
| Peak RAM | ~600 MB |

## Files

| File | Size | Compute units | SHA-256 |
|---|---:|---|---|
| `LaMa.mlpackage.zip` | 187 MB | `all` | `b57b8451a1a86c00…` |
| **Total** | **187 MB** | | |

`compute_units` is not a suggestion -- it is the configuration the conversion was verified against. Moving a package to a different compute unit can silently change the numerics (FP16 attention overflow) or crash on the GPU.

## Download

```bash
hf download mlboydaisuke/coreml-zoo --include "lama/*" --local-dir ./lama
unzip './lama/lama/*.zip' -d ./lama
```

## Use in Swift

```swift
import CoreML

let config = MLModelConfiguration()
config.computeUnits = .all   // as converted — see the table above

// Unzip the .mlpackage, drop it into your Xcode target and Xcode compiles it
// at build time:
let model = try LaMa(configuration: config)

// ...or compile a downloaded .mlpackage at runtime:
let compiled = try await MLModel.compileModel(at: mlpackageURL)
let model = try MLModel(contentsOf: compiled, configuration: config)
```

## Demo

- **Sample app** — [lama-cleaner-iOS](https://github.com/john-rocky/lama-cleaner-iOS), a standalone iOS project.
- **Models Zoo** — this model is downloadable and runnable inside the [Models Zoo app](https://apps.apple.com/app/id6762083207) on the App Store, no build required.

## Conversion

- Pitfalls hit during conversion (FP16 overflow, ANE buffer limits, stride handling): [`docs/coreml_conversion_notes.md`](https://github.com/john-rocky/CoreML-Models/blob/master/docs/coreml_conversion_notes.md)
- Model index: [CoreML-Models](https://github.com/john-rocky/CoreML-Models)

## License

The conversion inherits the upstream license: **Apache-2.0**.

## Credits

- Upstream authors: [advimman/lama](https://github.com/advimman/lama), 2022
- Core ML conversion: john-rocky (Daisuke Majima)

<!-- funnel:v1 -->

---

**More models in this format:** [Core ML Model Zoo](https://huggingface.co/collections/mlboydaisuke/core-ml-model-zoo-6a7078dc888e7b13efd35631) — 46 models, each with the recipe that produced it.

**Want a different model on-device?** [Open a request](https://github.com/john-rocky/on-device-requests) — free, open weights only; the export and its measured numbers get published publicly.

<!-- /funnel:v1 -->
