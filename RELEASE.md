# Gemini CLI release checklist

## Current status

Local preparation only. No GitHub repository has been created, no remote has been configured, and no gallery publication has been triggered for this extension.

Suggested repository: `Pageree/gemini-extension`. The owner will create or choose the repository before publication.

### Validation record — 2026-09-15

- Passed: JSON parsing, manifest fields, name/version format, Streamable HTTP configuration, exact production endpoint, and documented authentication/test commands.
- Passed: SVG XML validation and consistency with the existing Pageree logo.
- Confirmed: no local Git repository or remote configured.
- Pending: Gemini CLI installation, extension loading, OAuth, and authenticated tool calls. The `gemini` command was unavailable in the local shell during preparation.

## Connection test

- [ ] Install a current Gemini CLI and record `gemini --version`.
- [ ] Install this local directory with `gemini extensions install .`.
- [ ] Confirm `pageree` appears in `gemini extensions list`.
- [ ] Start Gemini and authenticate using `/mcp auth pageree`.
- [ ] Confirm `/mcp list` shows connected Pageree tools.
- [ ] Call `whoami` and `list_pages`; verify the intended account and successful results.
- [ ] Restart Gemini and repeat the read-only tool calls.

Use a test account. The verification prompt in the README requests no changes or publishing. Record results without tokens, authorization codes, or account data. Static validation does not establish that OAuth or tool calls work in Gemini.

## Publish after owner approval

1. Create or select the public GitHub repository and push the tested package with `gemini-extension.json` at its root.
2. Update the README status and add the install command using the actual repository URL: `gemini extensions install https://github.com/OWNER/REPOSITORY`.
3. Test installation from that URL.
4. When ready for public discovery, add the GitHub topic `gemini-cli-extension`.
5. Check the [Gemini CLI gallery](https://geminicli.com/extensions/) after indexing; record the actual listing URL before marking it live.

The [official release guide](https://geminicli.com/docs/extensions/releasing/#list-your-extension-in-the-gallery) says the gallery discovers tagged public repositories daily and lists extensions that pass validation. There is no submission form. Adding the topic is the publication trigger; leave it off until ready.

## Suggested repository metadata

- Description: Build, preview, publish, and improve landing pages from Gemini CLI using Pageree's hosted MCP server.
- Website: https://pageree.com/docs#gemini-cli
- Gallery topic, only when ready: `gemini-cli-extension`

The logo is included for documentation and reusable listing assets; this manifest does not declare an undocumented logo field.
