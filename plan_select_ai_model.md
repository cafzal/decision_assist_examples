## Data collection
### Objectives / Metrics
* Response time (s): median time‑to‑first‑token from Artificial Analysis
* Reasoning score: average of published MMLU + GPQA‑diamond (flag GPQA N/A if missing)
* Blended cost ($ per 1 M tokens): 0.5 × (input price + output price) × 1 000; use “N/A” for open‑weights
* Coherence: TruthfulQA error + MT‑Bench coherence; use Reddit/X sentiment only as a tie‑breaker
* API utility: weighted rubric: 40 % SLA, 30 % SDK/tooling breadth, 30 % enterprise adoption
* Context window: max contiguous tokens (provider docs cross‑checked with Artificial Analysis)
* Implementation complexity: 1 = turnkey HTTPS API, 2 = cloud‑specific or beta access, 3 = self‑host only

### Data Sources
* Provider docs & blogs: OpenAI, Anthropic, Google, X.ai (Grok), DeepSeek, Alibaba (Qwen), Meta
* Benchmarks: Artificial Analysis, vellum, openllm, lm‑eval‑harness dashboards, Hugging Face leaderboards
* Sentiment: Reddit (Pushshift, ≥ 10 upvotes), X/Twitter (Tweepy), Y Combinator threads

## Results

### Analysis

### Decision