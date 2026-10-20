# Reproducing Isolation Forest (Liu, Ting & Zhou, ICDM 2008)

Re-implementation of Isolation Forest from scratch in Python/NumPy, and reproduction of the
paper's main experiment (Table 3: AUC on 12 benchmark data sets).

## Files
- `iforest_reproduction.ipynb`: the full implementation, experiment and results (outputs included)
- `requirements.txt`: required Python packages

## How to run
```bash
git clone https://github.com/domamolnar-wq/iforest-reproduction.git
cd iforest-reproduction
pip install -r requirements.txt
jupyter notebook iforest_reproduction.ipynb
```
Then choose **Kernel → Restart & Run All**. The data sets are downloaded automatically into
`./data` on the first run (from the ADBench and PyOD GitHub repositories). A full run takes
about 10–15 minutes.

## Parameters
| Parameter | Value |
|---|---|
| Number of trees t | 100 |
| Sub-sampling size ψ | 256 |
| Height limit | ⌈log₂ ψ⌉ = 8 |
| Independent runs | 10 (seeds 0–9) |
| LOF baseline | k = 10 |
| k-NN baseline (ORCA's scoring rule) | k = 5 |
| Mulcross generator | 262,144 points, d = 4, 10% anomalies, distance factor 2, 2 clusters, cluster std 0.1 |

## Data sources
ODDS (Rayana, 2016), distributed by ADBench (Han et al., 2022) and PyOD (Zhao et al., 2019).
Mulcross is generated in the notebook following Rocke & Woodruff (1996).
