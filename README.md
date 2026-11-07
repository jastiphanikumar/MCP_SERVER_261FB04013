# Hello MCP

NAME: Jasti Phani Kumar
REG NO: 261FB04013

A small Python Model Context Protocol (MCP) server that exposes greeting, arithmetic, and numeric-summary tools.

## Requirements

- Python 3.10 or newer
- The MCP Python SDK (`mcp`)

## Setup

From the project directory, create and activate a virtual environment, then install the SDK.

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install mcp
```

If PowerShell prevents virtual-environment activation, run the commands using the interpreter directly instead:

```powershell
.\.venv\Scripts\python.exe -m pip install mcp
```

## Run the server

Run it directly with Python:

```powershell
.\.venv\Scripts\python.exe server.py
```

The server uses the MCP stdio transport. MCP hosts normally start it for you; the included `.vscode/mcp.json` config registers it in VS Code as `helloMcp` and launches `server.py` with the project virtual environment.

## Tools

### `get_greeting`

Returns a greeting for the supplied name.

- Input: `name` (string)
- Example: `{"name": "Students"}`
- Result: `Hello, Students! Your first MCP tool works.`

### `add_numbers`

Adds two integers.

- Inputs: `a` (integer), `b` (integer)
- Example: `{"a": 10, "b": 20}`
- Result: `30`

### `analyze_data`

Returns summary statistics for a list of numbers.

- Input: `numbers` (list of numbers)
- For a non-empty list, returns `status`, `count`, `min`, `max`, and `average` (rounded to two decimal places).
- For an empty list, returns `status: "error"` and a message explaining that analysis cannot be performed.
- Example: `{"numbers": [2, 4, 6]}` returns a successful summary with count `3`, minimum `2`, maximum `6`, and average `4.0`.
