## SoT-Reproducibility

Reproducibility study of the SQL-of-Thought (SoT) paper, using DeepSeek-Chat on the Spider benchmark (first 100 dev examples).

Original repo: https://github.com/shollercoaster/SQL-of-Thought

## Setup

- Runtime: Google Colab (free tier, no GPU needed)
- Model: DeepSeek-Chat via OpenAI-compatible API (base_url: https://api.deepseek.com)
- Dataset: Spider (downloaded via gdown)
- Key dependency: openai, gdown

## How to run

1. Open `SoT_Reproducibility.ipynb` in Google Colab
2. Run cells in order
3. When prompted, enter your DeepSeek API key
4. Results are saved as JSON files in `ablations_actual/`

## Experiments

Five configurations tested on 100 Spider dev examples:

| Config | EA | EM | Valid SQL |
|---|---|---|---|
| Full SoT (with correction) | 89% | 11% | 99% |
| SoT without correction | 85% | 6% | 100% |
| SoT without subproblem decomposition | 90% | 10% | 99% |
| SoT without schema linking | 89% | 12% | 100% |
| Direct prompting baseline | 87% | 21% | 100% |

## Modification

The original paper used GPT-4. This study swaps the LLM to DeepSeek-Chat and runs ablation experiments to measure the contribution of each pipeline component.

## Files

- `SoT_Reproducibility.ipynb` — main notebook with all code
- `ablations_actual/` — JSON result files for each experiment
