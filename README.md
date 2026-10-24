# NanoLM — Inspectable Transformer Sandbox

Tiny Transformer language model that runs entirely in the browser.

## Files

- **`nanolm_true_backprop.html`** — Recommended. Full analytical backpropagation through attention heads (Q/K/V + softmax), MLP, embeddings and positional encodings. Includes GradCheck (central difference) that compares analytical vs numerical gradients on multiple parameters.
- `nanolm_analitico.html` — Previous analytical attempt.
- `index.html` — Earlier partial version (kept for reference).

## How to use

1. Open `nanolm_true_backprop.html` in a modern browser.
2. Click **Inicializar**.
3. Train a few epochs.
4. Click **GradCheck** to verify gradients (expect mostly PASS).
5. Generate tokens.

## Limitations

- Extremely small (D=16, 2 heads). Only memorizes local patterns from the training text.
- Log is SHA-256 chained and verifiable **only within the browser session**.
- Educational sandbox, not a production model.

## License

MIT.
