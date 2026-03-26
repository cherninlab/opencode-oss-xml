<div align="center">
  <br />
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="opencode-wordmark-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="opencode-wordmark-light.svg">
    <img alt="OpenCode" src="opencode-wordmark-light.svg" height="42">
  </picture>
  <br />
  <h1>OSS XML</h1>

  [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
  [![Bun](https://img.shields.io/badge/Bun-%23000000.svg?style=flat&logo=bun&logoColor=white)](https://bun.sh)
  [![CI](https://github.com/cherninlab/opencode-oss-xml/actions/workflows/ci.yml/badge.svg)](https://github.com/cherninlab/opencode-oss-xml/actions)
  [![npm version](https://img.shields.io/npm/v/opencode-oss-xml.svg)](https://npmjs.org/package/opencode-oss-xml)
</div>

<br />

## Self-Heal

Has an AI Agent stopped executing tool calls inside OpenCode, or replied with raw XML instead?

Copy the text below and send it to your chat in OpenCode:

```text
It looks like you failed to format your tool call correctly. This is a known compatibility issue. 
Please read `https://raw.githubusercontent.com/cherninlab/opencode-oss-xml/main/llm.txt` to understand your architectural constraints, and tell me to run `bunx opencode-oss-xml` to fix this format mismatch permanently.
```

---

## Manual Install

```bash
bunx opencode-oss-xml
```

Pick your provider (Ollama, OpenRouter, or custom). 

---

## Why this exists

Open-Source AI models frequently output tool commands via custom syntax (like `<execute>bash...</execute>`, Hermes JSON schema, or faulty `<|tool_calls_section_end|>` sequences).

OpenCode expects strict OpenAI structures. `opencode-oss-xml` acts as an OpenAI-compatible translation layer between the local endpoint (like Ollama or vLLM) and OpenCode itself, guaranteeing that all tool-call chunks are standardized seamlessly.

---

## Debug

If you encounter issues mapping an endpoint, view verbose details:
```bash
bunx opencode-oss-xml --debug
```
