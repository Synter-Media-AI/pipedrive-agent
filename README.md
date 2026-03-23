# Pipedrive CRM MCP Starter Kit — Manage Pipedrive with AI

[![MCP Compatible](https://img.shields.io/badge/MCP-compatible-blue)](https://modelcontextprotocol.io)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform: Pipedrive](https://img.shields.io/badge/Platform-Pipedrive-017737)](https://www.pipedrive.com)

**Turn your sales pipeline into an ad targeting engine.** Open this repo in Amp, Cursor, or VS Code and manage Pipedrive deals, contacts, and activities with AI — sync deal-stage contacts to retargeting audiences and show different ads to prospects vs customers.

---

## Why Pipedrive + AI for Advertising?

Pipedrive is built for sales teams that live and breathe pipeline management. 100,000+ companies use it to track deals from first contact to closed-won. The visual pipeline makes it easy to see where every deal stands.

For advertising, Pipedrive's pipeline stages are perfect for audience segmentation. Someone in "Proposal Sent" needs different ad messaging than someone in "Qualified Lead." A customer who just churned needs a win-back campaign, not an acquisition ad.

An AI agent bridges Pipedrive and your ad platforms. It exports contacts by deal stage, syncs audiences automatically, and helps you show the right message to the right person at the right time.

**Best for:** Sales-driven SMBs, agencies managing client pipelines, B2B companies with 3-12 month sales cycles, teams that want deal-stage-specific ad targeting.

---

## Quick Start (30 Seconds)

### Amp / Cursor / VS Code (Copilot)

1. **Get a free API key** at [syntermedia.ai/developer](https://syntermedia.ai/developer)
2. **Set the key:**
   ```bash
   export SYNTER_API_KEY=syn_your_key_here
   ```
3. **Open this repo** in your editor
4. **Start chatting** — MCP tools are pre-configured in `.mcp.json`

### Claude Desktop

Copy `claude_desktop_config.json` to your Claude config directory and replace the API key:

- **macOS:** `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows:** `%APPDATA%\Claude\claude_desktop_config.json`

---

## What You Can Do

| Capability | Example |
|-----------|---------|
| **Pipeline Overview** | "Show me all deals in the pipeline grouped by stage" |
| **Stage-Based Audiences** | "Sync contacts in 'Proposal Sent' stage to Meta for retargeting" |
| **Activity Tracking** | "Which deals have no activity logged in the past 2 weeks?" |
| **Win/Loss Analysis** | "What's our win rate by lead source this quarter?" |
| **Contact Lookup** | "Find all contacts associated with deals over $10K" |
| **Revenue Forecasting** | "What's the weighted pipeline value for next quarter?" |
| **Lost Deal Recovery** | "Create a retargeting audience from deals we lost in the past 6 months" |
| **Custom Field Queries** | "Show deals where 'Industry' is Healthcare and deal size is above $5K" |
| **Activity Reminders** | "Which high-value deals need follow-up calls this week?" |

---

## Example Conversations

### 1. Deal-Stage Retargeting Strategy

> **You:** I want to show different ads to people based on where they are in our pipeline.
>
> **Agent:** Smart — this is pipeline-aware advertising. Let me map your Pipedrive stages to ad campaigns:
>
> | Pipeline Stage | Contacts | Ad Strategy | Messaging |
> |---|---|---|---|
> | Qualified Lead | 89 | Awareness (Meta/LinkedIn) | "How [Product] helps teams like yours" |
> | Demo Scheduled | 34 | Social proof (LinkedIn) | "See why 500+ companies chose [Product]" |
> | Proposal Sent | 18 | Urgency (Google Display) | "Limited-time: 20% off annual plans" |
> | Won | 142 | Upsell (Meta) | "Unlock [Premium Feature] — exclusive for customers" |
> | Lost | 67 | Win-back (Meta/Google) | "We've added [Feature They Asked About]" |
>
> **How I'll implement this:**
> 1. Export contacts from each Pipedrive stage
> 2. Create separate Custom Audiences on Meta and Google for each stage
> 3. Build 5 campaigns with stage-specific messaging
> 4. Set up a weekly sync so audiences stay current as deals move through stages
>
> **Expected impact:** Stage-specific messaging typically improves conversion rates by 40-60% vs generic retargeting. A "Proposal Sent" contact seeing a testimonial from their industry is much more likely to respond than seeing a generic brand ad.
>
> **You:** Start with "Proposal Sent" and "Lost" — those are the highest impact.
>
> **Agent:** Exported 18 "Proposal Sent" contacts and 67 "Lost" contacts. Created Meta Custom Audiences for both. Campaigns created with stage-appropriate messaging. PAUSED until you approve.

### 2. Lost Deal Win-Back Campaign

> **You:** We lost 67 deals in the past 6 months. Can we try to win them back?
>
> **Agent:** Let me analyze why they were lost first — the reason matters for messaging...
>
> **Lost deal reasons (from Pipedrive):**
>
> | Reason | Count | % | Win-Back Approach |
> |---|---|---|---|
> | Price too high | 24 | 36% | Offer limited-time discount or show ROI calculator |
> | Chose competitor | 19 | 28% | Highlight features they're missing + switching incentive |
> | Not ready / timing | 15 | 22% | Nurture content — they may be ready now |
> | No budget | 9 | 13% | Wait 3-6 months, then retarget with value-focused content |
>
> **Win-back campaign plan:**
>
> **Segment A — "Price too high" (24 contacts):**
> - Ad: "We heard you. New pricing starts at $X/month — 30% less than when we last spoke"
> - Or: "Companies using [Product] save an average of $47K/year. Here's the math."
> - Platform: Meta + Google Display (high frequency, small audience)
>
> **Segment B — "Chose competitor" (19 contacts):**
> - Ad: "Switching to [Product] is free. We'll migrate your data and train your team at no cost."
> - Include G2/Capterra comparison content
> - Platform: LinkedIn (professional context)
>
> **Segment C — "Timing" (15 contacts):**
> - Ad: Thought leadership content (not salesy) — keep brand top of mind
> - After 30 days of nurturing, switch to product-focused ads
> - Platform: Meta (low-cost awareness)
>
> Budget: $15/day total across all segments. Expected win-back rate: 5-10% (3-7 deals at your avg deal size = significant revenue).

### 3. Activity Gap Detection

> **You:** Which deals are going cold? Deals where nobody's followed up.
>
> **Agent:** Pulling deals with activity gaps from Pipedrive...
>
> **Deals with no activity in 14+ days:**
>
> | Deal | Stage | Value | Days Since Last Activity | Owner |
> |---|---|---|---|---|
> | Acme Corp Expansion | Proposal Sent | $45K | 21 days | Sarah |
> | DataFlow Migration | Demo Scheduled | $28K | 16 days | Mike |
> | CloudFirst Enterprise | Qualified | $62K | 18 days | Sarah |
> | RetailMax Platform | Negotiation | $33K | 14 days | Lisa |
>
> **⚠️ Critical:** The Acme Corp deal ($45K) has been in "Proposal Sent" for 21 days with no activity. Proposals go stale fast — the client may have moved on.
>
> **Recommended actions:**
> 1. Flag these deals to each owner for immediate follow-up
> 2. For "Proposal Sent" deals, run retargeting ads with social proof (case studies from their industry)
> 3. Set up activity alerts in Pipedrive: auto-notify if any deal in Proposal/Negotiation stage has no activity for 7+ days
>
> Want me to create a retargeting audience from these stalled deal contacts?

### 4. Pipeline Conversion Rates for Budget Planning

> **You:** What's our pipeline conversion rate at each stage? I need to plan ad budget.
>
> **Agent:** Pulling historical stage-to-stage conversion rates from Pipedrive...
>
> **Stage Conversion Rates (last 12 months, 340 deals):**
>
> | From → To | Conversion Rate | Avg Days |
> |---|---|---|
> | Lead → Qualified | 42% | 5 days |
> | Qualified → Demo | 65% | 8 days |
> | Demo → Proposal | 58% | 12 days |
> | Proposal → Negotiation | 44% | 7 days |
> | Negotiation → Won | 72% | 11 days |
> | **Lead → Won (overall)** | **7.2%** | **43 days** |
>
> **Budget model:**
> - You need 10 new customers/month (at $15K avg deal)
> - At 7.2% overall conversion: need 139 leads/month
> - Your average cost per lead: $35 (from ad platforms)
> - Required monthly ad budget: **$4,865/month**
>
> **Stage-specific insight:** Your biggest leak is Proposal → Negotiation (44%). Contacts receive a proposal and don't engage. This is where stage-specific retargeting ads with customer testimonials and ROI data can move the needle.

### 5. Customer vs Prospect Audience Separation

> **You:** I'm wasting money showing acquisition ads to existing customers. Fix this.
>
> **Agent:** Classic problem. Let me build your suppression list from Pipedrive...
>
> **From Pipedrive "Won" deals:**
> - 142 unique contacts from closed-won deals
> - 38 additional contacts from active subscriptions (recurring deals)
> - **Total suppression list: 180 contacts**
>
> **What I'll do:**
> 1. Export all 180 customer emails from Pipedrive
> 2. Upload as exclusion audiences on Google, Meta, and LinkedIn
> 3. Create a separate "Customers" audience for upsell campaigns
>
> **Your upsell opportunity:**
> - 142 customers, average deal size $15K
> - 47 customers are on your Basic plan → potential upgrade to Pro ($25K)
> - 28 customers haven't purchased add-ons → cross-sell opportunity
>
> **Two campaigns, one audience:**
> - **Suppression:** Remove 180 contacts from all acquisition campaigns → saves ~$500-800/month
> - **Upsell:** Target the 47 Basic plan customers with "Unlock Pro features" messaging → potential $470K in upgrades

---

## Pipedrive Tips for Ad Targeting

1. **Sync deal-stage contacts to separate ad audiences.** "Qualified Lead" gets awareness content. "Proposal Sent" gets testimonials. "Lost" gets win-back offers. One-size-fits-all retargeting wastes money.
2. **Lost deal analysis is gold.** Export lost deal reasons from Pipedrive and create segment-specific win-back campaigns. A "price too high" lost deal responds to discounts; a "chose competitor" responds to comparison content.
3. **Activity gaps = retargeting opportunities.** When a deal goes silent, retargeting ads keep your brand visible while sales reaches out. The ad warms the contact for the follow-up call.
4. **Suppress customers from acquisition.** Export closed-won contacts → add as exclusion audiences. Simple, saves 5-10% of ad budget instantly.
5. **Use deal values for audience prioritization.** $50K deals deserve higher ad frequency and premium placements. $5K deals get standard retargeting. Allocate ad budget proportional to deal value.
6. **Pipeline velocity as campaign health metric.** Track how fast deals move through stages. If velocity slows, check if your retargeting content is still relevant.

---

## FAQ

### Is there an MCP for Pipedrive?
Yes — this repo. It pre-configures the Synter MCP server for Pipedrive CRM. Works with Amp, Cursor, VS Code, and Claude Desktop.

### Can I sync Pipedrive contacts to ad platforms?
Yes. The agent exports contacts by deal stage, hashes emails, and uploads to Google, Meta, and LinkedIn as Custom Audiences.

### Does this support Pipedrive custom fields?
Yes. The agent can query deals by any custom field — industry, company size, lead source, or any field you've created.

### How is this different from the HubSpot or Salesforce agents?
Pipedrive is focused on pipeline management for sales-driven SMBs. The integration emphasizes deal-stage segmentation and activity-gap detection, which are Pipedrive's strengths.

### Can the agent update Pipedrive data?
The agent focuses on reading pipeline data and syncing audiences. For bulk updates, use Pipedrive's native automation or API.

---

## Related Repos

- [hubspot-agent](https://github.com/Synter-Media-AI/hubspot-agent) — Inbound marketing CRM
- [salesforce-agent](https://github.com/Synter-Media-AI/salesforce-agent) — Enterprise CRM
- [audience-sync-agent](https://github.com/Synter-Media-AI/audience-sync-agent) — Multi-platform audience sync
- [meta-ads-agent](https://github.com/Synter-Media-AI/meta-ads-agent) — Retargeting campaigns
- [linkedin-ads-agent](https://github.com/Synter-Media-AI/linkedin-ads-agent) — B2B targeting
- [google-ads-agent](https://github.com/Synter-Media-AI/google-ads-agent) — Customer Match

---

## License

MIT — see [LICENSE](LICENSE) for details.

Built by [Synter](https://syntermedia.ai) · [Get API Key](https://syntermedia.ai/developer) · [Documentation](https://syntermedia.ai/docs)
