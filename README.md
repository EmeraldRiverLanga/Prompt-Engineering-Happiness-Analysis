# Prompt Engineering — Happiness Analysis

## Overview

Exploring prompt engineering strategies using the **World Happiness Report 2017** dataset. Four strategies were tested and compared to analyze which factors most influence happiness scores.

## Technologies Used

- **Python** — core language
- **Pandas** — data processing
- **Matplotlib / Seaborn** — visualisation
- **Claude Haiku (Anthropic)** — LLM via OpenRouter API
- **Google Colab** — training environment

## Setup

### Install dependencies

```bash
pip install openai pandas matplotlib seaborn
```

### Run in Google Colab

1. Upload `2017.csv` to your Colab environment
2. Add your OpenRouter API key to Colab Secrets as `OPENROUTER_API_KEY`
3. Run all cells in order

## Project Structure

The notebook tests four prompting strategies on the same dataset:

### Strategy 1 — Zero-shot
- Task without examples
- Model relies entirely on training knowledge

### Strategy 2 — Few-shot
- Task with 2–3 examples to guide the model
- Improves consistency and output format

### Strategy 3 — Chain-of-Thought
- Step-by-step reasoning for systematic analysis
- Forces structured thinking before conclusions

### Strategy 4 — Super-prompt (CoT + Role)
- Chain-of-Thought combined with role prompting
- Expert-level analysis; revealed insights others missed

## Dataset

**World Happiness Report 2017** — Gallup World Poll
- 155 countries × 12 columns
- Factors: GDP, Family, Health, Freedom, Generosity, Trust

## Key Findings

- **GDP** is the strongest predictor of happiness (correlation: 0.812)
- **Latvia's biggest gap** vs Nordic countries is Trust in institutions (−77%)
- **Luxembourg paradox** — highest GDP (1.742), yet only 13th in happiness
- **Costa Rica phenomenon** — 39% lower GDP than USA, almost equal happiness

### Correlation with Happiness Score

| Factor | Correlation | Strength |
|--------|-------------|----------|
| GDP | 0.812 | 🟢 Strong |
| Health | 0.782 | 🟢 Strong |
| Family | 0.753 | 🟢 Strong |
| Freedom | 0.570 | 🟠 Medium |
| Trust | 0.429 | 🟠 Medium |
| Generosity | 0.155 | 🔴 Weak |

### Strategy Quality Comparison

| Strategy | Quality |
|----------|---------|
| Zero-shot | 40% |
| Few-shot | 60% |
| Chain-of-Thought | 80% |
| Super-prompt (CoT + Role) | 100% |

## Key Concepts Demonstrated

- **Zero-shot prompting** — baseline model capability without examples
- **Few-shot prompting** — guiding output format with examples
- **Chain-of-Thought** — structured step-by-step reasoning
- **Role prompting** — framing the model as a domain expert
- **Prompt comparison** — evaluating strategy quality systematically
