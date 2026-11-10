# Parvenu MCP Server

B2B lead sourcing and enrichment for AI agents. Build targeted lead lists with
verified emails, enrich LinkedIn profiles, search 60M+ companies, find hiring
managers, score contacts against your ICP and personalize outreach, from any
MCP client.

This repository documents Parvenu's **hosted** MCP server. There is nothing to
install or run: connect your client to the URL below.

| | |
|---|---|
| Server URL | `https://enterprise.parvenu.io/mcp` |
| Transport | Streamable HTTP |
| Auth | OAuth 2.0 (sign in with your Parvenu account) |
| Website | https://parvenu.io |
| API docs | https://developer.parvenu.io |

You need a Parvenu account. Tools that look data up are billed in Parvenu
credits on your account; every tool description states its price, and misses
are free on most lookups.

## Connect

### Claude (claude.ai / Claude Desktop)

Settings → Connectors → Add custom connector → paste
`https://enterprise.parvenu.io/mcp` → Connect, then sign in to Parvenu.

### Claude Code

```bash
claude mcp add --transport http parvenu https://enterprise.parvenu.io/mcp
```

### Cursor

`~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "parvenu": {
      "url": "https://enterprise.parvenu.io/mcp"
    }
  }
}
```

### VS Code

`.vscode/mcp.json`:

```json
{
  "servers": {
    "parvenu": {
      "type": "http",
      "url": "https://enterprise.parvenu.io/mcp"
    }
  }
}
```

### Windsurf, ChatGPT and other clients

Add a remote MCP server with the URL `https://enterprise.parvenu.io/mcp`
(streamable HTTP) and complete the Parvenu sign-in when prompted.

## Tools

117+ tools. The main groups:

| Group | Examples |
|---|---|
| Lead sourcing | `parvenu_lead_enrichment` (lead lists by title, industry, size, location, with verified emails), `parvenu_domain_enrichment`, `parvenu_sales_nav_search`, `parvenu_linkedin_search`, `parvenu_maps_search_list` |
| Contact lookups | `parvenu_email_lookup`, `parvenu_get_profile`, `parvenu_profile_with_company`, `parvenu_mobile_phone_enrichment`, `parvenu_verify_email` |
| Company data | `parvenu_company_search`, `parvenu_enrich_company_from_domain`, `parvenu_technology_stack`, `parvenu_company_news_lookup`, `parvenu_lookalike`, `parvenu_funding_search` |
| Hiring signals | `parvenu_jobs_search`, `parvenu_find_hiring_manager`, job search schedules |
| List enrichment | email, phone, LinkedIn, website, headcount, work history, open-to-work, job-function breakdown, AI research and website scraping per row |
| ICP scoring | `parvenu_create_icp`, `parvenu_multi_icp_score`, `parvenu_run_enrichment` |
| AI personalization | `parvenu_personalize_with_ai`, `parvenu_research_with_ai` |
| Lists | create, add, update, move, remove, share, download, saved views, custom columns |
| Flows | build, run and schedule multi-step enrichment automations |
| Account | `parvenu_credit_check`, `parvenu_skills_list`, `parvenu_skill_view`, plus credit purchase and auto top-up (`parvenu_buy_credits_quote` / `parvenu_buy_credits_confirm`, `parvenu_auto_topup_status` / `parvenu_auto_topup_update`), which charge the card on file and always quote the amount and ask you to confirm first |

Call `parvenu_skills_list` first: it returns step-by-step playbooks for the
common tasks (lead sourcing, deep personalization, ICP scoring and more).

## Example prompts

- "Find 50 owners of California roofing companies with 11–50 employees, with verified emails."
- "What's the work email for https://www.linkedin.com/in/example?"
- "Find US cybersecurity companies with 51–200 employees that use HubSpot."
- "Who is hiring a Head of Sales this week, and who is their hiring manager?"
- "Score my 'Q4 prospects' list against my ICPs."

## Support

patrick@parvenu.io · https://parvenu.io
