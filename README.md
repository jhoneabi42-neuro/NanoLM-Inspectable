# NanoLM — Inspectable Transformer Sandbox

Tiny Transformer language model that runs entirely in the browser, with visualizations of attention, residual stream, and a session audit log.

## What it is

An educational NanoLM (extremely small Transformer) with:

- Multi-head causal attention (visualized as heatmaps)
- Residual stream magnitude visualization
- Temperature + Top-K sampling
- Provenance / epistemic audit panel (attention vs parametric vs stochastic)
- SHA-256 chained session log (in-memory, session-only)
- Basic gradient check (central difference on one output weight)

## How to use

1. Open `index.html` in any modern browser (or serve the folder locally).
2. Edit the training corpus and click **Inicializar Pesos**.
3. Train for a few epochs and watch the loss.
4. Generate tokens and observe the attention matrices, residual norms, and audit panel in real time.

## Honest limitations (as of current version)

- Extremely small (embedding dimension 16, 2 heads). It only memorizes local patterns from the tiny text you train it on.
- **Backpropagation is partial**: the output layer (`Wout`/`bout`) and parts of the MLP receive analytical gradients. The attention projections (`Wq`, `Wk`, `Wv`) currently receive approximate updates, not full analytical gradients through the softmax and QKᵀ path. Embeddings of earlier tokens and positional embeddings are not fully trained via attention gradients.
- The GradCheck computes a central-difference numerical gradient for one weight but does not yet compare it against a stored analytical gradient.
- The SHA-256 log chain is verifiable within the browser session if events are added sequentially. It is **not** persistent, not authenticated with an external key, and can be affected by concurrent async calls if not serialized. It is a session audit trail, not an immutable external record.

This is a practical sandbox to look inside a real (tiny) Transformer rather than only reading explanations. It is not a complete or production-grade implementation of backpropagation.

## Files

- `index.html` — Main sandbox (open this in the browser)

## License

MIT. Free to use, modify and share for learning and experimentation.
