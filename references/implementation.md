# PIN implementation and verification

These are pointers for the current checkout, not a substitute for reading its code. Locate the PIN project in the current workspace, or ask the user for its location.

## Where changes belong

- `design/ceph_tab_patch.py`: composes the ceph tab, injects its scripts/styles, moves the shared `lateral-ceph` image card, and connects saved-state validation. `tools/build_release.py` builds `app/assessment.html` and `app/version.json`; `dist/PIN儿童牙骨肌颜面评估系统_macOS配色版.html` is a generated complete entry. Inspect `tools/package.py` and release manifests before preparing any update.
- `ceph/workspace.html`, `workspace.css`, `workspace.js`: image display, English-only landmark labels, zoom/pan, point editing, calibration controls and workspace interactions. `ceph/WORKSPACE.md` documents the UI API and Co/Xi handling.
- `ceph/engine-client.js`, `engine.worker.js`, `state.js`, `controller.js`, `geometry.js`: local research-model loading, inference, geometry, image binding, baseline/manual state and lifecycle. `ceph/build_model_pack.py`, `ceph/upstream/PROVENANCE.json`, and `ceph/model/` document reproducibility and attribution. The separately selected model bundle is currently `dist/PIN头影研究模型_CEPHA29.pinai`; it is not included in this skill.
- `ceph/adult-analysis*`, `adult-geometry*`: the 24-item user-provided adult analysis table, manual entries, derivations and research calculations.
- `ceph/clinical-transfer*`: explicit independently measured manual data transfer to matching PIN clinical fields, including provenance and undo.
- `reference/assessment-v8.6.original.html` contains the existing growth-reference selector (`input-gm-reference-mode`) and `gmFinding` logic; inspect the active generated logic and any build patches as well. `audit/validation.js` supplies numeric review gates. Check the actual age, sex, dentition stage, population and plane before interpreting a reference; do not extrapolate missing groups.
- `ceph/contour-*`: manual contour geometry, state, interaction and export. `ceph/tooth-asset-*`, `tooth-presets.js`: user-provided U1/U6/L1/L6 image overlays and controls. These are separate from landmark coordinates and measurements.
- `release-source.json` gates the separate optional WebCeph workbench. Do not assume the development files are deployed; check the actual flag and release. `webceph-local` provides that workbench's integration guidance.

## Invariants during edits and reuse

- All editable point coordinates refer to original image pixels with an upper-left origin. Keep pre/post-processing transforms reversible, and bind saved points, calibration, contours and overlays to the correct image identity and dimensions. On image/case changes clear stale active overlays; preserve valid saved data and reject mismatches without overwriting it.
- Retain the 29-point original AI baseline separately from human corrections; Co is an existing model point, Xi is a separate manually placed point, never an extra model channel or AI-confidence value. Maintain existing saved-state compatibility.
- Lengths require a user-confirmed scale. Do not invent a scale from image dimensions, or silently change plane or angle definitions.
- The PIN website has a shared side-view upload, case/JSON/HTML lifecycle, drafts, and clinical fields. Adapt these contracts and their validation explicitly before embedding the module in another application. Do not silently create duplicate image records or change reports, diagnoses or treatment plans.
- Preserve user-provided tooth assets and their attribution/permissions; do not use patient images, patient values, or case files as test fixtures or templates.

## Checks

Run from the project root, using the installed Node runtime; select tests relevant to the actual change. Examples:

```sh
node --test ceph/engine.test.mjs ceph/state.test.mjs ceph/geometry.test.mjs ceph/controller.test.mjs ceph/workspace.test.mjs
node --test ceph/adult-*.test.mjs ceph/clinical-transfer*.test.mjs
node --test ceph/contour-*.test.mjs ceph/tooth-asset*.test.mjs ceph/tooth-presets.test.mjs
python3 tools/build_release.py
```

Check model-pack hashes and original source restrictions before changing loader, runtime or weights. Test image change, saved-case round-trip, cancellation/failure, calibration and transfer behavior as applicable. Use synthetic, non-patient input. If a browser tool cannot open `file://`, distinguish an isolated component or automated test from actual full-file browser verification; don't bypass the restriction to inspect a user's open case. Engineering tests do not validate clinical accuracy.
