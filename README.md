# neptune-contracts

NeptuneKit v2 统一日志契约仓库。

## Contents
- `openapi/openapi.yaml`: v2 主契约
- `schemas/`: JSON Schema 验证定义
- `fixtures/`: 跨仓测试样例
- `compatibility-matrix.md`: 版本兼容矩阵

## Transport
- HTTP 用于查询与聚合接口：`/v2/logs:ingest`、`/v2/logs`、`/v2/metrics`、`/v2/sources`、`/v2/health`、`/v2/gateway/discovery`
- WS 用于实时总线主通道：`GET /v2/ws`
- 总线消息对象包括：`BusEnvelope`、`BusAck`、`BusTarget`
- `BusEnvelope.direction` 仅允许 `cli_to_client`
- `BusAck.direction` 仅允许 `client_to_cli`
- 旧兼容别名不再保留

## Scope
- 仅承载 contracts，不放业务实现。
- 供 gateway、SDK、Inspector、macOS App 共同引用。

## CI
- GitHub Actions 会在 `push(main)` 和 `pull_request` 上校验 `openapi/openapi.yaml` 的 YAML 语法。
- 同时会解析 `fixtures/*.json` 的 JSON 语法，以及 `fixtures/*.ndjson` 的逐行 JSON 语法。
