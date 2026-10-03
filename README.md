# Awesome EmDash [![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> A curated list of awesome resources, plugins, themes, developer tools, guides, and Astro integrations for **[EmDash CMS](https://emdashcms.com/)** — the open-source, agent-native, full-stack TypeScript CMS built on Astro and Cloudflare.

<br>

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./assets/emdash-dark-mode.svg">
    <img alt="EmDash CMS Logo" src="./assets/emdash-light-mode.svg" width="380">
  </picture>
</div>

<br>

EmDash is the spiritual successor to WordPress: an open-source, full-stack content management system designed for the modern web. Built as a native Astro integration with a built-in admin panel (`/_emdash/admin`), it combines the blazing speed of Astro's component-driven frontend with edge-native database persistence (Cloudflare D1 / SQLite), object storage (Cloudflare R2 / local disk), sandboxed plugins powered by Cloudflare Dynamic Workers / `workerd`, a decentralized AT Protocol plugin registry, and first-class Model Context Protocol (MCP) server support for AI coding agents.

---

## Contents

- [Official Resources](#official-resources)
- [Architecture & Concepts](#architecture--concepts)
- [Cloudflare AI Tools & MCP Ecosystem](#cloudflare-ai-tools--mcp-ecosystem)
  - [Official AI Tools & MCP Servers](#official-ai-tools--mcp-servers)
  - [Cloudflare Workers AI Integrations](#cloudflare-workers-ai-integrations)
  - [Community Agent Tools & Plugins](#community-agent-tools--plugins)
- [In The Wild (Real-World Sites)](#in-the-wild-real-world-sites)
- [Starters & Templates](#starters--templates)
  - [Official Starters](#official-starters)
  - [Community Starters & Themes](#community-starters--themes)
- [Plugins](#plugins)
  - [Official First-Party Plugins](#official-first-party-plugins)
  - [SEO, Analytics & Discovery](#seo-analytics--discovery)
  - [Email & Notifications](#email--notifications)
  - [Forms & Submissions](#forms--submissions)
  - [E-Commerce, Payments & Memberships](#e-commerce-payments--memberships)
  - [Authentication & Access Control](#authentication--access-control)
  - [Accessibility & Privacy](#accessibility--privacy)
  - [Content, Media & Integrations](#content-media--integrations)
- [Astro Ecosystem Synergy](#astro-ecosystem-synergy)
  - [UI Framework Adapters](#ui-framework-adapters)
  - [Styling & UI Systems](#styling--ui-systems)
  - [SEO, Media & Performance](#seo-media--performance)
  - [Content & Search](#content--search)
- [Developer Tools & Tooling](#developer-tools--tooling)
- [Deployment & Operations](#deployment--operations)
  - [Deployment Guides](#deployment-guides)
  - [Docker & Containerized](#docker--containerized)
- [Migration from WordPress](#migration-from-wordpress)
  - [Guides & Concept Mapping](#guides--concept-mapping)
  - [Migration Tools](#migration-tools)
- [Articles, Case Studies & Media](#articles-case-studies--media)
  - [Official Cloudflare Engineering & Announcement Posts](#official-cloudflare-engineering--announcement-posts)
  - [EmDash Team Technical Deep Dives](#emdash-team-technical-deep-dives)
  - [Community & Industry Analyses](#community--industry-analyses)
  - [Tutorials & Courses](#tutorials--courses)
  - [Video Walkthroughs & Interviews](#video-walkthroughs--interviews)
- [Community & Support](#community--support)
- [Contributing](#contributing)

---

## Official Resources

- [Website](https://emdashcms.com/) — Official EmDash homepage and product highlights.
- [Documentation](https://docs.emdashcms.com/) — Comprehensive documentation, API references, and guides.
- [Documentation Index (`llms.txt`)](https://docs.emdashcms.com/llms.txt) — Machine-readable documentation index optimized for AI agents and LLMs.
- [GitHub Monorepo](https://github.com/emdash-cms/emdash) — Core monorepo containing the engine, admin UI, official plugins, and CLI.
- [npm Organization](https://www.npmjs.com/org/emdash-cms) — Official npm packages (`@emdash-cms/*`).
- [EmDash Build](https://build.emdashcms.com/) ([GitHub](https://github.com/emdash-cms/emdash-build)) — Open-source AI chat interface for building and previewing EmDash sites in Cloudflare Sandboxes.
- [Online Playground](https://try.emdashcms.com/) — Instant in-browser interactive demo of the EmDash admin panel.
- [Plugin Registry & Store](https://plugins.emdashcms.com/) — Official registry browser for finding and installing plugins.
- [EmDash Blog](https://emdashcms.com/blog) — Official release announcements, deep dives, and architectural tutorials.
- [EmDash Starter Prompt (`start.md`)](https://emdashcms.com/start.md) — Official prompt bootstrapping instruction file for autonomous coding agents.

---

## Architecture & Concepts

- [Why EmDash?](https://docs.emdashcms.com/why-emdash/) — Core philosophy, rationale for building on Astro, and architectural design principles.
- [Architecture Overview](https://docs.emdashcms.com/concepts/architecture/) — Technical anatomy of EmDash, edge execution model, and runtime flow.
- [Content Model](https://docs.emdashcms.com/concepts/content-model/) — Schema-driven content modeling, collections, fields, and taxonomies.
- [Collections](https://docs.emdashcms.com/concepts/collections/) — Guide to structuring and defining collections in EmDash.
- [The Admin Panel](https://docs.emdashcms.com/concepts/admin-panel/) — Architecture and layout of the integrated `/_emdash/admin` panel.
- [Content Lifecycle](https://docs.emdashcms.com/reference/content-lifecycle/) — State transitions, drafting, revisions, publication events, and hooks.
- [Field Types](https://docs.emdashcms.com/reference/field-types/) — Complete reference of primitive and composite field types supported by collection schemas.
- [Plugin Sandboxing & Capabilities](https://docs.emdashcms.com/plugins/creating-plugins/capabilities/) — Capability-based security model using Cloudflare Dynamic Workers and `workerd` isolates.
- [AT Protocol Plugin Registry](https://docs.emdashcms.com/plugins/registry/) — Architecture of the decentralized, federated plugin distribution system.

---

## Cloudflare AI Tools & MCP Ecosystem

### Official AI Tools & MCP Servers

- [EmDash Build](https://build.emdashcms.com/) ([GitHub](https://github.com/emdash-cms/emdash-build)) ([Launch Post](https://emdashcms.com/blog/emdash-build)) — Open-source AI chat interface for generating full-stack EmDash sites using Cloudflare Sandboxes, Durable Objects, and git-backed Artifacts.
- [EmDash Docs MCP Server](https://docs.emdashcms.com/docs-mcp/) (`https://docs.emdashcms.com/mcp`) — Official remote MCP server powered by Cloudflare AI Search over the complete EmDash documentation.
- [Built-In Site Content MCP Server](https://docs.emdashcms.com/reference/mcp-server/) (`/_emdash/api/mcp`) — First-class site endpoint allowing AI assistants to query and manage collections, schemas, media, taxonomies, and menus.
- [Official Agent Skills](https://github.com/emdash-cms/skills) ([Docs](https://docs.emdashcms.com/agent-skills/)) — Repository of official agent skills for site scaffolding, plugin development, CLI automation, and WordPress migrations.
- [Agent Bootstrapping Prompt (`start.md`)](https://emdashcms.com/start.md) — Official prompt specification instructing coding agents to inspect requirements, build collections, and verify sites.
- [AI Tools Integration Guide](https://docs.emdashcms.com/guides/ai-tools/) — Documentation guide to connecting EmDash with MCP clients, editor extensions, and autonomous workflows.

### Cloudflare Workers AI Integrations

- [`@emdash-cms/plugin-ai-moderation`](https://github.com/emdash-cms/emdash/tree/main/packages/plugins/ai-moderation) — Edge content and comment moderation powered by Cloudflare Workers AI (Llama Guard).
- [enhancely-emdash](https://github.com/enhancely/enhancely-emdash) — AI-powered JSON-LD structured data and entity schema generator.
- [pixelseo-emdash-plugin](https://github.com/codebiwan/pixelseo-emdash-plugin) — Automated AI image generation pipeline piping generated assets into the EmDash media library.
- [emdash-ai-search](https://github.com/theweekendprojects/emdash-ai-search) — Drop-in semantic vector search and AI chat bar powered by Cloudflare AI Search and Workers AI.

### Community Agent Tools & Plugins

- [emdash-claude-plugin](https://github.com/EngDawood/emdash-claude-plugin) — Claude Code plugin equipping Claude with site-building subagents and Cloudflare EmDash workflows.
- [emdash-skills](https://github.com/OziNetworkVN/emdash-skills) — Community skill library and agent workflows for building and maintaining EmDash with AI.
- [jdevalk/skills](https://github.com/jdevalk/skills) — Multi-agent skill bundle covering EmDash plugins, Astro integration, WordPress migration, and SEO.
- [emdash-akari](https://github.com/bnomei/emdash-akari) — Agent-focused discovery CLI for inspecting nested content structures and JSON models.
- [migrate-site-skill](https://github.com/Iceberg-Media/migrate-site-skill) — AI agent skill scaffold for converting legacy sites into Astro + EmDash.
- [n8n-nodes-emdash](https://github.com/BlackSwampAI/n8n-nodes-emdash) ([npm](https://www.npmjs.com/package/@blackswampai/n8n-nodes-emdash)) — Community n8n nodes for automating publishing workflows and managing EmDash collections.

---

## In The Wild (Real-World Sites)

- [The Cloudflare Blog](https://blog.cloudflare.com/) — Cloudflare’s global engineering and corporate blog. Migrated to EmDash ahead of Agents Week, serving millions of pageviews globally via Cloudflare Workers and D1.
- [EmDash Official Marketing & Documentation Site](https://emdashcms.com/) ([Source Code](https://github.com/emdash-cms/emdashcms.com)) — Official EmDash homepage and Starlight documentation site, self-hosted on EmDash and Astro.
- [astro-emdash-sqlite-r2-starter](https://github.com/milzamsz/astro-emdash-sqlite-r2-starter) — Open-source marketing, blog, and documentation stack featuring SQLite + Cloudflare R2 storage, full-text search, and typed Astro pages.
- [mise](https://github.com/mo3moha/mise) — Reservation and booking application for hospitality businesses, built on Astro 6 + EmDash + Cloudflare D1 with multi-language i18n and automated customer emails.
- [emdash_property_web_builder](https://github.com/RealEstateWebTools/emdash_property_web_builder) — Production real-estate website builder and property catalog management CMS.
- [By the Boys Bakery](https://github.com/jamesqquick/by-the-boys-bakery) — Production micro-bakery storefront built with Astro, EmDash CMS, Tailwind v4, and shadcn on Cloudflare.
- [engineerlab.jp](https://www.engineerlab.jp) ([Source Code](https://github.com/al17091/blog-emdash)) — Japanese engineering blog running Astro SSR + EmDash with PostgreSQL, deployed via Helm on Kubernetes (K3s).
- [v5.satooru.me](https://v5.satooru.me) ([Source Code](https://github.com/SatooRu65536/v5.satooru.me)) — Personal profile site built on the official EmDash Cloudflare portfolio template.
- [Tony Ciencia](https://github.com/tinychef/tonyciencia-blog) — Official bilingual science and editorial blog running on Astro 6 + EmDash CMS + Cloudflare Workers.
- [hytech3](https://github.com/hyrorre/hytech3) — Personal tech blog built on the Cloudflare Workers blog template.
- [sk-personal-website](https://github.com/therealsamyak/sk-personal-website) — Developer portfolio and blog powered by EmDash.
- [modern-emdash-cms](https://github.com/EngDawood/modern-emdash-cms) — Bilingual Arabic/English portfolio on EmDash, Cloudflare Workers, and the built-in MCP server.
- [EmDash Build](https://build.emdashcms.com/) ([Source Code](https://github.com/emdash-cms/emdash-build)) — AI-powered chat website builder running on Cloudflare Agents SDK, Sandboxes, and Workers for Platforms.
- [Empress](https://tryempress.dev) — Platform for multi-brand entities managing a fleet of EmDash sites with natural language or a conventional CMS admin panel.
- [EmDash Interactive Playground](https://try.emdashcms.com/) — Ephemeral in-browser sandbox running a live EmDash admin panel for instant evaluation.

---

## Starters & Templates

### Official Starters

Maintained in the [emdash-cms/emdash](https://github.com/emdash-cms/emdash/tree/main/templates) monorepo and mirrored at [emdash-cms/templates](https://github.com/emdash-cms/templates):

- [blog](https://github.com/emdash-cms/emdash/tree/main/templates/blog) — Editorial blog template with categories, tags, author bylines, FTS search, and RSS (Node.js/SQLite).
- [blog-cloudflare](https://github.com/emdash-cms/emdash/tree/main/templates/blog-cloudflare) — Edge-native editorial blog running on Cloudflare Workers, D1, and R2.
- [marketing](https://github.com/emdash-cms/emdash/tree/main/templates/marketing) — Product marketing site with hero sections, feature grids, pricing tiers, and contact forms (Node.js/SQLite).
- [marketing-cloudflare](https://github.com/emdash-cms/emdash/tree/main/templates/marketing-cloudflare) — High-concurrency edge marketing starter on Cloudflare Workers and D1.
- [portfolio](https://github.com/emdash-cms/emdash/tree/main/templates/portfolio) — Portfolio and showcase template for designers and developers with project galleries (Node.js/SQLite).
- [portfolio-cloudflare](https://github.com/emdash-cms/emdash/tree/main/templates/portfolio-cloudflare) — Edge portfolio template optimized for fast image delivery via Cloudflare R2.
- [starter](https://github.com/emdash-cms/emdash/tree/main/templates/starter) — Clean starter template with a curated seed dataset for rapid prototyping (Node.js/SQLite).
- [starter-cloudflare](https://github.com/emdash-cms/emdash/tree/main/templates/starter-cloudflare) — Minimal starter configured for Cloudflare Workers, D1 database, and R2 storage bindings.
- [blank](https://github.com/emdash-cms/emdash/tree/main/templates/blank) — Barebones boilerplate with EmDash core and Astro server configuration.

### Community Starters & Themes

- [astro-emdash-sqlite-r2-starter](https://github.com/milzamsz/astro-emdash-sqlite-r2-starter) — Self-hostable marketing, blog, and docs starter featuring SQLite + Cloudflare R2, typed Astro pages, FTS, and SEO.
- [mise](https://github.com/mo3moha/mise) — Reservation and booking starter built on Astro + Cloudflare Workers + D1, with full internationalization (i18n) and automated email flows.
- [Themes on the EmDash Plugin Registry](https://plugins.emdashcms.com/) — Official registry catalog where free and commercial themes and plugins are distributed.
- [Lexington Themes](https://lexingtonthemes.com/templates/astro-emdash-templates) — 44 polished Astro themes with EmDash variants, complete with reusable components and built-in content collections.
- [emdash-theme-mainstreet](https://github.com/ecropolis/emdash-theme-mainstreet) — Service-business theme with services, pricing, team, hours, booking CTAs, and the no-code Compass Customizer.
- [emdash-theme-supper](https://github.com/ecropolis/emdash-theme-supper) — Restaurant theme with structured menus, dietary flags, hours, gallery, reviews, and reservation CTAs.
- [Bravada for Astro](https://github.com/vhscom/emdash-theme-bravada) — Astro + EmDash port of Cryout Creations' popular Bravada magazine and editorial WordPress theme.
- [Masthead](https://github.com/ondelva/astro-theme-masthead) — Newspaper-style publication and editorial news theme for EmDash and Astro (MIT).
- [Persona Bio](https://github.com/ahmetcigsar/emdash-theme-persona-bio) — Personal profile, portfolio, and micro-blogging theme for creators (MIT).
- [star-lite-docs](https://github.com/gruntlord5/star-lite-docs) — Starlight-style technical documentation experience powered by EmDash collections with visual in-browser editing.
- [emdash-template-switcher](https://github.com/pk1983/emdash-template-switcher) — Admin-switchable site templates using an interactive CLI.
- [emdash_property_web_builder](https://github.com/RealEstateWebTools/emdash_property_web_builder) — Real estate website builder and property catalog CMS template.
- [emdash-templates by Majestic Labs](https://github.com/majesticlabs-dev/emdash-templates) — Collection of modern starter templates for business and agency sites.
- [compose-cli](https://github.com/Compose-Project/compose-cli) — Command-line scaffolding tool for the Compose blank template.

---

## Plugins

EmDash supports both sandboxed plugins (isolated Workers/`workerd` environments with capability permissions) and native plugins (npm packages with React admin UI extensions). See the [Plugin Overview](https://docs.emdashcms.com/plugins/overview/) and [Choosing a Plugin Format](https://docs.emdashcms.com/plugins/creating-plugins/choosing-a-format/) guides.

### Official First-Party Plugins

Maintained in the [emdash packages/plugins](https://github.com/emdash-cms/emdash/tree/main/packages/plugins) directory:

- [`@emdash-cms/plugin-ai-moderation`](https://github.com/emdash-cms/emdash/tree/main/packages/plugins/ai-moderation) — Automated content and comment moderation powered by Cloudflare Workers AI (Llama Guard).
- [`@emdash-cms/plugin-atproto`](https://github.com/emdash-cms/emdash/tree/main/packages/plugins/atproto) — Syndication and federation to the AT Protocol network and standard.site.
- [`@emdash-cms/plugin-audit-log`](https://github.com/emdash-cms/emdash/tree/main/packages/plugins/audit-log) — Audit trail tracking all editorial and administrative changes across the CMS.
- [`@emdash-cms/plugin-color`](https://github.com/emdash-cms/emdash/tree/main/packages/plugins/color) — Color picker field widget for visual design controls in the admin.
- [`@emdash-cms/plugin-embeds`](https://github.com/emdash-cms/emdash/tree/main/packages/plugins/embeds) — Rich oEmbed embed blocks (YouTube, Vimeo, Bluesky, X/Twitter, Mastodon, Spotify).
- [`@emdash-cms/plugin-field-kit`](https://github.com/emdash-cms/emdash/tree/main/packages/plugins/field-kit) — Composable field widgets for JSON attributes (dynamic lists, key-value maps, object forms, tag pickers).
- [`@emdash-cms/plugin-forms`](https://github.com/emdash-cms/emdash/tree/main/packages/plugins/forms) — Form builder with customizable fields, spam protection, entry storage, and webhook alerts.
- [`@emdash-cms/plugin-troubleshooting`](https://github.com/emdash-cms/plugin-troubleshooting) — Diagnostics and runtime troubleshooting tool for inspecting object caching, KV keys, and runtime state.
- [`emdash-cms/blob-proxy`](https://github.com/emdash-cms/blob-proxy) — High-performance AT Protocol image and media blob proxy built on Cloudflare Workers Cache.
- [`@emdash-cms/plugin-webhook-notifier`](https://github.com/emdash-cms/emdash/tree/main/packages/plugins/webhook-notifier) — Dispatches HTTP webhooks to external services whenever content is created, updated, or published.

### SEO, Analytics & Discovery

- [emdash-plugin-seo (jdevalk)](https://github.com/jdevalk/emdash-plugin-seo) — Comprehensive Yoast-style SEO suite: Open Graph, Twitter Cards, canonical links, robots rules, and JSON-LD schema.
- [emdash-plugin-seo (DreamsEngine)](https://github.com/DreamsEngine/emdash-plugin-seo) — AI-assisted SEO analysis tool with on-page optimization recommendations.
- [emdash-auto-meta](https://github.com/marcusbellamyshaw-cell/emdash-auto-meta) — AI-generated SEO titles, meta descriptions, image alt texts, and automated taxonomy tagging.
- [emdash-plugin-analytics (MosierData)](https://github.com/MosierData/emdash-plugin-analytics) — Google Tag Manager, GA4, Search Console tracking, UTM attribution, and call tracking.
- [emdash-plugin-analytics (eisbachcode)](https://github.com/eisbachcode/emdash-plugin-analytics) ([npm](https://www.npmjs.com/package/@eisbachcode/emdash-plugin-analytics)) — Cloudflare Web Analytics on the EmDash dashboard with per-entry view counters and MCP tools.
- [SerpDelta](https://github.com/SerpDelta/emdash-plugin) — Google Search Console keyword and ranking shift tracking directly in the dashboard.
- [em-content-insights](https://github.com/facuzarate04/em-content-insights) — Privacy-respecting post analytics (read depth, read rate, average time on page, referrers).
- [em-analytics-hub](https://github.com/facuzarate04/em-analytics-hub) — Privacy-first analytics suite with custom conversion funnels, goals, and campaign attribution.
- [enhancely-emdash](https://github.com/enhancely/enhancely-emdash) — AI-generated structured data and JSON-LD Schema.org graph builder.
- [aeo-ultimate-emdash](https://github.com/tampawebtech/aeo-ultimate-emdash) — Answer Engine Optimization (AEO) and semantic knowledge graph for AI search agents.
- [plugin-ai-discovery](https://github.com/awesomeem/plugin-ai-discovery) — Generates machine-readable `llms.txt`, agent manifests, and semantic discovery links.
- [emdash-human-sitemap](https://github.com/masonjames/emdash-human-sitemap) — Visual, accessible sitemap block and Astro component for human visitors.
- [sph-emdash-plugin-sitemap-rebuild](https://github.com/merrickma/sph-emdash-plugin-sitemap-rebuild) — Automatically dispatches background sitemap rebuilds upon publishing content.

### Email & Notifications

- [emdash-plugin-cloudflare-email](https://github.com/velvee-ai/emdash-plugin-cloudflare-email) — Native Cloudflare Email Routing & Sending using direct Workers bindings (no external API keys).
- [emdash-plugin-resend](https://github.com/maikunari/emdash-plugin-resend) — Transactional and marketing email delivery via the Resend API.
- [emdash-plugin-postmark](https://github.com/drudge/emdash-plugin-postmark) — Fast, deliverable transactional email delivery through Postmark.
- [emdash-plugin-brevo](https://github.com/marcusbellamyshaw-cell/emdash-plugin-brevo) — Transactional email and marketing automation delivery via Brevo (formerly Sendinblue).
- [emdash-aws-ses](https://github.com/AB6162/emdash-aws-ses) — Amazon Simple Email Service (SES) SMTP transport.
- [emdash-postal](https://github.com/undefined-charity/emdash-postal) — Integration with self-hosted Postal mail servers for privacy-conscious applications.
- [emdash-mailing-list](https://github.com/WoofyIO/emdash-mailing-list) — Lightweight newsletter and mailing list management with double opt-in and Markdown broadcasts.
- [emdash-plugin-lettermint](https://github.com/jdevalk/emdash-plugin-lettermint) — Lettermint email service integration.
- [emdash-plugin-anymail](https://github.com/nexed-tech/emdash-plugin-anymail) ([npm](https://www.npmjs.com/package/emdash-plugin-anymail)) — Universal HTTP email dispatcher connecting Maileroo, Mailgun, Postmark, and Resend via lightweight fetch calls.
- [emdash-plugin-twilio-sms](https://github.com/Full-Stack-Tech/emdash-plugin-twilio-sms) — Twilio SMS plugin with broadcast messaging, STOP/opt-out compliance, delivery webhooks, and a form-submission bridge.

### Forms & Submissions

- [emdash-forms-builder](https://github.com/hassantafreshi/emdash-forms-builder) — Drag-and-drop form creator with custom validation rules and field types.
- [emdash-freeform](https://github.com/solspace/emdash-freeform) — Advanced form creation suite for multi-step workflows.
- [emdash-contact-forms](https://github.com/masonjames/emdash-contact-forms) — Clean contact form system with Turnstile bot protection.
- [emdash-inbox](https://github.com/proverbiallemon/emdash-inbox) — Admin mailbox UI for reviewing and responding to form submissions directly in EmDash.
- [emdash-cloudflare-form](https://github.com/tmyuu/emdash-cloudflare-form) — Contact form handler with Cloudflare Turnstile CAPTCHA and Cloudflare Email transport.

### E-Commerce, Payments & Memberships

- [DashCommerce](https://github.com/emdashCommerce/dashcommerce) ([npm](https://www.npmjs.com/package/@dashcommerce/core)) — Full-featured, WooCommerce-equivalent commerce plugin for EmDash on Cloudflare Workers and D1.
- [Otta by Urumi](https://urumi.ai/otta-is-the-ecommerce-plugin-for-cloudflares-em-dash) ([GitHub](https://github.com/UrumiAI/otta.sh)) — Open-source commerce layer for EmDash with a Node/Hono backend handling catalogs, cart, checkout, payments, and inventory; the first eCommerce plugin for the platform.
- [emdash-lms](https://github.com/tohaitrieu/emdash-lms) ([npm](https://www.npmjs.com/package/emdash-lms)) — Learning management system plugin supporting courses, memberships, quizzes, and digital certificates.
- [emdashlearn](https://github.com/emdash-learn/emdashlearn) — Open-source LMS plugin providing courses, lessons, and student progress tracking on the edge.

### Authentication & Access Control

- [emdash-better-auth](https://github.com/theweekendprojects/emdash-better-auth) ([npm](https://www.npmjs.com/package/emdash-better-auth)) — Email/password and social (Google, GitHub) authentication powered by Better Auth, with prebuilt sign-in/sign-up pages and email verification.
- [emdash-plugin-password-auth](https://github.com/feronera/emdash-plugin-password-auth) — Turnkey email and password sign-in for the admin with first-admin setup, self-service change, and password reset (PBKDF2 via Web Crypto).
- [@hellocoop/emdash](https://github.com/hellocoop/emdash) ([npm](https://www.npmjs.com/package/@hellocoop/emdash)) — Hellō passwordless login and OpenID Connect identity provider integration.

### Accessibility & Privacy

- [emdash-plugin-a11y](https://github.com/Full-Stack-Tech/emdash-plugin-a11y) — WCAG 2.2 AA accessibility auditing that reports contrast, structure, and media issues directly in the admin editor.
- [emdash-plugin-cookie-consent](https://github.com/adrianoamalfi/emdash-plugin-cookie-consent) — Customizable GDPR/CCPA cookie consent banner with category-level opt-in, theming, and an admin settings panel.

### Content, Media & Integrations

- [obsidian-pensieve-publisher](https://github.com/deathemperor/obsidian-pensieve-publisher) — Publish notes and articles directly from Obsidian to your EmDash CMS.
- [emdash-fields](https://github.com/bnomei/emdash-fields) ([npm](https://www.npmjs.com/package/@bnomei/emdash-fields)) — Structured JSON field editors for collections: nested objects, structures, links, and choices.
- [emcanvas](https://github.com/emcanvas/emcanvas) — Visual canvas drag-and-drop page builder for EmDash entries and landing pages.
- [emdash-plugin-puck](https://github.com/markoinla/emdash-plugin-puck) ([npm](https://www.npmjs.com/package/emdash-plugin-puck)) — Embeds the Puck visual page builder as an EmDash field widget with media library integration and optional AI layout generation.
- [emdash-notion](https://github.com/kjfsm/emdash-notion) ([npm](https://www.npmjs.com/package/@emdash-notion/sync)) — Webhook synchronization of Notion pages and databases into EmDash collections as Portable Text.
- [emdash-plugin-katex](https://github.com/ibnutoriq/emdash-plugin-katex) ([npm](https://www.npmjs.com/package/emdash-plugin-katex)) — Server-rendered LaTeX math and equation blocks powered by KaTeX.
- [emdash-plugin-linguadash](https://github.com/swissky/emdash-plugin-linguadash) ([npm](https://www.npmjs.com/package/emdash-plugin-linguadash)) — Content localization and translation plugin supporting DeepL, Google Translate, and OpenAI models.
- [emdash-plugin-modern-images](https://github.com/adrianoamalfi/emdash-plugin-modern-images) — Converts uploaded media to modern WebP/AVIF formats with responsive srcset delivery, disk caching, and LCP preload support.
- [emdash-syntax-highlighter](https://github.com/masonjames/emdash-syntax-highlighter) — Server-side syntax highlighting for Portable Text code blocks in Astro templates.
- [plugdash](https://github.com/plugdash/plugdash) — Modular utilities monorepo: callouts, Shiki codeblocks, dynamic tables of contents, reading time, Open Graph social cards, shortlinks, and build webhooks.
- [pixelseo-emdash-plugin](https://github.com/codebiwan/pixelseo-emdash-plugin) — Generate AI-crafted featured images and save them directly into the EmDash Media Library.
- [emdash-render](https://github.com/awesomeem/emdash-render) — Direct D1 reader and Portable Text renderer for ultra-low latency edge consumption (Hono / Cloudflare Workers).
- [emdash-taki](https://github.com/bnomei/emdash-taki) — Head waterfall preloading and dynamic resource optimizations for Astro + Cloudflare.

---

## Astro Ecosystem Synergy

Because EmDash is a standard Astro integration running with `output: "server"`, the Astro ecosystem works seamlessly out-of-the-box.

### UI Framework Adapters

Render interactive UI components inside your Astro templates alongside EmDash content:

- [`@astrojs/react`](https://docs.astro.build/en/guides/integrations-guide/react/) — Required for EmDash admin extensions and React admin widgets; powers frontend islands.
- [`@astrojs/vue`](https://docs.astro.build/en/guides/integrations-guide/vue/) — Build frontend widgets and interactive components with Vue 3 SFCs.
- [`@astrojs/svelte`](https://docs.astro.build/en/guides/integrations-guide/svelte/) — Ultra-lightweight reactive components for dynamic UI islands.
- [`@astrojs/solid-js`](https://docs.astro.build/en/guides/integrations-guide/solid-js/) — High-performance reactive islands.
- [`@astrojs/preact`](https://docs.astro.build/en/guides/integrations-guide/preact/) — 3KB lightweight alternative to React for customer-facing pages.

### Styling & UI Systems

- [`@astrojs/tailwind`](https://docs.astro.build/en/guides/integrations-guide/tailwind/) / Tailwind CSS — Utility-first styling for frontend templates and custom Portable Text blocks.
- [shadcn/ui](https://ui.shadcn.com/) — Beautifully designed React components that pair cleanly with `@astrojs/react` in EmDash themes.
- [UnoCSS](https://unocss.dev/integrations/astro) — Instant on-demand atomic CSS engine.

### SEO, Media & Performance

- [astro-seo](https://github.com/jonasmerlin/astro-seo) — Open-source component to easily inject Open Graph, Twitter Cards, and canonical tags into Astro layouts.
- [`@astrojs/sitemap`](https://docs.astro.build/en/guides/integrations-guide/sitemap/) — Automatic XML sitemap generation for all static and dynamically rendered routes.
- [astro-icon](https://github.com/natemoo-re/astro-icon) — Icon component supporting thousands of icon sets from Iconify (Lucide, Ph, Heroicons).
- [sharp](https://sharp.pixelplumbing.com/) — High-speed image transformation engine used by Astro's native `<Image />` component during server-side rendering.

### Content & Search

- [Portable Text Tooling (`@portabletext/react` / `@portabletext/to-html`)](https://github.com/portabletext/portabletext) — Render EmDash's structured JSON rich-text fields into accessible HTML or styled React components.
- [Pagefind](https://pagefind.app/) — Client-side search engine providing fast full-text search with zero server overhead.
- [`@astrojs/mdx`](https://docs.astro.build/en/guides/integrations-guide/mdx/) — Coexist file-based developer-owned documentation/MDX with editor-managed EmDash collections.

---

## Developer Tools & Tooling

- [EmDash CLI](https://docs.emdashcms.com/reference/cli/) — Official command-line utility for project scaffolding, schema migrations, and database seeding.
- [create-emdash](https://www.npmjs.com/package/create-emdash) — Official `npm create emdash` scaffolding CLI for bootstrapping new EmDash + Astro projects in seconds.
- [Plugin CLI](https://docs.emdashcms.com/plugins/creating-plugins/cli/) — Tooling for testing, bundling, capability validation, and publishing plugins to the AT Protocol registry.
- [Registry Client](https://docs.emdashcms.com/plugins/registry-client/) — Client library for programmatic querying and resolution against the AT Protocol plugin registry.
- [`@emdash-cms/registry-loader`](https://github.com/emdash-cms/emdash/tree/main/packages/registry-loader) — Astro live content loader for embedding plugin registry listings in any Astro site.
- [`@emdash-cms/x402`](https://www.npmjs.com/package/@emdash-cms/x402) — Official HTTP 402 payment protocol handler for building agentic, paid-per-call API endpoints.
- [emdash-run](https://github.com/joeblew999/emdash-run) — Fast local runner for EmDash development using `mise` and `pitchfork`.
- [emdash-platform-wfp](https://github.com/scottbuscemi/emdash-platform-wfp) — Multi-tenant prompt-to-site generator built on Cloudflare Workers for Platforms + EmDash.
- [emdash-plugin-github-backup](https://github.com/dennisklappe/emdash-plugin-github-backup) — Backs up collection content to a GitHub repository on every edit for file-based Git versioning.

---

## Deployment & Operations

### Deployment Guides

- [Deploy to Cloudflare](https://docs.emdashcms.com/deployment/cloudflare/) — Official guide for deploying EmDash to Cloudflare Workers, D1 database, and R2 storage.
- [Deploy to Node.js](https://docs.emdashcms.com/deployment/nodejs/) — Self-hosting guide for standard Linux VPS, Fly.io, Railway, and Render with SQLite or LibSQL.
- [Database Options](https://docs.emdashcms.com/deployment/database/) — Configuration guide for Cloudflare D1, local SQLite (`better-sqlite3`), and LibSQL/Turso.
- [Storage Options](https://docs.emdashcms.com/deployment/storage/) — Setting up Cloudflare R2 or local filesystem asset storage.
- [Object Cache](https://docs.emdashcms.com/deployment/object-cache/) — Edge caching setup with Cloudflare KV or in-memory caches.
- [Plugin Sandbox Configuration](https://docs.emdashcms.com/deployment/plugin-sandbox/) — Configuring Dynamic Workers and `workerd` runtime isolate sandboxing.
- [Core Database Migrations](https://docs.emdashcms.com/deployment/core-migrations/) — Running and managing database schema updates in production.
- [Schema Evolution](https://docs.emdashcms.com/deployment/schema-evolution/) — Best practices for evolving content schemas and seed data on deployed sites.
- [Secrets & Key Management](https://docs.emdashcms.com/deployment/secrets/) — Managing environment variables, API tokens, and runtime secrets.
- [Backups & Restore](https://docs.emdashcms.com/guides/backups/) — Creating snapshot backups and restoring database and media state.
- [Site Transfer](https://docs.emdashcms.com/guides/site-transfer/) — Exporting and importing full site data across environments.

### Docker & Containerized

- [emdash-docker (MarianSEO)](https://github.com/MarianSEO/emdash-docker) — Production-ready Docker Compose stack running EmDash with automated SQLite backups.
- [emdash-docker (rubengmez)](https://github.com/rubengmez/emdash-docker) — Multi-architecture OCI images automatically rebuilt against upstream EmDash releases.
- [docker-emdash (jstgnkl)](https://github.com/jstgnkl/docker-emdash) — Clean Dockerfile configuration for building self-hosted EmDash images.
- [EmdashDeploy](https://github.com/web-casa/EmdashDeploy) — Interactive VPS deployment script featuring automated Docker setup, Caddy reverse proxy, and backup utilities.

---

## Migration from WordPress

### Guides & Concept Mapping

- [EmDash for WordPress Developers](https://docs.emdashcms.com/coming-from/wordpress/) — Conceptual mapping of WordPress paradigms (post types, hooks, themes) to EmDash and Astro.
- [Astro for WordPress Developers](https://docs.emdashcms.com/coming-from/astro-for-wp-devs/) — Primer on Astro templates, components, and zero-JS frontend architecture for PHP developers.
- [Migrate from WordPress](https://docs.emdashcms.com/migration/from-wordpress/) — Step-by-step guide to migrating content, media, taxonomies, and users from WordPress to EmDash.
- [Content Import](https://docs.emdashcms.com/migration/content-import/) — Technical reference on importing structured content and JSON seed files into EmDash.
- [Porting WordPress Plugins](https://docs.emdashcms.com/migration/porting-plugins/) — Guide for translating WordPress actions, filters, and admin settings into EmDash sandboxed plugins and hooks.
- [Porting WordPress Themes](https://docs.emdashcms.com/themes/porting-wp-themes/) — Strategies for converting PHP theme templates and block patterns into Astro components.

### Migration Tools

- [wp-emdash](https://github.com/emdash-cms/wp-emdash) — Official companion WordPress plugin to export posts, pages, users, media, and taxonomies into EmDash seed format.
- [wp2emdash](https://github.com/sibukixxx/wp2emdash) — Community WordPress export converter and Unix-philosophy CLI orchestrator producing ready-to-import EmDash collections.
- [`@emdash-cms/gutenberg-to-portable-text`](https://www.npmjs.com/package/@emdash-cms/gutenberg-to-portable-text) — Official AST parser converting WordPress Gutenberg blocks into Portable Text JSON.
- [hatena-to-emdash](https://github.com/ochanuco/hatena-to-emdash) — CLI tool to convert Hatena Blog Movable Type exports into EmDash-ready Markdown.
- [emdash-mt-import](https://github.com/kennyg/emdash-mt-import) — CLI importer translating standard Movable Type blog archives into EmDash seed JSON.

---

## Articles, Case Studies & Media

### Official Cloudflare Engineering & Announcement Posts

- [The Cloudflare Blog — Brought to you by EmDash (Cloudflare Blog, Aug 24, 2026)](https://blog.cloudflare.com/cloudflare-blog-uses-emdash/) — In-depth engineering case study detailing how Cloudflare migrated its primary corporate blog to EmDash as "Customer Zero", serving millions of live pageviews and withstanding DDoS attacks.
- [EmDash 1.0: the stable CMS with a secure plugin registry (Cloudflare Blog, Sept 28, 2026)](https://blog.cloudflare.com/emdash-cms-plugin-registry/) — Cloudflare's official stable 1.0 release announcement covering production readiness, sandboxed plugins, and the decentralized AT Protocol plugin registry.
- [Introducing EmDash — the spiritual successor to WordPress that solves plugin security (Cloudflare Blog, April 1, 2026)](https://blog.cloudflare.com/emdash-wordpress/) — The original launch post introducing the beta of EmDash as an open-source successor to WordPress running in sandboxed Worker isolates.

### EmDash Team Technical Deep Dives

- [EmDash Build: an open source AI site builder (EmDash Blog, Sept 28, 2026)](https://emdashcms.com/blog/emdash-build) — Launch article by Noah Pham explaining the Agents SDK, Cloudflare Sandboxes, and git-backed Artifacts for prompt-based site creation.
- [Ship your plugin to the EmDash plugin registry (EmDash Blog, Sept 28, 2026)](https://emdashcms.com/blog/emdash-plugin-registry) — Practical guide by Scott Buscemi on AT Protocol signed publishing, Atmosphere accounts, and `@emdash-cms/plugin-cli`.
- [EmDash 1.0: an open source CMS for Astro (EmDash Blog, Sept 28, 2026)](https://emdashcms.com/blog/emdash-1-0) — Comprehensive 1.0 architecture overview by creator Matt Kane on why EmDash was built on Astro and how sandboxing eliminates security hazards.
- [EmDash is live (EmDash Blog, April 28, 2026)](https://emdashcms.com/blog/emdash-is-live) — First public release announcement detailing the 0.x roadmap and agent capabilities.

### Community & Industry Analyses

- [EmDash CMS by Cloudflare — The Open-Source TypeScript Successor to WordPress (WP Poland, 2026)](https://wppoland.com/en/emdash-cloudflare-open-source-cms-wordpress-successor-2026/) — Architectural deep-dive comparing WordPress security vulnerabilities with EmDash's modern model.
- [EmDash CMS vs WordPress: An Honest Benchmark (SHIFT64, 2026)](https://shift64.com/blog/emdash-cms-vs-wordpress-honest-benchmark) ([Benchmark Suite](https://github.com/mateusz-zadorozny/shift64-emdash-cms-benchmark)) — Empirical comparison with 4,732 measurements covering latency, TTFB, memory usage, and throughput of EmDash on Cloudflare Workers versus WordPress on a VPS.
- [6 Reasons Why Cloudflare's EmDash Can't Compete With WordPress (Search Engine Journal, April 2026)](https://www.searchenginejournal.com/reasons-cloudflare-emdash-cant-compete-wordpress/543165/) — Roger Montti's analysis of EmDash's early developer-centric positioning versus WordPress's established consumer ecosystem.

### Tutorials & Courses

- [tzu-chi-vibe-coding-emdash](https://github.com/phoenix581228/tzu-chi-vibe-coding-emdash) — Complete university curriculum artifact for teaching Vibe Coding with EmDash, including a course site, student starter kits, demo sites, and agent skills (MIT).

### Video Walkthroughs & Interviews

- [EmDash: The WordPress Successor That Fixes Plugin Security (Cloudflare TV)](https://cloudflare.tv/this-week-in-net/emdash-the-wordpress-successor-that-fixes-plugin-security/5vpEE7aP) — This Week in NET interview with the EmDash engineering team covering the project's origins, Astro integration, and Dynamic Workers isolation.
- [What Everyone Missed About EmDash (James Q Quick)](https://www.youtube.com/watch?v=hgOJH9bp75k) — Architectural analysis of why Cloudflare's sandboxed Dynamic Workers eliminate traditional CMS plugin vulnerabilities.
- [EmDash + Astro: The CMS Combo That Could Power Your Next Site (WPTuts)](https://www.youtube.com/watch?v=RTrbg5z_UBk) — Detailed walkthrough of the EmDash 1.0 admin interface, content modeling, and Astro frontend pairing.
- [WordPress is COOKED — Long Live EmDash! (WPTuts)](https://www.youtube.com/watch?v=0vmxzhRsZQI) — Hands-on first look exploring admin navigation, schema generation, and comparisons with WordPress developer workflows.
- [Cloudflare Just Killed WordPress?! (Mehul Mohan / codedamn)](https://www.youtube.com/watch?v=sBXC63ULDAE) — Technical overview of EmDash's architecture, serverless performance, and implications for modern web development.

---

## Community & Support

- [Discord](https://discord.gg/YY9vBaQRYt) — Active community of developers, contributors, and the core team.
- [Bluesky (@emdashcms.com)](https://bsky.app/profile/emdashcms.com) — Official announcements and AT Protocol updates.
- [X / Twitter (@EmDashCMS)](https://x.com/EmDashCMS) — Product updates, feature showcases, and tutorials.
- [GitHub Discussions](https://github.com/emdash-cms/emdash/discussions) — Ask questions, suggest features, and share your projects.

---

## Contributing

Contributions are warmly welcome! Please check out [CONTRIBUTING.md](CONTRIBUTING.md) for details on formatting, submission rules, and inclusion criteria.

If you find a broken link or want to suggest a new plugin, template, or guide, feel free to open a Pull Request!
