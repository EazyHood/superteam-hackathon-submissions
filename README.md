# Superteam Hackathon Submissions

Submissions for the **[Create an App on Cookie Chain](https://superteam.fun/earn/listing/create-an-app-on-cookie-chain-app/)** bounty on Superteam Earn, sponsored by [Cookie Chain](https://www.cookiechain.wtf/).

## The Bounty

| | |
| --- | --- |
| **Sponsor** | Cookie Chain |
| **Prize pool** | $1,000 USDC — 2 × $500 USDC (1st and 2nd place) |
| **Winners announced** | September 28, 2026 |
| **Scope** | Build an app on Cookie Chain — frontend, backend, and/or on-chain |
| **Listing** | https://superteam.fun/earn/listing/create-an-app-on-cookie-chain-app/ |

Cookie Chain is a Solana-fork L1 with native token **COOK**. Useful endpoints for builders:

```txt
RPC      https://rpc.cookiescan.io
Explorer https://cookiescan.io
```

Questions about the bounty go through the Cookie Chain Telegram and Discord linked on the Superteam listing.

## What This Repo Is

This repo is the record of everything submitted to the bounty. Each entry is captured in `apps.json` with its logo in `logos/`, so submissions can be reviewed side by side and the winners can be promoted straight into the public [Cookie Chain Apps Registry](https://github.com/cookiechain/apps).

```txt
.
├── apps.json   # one object per submission
└── logos/      # logo assets referenced by apps.json
```

## Entry Format

```json
{
  "title": "Cookie MCP",
  "description": "An MCP server that gives AI agents full onchain access to Cookie Chain — trade, launch, LP, stake, and bridge.",
  "tag": "Infra",
  "href": "https://github.com/cookiechain/cookie-mcp",
  "x": "https://x.com/TheCookieChain",
  "github": "https://github.com/cookiechain/cookie-mcp",
  "logo": "https://raw.githubusercontent.com/cookiechain/apps/main/logos/cookie-mcp.png",
  "live": true
}
```

| Field | Notes |
| --- | --- |
| `title` | Project name |
| `description` | One sentence, plain language |
| `tag` | One of `DeFi`, `Wallet`, `Infra`, `NFT`, `Meme` |
| `href` | Public URL of the live app |
| `x` | X (Twitter) profile of the project |
| `github` | Source repository for the submission — public, and containing the code you actually built |
| `logo` | Raw GitHub URL to the file added under `logos/` |
| `live` | `true` if the app is deployed and usable, `false` if not yet |

Logos may be PNG, JPG, JPEG, SVG, or WEBP. Keep them square and reasonably small — 512×512 is plenty:

```bash
magick in.png -resize 512x512 -strip -define png:compression-level=9 logos/myapp.png
```

## Submitting

Submitting here does **not** enter you into the bounty on its own — the official submission still goes through the Superteam Earn listing. Use this repo so the app is catalogued alongside the rest.

1. Fork this repository.
2. Add your logo to `logos/`.
3. Append your entry to `apps.json`.
4. Open a Pull Request titled with your project name.

Validate before opening the PR:

```bash
jq empty apps.json && jq 'length' apps.json
```

## Review Criteria

Submissions are expected to:

* Run on Cookie Chain (mainnet or a clearly documented testnet deployment).
* Have a working public URL, not just a repo.
* Point `github` at a public repo with the real source, with commits from the hackathon period.
* Ship something usable, not a landing page or a mockup.
* Include a clear description and an appropriate category.
* Include a logo asset.

Spam, forks with no meaningful changes, and misleading submissions are rejected.

## Reading the Data

```txt
https://raw.githubusercontent.com/cookiechain/superteam-hackathon-submissions/main/apps.json
```

```javascript
const submissions = await fetch(
  "https://raw.githubusercontent.com/cookiechain/superteam-hackathon-submissions/main/apps.json"
).then((res) => res.json());
```

Same shape as the [Cookie Chain Apps Registry](https://github.com/cookiechain/apps) plus the extra `github` field, so anything that renders that one renders this too — it just ignores the repo link.

---

Built by builders.
Maintained by degens.
Powered by cookies. 🍪
