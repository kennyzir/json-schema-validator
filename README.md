# "JSON Schema Validator"

> Validate JSON data against a JSON Schema. Use when agents need to verify API responses, validate pipeline data, check CI quality gates, or ensure config files match expected structure. Returns detailed error paths.

[![License: MIT-0](https://img.shields.io/badge/License-MIT--0-blue.svg)](LICENSE)
[![Claw0x](https://img.shields.io/badge/Powered%20by-Claw0x-orange)](https://claw0x.com)
[![OpenClaw Compatible](https://img.shields.io/badge/OpenClaw-Compatible-green)](https://openclaw.org)

## What is This?

This is a native skill for **OpenClaw** and other AI agents. Skills are modular capabilities that agents can install and use instantly - no complex API setup, no managing multiple provider keys.

Built for OpenClaw, compatible with Claude, GPT-4, and other agent frameworks.

## Installation

### For OpenClaw Users

Simply tell your agent:

```
Install the ""JSON Schema Validator"" skill from Claw0x
```

Or use this connection prompt:

```
Add skill: json-schema-validator
Platform: Claw0x
Get your API key at: https://claw0x.com
```

### For Other Agents (Claude, GPT-4, etc.)

1. Get your free API key at [claw0x.com](https://claw0x.com) (no credit card required)
2. Add to your agent's configuration:
   - Skill name: `json-schema-validator`
   - Endpoint: `https://claw0x.com/v1/call`
   - Auth: Bearer token with your Claw0x API key

### Via CLI

```bash
npx @claw0x/cli add json-schema-validator
```

---


# JSON Schema Validator

Validate any JSON data against a JSON Schema definition. Returns whether the data is valid and detailed error paths for every violation.

Supports: type checking, required fields, enum, const, minLength/maxLength, pattern, minimum/maximum, multipleOf, nested objects, arrays (minItems/maxItems/uniqueItems), additionalProperties.

## Use Cases

- API response validation (verify shape before processing)
- Data pipeline quality gates (reject malformed records)
- Config file validation (ensure correct structure)
- CI/CD checks (validate JSON artifacts)

## Prerequisites

1. **Sign up at [claw0x.com](https://claw0x.com)**
2. **Create API key** in Dashboard

## Pricing

**FREE.** No charge per call.

- Requires Claw0x API key for authentication
- No usage charges (price_per_call = 0)
- Unlimited calls

## Example

**Input**:
```json
{
  "data": {"name": "Alice", "age": "not-a-number"},
  "schema": {
    "type": "object",
    "required": ["name", "age"],
    "properties": {
      "name": {"type": "string"},
      "age": {"type": "number", "minimum": 0}
    }
  }
}
```

**Output**:
```json
{
  "valid": false,
  "errors": [{"path": "$.age", "message": "Expected type number, got string"}],
  "error_count": 1
}
```

## About Claw0x

[Claw0x](https://claw0x.com) is the native skills layer for AI agents.

**GitHub**: [github.com/kennyzir/json-schema-validator](https://github.com/kennyzir/json-schema-validator)


---

## About Claw0x

Claw0x is the native skills layer for AI agents - not just another API marketplace.

**Why Claw0x?**
- **One key, all skills** - Single API key for 50+ production-ready skills
- **Pay only for success** - Failed calls (4xx/5xx) are never charged
- **Built for OpenClaw** - Native integration with the OpenClaw agent framework
- **Zero config** - No upstream API keys to manage, we handle all third-party auth

**For Developers:**
- [Browse all skills](https://claw0x.com/skills)
- [Sell your own skills](https://claw0x.com/docs/sell)
- [API Documentation](https://claw0x.com/docs/api-reference)
- [OpenClaw Integration Guide](https://claw0x.com/docs/openclaw)

## Links

- [Claw0x Platform](https://claw0x.com)
- [OpenClaw Framework](https://openclaw.org)
- [Skill Documentation](https://claw0x.com/skills/json-schema-validator)
