# neptune-contracts

NeptuneKit v2 统一日志契约仓库。

## Contents
- `openapi/openapi.yaml`: v2 主契约
- `schemas/`: JSON Schema 验证定义
- `fixtures/`: 跨仓测试样例
- `compatibility-matrix.md`: 版本兼容矩阵

## Scope
- 仅承载 contracts，不放业务实现。
- 供 gateway、SDK、Inspector、macOS App 共同引用。

## CI
- GitHub Actions 会在 `push(main)` 和 `pull_request` 上校验 `openapi/openapi.yaml` 的 YAML 语法。
- 同时会解析 `fixtures/*.json` 的 JSON 语法，以及 `fixtures/*.ndjson` 的逐行 JSON 语法。
