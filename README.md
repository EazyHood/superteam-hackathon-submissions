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

This repo is the record of everything submitted to the bounty. Each entry is captured in `apps.json` with its logo in `logos/`, so submissions can be reviewed side by side and the winners can be carried over into the public [Cookie Chain Apps Registry](https://github.com/cookiechain/apps).

```txt
.
├── apps.json      # one object per submission
├── logos/         # logo assets referenced by apps.json
└── screenshots/   # screenshot and banner assets, one subfolder per submission
```

## Entry Format

Each submission is one object in `apps.json`. `null` and `[]` are fine for anything you don't have — leave the key in place rather than omitting it.

```json
{
  "id": "cookie-mcp",
  "title": "Cookie MCP",
  "shortDescription": "The onchain execution layer for AI agents on Cookie Chain.",
  "description": "Cookie MCP is a Model Context Protocol server that enables AI agents to interact directly with Cookie Chain. Agents can execute swaps, launch tokens, provide liquidity, stake assets, bridge tokens, inspect balances, and interact with supported DeFi protocols through a unified interface.",
  "category": "Infrastructure",
  "tags": ["AI", "MCP", "Infrastructure", "DeFi"],
  "links": {
    "website": "https://cookiechain.wtf",
    "demo": "https://cookiechain.wtf",
    "github": "https://github.com/cookiechain/cookie-mcp",
    "x": "https://x.com/TheCookieChain",
    "docs": "https://github.com/cookiechain/cookie-mcp/blob/main/README.md",
    "video": "https://raw.githubusercontent.com/cookiechain/cookie-mcp/main/docs/demo.gif"
  },
  "media": {
    "logo": "https://raw.githubusercontent.com/cookiechain/superteam-hackathon-submissions/main/logos/cookie-mcp.png",
    "banner": "https://x.com/TheCookieChain/header_photo",
    "screenshots": []
  },
  "team": [
    {
      "name": "Alex",
      "role": "Developer",
      "x": "https://x.com/fibanachos",
      "github": "https://github.com/fibanachos"
    }
  ]
}
```

### Fields

| Field | Required | Notes |
| --- | --- | --- |
| `id` | yes | Lowercase kebab-case slug, unique in the file. Use it for your logo filename too. |
| `title` | yes | Project name as you want it displayed |
| `shortDescription` | yes | One line for cards and list views |
| `description` | yes | A paragraph: what it does, and what it does *on Cookie Chain* |
| `category` | yes | Single primary category, e.g. `DeFi`, `Infrastructure`, `Wallet`, `NFT`, `Gaming`, `Tooling`, `Social`. Reuse a value already in the file if one fits. |
| `tags` | yes | Array of free-form keywords for filtering. Repeating the category here is fine. |
| `links.website` | yes | The live app |
| `links.demo` | — | Hosted demo, if it differs from the website |
| `links.github` | yes | Public source repo containing the code you actually built |
| `links.x` | — | Project or builder X account |
| `links.docs` | — | Documentation |
| `links.video` | — | Demo walkthrough — the single most useful thing for a reviewer if the app needs setup |
| `media.logo` | yes | Raw GitHub URL to the file you added under `logos/` |
| `media.banner` | — | Wide header image, committed under `screenshots/<id>/` |
| `media.screenshots` | — | Array of raw GitHub URLs — see [Screenshots](#screenshots) |
| `team[].name` | yes | One object per team member |
| `team[].role` | — | e.g. `Developer`, `Design` |
| `team[].x`, `team[].github` | — | Per-member profiles |

### Logos

Put the file in `logos/`, named after your `id`. PNG, JPG, JPEG, SVG, or WEBP; square, and 512×512 is plenty:

```bash
magick in.png -resize 512x512 -strip -define png:compression-level=9 logos/my-app.png
```

Then reference it by raw URL:

```txt
https://raw.githubusercontent.com/cookiechain/superteam-hackathon-submissions/main/logos/<id>.png
```

### Screenshots

Screenshots and banners go in their own subfolder under `screenshots/`, named after your `id`:

```txt
screenshots/
└── cookie-mcp/
    ├── banner.png
    ├── 01-agent-swap.png
    └── 02-token-launch.png
```

Reference them by raw URL, the same as the logo:

```json
"media": {
  "logo": "https://raw.githubusercontent.com/cookiechain/superteam-hackathon-submissions/main/logos/cookie-mcp.png",
  "banner": "https://raw.githubusercontent.com/cookiechain/superteam-hackathon-submissions/main/screenshots/cookie-mcp/banner.png",
  "screenshots": [
    "https://raw.githubusercontent.com/cookiechain/superteam-hackathon-submissions/main/screenshots/cookie-mcp/01-agent-swap.png",
    "https://raw.githubusercontent.com/cookiechain/superteam-hackathon-submissions/main/screenshots/cookie-mcp/02-token-launch.png"
  ]
}
```

Number them so they display in a sensible order. Keep each under ~1 MB — resize wide images to 1600px:

```bash
magick shot.png -resize 1600x -strip -define png:compression-level=9 screenshots/<id>/01-name.png
```

> **All media must be committed to this repo.** `logo`, `banner`, and every entry in `screenshots` must be a
> `raw.githubusercontent.com/cookiechain/superteam-hackathon-submissions/main/...` URL pointing at a file you
> added under `logos/` or `screenshots/`. Hotlinking to X, Imgur, IPFS, or your own host is not accepted —
> those links rot, change behind our backs, and several are not image endpoints at all. Anything you can't
> host here yet should be `null` or `[]`.

## Submitting

Submitting here does **not** enter you into the bounty on its own — the official submission still goes through the Superteam Earn listing. Use this repo so the app is catalogued alongside the rest.

1. Fork this repository.
2. Add your logo to `logos/`, named after your `id`, and any screenshots to `screenshots/<id>/`.
3. Append your entry to `apps.json`.
4. Open a Pull Request titled with your project name.

Validate before opening the PR — valid JSON, no duplicate `id`, no externally hosted media, and every referenced file actually present:

```bash
jq empty apps.json
jq -r '[.[].id] | group_by(.) | map(select(length > 1) | .[0]) | join(", ")' apps.json
PREFIX=https://raw.githubusercontent.com/cookiechain/superteam-hackathon-submissions/main/
jq -r --arg p "$PREFIX" '.[].media | [.logo, .banner] + .screenshots | .[] | select(. != null)
   | select(startswith($p) | not)' apps.json          # must print nothing: no external media
jq -r --arg p "$PREFIX" '.[].media | [.logo, .banner] + .screenshots | .[] | select(. != null)
   | sub($p; "")' apps.json | xargs ls                 # every referenced file exists
```

## Review Criteria

Submissions are expected to:

* Run on Cookie Chain (mainnet or a clearly documented testnet deployment).
* Have a working public URL, not just a repo.
* Point `links.github` at a public repo with the real source, with commits from the hackathon period.
* Ship something usable, not a landing page or a mockup.
* Fill in `shortDescription`, `description`, and an appropriate `category`.
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

This is a richer schema than the [Cookie Chain Apps Registry](https://github.com/cookiechain/apps), which uses a flat `title`/`description`/`tag`/`href`/`logo`/`live` shape. Promoting a winner into the registry means flattening the entry — `links.website` becomes `href`, `media.logo` becomes `logo`, `category` becomes `tag`.

---

Built by builders.
Maintained by degens.
Powered by cookies. 🍪
