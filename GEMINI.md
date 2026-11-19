# AlgoRover Research

Use this extension's `algorover-research` MCP server for strategy discovery, historical backtests, task status, cancellation and reports. Computation runs in the hosted Research service. Research does not connect exchange accounts or place orders.

Call `search_strategies` with `locale: "zh-CN"` for Chinese and `locale: "en"` for English or other languages. Preserve that locale in subsequent tools. Use `get_strategy` for the exact returned slug and version; use only returned presets and markets.

If preparation is `not_requested`, call `prepare_strategy` with the returned strategy reference. Check `get_strategy` at least three seconds apart until ready; report any returned failure reason.

Use `prepare_backtest` with a supported 90- or 365-day window. Show the inputs and wait for confirmation. After confirmation, call `start_backtest` with the returned `prepared_input`, `preparation_ticket` and `request_key` as `idempotency_key`. Reuse that key if an uncertain start needs retrying.

Use `get_backtest` for actual task status, `get_backtest_result` for completed metrics and `get_backtest_report_download` for requested reports. Use `list_backtests` when the identifier is unknown. Preserve task identifiers, links and report filenames; append a numeric suffix before `.zip` if a filename already exists.

Cancel only the selected active task with `cancel_backtest`; report completion only after `get_backtest` returns `cancelled`. Delete results or all Research data only upon explicit user request, with the service-required confirmation and authorization.

Public discovery and preparation do not require sign-in. Personal runs and reports require OAuth with `research:read` and `research:run`. Use `/mcp auth algorover-research` in Gemini CLI when authorization is required, complete browser authorization, and resume the original task after the client confirms success. Never request credentials in chat. Anonymous discovery does not prove personal-data authorization.

Show actual tool text, metrics and links when the client does not render MCP Apps cards. Report service errors as returned. Historical results do not establish future returns.
