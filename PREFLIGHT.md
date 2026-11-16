# Preflight record

Record of the pre-publication gate run with the `preflight` skill, one section per run. Item ids point at the checklist items in the skill's `references/` (A = private, B = public, C = announce, D = contribute, other letters = modules); results are PASS, FINDINGS n resolved (n hits found and dispositioned), N/A <reason>, DEFERRED <reason, owner>, TOOL-ERROR <tool>, FAIL.

## 2026-11-16 · public · candidate 4f95f4a · destination github:DamianPala/lonewrt-build (public)
Decisions: name lonewrt-build · licence MIT · history squash · maturity experimental · disclosure: "Built with AI coding agents under my direction."

| Item | Result | Note |
|---|---|---|
| A01 | PASS | every decision filled from the owner's answers |
| A02 | PASS | tree clean at the candidate |
| A03 | PASS | squash in place, bundle kept, never pushed |
| A04 | PASS | secret scans clean |
| A05 | N/A no credential committed | |
| A06 | FINDINGS 7 resolved | 7 kept: the public account name in links to lonewrt |
| A07 | PASS | nothing private tracked |
| A08 | PASS | one approved identity |
| A09 | PASS | no status or planning files |
| A10 | PASS | no fixtures or sample data |
| A11 | N/A no non-text content | |
| A12 | PASS | outside pointers are public URLs |
| A13 | PASS | first-party; actions referenced, not vendored |
| A14 | DEFERRED (owner) | 2FA line to refresh from the laptop |
| A15 | PASS | no dependents |
| A16 | PASS | public, template, not a fork, owner only |
| A17 | N/A no workflow fires on push | |
| B01 | PASS | published set = all except the private record |
| B02 | PASS | MIT in LICENSE and README |
| B03 | PASS | the owner's own repository |
| B04 | DEFERRED after the owner's upload | the route runs only on GitHub; test run after the push |
| B05 | PASS | README walked; terms present; holds once lonewrt 0.2.0 is out |
| B06 | PASS | the build script's gates and failures tested in lonewrt |
| B07 | PASS | download hosts listed; the profile goes only into the run's download |
| B08 | PASS | two official actions pinned by SHA |
| B09 | N/A no release version | |
| B10 | PASS | zizmor clean, read-only permissions, SHA pins |
| B11 | PASS | three files |
| B12 | PASS | links point at lonewrt pages that exist |
| B13 | DEFERRED (owner) | secret scanning and push protection on the new repository |
| B14 | DEFERRED after the owner's upload | test run and rendered README |
| B15 | DEFERRED after the owner's upload | status update after the push |
| B16 | N/A no agent instructions shipped | |
| L13 | FINDINGS 1 resolved | 1 kept: the run's own GitHub token |
| L14 | PASS | one manual trigger, one download, test mode explicit |
| L15 | PASS | runs are independent |
| L16 | PASS | no paid endpoint; failure messages written |
| L21 | PASS | gh and bash on the runner; host tools installed by the script |
