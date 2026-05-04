# ComboConsistencyV3 (Legacy / Akatsuki-Base)

Formerly the main repository for the **Combo Consistency V3** project. Development of the primary performance model has moved to the `rosu-pp` ecosystem, but this repository serves as the definitive version for the **original Akatsuki-based core**.

---

## 🛠️ Overview
This implementation maintains the original architecture and mathematical constants required for legacy compatibility while integrating the latest logic reworks from the active project. CCV3 is a fork of [`akatsuki-pp-rs`](https://github.com/osuAkatsuki/akatsuki-pp-rs) which itself is a fork of MaxOhn's [`rosu-pp`] (https://github.com/MaxOhn/rosu-pp). 

### Core Features
*   **Continuous Miss Decay:** A smooth exponential scaling system for misses, removing the "tiers" of previous versions.
*   **n50 Effective Misses:** Dynamic inflation of 50 hits into the miss count based on OD, AR, and map length.
*   **Combo-Ratio Tax:** A light performance penalty (up to 15%) for low-combo scores that still maintain high accuracy.
*   **Sin² Angle System:** Explicitly preserves the $sin^2$ trigonometric model for angle-based difficulty.

---

## 📋 Integration TODOs
The following tasks are currently pending to reach parity with the `rosu` main branch:

- [ ] **[Continuous Miss Rework:** Port the `e^(-misses/8)` curve logic.
- [ ] **NoFail Standalone Scaling:** Port the HP/Acc-based failure estimation for NF scores.
- [ ] **Compatibility Check:** Use LLM assistance to verify logic errors or type mismatches between the `rosu` port and this `akat` base.

---

## ⚙️ Logic Structure
This version is designed to be used as a drop-in replacement for performance calculators using the Akatsuki state structure:

```rust
// Porting Note:
// Ensure the sin^2 system is preserved over the newer 
// smoothstep/smootherstep interpolation used in ccv3-rosu.
```

## 📜 Acknowledgments
Special thanks to MaxOhn and the Akatsuki team for the foundational performance core.
 
