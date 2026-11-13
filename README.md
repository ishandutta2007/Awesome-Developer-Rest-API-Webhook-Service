# Awesome-Developer-Rest-API-Webhook-Service

# Top Developer REST API & Webhook Service Ecosystem

**Curated List of SaaS Platforms & Open-Source GitHub Projects**  
*Focused on API Gateway Management, Inbound Webhook Ingress & Outbound Delivery Infrastructure*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Developer REST API & Webhook Services**. These tools provide the infrastructure to expose REST APIs securely, receive and process inbound webhooks reliably, and deliver outbound webhooks to customer endpoints—covering API gateways, webhook ingress proxies, and delivery engines that handle retries, signatures, and observability.

**Examples** include BrowserStack REST API & Webhooks, Postman, Kong Gateway, AWS API Gateway, Apigee, Tyk, Hookdeck, Svix, Hook0, and Outpost (the category leaders).

**Open-source emphasis**: This section highlights every major active project for self-hosted API gateways, open-source webhook infrastructure, and community-driven delivery engines—ideal for organizations seeking data sovereignty and predictable costs over per-event or per-gateway SaaS billing. The open-source webhook landscape has matured significantly: **Hook0** offers full-feature-parity self-hosting under SSPL-1.0 , **Outpost** provides production-ready outbound delivery under Apache-2.0 , and **Convoy** delivers a Go-based webhook gateway with a dashboard .

Contributions welcome! Open an PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

