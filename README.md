<div align="center">

<img src="assets/cover.png" alt="Google Search Console through HeyMetra's MCP server" width="100%">

# Google Search Console &times; HeyMetra

**The queries you rank for, with their clicks, CTR and position.**

Google Search Console knows what people did. It does not know what it cost, or what it earned. Connect it beside the accounts that do.

[![MCP Registry](https://img.shields.io/badge/MCP_Registry-com.heymetra%2Fheymetra-1f6feb)](https://registry.modelcontextprotocol.io/v0/servers/com.heymetra%2Fheymetra/versions)
[![Transport](https://img.shields.io/badge/transport-Streamable_HTTP-444)](https://modelcontextprotocol.io/)
[![Auth](https://img.shields.io/badge/auth-OAuth_2.1-444)](https://heymetra.com/security/)
[![Connector page](https://img.shields.io/badge/heymetra.com-google-search-console-1f6feb)](https://heymetra.com/connectors/google-search-console/)

```
https://mcp.heymetra.com/mcp
```

</div>

---

## Ask it things like

> Which queries brought the most impressions last month, and how many clicks did each get?

> Where are impressions high and clicks low?

> How did clicks and average position move over the last 30 days?

> Did impressions fall this month compared with last month?

No dashboard, no export, no query language. You ask in the assistant you already use and the answer comes back with the account it came from.

## Connect Google Search Console

**1. Check which Google account owns the property**

Open search.google.com/search-console and look at the property list. Connect with the account you see it in — not a personal account that happens to be signed in, and not the agency account unless the property is listed there too.

> Search Console permissions are per property, not per domain. Being an owner of example.com says nothing about shop.example.com.

**2. Choose Google Search Console in HeyMetra**

On the Connections screen. There is nothing to copy and no key to generate: this connector uses Google's own sign-in.

**3. Sign in on Google's screen and grant read access**

Your password stays with Google; HeyMetra receives a token you can revoke at any time from your Google account. The permission asked for is read-only — nothing here submits a sitemap, removes a URL or changes a setting.

> If Google offers an account picker, the account you pick is the one whose properties HeyMetra can see. Picking the wrong one shows an empty list on the next step rather than an error.

**4. Pick the property**

HeyMetra lists what that Google account can read. A domain property (sc-domain:example.com) covers every subdomain and both http and https; a URL-prefix property covers exactly the address it names. Pick the one whose figures you recognise.

**5. Add HeyMetra to the assistant you use**

Claude, ChatGPT, Cursor or Codex — HeyMetra gives you the address and the key to paste. The Search Console tools appear there and answer from the live property.

## Then add HeyMetra to your assistant

Add HeyMetra once and it is there in every conversation. The address is the same everywhere:

```
https://mcp.heymetra.com/mcp
```

### One command

```bash
npx add-mcp https://mcp.heymetra.com/mcp
```

[`add-mcp`](https://www.npmjs.com/package/add-mcp) is a third-party installer that writes the configuration for Claude Code, Codex, Cursor, Antigravity, VS Code and seventeen other agents. It infers the name from the address, so the server lands as `heymetra`. Run against this endpoint before it was written here.

### Or by hand

<details>
<summary><b>Claude</b> — Settings → Customize → Connectors → Add custom connector</summary>

Paste the address above into Settings → Customize → Connectors → Add custom connector.

_On Team and Enterprise plans only an owner can add it, under Organization settings._

Full walkthrough: [heymetra.com/mcp/claude/](https://heymetra.com/mcp/claude/)
</details>

<details>
<summary><b>ChatGPT</b> — Settings → Security and login → Developer mode, then chatgpt.com/plugins</summary>

Paste the address above into Settings → Security and login → Developer mode, then chatgpt.com/plugins.

_The endpoint has to include its /mcp path here._

Full walkthrough: [heymetra.com/mcp/chatgpt/](https://heymetra.com/mcp/chatgpt/)
</details>

<details>
<summary><b>Grok</b> — grok.com/connectors → New Connector → Custom</summary>

Paste the address above into grok.com/connectors → New Connector → Custom.

_XAI calls this “bring your own MCP”._

Full walkthrough: [heymetra.com/mcp/grok/](https://heymetra.com/mcp/grok/)
</details>

<details>
<summary><b>Perplexity</b> — Settings → Connectors → Custom connector → Remote</summary>

Paste the address above into Settings → Connectors → Custom connector → Remote.

_Perplexity documents it as a Pro, Max and Enterprise feature._

Full walkthrough: [heymetra.com/mcp/perplexity/](https://heymetra.com/mcp/perplexity/)
</details>

<details>
<summary><b>Claude Code</b> — claude mcp add --transport http</summary>

```bash
claude mcp add --transport http heymetra https://mcp.heymetra.com/mcp
```

_Or a .mcp.json in the project root; /mcp inside a session shows what connected._

Full walkthrough: [heymetra.com/mcp/claude-code/](https://heymetra.com/mcp/claude-code/)
</details>

<details>
<summary><b>Codex</b> — ~/.codex/config.toml</summary>

```toml
[mcp_servers.heymetra]
url = "https://mcp.heymetra.com/mcp"
```

_Under an [mcp_servers.<name>] section, then codex mcp login._

Full walkthrough: [heymetra.com/mcp/codex/](https://heymetra.com/mcp/codex/)
</details>

<details>
<summary><b>Cursor</b> — ~/.cursor/mcp.json, or .cursor/mcp.json in a project</summary>

```json
{
  "mcpServers": {
    "heymetra": { "url": "https://mcp.heymetra.com/mcp" }
  }
}
```

_Leave the static OAuth fields empty — they exist for servers that cannot register themselves._

Full walkthrough: [heymetra.com/mcp/cursor/](https://heymetra.com/mcp/cursor/)
</details>

<details>
<summary><b>Antigravity</b> — ~/.gemini/config/mcp_config.json, or .agents/mcp_config.json in a project</summary>

```json
{
  "mcpServers": {
    "heymetra": { "serverUrl": "https://mcp.heymetra.com/mcp" }
  }
}
```

_The key is serverUrl, not url — the one every other JSON client spells differently._

Full walkthrough: [heymetra.com/mcp/antigravity/](https://heymetra.com/mcp/antigravity/)
</details>

## What it may and may not touch

Google Search Console is a read-only source — HeyMetra reads it to answer questions and never changes the account.

Permissions are switched on per connection, and one you leave off is a tool your assistant never sees.

| Permission | What it covers | Changes anything? |
|---|---|---|
| **Included with the connection** | What HeyMetra needs to set the connection up and nothing more. It cannot be switched off on its own — removing the connection is how you withdraw it. | No, read only |
| **Direct API access** | Let your assistant use this account's own API for anything HeyMetra's other operations do not cover. It reads directly, and what comes back is the provider's own answer rather than a figure HeyMetra has checked. It can also propose changes — those are never applied until you approve them, and HeyMetra cannot undo one afterwards — Google keeps about 16 months and deletes the rest. An older period is refused rather than answered as a stretch with no search traffic.; The last two days are still being processed, so a window that reaches them looks like a decline that is not there.; Google leaves rare searches out of query reports entirely, to protect the people who typed them. Measured on a real site: the same month showed 339 impressions by query and 1,244 by page — so these terms do not add up to the site's traffic, and the search performance report is where a total comes from.; Google keeps about 16 months and deletes the rest.; Error and warning COUNTS only. Search Console keeps what they actually say to its own interface, so a report can say a sitemap has three errors and cannot say what they are.; Submitted counts only. Google removed indexed counts from this report and from its API — the field still exists and is always zero — so nothing here says how many submitted pages are indexed.; One page per question, and 2,000 a day per site on a rolling 24-hour window. There is no bulk form — Search Console's page indexing report is in no API — so this explains a specific page rather than surveying a site.. | No, read only |

<details>
<summary>What each permission lets an assistant do, in full</summary>

- Ask this account's own API a question HeyMetra's other operations do not cover. Reads only, and the answer is the provider's own rather than a figure HeyMetra has checked.
</details>

## When something goes wrong

<details>
<summary>The property list is empty after signing in.</summary>

**Why:** That Google account is not verified for any property. Being able to see a site in Analytics, or owning the domain, is not the same permission.

**Fix:** In Search Console, have an existing owner add this account under Settings → Users and permissions. Full or Restricted both work; read access is all HeyMetra asks for.

</details>

<details>
<summary>The site is in the list twice, with different numbers in each.</summary>

**Why:** A domain property and a URL-prefix property for the same site are two different properties and count different traffic — the domain one includes subdomains and the other protocol.

**Fix:** Connect the one whose figures match what you report on. They are not two views of one number and must never be added together.

</details>

<details>
<summary>Asking about the last two days returns nothing, or a drop.</summary>

**Why:** Google finishes processing search data about two days behind, and HeyMetra asks only for finished data rather than serving a partial day as a fall.

**Fix:** Ask for a period ending three days ago. Every answer says which days it actually covers.

</details>

<details>
<summary>The queries add up to far less traffic than the site's own total.</summary>

**Why:** Google leaves rare searches out of query reports entirely, to protect the privacy of whoever typed them. On one measured site the same month showed 339 impressions by query against 1,244 by page.

**Fix:** Read the query list as the named part of the traffic, not as all of it. The site total is the figure to compare months by.

</details>

<details>
<summary>A question about backlinks, Core Web Vitals or AI Overviews is refused.</summary>

**Why:** Search Console shows those in its own interface and publishes no API for them. Nothing can read them on your behalf.

**Fix:** Those stay in Search Console itself for now. HeyMetra refuses them rather than answering from something adjacent and calling it the same thing.

</details>

## What HeyMetra reads from Google Search Console

Connect the property once and your MCP client gets four Search Console tools: clicks, impressions, CTR and impression-weighted average position for a period, with a day-by-day series; the queries with the most impressions, each carrying its own clicks, CTR and position; which sitemaps you submitted and whether Google still reads them; and what Google says about one page you name — whether it is indexed, when it was last crawled, and what links to it. Search Console is read-only here: no tool submits a sitemap, removes a URL or changes a setting on your property.

<details>
<summary>About Google Search Console</summary>

Google Search Console reports how your site performs in Google’s organic search results — the queries you rank for, your clicks and impressions, and indexing health. It’s the ground truth for SEO.
</details>

## One connection, not seven

The reason to read Google Search Console through HeyMetra rather than through a server that only knows Google Search Console is everything else it can answer in the same breath:

**Ads** — [Google Ads](https://heymetra.com/connectors/google-ads/) · [Meta](https://heymetra.com/connectors/meta-ads/)

**Analytics** — [Google Analytics 4](https://heymetra.com/connectors/google-analytics-4/) · **Google Search Console**

**Ecommerce** — [Shopify](https://heymetra.com/connectors/shopify/) · [Trendyol](https://github.com/zeisoft/trendyol-mcp) · [WooCommerce](https://github.com/zeisoft/woocommerce-mcp)

**Revenue & CRM** — [Stripe](https://heymetra.com/connectors/stripe/) · [HubSpot](https://heymetra.com/connectors/hubspot/) · [Zoho CRM](https://github.com/zeisoft/zoho-crm-mcp) · [Zoho SalesIQ](https://github.com/zeisoft/zoho-salesiq-mcp) · [Zoho Marketing Automation](https://github.com/zeisoft/zoho-marketing-automation-mcp)

**Mobile** — [AppsFlyer](https://github.com/zeisoft/appsflyer-mcp) · [RevenueCat](https://heymetra.com/connectors/revenuecat/) · [Adapty](https://github.com/zeisoft/adapty-mcp) · [App Store Connect](https://github.com/zeisoft/app-store-connect-mcp)

**Channels** — [Slack](https://github.com/zeisoft/slack-mcp) · [Telegram](https://github.com/zeisoft/telegram-mcp)

The full catalogue is at [heymetra.com/connectors/](https://heymetra.com/connectors/).

## Links

- [Google Search Console connector page](https://heymetra.com/connectors/google-search-console/)
- [HeyMetra](https://heymetra.com/) — what the product is
- [Setup for every assistant](https://heymetra.com/mcp/)
- [Security and limits](https://heymetra.com/security/)
- [Pricing](https://heymetra.com/pricing/)
- [HeyMetra's own repository](https://github.com/zeisoft/heymetra-mcp)

---

<sub>Built by <a href="https://zeisoft.com">Zeisoft</a>, who make HeyMetra. Not affiliated with Google Search Console. This README is generated from HeyMetra's live connector catalogue and refreshed daily; corrections are welcome as issues.</sub>
