# NanoLM — Inspectable Transformer Sandbox

Tiny Transformer language model that runs entirely in the browser, with visualizations of attention, residual stream, and a session audit log.

## Files

- **`nanolm_analitico.html`** — Recommended version. Implements **analytical backpropagation** through the attention heads (Q, K, V and softmax), MLP, embeddings and positional encodings. Includes GradCheck with central differences that compares analytical vs numerical gradients.
- `index.html` — Earlier version with partial training (output layer only). Kept for reference.

## How to use

1. Open `nanolm_analitico.html` in any modern browser.
2. Edit the training corpus and click **Inicializar pesos**.
3. Train for a few epochs and watch the loss.
4. Use **GradCheck** to verify that analytical gradients match numerical ones.
5. Generate tokens and observe the attention matrices and residual norms.

## Honest limitations

- Extremely small (embedding dimension 16, 2 heads). It only memorizes local patterns from the tiny text you train it on.
- The analytical version correctly propagates gradients through attention, but the model remains a tiny educational sandbox, not a production system.
- The SHA-256 log chain is verifiable within the browser session. It is **not** persistent or authenticated outside the page.

## License

MIT. Free to use, modify and share for learning and experimentation.
