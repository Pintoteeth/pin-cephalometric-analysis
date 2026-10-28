---
name: pin-cephalometric-analysis
description: Operate, maintain, debug, or adapt the PIN website's local cephalometric analysis module, including research AI landmarks, manual tracing, measurements, and explicit clinical data transfer. Use for the PIN module, not the separate forabi/WebCeph workbench or a commercial WEBCEPH service.
---

# PIN 头影测量分析

Support the user's existing PIN cephalometric analysis workspace. This skill is a reusable Codex workflow; it is not an AI model or a standalone application. The module, image handling, case storage, and build remain in the PIN project. Resolve its root from the current workspace. Verify the checkout and current release files before relying on recorded details. If it is unavailable, ask for the project location rather than inventing an implementation.

## Workflow

1. Identify whether the request concerns using the current workspace, changing its UI or calculations, debugging local AI/model loading, case persistence, clinical transfer, or adapting it to another site. Read [implementation and verification](references/implementation.md) for the relevant code map and checks. Read the project `README.md`, `ceph/WORKSPACE.md`, and the relevant source before changes; current code wins over old notes.
2. For measurements, references, or any clinical-facing change, read [measurement and safety boundaries](references/measurement-boundaries.md). Preserve explicit definitions, image binding, calibration, provenance, and user review. Existing research AI is restricted to research and education: its output must not be used for diagnosis or treatment or automatically written to clinical fields.
3. For project changes, edit the maintained `ceph/` sources and build integration instead of editing only the generated HTML. Preserve unrelated modules and patient data. Run checks appropriate to the change, including synthetic inputs for image, state, geometry, or transfer paths; report what was actually verified and any untested direct-file or browser behavior.
4. The original module is coupled to the PIN case schema, shared image slot, and lifecycle. For reuse elsewhere, inspect and adapt those interfaces explicitly; do not present a copied folder or this skill as an independently runnable product. Retain source, model and runtime attribution and applicable licenses.

Keep patient images and case files local by default. Do not upload them or enable a remote service without the user's explicit authorization. Do not fabricate landmarks, measurements, reference values, validation, or model capabilities. Preserve the original AI result separately from manual edits and require user confirmation for actions that overwrite case values.

The separate `webceph-local` skill covers the forabi/WebCeph workbench, which must not be confused with the PIN research model or the commercial WEBCEPH service. Check `release-source.json` before claiming the workbench is enabled.
