# Gemini CLI release checklist

## Current status

Published to [Pageree/gemini-extension](https://github.com/Pageree/gemini-extension) on 2026-09-15. The repository is public, uses `main`, and has the `gemini-cli-extension` topic required for gallery discovery. Gallery indexing and acceptance are pending confirmation.

### Validation record — 2026-09-15

- Passed: JSON parsing, manifest fields, name/version format, Streamable HTTP configuration, exact production endpoint, and documented authentication/test commands.
- Passed: SVG XML validation and consistency with the existing Pageree logo.
- Passed: installation from the public GitHub URL using Google's official standalone Gemini CLI 0.59.0 release in an isolated temporary profile.
- Passed: `gemini extensions list` reports Pageree 1.0.0 enabled and includes its `pageree` MCP server.
- Observed: `gemini mcp list` recognizes `https://mcp.pageree.com/` as HTTP and reports Disconnected in the unauthenticated profile. This does not establish a successful authenticated connection.
- Pending: OAuth authorization, authenticated tool calls, and reconnect verification. No end-to-end Gemini connection test is claimed.

## Connection test

- [x] Run a current Gemini CLI and record `gemini --version`: 0.59.0.
- [x] Install the extension from its public GitHub repository.
- [x] Confirm `pageree` appears in `gemini extensions list`.
- [ ] Start Gemini and authenticate using `/mcp auth pageree`.
- [ ] Confirm `/mcp list` shows connected Pageree tools.
- [ ] Call `whoami` and `list_pages`; verify the intended account and successful results.
- [ ] Restart Gemini and repeat the read-only tool calls.

Use a test account. The verification prompt in the README requests no changes or publishing. Record results without tokens, authorization codes, or account data. Static validation does not establish that OAuth or tool calls work in Gemini.

## Gallery submission

- [x] Create a public repository with `gemini-extension.json` at its root.
- [x] Document and test installation from the public repository URL.
- [x] Add the GitHub topic `gemini-cli-extension` with owner authorization.
- [ ] Confirm the entry in the [Gemini CLI gallery](https://geminicli.com/extensions/) after indexing and record its actual listing URL.

The [official release guide](https://geminicli.com/docs/extensions/releasing/#list-your-extension-in-the-gallery) says the gallery discovers tagged public repositories daily and lists extensions that pass validation. There is no submission form. The required topic is now set; this is not confirmation of a live gallery listing.

## Repository metadata

- Description: Build, preview, publish, and improve landing pages from Gemini CLI using Pageree's hosted MCP server.
- Website: https://pageree.com/docs#gemini-cli
- Gallery topic: `gemini-cli-extension`

The logo is included for documentation and reusable listing assets; this manifest does not declare an undocumented logo field.