| Product | Description | Pricing (Starting) | Free Tier / Trial Limits |
|---------|-------------|-------------------|--------------------------|
| **[BrowserStack REST API & Webhooks](https://www.browserstack.com/)** | Test Reporting & Analytics webhooks send real-time events (Build Finish, Test Failure, Quality Gate Result, Alert Trigger) to external endpoints. Supports default/custom payloads, POST/PUT methods, authorization types, re-trigger on passing builds, and template variables. Endpoint must be publicly reachable—localhost and private IP ranges rejected . | Included with BrowserStack subscription | No standalone free tier; webhooks bundled with BrowserStack plans |
| **[Postman](https://www.postman.com/)** | API development platform with **webhook listeners** that provide stable public URLs for capturing inbound events. Features: raw header/body inspection, routing to target URLs or custom responses, **event replay**, and **JavaScript scripting** on Solo/Team/Enterprise plans for payload validation, HMAC signature verification (with built-in presets for Stripe, GitHub, Slack), and chaining collection requests . | Solo: $9/month; Team: $19/user/month | **Free**: 1 user only, unlimited collection runs; webhook scripting on paid plans . **100 requests/minute per IP** limit per webhook  |
| **[Kong Konnect](https://konghq.com/)** | Managed API lifecycle platform with gateway, control plane, and developer portal. **Plus: $500/month per Dedicated Cloud Gateway control plane** (1M requests included, 5 Serverless + 2 Hybrid + 2 DCGW). Overage: $200/month per additional 1M requests; **$200/month per additional Developer Portal** . | Plus: **$500/month per control plane**; Enterprise: custom | **30-day free trial**: full Enterprise functionality  |
| **[AWS API Gateway](https://aws.amazon.com/api-gateway/)** | Fully managed gateway for REST, HTTP, and WebSocket APIs. Pay-per-request. **Does not natively validate webhook HMAC signatures**—requires custom Lambda authorizers per provider . For inbound webhooks, teams often add SQS/EventBridge for queueing and DynamoDB for replay storage . | HTTP API: ~$1.00/million requests; REST API: ~$3.50/million | **New AWS customers**: 1M API calls/month per type for 12 months |
| **[Apigee (Google Cloud)](https://cloud.google.com/apigee)** | Enterprise API management with gateway, analytics, developer portal, and monetization. Pay-as-you-go for gateway nodes (per minute) and analytics (per request). Developer portal included with up to 3 custom domains . | Pay-as-you-go (gateway per-minute + analytics per-request) | **60-day free evaluation plan** |
| **[Tyk](https://tyk.io/)** | Open-core API gateway (**Tyk Gateway MPL 2.0, free**). Dashboard, Developer Portal, and MDCB are paid components. **No public list pricing**—quoted by sales. Core usage-based; Professional architecture-based with unlimited APIs . | Quote-only | **Self-Managed trial license** via request; Gateway OSS free forever |
| **[MuleSoft Anypoint](https://www.mulesoft.com/)** | Enterprise iPaaS and API management. vCore-based pricing with typical mid-five to low-six figures annually. Implementation services 20–40% of first-year software cost . | Quote-only (median ~$68,695/year per Vendr) | 30-day free trial available |

## Open-Source GitHub Projects

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Hook0](https://github.com/hook0/hook0)** | [![Stars](https://img.shields.io/github/stars/hook0/hook0?style=social&color=white)](https://github.com/hook0/hook0/stargazers) | **The most complete open-source webhook delivery platform with full-feature-parity self-hosting.** SSPL-1.0 licensed, no closed tier. **Outbound webhooks** with multi-tenant label-based filtering, HMAC signatures, fixed escalating backoff retries capped by max retries + window, **dead letter queue** (failed attempts kept and replayable), dot-notation event type hierarchy, delivery logs and replay, REST API, and **SDKs for JS, Rust, Python, Go, Ruby, PHP, C#, Java, Kotlin, Lua, and Zig**. Authentication via Biscuit tokens + service tokens. EU data plane available . |
| **[Outpost (Hookdeck)](https://github.com/hookdeck/outpost)** | [![Stars](https://img.shields.io/github/stars/hookdeck/outpost?style=social&color=white)](https://github.com/hookdeck/outpost/stargazers) | **Production-ready self-hosted outbound webhook and event destinations infrastructure.** Apache-2.0, Go binary/Docker. Supports **Webhooks, Amazon EventBridge, AWS SQS, AWS SNS, GCP Pub/Sub, RabbitMQ, and Kafka** as destinations. Features: at-least-once delivery, event fanout, automatic and manual retries, **multi-tenant support**, **user portal** (white-label React) for customers to view metrics and debug deliveries, delivery failure alerts, OpenTelemetry traces/metrics/logs, and **webhook best practices** (idempotency headers, timestamp, signature rotation) opt-out. SDKs for Go, Python, TypeScript; ships with MCP server . |
| **[Svix](https://github.com/svix/svix-webhooks)** | [![Stars](https://img.shields.io/github/stars/svix/svix-webhooks?style=social&color=white)](https://github.com/svix/svix-webhooks/stargazers) | **Hosted webhook service with an open-source Rust server (MIT core).** Self-hosting is **open-core**—the OSS version has limited features; supported on-prem requires Enterprise. Features: Standard Webhooks signing (svix-* names), automatic pause after 5 days of failures, replay (single message, failed from date, or missing), event types with schemas, channels, JS transformations, and receiver portal (iframe/React, white-label from Pro). SDKs for JS, Python, Go, Ruby, Java. Raised **$17M**—not self-funded . |
| **[Convoy](https://github.com/frain-dev/convoy)** | [![Stars](https://img.shields.io/github/stars/frain-dev/convoy?style=social&color=white)](https://github.com/frain-dev/convoy/stargazers) | **Go-based webhook gateway with dashboard.** Self-hosted or cloud. Features: own `X-Convoy-Signature` scheme (not Standard Webhooks), configurable linear/exponential backoff per project, dead endpoints when `disable_endpoint` is on plus circuit breaker on paid plans, replay (single delivery or filtered batch), event catalogue (Premium), and JS transforms (Premium). **Elastic License v2.0**—paid features behind license key . |

### Additional Strong Open-Source Options

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[good-webhooks](https://github.com/pplytas/good-webhooks)** | [![Stars](https://img.shields.io/github/stars/pplytas/good-webhooks?style=social&color=white)](https://github.com/pplytas/good-webhooks/stargazers) | **Outbox-pattern webhook library** (MIT). `publish()` joins your database transaction—no separate outbox table. Standard Webhooks signing (HMAC-SHA256), 8 retries over ~28 hours with `Retry-After` on 429/503, automatic pause after 5 days of failures or 410, replay (single delivery or page), PostgreSQL storage. **Library, not a service**—you integrate it into your application . |
| **[dhook](https://pub.dev/packages/dhook)** | — | **Lightweight self-hosted webhook relay for local development** (alternative to smee.io). Deploy server on a VPS with public IP; run client locally connecting via WebSocket. Forwards cloud webhooks to `localhost` in real-time. API key auth, Docker deployment, Dart package. Useful for developing webhook integrations without paid tunneling services . |

**Frameworks for building custom systems**: For **outbound webhooks** (sending to your customers), choose **Hook0** for full-feature-parity self-hosting with multi-tenant filtering , **Outpost** for production-ready delivery to multiple destination types (queues, brokers, buses) with a customer portal , or **good-webhooks** for an outbox-pattern library that joins your transaction . For **inbound webhooks** (receiving from providers), **Hookdeck Event Gateway** is the dedicated ingress proxy (closed-source, but Outpost is its open-source outbound counterpart) , or use **Postman webhook listeners** for development and debugging with scripting and replay . For **API gateways**, **Kong OSS** or **Tyk Gateway** provide the routing and policy layer—but note that **API gateways do not natively validate webhook HMAC signatures**; you need custom authorizers or a dedicated webhook ingress layer .

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- API gateways and webhook services handle authentication tokens and sensitive event payloads; enforce least-privilege policies, HMAC signature validation, and idempotent processing (most providers guarantee "at-least-once" delivery—duplicates are normal, not edge cases) .
- **API Gateways are not webhook ingress.** Gateways handle routing and auth but lack native HMAC validation, durable queueing, exponential backoff, dead-letter queues, and replay UIs—building these on AWS typically means stitching together API Gateway + Lambda authorizers + SQS/EventBridge + DynamoDB + Step Functions + custom frontend . **Open-source webhook infrastructure is genuinely viable**: Hook0 offers full-feature-parity self-hosting with no closed tier , Outpost provides production-ready outbound delivery with multi-tenant portals and multiple destination types , and good-webhooks offers an outbox-pattern library for teams wanting to own the delivery logic . **Licensing varies**: Hook0 is SSPL-1.0 (not OSI-approved, but source-available with full self-hosting), Outpost is Apache-2.0, Convoy is Elastic License v2.0, and Svix is open-core with limited OSS features . Validate licensing compatibility with your organization's policies before committing.

---

**Made for API engineers, platform teams, and developers building reliable webhook infrastructure.**  
Let's make REST API and webhook services more open, reliable, and developer-friendly.
