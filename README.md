# AlgoRover Research for Gemini CLI

A Gemini CLI extension for strategy discovery and reproducible historical backtests on the hosted AlgoRover Research service.

## Install

```sh
gemini extensions install https://github.com/algorover/algorover-research-gemini
```

The extension connects to `https://research.algorover.ai/mcp` over Streamable HTTP. No local Research engine is required.

Discovery and preparation are public. For personal backtests and reports, use `/mcp auth algorover-research` in Gemini CLI and complete Research sign-in in your browser. The extension requests `research:read` and `research:run`. Deletion requires separately authorized `research:delete` permission.

## Example workflow

1. Find a strategy and inspect its available presets and markets.
2. Preview a 90-day historical backtest.
3. Confirm the preview to start the job.
4. Check progress, inspect results and download the report, or cancel the selected active job.

The extension uses actual tool text and links in text-only clients. Historical results do not establish future returns. Research does not connect exchange accounts or execute orders.

## Validation

Installed using Gemini CLI 0.69.0; the MCP connection was verified. Public strategy discovery was also verified with the official MCP SDK. End-to-end Gemini OAuth, backtest and report flows remain under validation.

Published by Rivendell Holdings Investment Limited. Research version 0.1.5.

- [Research](https://research.algorover.ai/)
- [Support](https://www.algorover.ai/en/help/)
- [Privacy](https://www.algorover.ai/privacy/)
- [Terms](https://www.algorover.ai/terms/)
