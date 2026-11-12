# Awesome AI Cost Tracking [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Tools and guides to track, manage and cut AI and LLM API costs: cost trackers, spend limits, Claude Code and Codex usage, AI gross margin per customer, and usage-based billing.

AI spend arrives as one line on a provider invoice. This list collects the tools that break it down: by API key, team, developer, project, customer or workflow, and the ones that help you set limits, charge it back or price your product on top of it.

Tools are listed alphabetically within each section. Descriptions say what each tool does for cost, not everything it does.

*Maintained by the team behind Ganivra, which is listed below under the same rules as everything else. Corrections and additions from anyone, including other vendors, are welcome.*

## Contents

- [Provider usage and cost APIs](#provider-usage-and-cost-apis)
- [AI API cost trackers](#ai-api-cost-trackers)
- [LLM gateways with spend limits](#llm-gateways-with-spend-limits)
- [LLM monitoring with cost tracking](#llm-monitoring-with-cost-tracking)
- [Claude Code and Codex usage trackers](#claude-code-and-codex-usage-trackers)
- [AI gross margin and cost per customer](#ai-gross-margin-and-cost-per-customer)
- [Usage-based billing for AI products](#usage-based-billing-for-ai-products)
- [Model prices and price data](#model-prices-and-price-data)
- [Standards](#standards)
- [Guides](#guides)
- [Templates](#templates)

## Provider usage and cost APIs

The source data. Everything else in this list builds on these or on request-level logs.

- [Anthropic Usage and Cost Analytics API](https://platform.claude.com/docs/en/manage-claude/usage-cost-analytics-api) - Token usage and cost for a Claude Console or Claude Enterprise organization, by model, workspace, API key and user.
- [Claude Code Analytics API](https://platform.claude.com/docs/en/manage-claude/claude-code-analytics-api) - Admin API for an organization's Claude Code usage and productivity metrics.
- [OpenAI Usage API](https://developers.openai.com/api/reference/resources/organization/subresources/usage) - Organization usage by model, project, API key and user, from the Admin API.
- [OpenRouter usage accounting](https://openrouter.ai/docs/cookbook/administration/usage-accounting) - Token counts and cost returned with each request routed through OpenRouter.

## AI API cost trackers

Pull provider spend into one place, usually next to cloud costs.

- [CloudZero](https://www.cloudzero.com) - Cloud and AI cost platform that allocates spend to the customers, products and teams it serves.
- [KeyBark](https://keybark.com/?utm_source=github&utm_medium=listing&utm_campaign=w1&utm_content=ai-cost-tracking-pr) - Reads spend for OpenAI, Anthropic and OpenRouter API keys from each provider's own usage and cost data and emails when a daily or monthly threshold is crossed or spend jumps above its 7-day average; it alerts but doesn't enforce limits.
- [Vantage](https://www.vantage.sh) - Cloud cost platform with [Anthropic](https://docs.vantage.sh/connecting_anthropic) and [OpenAI](https://docs.vantage.sh/connecting_openai) connectors, including Claude.ai and Codex usage.

## LLM gateways with spend limits

Proxies that sit between your app and the providers. They see every request, so they can count cost and stop it at a budget.

- [Cloudflare AI Gateway](https://developers.cloudflare.com/ai-gateway/) - Managed gateway with analytics, caching, rate limits and [cost tracking](https://developers.cloudflare.com/ai-gateway/observability/costs/).
- [Helicone](https://github.com/Helicone/helicone) - Open-source gateway and observability with [cost tracking](https://docs.helicone.ai/guides/cookbooks/cost-tracking) per user and property.
- [LiteLLM](https://github.com/BerriAI/litellm) - Open-source gateway for 100+ providers with [spend tracking](https://docs.litellm.ai/docs/proxy/cost_tracking) and [budgets](https://docs.litellm.ai/docs/proxy/users) per key, user and team.
- [OpenRouter](https://openrouter.ai) - Hosted router across many model providers, with credit limits per key and per-request cost.
- [Portkey](https://github.com/Portkey-AI/gateway) - Open-source gateway; the hosted product adds [budget limits](https://docs.portkey.ai/docs/product/enterprise-offering/budget-limits).

## LLM monitoring with cost tracking

Tracing and evaluation tools that also price each call. Best when you already want traces; cost is a by-product.

- [Arize Phoenix](https://github.com/Arize-ai/phoenix) - Open-source tracing and evaluation, with token counts and cost per span.
- [Datadog LLM Observability](https://www.datadoghq.com/products/ai/agent-observability/) - Agent and LLM tracing inside Datadog, with [cost monitoring](https://docs.datadoghq.com/llm_observability/monitoring/cost/).
- [Langfuse](https://github.com/langfuse/langfuse) - Open-source tracing and evals with [token and cost tracking](https://langfuse.com/docs/observability/features/token-and-cost-tracking) by user, session and trace.
- [LangSmith](https://www.langchain.com/langsmith/observability) - LangChain's tracing platform; tracks cost and latency per run.
- [OpenLIT](https://github.com/openlit/openlit) - Open-source, OpenTelemetry-native monitoring focused on token and compute cost.
- [Opik](https://github.com/comet-ml/opik) - Open-source tracing, evaluation and dashboards from Comet, with cost per trace.

## Claude Code and Codex usage trackers

AI coding agents bill per developer seat or per token. These show who used what.

- [ccusage](https://github.com/ccusage/ccusage) - Free CLI that reads local logs and reports daily, monthly and per-session usage for Claude Code, Codex, OpenCode, Amp and Gemini CLI.
- [Claude Code Usage Monitor](https://github.com/Maciek-roboblog/Claude-Code-Usage-Monitor) - Terminal monitor for Claude Code usage with burn-rate predictions and limit warnings.
- [Claude Code monitoring](https://code.claude.com/docs/en/monitoring-usage) - Built-in OpenTelemetry export of per-request cost, tokens and model; point it at any collector.
- [Codex OpenTelemetry](https://learn.chatgpt.com/docs/config-file/config-advanced) - Codex's `[otel]` config for exporting per-request usage events.
- [Ganivra](https://ganivra.com/ai-coding-cost-tracking) - Hosted Claude Code and Codex cost by developer, team, project and client from their OpenTelemetry exports, with chargeback CSV. Prompts and code are not collected. No Cursor support yet.

## AI gross margin and cost per customer

For companies selling an AI product: what each customer, plan or workflow costs to serve, against what it pays. CloudZero, above, also allocates AI spend to customers.

- [Ganivra](https://ganivra.com) - AI cost per customer, plan and workflow, and margin after AI cost, with Stripe revenue. No proxy.
- [Paid](https://paid.ai) - Pricing, billing and margin tracking for AI agent companies.
- [Revenium](https://www.revenium.ai) - Transaction-level cost attribution and controls across tokens, APIs and agent workflows, for engineering and finance.

## Usage-based billing for AI products

Charge customers for tokens, credits or outcomes. These meter usage for invoicing; most don't track your own provider cost.

- [Flexprice](https://github.com/flexprice/flexprice) - Open-source usage, credit and hybrid billing with real-time metering.
- [Lago](https://github.com/getlago/lago) - Open-source metering and usage-based billing, self-hosted or cloud.
- [Metronome](https://metronome.com) - Usage-based billing platform for pricing models and invoicing.
- [OpenMeter](https://github.com/openmeterio/openmeter) - Open-source metering and billing for AI and API usage, now part of Kong.
- [Orb](https://www.withorb.com) - Usage-based billing and pricing changes as usage and costs evolve.
- [Stripe usage-based billing](https://docs.stripe.com/billing/subscriptions/usage-based) - Meters and usage pricing inside Stripe Billing.

## Model prices and price data

- [Anthropic pricing](https://claude.com/pricing) - Official Claude API and plan prices.
- [Artificial Analysis](https://artificialanalysis.ai) - Independent comparison of model quality, price and speed across providers.
- [LiteLLM model prices](https://github.com/BerriAI/litellm/blob/main/model_prices_and_context_window.json) - Community-maintained JSON of per-token prices for many models, used by several tools above.
- [OpenAI pricing](https://developers.openai.com/api/docs/pricing) - Official OpenAI API prices.
- [tokencost](https://github.com/AgentOps-AI/tokencost) - Python library that estimates the cost of a prompt and completion for 400+ models.

## Standards

- [FinOps for AI](https://www.finops.org/wg/finops-for-ai-overview/) - FinOps Foundation overview of where AI spend shows up, practices and KPIs.
- [OpenTelemetry GenAI semantic conventions](https://github.com/open-telemetry/semantic-conventions-genai) - Standard attribute names for model calls, including token usage, so any backend can price them.

## Guides

- [Manage Claude Code costs](https://code.claude.com/docs/en/costs) - Anthropic's guide to tracking usage, team spend limits and reducing cost.
- [Claude Code cost per developer](https://ganivra.com/blog/claude-code-cost-per-developer) - How to measure it and what drives it. *(Ganivra)*
- [Claude Code managed settings for cost tracking](https://ganivra.com/blog/claude-code-managed-settings-cost-tracking) - Sending usage from every machine with settings developers can't override. *(Ganivra)*
- [Charging AI coding costs back to teams](https://ganivra.com/blog/ai-coding-costs-chargeback-by-team) - Showback versus chargeback, with a worked example. *(Ganivra)*

## Templates

- [AI coding chargeback template](https://ganivra.com/templates/ai-coding-chargeback-template.xlsx) - Free spreadsheet to split AI coding spend across teams or clients. *(Ganivra, .xlsx)*

## Contributing

Additions and corrections are welcome, including for your own tool. Read the [contributing guide](contributing.md) first.
