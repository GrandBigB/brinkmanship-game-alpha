# Validation results

Passed on this build:

- Exact inline-script equality between each newest supplied framework and its desktop/mobile output.
- Automatic layout differs only in its presentation-level LAYOUT constant.
- 100 countries × 17 screen generators × 2 layouts: 3,400 screen-generation checks.
- Nonempty country institution labels and all 100 national portrait mappings.
- Adviser/institution reads leave campaign state unchanged.
- US Department of Defense and Russian SVR display assertions.
- Four identical-seed campaign comparisons (USA, Russia, China, Estonia), each advanced three turns: reskinned and unmodified game states matched exactly.
- Campaign JSON restoration in those comparisons.
- Syntax checks for the original inline scripts and new presentation/service-worker scripts.

These are headless engine and output checks, not browser interaction tests. They do not verify every user action, visual layout, native export/share behaviour, touch-device performance, or App Store acceptance. No signed native build was produced.
