# Decentralized AI Day Warsaw 2026

Slides and hands-on notebooks for Piotr Plonski's Numerai talk and dashboard workshop at [Decentralized AI Day Warsaw](https://luma.com/k7v8usb6), September 26, 2026.

## Choose a session

| Session | Start here | Then explore |
| --- | --- | --- |
| **Silent Mistakes That Can Hurt Your Numerai Models** | [Talk slides](presentation.pdf) | [Mistakes notebook](hidden-mistakes.ipynb) and [SuperTree demo](supertree.ipynb) |
| **Beyond the Leaderboard: Build Your Own Numerai Dashboard** | [Workshop slides](tutorial.pdf) | [Mercury starter](mercury-starter.ipynb), [Numerai dashboard](numerai-dashboard.ipynb), and [advanced dashboard](numerai-dashboard-advanced.ipynb) |

The talk demonstrates how feature-column order, random seeds, and ensemble scaling can silently change results. The workshop builds a live Numerai dashboard with Python and [Mercury](https://runmercury.com/).

## Run the notebooks

From the repository root, with Python 3.11:

```bash
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab
```

To serve the Mercury dashboards instead, run `mercury` from the repository root and open the local URL it prints. Start with `mercury-starter.ipynb`, then try the two Numerai dashboards. The notebooks expect their relative paths to resolve from this directory.

The dashboards fetch public model data from Numerai's GraphQL API, so they need an internet connection but no API key. The basic dashboard focuses on resolved CORR60 and MMC60 scores; the advanced dashboard also follows submissions, developing scores, and payouts. Early scores and estimated payouts can change before a round resolves. Locally cached responses may be reused, but offline snapshots are **not** included in this repository.

`supertree.ipynb` can use the bundled [sample data](data-v5.3/supertree-quantum-500.parquet) and [trained artifacts](hidden-mistakes-artifacts/3e0cbf61aefc/). Running `hidden-mistakes.ipynb` itself requires the full Numerai v5.3 `train.parquet`, `validation.parquet`, `validation_benchmark_models.parquet`, and `features.json` in `data-v5.3/`; those large datasets are not included. Its existing model artifacts do not replace that data requirement.

## License

See [LICENSE](LICENSE). These notebooks are educational demonstrations, not staking advice.
