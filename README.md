# Empirical Validation of the Power of Two Choices

**Authors:** Awatif Alshehri, Padmaja S  
**Affiliation:** Dept. of Computer Science, College of Computer Engineering and Sciences, Prince Sattam Bin Abdulaziz University, Al-Kharj 11942, Saudi Arabia  
**Published:** IEEE TEMSCON-ASPAC 2026

---

## Overview

Python discrete-event simulation comparing three web server load-balancing algorithms:

| Algorithm | Decision Cost | Load-Aware | Max-Load Bound |
|-----------|--------------|------------|----------------|
| Round-Robin (RR) | O(1) | No | Θ(n/m) |
| Random Assignment (RA) | O(1) | No | Θ(log n / log log n) |
| **Power of Two Choices (P2C)** | **O(1)** | **Yes** | **Θ(log log n)** |

### Key Results
- P2C reduces Average Response Time by **50%** over RA under Bursty traffic (t = −79.6, p < 0.001)
- P2C reduces ART by **46%** over RA under Heavy-Tailed traffic (t = −33.3, p < 0.001)
- 7,200 simulation runs across 36 configurations (3 algorithms × 4 server counts × 3 traffic patterns)
- Complete experiment runs in **33 seconds** on a standard laptop

---

## Requirements

```bash
pip install numpy scipy pandas matplotlib
```

---

## How to Run

```bash
python p2c-load-balancing.py
```

---

## Outputs

All outputs are saved automatically:

```
results/
├── simulation_results.csv       # 36-row summary
├── raw_simulation_7200.csv      # 7,200-row raw dataset
└── summary_table.csv            # Pivot table

figures/
├── fig1_nml.png                 # NML vs number of servers
├── fig2_art.png                 # ART vs number of servers
├── fig3_bar.png                 # Bar comparison at m=5
├── fig4_heatmap.png             # Heatmap — all 36 configurations
└── fig5_theory.png              # Empirical vs theoretical bounds
```

---

## Simulation Parameters

| Parameter | Value |
|-----------|-------|
| Fleet sizes (m) | 3, 5, 7, 10 |
| Arrival rate (λ) | 10–200 req/s (Poisson) |
| Service rate (μ) | 50 req/s/server |
| Traffic patterns | Uniform, Bursty, Heavy-Tailed |
| Runs per config (K) | 200 |
| Total runs | 7,200 |
| Random seed | 42 (reproducible) |

---

## Citation

If you use this code, please cite:

```
Alshehri, A. & Padmaja, S. (2026). Empirical Validation of the Power
of Two Choices. Proceedings of the 5th
IEEE International Conference on Technology, Engineering, Management
and Science (TEMSCON-ASPAC 2026).
```

---

## License

MIT License — free to use, modify, and distribute with attribution.
