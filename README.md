<div align="center">

<img src="assets/cover.png" alt="Google Search Console through HeyMetra's MCP server" width="100%">

# Google Search Console &times; HeyMetra

**The queries you rank for, with their clicks, CTR and position.**

Google Search Console knows what people did. It does not know what it cost, or what it earned. Connect it beside the accounts that do.

[![MCP Registry](https://img.shields.io/badge/MCP_Registry-com.heymetra%2Fheymetra-1f6feb)](https://registry.modelcontextprotocol.io/v0/servers/com.heymetra%2Fheymetra/versions)
[![Transport](https://img.shields.io/badge/transport-Streamable_HTTP-444)](https://modelcontextprotocol.io/)
[![Auth](https://img.shields.io/badge/auth-OAuth_2.1-444)](https://heymetra.com/security/)
[![Connector page](https://img.shields.io/badge/heymetra.com-google--search--console-1f6feb)](https://heymetra.com/connectors/google-search-console/)

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

Open search.google.com/search-console and look at the property list. Connect with the account you see it in. Not a personal account that happens to be signed in, and not the agency account unless the property is listed there too.

> Search Console permissions are per property, not per domain. Being an owner of example.com says nothing about shop.example.com.

**2. Choose Google Search Console in HeyMetra**

On the Connections screen. There is nothing to copy and no key to generate: this connector uses Google's own sign-in.

**3. Sign in on Google's screen and grant read access**

Your password stays with Google, and you can revoke HeyMetra's access at any time from your Google account. The permission asked for is read-only, so nothing here submits a sitemap, removes a URL or changes a setting.

> If Google offers an account picker, the account you pick is the one whose properties HeyMetra can see. Picking the wrong one shows an empty list on the next step rather than an error.

**4. Pick the property**

HeyMetra lists what that Google account can read. A domain property (sc-domain:example.com) covers every subdomain and both http and https; a URL-prefix property covers exactly the address it names. Pick the one whose figures you recognise.

**5. Add HeyMetra to the assistant you use**

Claude, ChatGPT, Grok, Perplexity, Claude Code, Codex, Cursor or Antigravity. You paste one address and sign in once. Search Console then answers there, from the live property.

The same steps are on the docs page: [Google Search Console setup guide](https://heymetra.com/docs/google-search-console/).

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

_On Team and Enterprise plans, an owner adds the connector for the whole organization under Organization settings → Connectors, and each member then connects to it._

Full walkthrough: [heymetra.com/mcp/claude/](https://heymetra.com/mcp/claude/)
</details>

<details>
<summary><b>ChatGPT</b> — chatgpt.com/plugins → + → Add custom MCP server</summary>

Paste the address above into chatgpt.com/plugins → + → Add custom MCP server.

_Add it on chatgpt.com in a browser, because the mobile app cannot add one. Every ChatGPT plan can, Free included. In a Business, Enterprise or Edu workspace, an admin or owner decides whether members can add custom MCP servers. ChatGPT needs the full address, including /mcp at the end._

Full walkthrough: [heymetra.com/mcp/chatgpt/](https://heymetra.com/mcp/chatgpt/)
</details>

<details>
<summary><b>Grok</b> — grok.com/connectors → New Connector → Custom</summary>

Paste the address above into grok.com/connectors → New Connector → Custom.

_On Grok Business and Enterprise, a team admin has to provision the connector in xAI's cloud console before members can use it._

Full walkthrough: [heymetra.com/mcp/grok/](https://heymetra.com/mcp/grok/)
</details>

<details>
<summary><b>Perplexity</b> — Plugins → Add custom → Connector → Add MCP connector → Remote</summary>

Paste the address above into Plugins → Add custom → Connector → Add MCP connector → Remote.

_In an organization, members can add a custom connector only after an admin turns on Allow members to add custom connectors, which is off by default._

Full walkthrough: [heymetra.com/mcp/perplexity/](https://heymetra.com/mcp/perplexity/)
</details>

<details>
<summary><b>Claude Code</b> — claude mcp add --transport http</summary>

```bash
claude mcp add --transport http heymetra https://mcp.heymetra.com/mcp
```

_You can also add the server to a .mcp.json file at the project root. Run /mcp in a session to sign in and to check that it connected._

Full walkthrough: [heymetra.com/mcp/claude-code/](https://heymetra.com/mcp/claude-code/)
</details>

<details>
<summary><b>Codex</b> — ~/.codex/config.toml</summary>

```toml
[mcp_servers.heymetra]
url = "https://mcp.heymetra.com/mcp"
```

_Codex reads the server from an [mcp_servers.<name>] section in config.toml, and you sign in with codex mcp login <name>._

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

_Cursor signs in to HeyMetra without a client ID or secret, so the server entry needs no auth block._

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

_Antigravity's documented key for the address is serverUrl, though it also accepts url._

Full walkthrough: [heymetra.com/mcp/antigravity/](https://heymetra.com/mcp/antigravity/)
</details>

## What it may and may not touch

Google Search Console is a read-only source. HeyMetra reads it to answer your questions and never changes anything in it.

Permissions are switched on per connection, and one you leave off is a tool your assistant never sees.

| Permission | What it covers | Changes anything? |
|---|---|---|
| **Included with the connection** | What HeyMetra needs to set the connection up, and nothing more. It cannot be switched off on its own; to withdraw it, remove the connection. | No, read only |
| **Full account access** | Lets your assistant read anything in this account to answer your questions. The figures are the provider's own, not ones HeyMetra has checked. It cannot change anything in this account — Google keeps about 16 months and deletes the rest. An older period is refused rather than answered as a stretch with no search traffic; The last two days are still being processed, so a window that reaches them looks like a decline that is not there; Google leaves rare searches out of query reports entirely, to protect the people who typed them. Measured on a real site, the same month showed 339 impressions by query and 1,244 by page. So these terms do not add up to the site's traffic, and the search performance report is where a total comes from; Google keeps about 16 months and deletes the rest; Error and warning COUNTS only. Search Console keeps what they actually say to its own interface, so a report can say a sitemap has three errors and cannot say what they are; Submitted counts only. Google no longer reports how many submitted pages are indexed, so nothing here can say it; One page per question, and 2,000 a day per site on a rolling 24-hour window. Google offers no way to check a whole site at once, so this explains a specific page rather than surveying a site. | No, read only |

<details>
<summary>What each permission lets an assistant do, in full</summary>

- Ask anything about this account and get the answer from its live data. Reads only, and the figures are the provider's own rather than ones HeyMetra has checked.
</details>

## When something goes wrong

<details>
<summary>The property list is empty after signing in.</summary>

**Why:** That Google account is not verified for any property. Being able to see a site in Analytics, or owning the domain, is not the same permission.

**Fix:** In Search Console, have an existing owner add this account under Settings → Users and permissions. Full or Restricted both work; read access is all HeyMetra asks for.

</details>

<details>
<summary>The site is in the list twice, with different numbers in each.</summary>

**Why:** A domain property and a URL-prefix property for the same site are two different properties and count different traffic. The domain one includes subdomains and the other protocol.

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

Connect the property once and ask about it from your assistant: clicks, impressions, CTR and average position for any period, day by day; the queries and pages with the most impressions, each with its own clicks, CTR and position; which sitemaps you submitted and whether Google still reads them; and what Google says about one page you name, such as whether it is indexed, when it was last crawled and what links to it. Search Console holds back its rarest queries, so the same month adds up to less by query than by page, and every answer says which report it used. HeyMetra only reads: it never submits a sitemap, removes a URL or changes a setting on your property.

<details>
<summary>About Google Search Console</summary>

Google Search Console reports how your site performs in Google’s organic search results: the queries you rank for, your clicks and impressions, and indexing health. It’s the ground truth for SEO.
</details>

## One connection, not seven

The reason to read Google Search Console through HeyMetra rather than through a server that only knows Google Search Console is everything else it can answer in the same breath:

**Ads** — [Google Ads](https://github.com/zeisoft/google-ads-mcp)

**Analytics** — [Google Analytics 4](https://github.com/zeisoft/google-analytics-4-mcp) · **Google Search Console** · [PostHog](https://github.com/zeisoft/posthog-mcp)

**Ecommerce** — [Trendyol](https://github.com/zeisoft/trendyol-mcp) · [n11](https://github.com/zeisoft/n11-mcp) · [Çiçeksepeti](https://github.com/zeisoft/ciceksepeti-mcp) · [Amazon Seller Central](https://github.com/zeisoft/amazon-seller-central-mcp) · [ikas](https://github.com/zeisoft/ikas-mcp) · [WooCommerce](https://github.com/zeisoft/woocommerce-mcp)

**Revenue & CRM** — [Stripe](https://github.com/zeisoft/stripe-mcp) · [Zoho CRM](https://github.com/zeisoft/zoho-crm-mcp) · [Zoho SalesIQ](https://github.com/zeisoft/zoho-salesiq-mcp) · [Zoho Marketing Automation](https://github.com/zeisoft/zoho-marketing-automation-mcp)

**Mobile** — [AppsFlyer](https://github.com/zeisoft/appsflyer-mcp) · [RevenueCat](https://github.com/zeisoft/revenuecat-mcp) · [Adapty](https://github.com/zeisoft/adapty-mcp) · [App Store Connect](https://github.com/zeisoft/app-store-connect-mcp)

**Work** — [Jira](https://github.com/zeisoft/jira-mcp)

**Channels** — [Slack](https://github.com/zeisoft/slack-mcp) · [Telegram](https://github.com/zeisoft/telegram-mcp)

The full catalogue is at [heymetra.com/connectors/](https://heymetra.com/connectors/).

## Links

- [Google Search Console connector page](https://heymetra.com/connectors/google-search-console/)
- [Google Search Console setup guide](https://heymetra.com/docs/google-search-console/)
- [HeyMetra](https://heymetra.com/) — what the product is
- [Setup for every assistant](https://heymetra.com/mcp/)
- [Security and limits](https://heymetra.com/security/)
- [Pricing](https://heymetra.com/pricing/)
- [HeyMetra's own repository](https://github.com/zeisoft/heymetra-mcp)

---

<sub>Built by <a href="https://zeisoft.com">Zeisoft</a>, who make HeyMetra. Not affiliated with Google Search Console. This README is generated from HeyMetra's live connector catalogue and refreshed daily; corrections are welcome as issues.</sub>
