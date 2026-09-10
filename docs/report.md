# Composite Benchmark Report

## Result

The ten-output composite achieved 100% viewable completion, a 60% strict pass rate, and a weighted mean of 3.97 out of 5.

| Dimension | Mean |
|---|---:|
| Source fidelity | 3.80 |
| Geometric consistency | 4.20 |
| Instruction adherence | 3.90 |
| Plausibility | 4.00 |
| Aesthetic quality | 4.10 |

## Method

Scores use integer 1–5 judgments for fidelity, geometry, adherence, plausibility, and aesthetics:

```text
S = 0.30F + 0.25I + 0.20G + 0.15P + 0.10A
```

A result passes only when its weighted score is at least 3.50, fidelity and instruction adherence are each at least 3, every case-specific critical condition is met, and no hard failure applies.

No image was regenerated for this release. The ten-slot result recomputes aggregation from previously locked item-level evaluations. It is not presented as a fresh independent blind review.

## Composition and comparability

Seven outputs correspond to original frozen benchmark tasks. Three R-suffix outputs are policy-safe proxies created after the associated original requests were blocked by output moderation.

The proxies do not silently replace the blocked tasks:

- **01R** infers a fully draped bust beneath a surviving portrait head rather than reconstructing missing nude anatomy.
- **03R** transfers visual language onto two rigid vessels rather than preserving an articulated three-figure sculpture group.
- **10R** composes one rigid armor figure with a painting rather than integrating a multi-figure group and serpent.

The composite mean is therefore an operational mixed-suite metric, not a corrected score for the original benchmark.

## Failure analysis

### 03R — content/style leakage

Both vessels, their handles, size relationship, and major color zones survive, but the output reproduces the style reference's literal pond, flowers, lily pads, and reflections. The model learned a coupled scene-and-style representation when the task required visual language alone.

### 07 — ambiguous coordinated motion

The gallery remains recognizable and visually compelling, but the central group and tapestry drift, and the required helmet turns are difficult to verify. Dense source geometry and pre-existing armor orientation make the requested delta underdetermined.

### 08 — source-description and pose failure

The generated mosaic is coherent, but the grazing camel's lowered neck changes and a vessel-like source form becomes another animal. The frozen prompt itself incorrectly described that form, demonstrating that benchmark annotation error can masquerade as model error.

### 10R — transformation over-amplification

The armor-gallery narrative is coherent, but a requested narrow reflected-color ribbon becomes a broad waterfall and floor-spanning pool. The output also retains text. The failure is not composition; it is constraint calibration.

## Research implication

The model is better at producing aesthetically and geometrically coherent transformations than at isolating which latent attributes should transfer. The next experiment should use a factorial design that independently requests palette, brushwork, illumination, or scene-content transfer from the same second reference. This converts a qualitative failure into an identifiable boundary in reference-role control.

## Publication boundary

This public subset excludes original full-resolution and unredacted museum photographs, raw local manifests, provider receipts, account details, workstation paths, task identifiers, shared-chat URLs, and embedded image metadata. Nine lower-resolution source derivatives are included solely to establish the input-to-output association; frames containing bystanders were cropped or visibly pixelated. The generated images are benchmark outputs and should not be treated as authoritative historical reconstructions.
