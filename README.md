# NanoLM — Inspectable Transformer Sandbox

Tiny, fully inspectable Transformer language model running entirely in the browser.

## What it is

An educational NanoLM (extremely small Transformer) with:

- Multi-head causal attention (visualized as heatmaps)
- Residual stream magnitude visualization
- Temperature + Top-K sampling
- Provenance / epistemic audit panel (attention vs parametric vs stochastic)
- SHA-256 chained session log
- Gradient check (central difference)

## How to use

1. Open `index.html` in any modern browser (or serve the folder locally).
2. Edit the training corpus and click **Inicializar Pesos**.
3. Train for a few epochs and watch the loss.
4. Generate tokens and observe the attention matrices, residual norms, and audit panel in real time.

## Honest limitations

- Extremely small (embedding dimension 16, 2 heads).
- Analytical gradients for embeddings, MLP and output layer. Full analytical backpropagation through the attention heads (softmax + Q/K/V) is still approximated.
- The model only memorizes local patterns from the tiny text you train it on.
- The SHA-256 log chain is verifiable within the browser session but is not an immutable external record.

Built as a practical tool to look inside a real (tiny) Transformer instead of only reading explanations about them.

## Files

- `index.html` — Main sandbox (open this in the browser)

## License

MIT. Free to use, modify and share for learning and experimentation.
