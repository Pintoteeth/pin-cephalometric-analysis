# Measurement and clinical boundaries

The implementation and the model's own attribution/restrictions are authoritative for the current version; inspect them before changing behavior. These notes preserve the user's established choices, not a substitute for clinical validation.

## Research landmarks and measurements

The current CEPHA29 HRNet-W32 model and associated runtime run locally from a separately selected model bundle. The original author restricts the model to research and education and excludes diagnosis and treatment; the PIN installation has not established clinical validity for its target population. Model responses are not accuracy probabilities. Do not present model output, calculated research values, or cosmetic overlays as verified clinical findings. The original 29 points and manual corrections retain distinct provenance; Co is a model point and Xi is independently manual.

Require a real, confirmed scale for millimetres, and review landmark and plane definitions before calculation. Existing MP–SN requires the GoGn or GoMe plane choice; FMA uses an FH–GoMe variant. Wits, OP–FH(up), and basic upper lip thickness are manual-only in the current user-defined table because the matching definition or landmarks are not established. Do not silently equate similarly named parameters or change signed distance conventions.

## Adult reference and transfer

The 24-item adult reference means and standard deviations came from the user's supplied report. Sex, reference population, original literature, and some plane definitions are unspecified; mean ± 1 SD is descriptive, not a validated normal range. Do not use these adult comparisons for children or unknown ages. The reported Mx/Md difference reference mean is inconsistent with the difference of the reported component means; retain the warning and do not interpret that reference until resolved.

Clinical transfer is limited to nine matching, independently sourced manual measurements and requires an explicit source declaration. Default to filling empty fields; replacing a different value requires the user's deliberate choice. Respect method matching, numeric validation, provenance and undo, and do not relabel research/AI-derived or mixed results as independent clinical measurements. Do not transfer adult reference values, diagnostic labels or treatment recommendations. Clinical diagnosis and treatment decisions remain with the responsible clinician.

Manual contours and tooth images are visualization overlays, not automatic segmentation, anatomical proof, or measurement data. Preserve image binding and do not infer new points from their placement. Confirm clinical sources and applicable population before changing standards, and document uncertainty instead of filling gaps with guessed values.
