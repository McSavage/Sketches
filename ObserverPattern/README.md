
# Observer Pattern – Yield Curve Swaps

This sketch demonstrates the Observer pattern using a simple yield curve and swap portfolio. Swaps subscribe to a `YieldCurve` and automatically recalculate present value when curve rates change.

## Contents

- `Observer_Pattern.ipynb`: runnable notebook showing the example code and output.

### How it works

1. `YieldCurve` holds rate data and lets observers subscribe.
2. `Swap` implements the observer callback `on_curve_update`.
3. When `YieldCurve.update_rates` is called, all observers are notified; each swap recalculates via `_calculate_pv` and a pure `_compute_present_value` helper.

### Running the notebook

1. Open `Observer_Pattern.ipynb` in VS Code or Jupyter.
2. Select a Python 3.10+ kernel.
3. Run the cells to see pre- and post-update PVs.

### Key takeaways

- Observer pattern decouples the curve publisher from swap consumers.
- Separating the callback (`on_curve_update`), orchestration (`_calculate_pv`), and pure logic (`_compute_present_value`) keeps the code testable and adaptable.
