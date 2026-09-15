# Pageree for Gemini CLI

<img src="assets/logo.svg" alt="Pageree" width="64" height="64">

Build and run landing pages from Gemini CLI. Pageree provides hosted previews, publishing, lead capture, and page analytics through a remote MCP connection.

Connect Gemini CLI to Pageree using the extension below. Gallery discovery is tracked in [RELEASE.md](RELEASE.md).

## Requirements

- [Gemini CLI](https://geminicli.com/docs/get-started/installation/) installed and authenticated.
- A [Pageree account](https://console.pageree.com/signup).
- Internet access to `https://mcp.pageree.com/`.

Pageree hosts the MCP service. There are no extension dependencies to install and no API key to copy. Pageree service usage is subject to your account plan.

## Install

Run in your terminal:

```sh
gemini extensions install https://github.com/Pageree/gemini-extension
gemini extensions list
```

### Install from a local checkout

From this directory, run in your terminal:

```sh
gemini extensions install .
```

Review the installation prompt and confirm that the extension connects to `https://mcp.pageree.com/`. Restart any existing Gemini CLI session after installation, or start one with:

```sh
gemini
```

Inside the interactive Gemini CLI session:

```text
/extensions list
/mcp list
/mcp auth pageree
```

Sign in to Pageree in the browser and review the access request. Approve it if you want Gemini CLI to use Pageree on your behalf. Return to the terminal and run `/mcp list` to check the connection.

The manifest uses `httpUrl` to select Streamable HTTP. Gemini discovers Pageree's OAuth settings automatically. The endpoint ends at `/`; do not append `/mcp` or `/sse`.

## Verify the connection

Ask Gemini:

> Use Pageree to call whoami and list_pages. Do not create, change, or publish anything.

Confirm that the account is correct and both calls succeed. A new account can have an empty page list. Restart Gemini and repeat the check to verify that the connection survives a new session.

## Example prompts

**Create a draft**

> Use Pageree to create a landing page for my product. Start by asking about the product, audience, and desired action. Show me a draft preview before publishing.

**Publish a reviewed draft**

> Publish the Pageree draft I just approved to the subdomain we chose.

**Improve a page**

> Use Pageree to review my page's analytics and suggest improvements supported by the data. Wait for my approval before editing or publishing.

Pageree delivers its page-building guidance through MCP tools. Publishing makes a page public, so review the preview and confirm the destination before asking the agent to publish.

## Troubleshooting

| Problem | Next step |
| --- | --- |
| `gemini` command is missing | Install Gemini CLI using its official installation guide above. |
| Extension is missing | Run `gemini extensions list` in the terminal, check that `pageree` is enabled, and restart the interactive session. |
| Authentication is required | Run `/mcp auth pageree` inside Gemini and finish the browser flow. |
| Server uses unexpected settings | Check for an existing `mcpServers.pageree` entry in your Gemini settings; settings take precedence over extension configuration. Preserve unrelated servers. |
| No connection | Check internet access and the exact root endpoint, then inspect `/mcp list` for the error. |

## Remove the extension

Exit Gemini, then run:

```sh
gemini extensions uninstall pageree
```

Removing the extension does not delete your hosted Pageree pages.

## Package contents

- `gemini-extension.json` — extension metadata and hosted MCP connection.
- `assets/logo.svg` — Pageree logo used in this README.
- `RELEASE.md` — testing and gallery publication checklist.

This package contains no executable hooks, server runtime, or credentials. Tool requests go to the hosted Pageree service. Gemini manages OAuth credentials outside this package.

## Links

- [Pageree setup documentation](https://pageree.com/docs#gemini-cli)
- [Pageree dashboard](https://console.pageree.com/)
- [Privacy](https://pageree.com/privacy) · [Terms](https://pageree.com/terms)
- [Gemini extension reference](https://geminicli.com/docs/extensions/reference/)
- [Gemini MCP authentication](https://geminicli.com/docs/tools/mcp-server/)
- Support: [support@pageree.com](mailto:support@pageree.com)
