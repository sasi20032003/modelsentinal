# Limitations

- **Synthetic-only training data:** The ML meta-classifier is trained exclusively on synthetic anomalies.
- **Topological Constraints:** The Topological Attention Scanner currently relies on standard HuggingFace naming conventions (e.g., `q_proj`, `k_proj`, `Wq`, `Wk`) to pair matrices. Architectures with non-standard tensor names may not be topologically scanned.
- **No protection against adaptive white-box adversaries:** An attacker with full access to our scoring weights and topological thresholds can mathematically optimize a payload to bypass our heuristics (e.g., spreading the trigger over multiple singular vectors to bypass BBP and Cosine Similarity thresholds).
- **No quantized format support:** Currently lacks GGUF, AWQ, and GPTQ parsing. Quantization fundamentally breaks RMT assumptions because of the discrete steps, requiring a completely separate statistical regime.
- **Research-grade:** Not yet enterprise-validated. Use at your own risk.
