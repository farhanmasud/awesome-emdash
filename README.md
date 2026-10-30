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
  - [Official Guides & How-Tos](#official-guides--how-tos)
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
  - [Forms, Surveys & CRM](#forms-surveys--crm)
  - [E-Commerce, Payments & Memberships](#e-commerce-payments--memberships)
  - [Authentication & Access Control](#authentication--access-control)
  - [Security & Site Protection](#security--site-protection)
  - [Accessibility & Privacy](#accessibility--privacy)
  - [Content, Media & Integrations](#content-media--integrations)
  - [Page & Visual Builders](#page--visual-builders)
  - [Editorial Workflow & Maintenance](#editorial-workflow--maintenance)
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

### Official Guides & How-Tos

- [Upgrade to EmDash 1.0](https://docs.emdashcms.com/upgrade-to-v1/) — Official migration guide covering removed `0.x` APIs, `cacheCloudflare()`, `emdash/internal/` entrypoints, and capability renames.
- [Update EmDash (`upgrade-emdash`)](https://docs.emdashcms.com/deployment/updating/) — Operator guide for upgrading `emdash` and `@emdash-cms/*` packages using `npx upgrade-emdash@latest` and `.emdash/UPGRADE.md` agent work orders.
- [Move to a New Domain](https://docs.emdashcms.com/guides/change-domain/) — Step-by-step guide to migrating an EmDash site to a new domain from the admin while preserving passkey sign-in and updating canonicals/sitemaps.
- [Internationalization (i18n)](https://docs.emdashcms.com/guides/internationalization/) — Official guide to configuring multi-locale collections, translated content entries, and localized admin bundles (`admin.locales`).
- [Atmosphere Login](https://docs.emdashcms.com/guides/atmosphere-auth/) — Configuring decentralized AT Protocol / Atmosphere account authentication in EmDash.
- [x402 Payments](https://docs.emdashcms.com/guides/x402-payments/) — Official guide to monetizing content and agentic endpoints with HTTP 402 payment requirements.
- [EmDash for Astro Developers](https://docs.emdashcms.com/coming-from/astro/) — Guide for existing Astro developers adding EmDash live collections, server rendering, and admin routes to Astro projects.
- [Block Kit](https://docs.emdashcms.com/plugins/creating-plugins/block-kit/) — Reference for building declarative admin UI pages, forms, and dashboard widgets inside sandboxed plugins.
- [Automated Plugin Releases](https://docs.emdashcms.com/plugins/creating-plugins/delegated-releases/) — Setting up delegated AT Protocol package profiles and GitHub Actions workflows with `emdash-plugin release setup`.
- [Migrating to the Plugin CLI](https://docs.emdashcms.com/plugins/creating-plugins/migrating-to-the-cli/) — Guide for migrating sandboxed plugins to `@emdash-cms/plugin-cli`, `emdash-plugin.jsonc`, and the `SandboxedPlugin` type.
- [Upgrading Plugins on Your Site](https://docs.emdashcms.com/plugins/upgrading-sites/) — Operator instructions for updating first-party and third-party plugins to the 1.x default-export convention.
- [AI Search Plugin](https://docs.emdashcms.com/plugins/ai-search/) — Official guide to adding Cloudflare AI Search to an EmDash site with the first-party AI Search plugin.
- [Route Caching](https://docs.emdashcms.com/deployment/route-caching/) — Caching rendered pages with Astro route caching, with EmDash invalidating them by tag when content changes.

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
- [emdash-plugin-ai-alt-text](https://github.com/DavidPivert/emdash-plugin-ai-alt-text) ([Registry](https://plugins.emdashcms.com/plugins/@lasymphonieagency.com/ai-alt-text)) — Sandboxed plugin that generates localized image alt text with Claude directly from the EmDash media library.
- [`@writealt/emdash-writealt`](https://www.npmjs.com/package/@writealt/emdash-writealt) — Native EmDash plugin for automated AI alt-text generation and in-place image optimization.
- [emdash-injectai](https://github.com/muzammildafedar/emdash-injectai) — Adds Retrieval-Augmented Generation (RAG) chatbot support across uploaded files and collections.

### Community Agent Tools & Plugins

- [emdash-claude-plugin](https://github.com/EngDawood/emdash-claude-plugin) — Claude Code plugin equipping Claude with site-building subagents and Cloudflare EmDash workflows.
- [emdash-skills](https://github.com/OziNetworkVN/emdash-skills) — Community skill library and agent workflows for building and maintaining EmDash with AI.
- [jdevalk/skills](https://github.com/jdevalk/skills) — Multi-agent skill bundle covering EmDash plugins, Astro integration, WordPress migration, and SEO.
- [emdash-akari](https://github.com/bnomei/emdash-akari) — Agent-focused discovery CLI for inspecting nested content structures and JSON models.
- [migrate-site-skill](https://github.com/Iceberg-Media/migrate-site-skill) — AI agent skill scaffold for converting legacy sites into Astro + EmDash.
- [n8n-nodes-emdash](https://github.com/BlackSwampAI/n8n-nodes-emdash) ([npm](https://www.npmjs.com/package/@blackswampai/n8n-nodes-emdash)) — Community n8n nodes for automating publishing workflows and managing EmDash collections.
- [ChangeWard](https://github.com/mirza-rizvi/ChangeWard) — Content integrity and change-monitoring plugin with MCP tools that logs modifications, monitors protected pages, and blocks rule-violating publishes.
- [LLMs.txt Publisher (`@agenticecom.net/llms-txt`)](https://plugins.emdashcms.com/plugins/@agenticecom.net/llms-txt) — Sandboxed registry plugin that generates an `llms.txt` index and companion Markdown pages to help AI agents navigate published site content.
- [EdgeEver Sync (`@otscup.bsky.social/edgeever-sync`)](https://plugins.emdashcms.com/plugins/@otscup.bsky.social/edgeever-sync) — Synchronizes EdgeEver memos into EmDash blog posts over MCP.
- [EmDash Preflight (`@jammaru.com/preflight`)](https://plugins.emdashcms.com/plugins/@jammaru.com/preflight) — Enforces deterministic publishing policies across human editors, REST API, MCP, autonomous agents, and scheduled publishes.
- [Tracy](https://github.com/TracyHQ/tracy) ([Website](https://tracy.ai)) — AI agent that edits running EmDash, WordPress, and Joomla sites through natural language, with diff review and rollback.
- [emdash-vibe-editor](https://www.npmjs.com/package/emdash-vibe-editor) — Front-end "vibe editing" for EmDash: click text and images on the live site and edit them with AI.
- [lynx-emdash](https://github.com/realmag777/lynx-emdash) — Bulk content editor and AI-agent tools for EmDash.

---

## In The Wild (Real-World Sites)

- [The Cloudflare Blog](https://blog.cloudflare.com/) — Cloudflare’s global engineering and corporate blog. Migrated to EmDash ahead of Agents Week, serving millions of pageviews globally via Cloudflare Workers and D1.
- [EmDash Official Marketing & Documentation Site](https://emdashcms.com/) ([Source Code](https://github.com/emdash-cms/emdashcms.com)) — Official EmDash homepage and Starlight documentation site, self-hosted on EmDash and Astro.
- [astro-emdash-sqlite-r2-starter](https://github.com/milzamsz/astro-emdash-sqlite-r2-starter) — Open-source marketing, blog, and documentation stack featuring SQLite + Cloudflare R2 storage, full-text search, and typed Astro pages.
- [mise](https://github.com/mo3moha/mise) — Reservation and booking application for hospitality businesses, built on Astro 6 + EmDash + Cloudflare D1 with multi-language i18n and automated customer emails.
- [emdash_property_web_builder](https://github.com/RealEstateWebTools/emdash_property_web_builder) — Production real-estate website builder and property catalog management CMS.
- [By the Boys Bakery](https://github.com/jamesqquick/by-the-boys-bakery) — Production micro-bakery storefront built with Astro, EmDash CMS, Tailwind v4, and shadcn on Cloudflare.
- [engineerlab.jp](https://www.engineerlab.jp) ([Source Code](https://github.com/al17091/blog-emdash)) — Japanese engineering blog running Astro SSR + EmDash with PostgreSQL, deployed via Helm on Kubernetes (K3s).
- [v5.satooru.me](https://github.com/SatooRu65536/v5.satooru.me) — Personal profile site built on the official EmDash Cloudflare portfolio template (source only; the live domain is currently offline).
- [Tony Ciencia](https://github.com/tinychef/tonyciencia-blog) — Official bilingual science and editorial blog running on Astro 6 + EmDash CMS + Cloudflare Workers.
- [hytech3](https://github.com/hyrorre/hytech3) — Personal tech blog built on the Cloudflare Workers blog template.
- [sk-personal-website](https://github.com/therealsamyak/sk-personal-website) — Developer portfolio and blog powered by EmDash.
- [modern-emdash-cms](https://github.com/EngDawood/modern-emdash-cms) — Bilingual Arabic/English portfolio on EmDash, Cloudflare Workers, and the built-in MCP server.
- [biancafiore.me](https://biancafiore.me) ([Source Code](https://github.com/fbuireu/biancafiore)) — Portfolio and blog of content writer Bianca Fiore running Astro SSR on Cloudflare Workers with EmDash CMS, Turso, Drizzle ORM, and Resend.
- [seanbehan.ca](https://seanbehan.ca) ([Source Code](https://github.com/codebam/seanbehan.ca)) — Personal developer website and blog built with Astro, TypeScript, and EmDash CMS.
- [theweekendprojects.com](https://theweekendprojects.com) ([Source Code](https://github.com/theweekendprojects/landing-page)) — Official site and blog for The Weekend Projects running on EmDash CMS, Astro, and Cloudflare Workers.
- [blog.melvinjonesrepol.com](https://blog.melvinjonesrepol.com) ([Source Code](https://github.com/mrepol742/blog)) — Minimal personal engineering blog built with EmDash and deployed on Cloudflare Workers with D1 and R2.
- [suntory-n-water.com](https://suntory-n-water.com) ([Source Code](https://github.com/Suntory-N-Water/sui-blog)) — Personal tech blog powered by EmDash CMS and Astro.
- [EmDash Build](https://build.emdashcms.com/) ([Source Code](https://github.com/emdash-cms/emdash-build)) — AI-powered chat website builder running on Cloudflare Agents SDK, Sandboxes, and Workers for Platforms.
- [Empress](https://tryempress.dev) — Platform for multi-brand entities managing a fleet of EmDash sites with natural language or a conventional CMS admin panel.
- [EmDash Interactive Playground](https://try.emdashcms.com/) — Ephemeral in-browser sandbox running a live EmDash admin panel for instant evaluation.
- [jbolabs/sites](https://github.com/jbolabs/sites) — Client marketing sites built with Astro and EmDash on Cloudflare Workers, deployed with Alchemy.
- [serhiichernenko.com/blog](https://serhiichernenko.com/blog) ([Source Code](https://github.com/serhii-chernenko/portfolio-blog)) — Personal portfolio blog powered by EmDash.
- [balasto](https://balasto.vercel.app) ([Source Code](https://github.com/vladyn/balasto)) — B2B website built with EmDash and Astro.
- [yansir-repo/emdash-blog](https://github.com/yansir-repo/emdash-blog) — Chinese B2B-inquiry blog migrated from Next.js to EmDash on Astro and Cloudflare.

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
- [terrasuite-emdash](https://github.com/havenswift-hosting/terrasuite-emdash) ([Live Demo](https://emdash.terrasuite.uk)) — Estate agency and real-estate site template for EmDash featuring a property collection, fast filtered search, and agency landing pages.
- [DashCommerce Starter](https://github.com/emdashCommerce/starter) ([Live Demo](https://demo.dashcommerce.dev)) — Official Astro + EmDash e-commerce storefront starter template for `@dashcommerce/core`.
- [emdash-theme-omarchy](https://github.com/siygle/emdash-theme-omarchy) — Omarchy-inspired blog theme for EmDash featuring Hyprland tiling window aesthetics, a Waybar top bar, and Omarchy color palettes.
- [emdash-railway](https://github.com/aimranov27/emdash-railway) — Railway deployment starter template for EmDash CMS backed by PostgreSQL, featuring a locked setup wizard and automated tested updates.
- [astro-emdash-libsql-r2-starter](https://github.com/milzamsz/astro-emdash-libsql-r2-starter) — Production-ready Astro + EmDash starter for Dokploy with native libSQL/Turso and Cloudflare R2 storage.
- [emdash-admin-theme-classic](https://github.com/marks-zyz/emdash-admin-theme-classic) ([npm](https://www.npmjs.com/package/emdash-admin-theme-classic)) — Classic `wp-admin` design token and layout geometry theme for the EmDash admin panel without core patching.
- [DinkusKit Store / Services / Marketing Starters](https://github.com/dinkuskit/template-store) ([Services](https://github.com/dinkuskit/template-services), [Marketing](https://github.com/dinkuskit/template-marketing)) — Astro + EmDash starter templates for storefronts, service businesses, and marketing sites.
- [`@wptom/cms-emdash`](https://www.npmjs.com/package/@wptom/cms-emdash) — Content loader and seed generator mapping EmDash collections, fields, and block types to WPTom Astro templates.
- [emdash-template-switcher](https://github.com/pk1983/emdash-template-switcher) — Admin-switchable site templates using an interactive CLI.
- [emdash_property_web_builder](https://github.com/RealEstateWebTools/emdash_property_web_builder) — Real estate website builder and property catalog CMS template.
- [emdash-templates by Majestic Labs](https://github.com/majesticlabs-dev/emdash-templates) — Collection of modern starter templates for business and agency sites.
- [compose-cli](https://github.com/Compose-Project/compose-cli) — Command-line scaffolding tool for the Compose blank template.
- [Baseline](https://github.com/Vermeulen-Solutions/baseline) — Agent-first web starter for Astro and EmDash with a shared fluid design system and "Platform Profiles" for EmDash relational content.
- [Kexi](https://github.com/AK-103U/kexi) — Modern Cloudflare-native blog theme built on Astro and EmDash (Chinese-language docs).
- [Holly Template](https://github.com/Whitney-Bateson-Digital-Strategy/Template_Holly-Astro-EmDash_Websites) ([Live Demo](https://template-holly-astro-em-dash-websit.vercel.app)) — Agency website template built on Astro and EmDash.
- [astro-emdash-local-workshop](https://github.com/pwlee-xyz/astro-emdash-local-workshop) — Local-first Astro and EmDash portfolio starter designed for workshops.
- [emdash-easy-setup](https://github.com/kwonq10/emdash-easy-setup) — Beginner-oriented Claude Code skill for trying EmDash locally on Windows (Japanese).

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
- [emdash-schema-identity](https://github.com/monprez/emdash-schema-identity) — Structured data, Schema.org JSON-LD, and E-E-A-T author/organization credentials plugin for EmDash sites.
- [emdash-plugin-indexnow](https://github.com/jesseagleboy/emdash-plugin-indexnow) ([npm](https://www.npmjs.com/package/emdash-plugin-indexnow)) — Automatically pings IndexNow-participating search engines whenever EmDash pages or events are published or unpublished.
- [Instant Indexer (`@peachfinthemes.com/instant-indexer`)](https://plugins.emdashcms.com/plugins/@peachfinthemes.com/instant-indexer) — Sandboxed registry plugin that notifies search engines via IndexNow when public pages change.
- [emdash-plugin-indexnow (tagperfect)](https://github.com/tagperfect/emdash-plugin-indexnow) ([npm](https://www.npmjs.com/package/@tagperfect/emdash-plugin-indexnow)) ([Registry](https://plugins.emdashcms.com/plugins/@tagperfect.eu/indexnow)) — Sends URLs to IndexNow on publish, update, unpublish and delete, with per-locale URL rules, a submission log and a dashboard widget.
- [SEO & Schema Markup (`@moorage.dev/seo`)](https://github.com/moorage-dev/moorage) ([Registry](https://plugins.emdashcms.com/plugins/@moorage.dev/seo)) — Yoast-style SEO plugin with JSON-LD structured data, Google SERP preview, SEO checks, `noindex` controls, and WordPress redirect imports.
- [SEO Suite (`@nookeshk.bsky.social/seo-suite`)](https://plugins.emdashcms.com/plugins/@nookeshk.bsky.social/seo-suite) — Focus-keyphrase analysis, readability scoring, JSON-LD schema, redirect management, and SEO health checks.
- [Page SEO Inspector (`@agenticecom.net/rendered-seo-inspector`)](https://plugins.emdashcms.com/plugins/@agenticecom.net/rendered-seo-inspector) — Inspects rendered page metadata (titles, descriptions, headings, social tags) to flag missing or inconsistent SEO output.
- [seo-guard (`@eclipsedigi.bsky.social/seo-guard`)](https://plugins.emdashcms.com/plugins/@eclipsedigi.bsky.social/seo-guard) ([GitHub](https://github.com/Eclipse-Digital-Inc/emdash-plugins)) — Pre-publish guardrail that blocks publishing posts failing basic SEO checks (title/description length, featured image, slug).
- [Umami Analytics (`@shane.bsky.shas.am/emdash-umami-analytics`)](https://plugins.emdashcms.com/plugins/@shane.bsky.shas.am/emdash-umami-analytics) — Displays Umami traffic metrics, top pages, referrers, and per-entry view counts inside the EmDash admin.
- [`@plukio/emdash-analytics`](https://www.npmjs.com/package/@plukio/emdash-analytics) — Native EmDash plugin that tracks first-party analytics events and routes them to PostHog and GA4.
- [emdash-plugin-openanalytics](https://github.com/BlackSwampAI/emdash-plugin-openanalytics) — Native EmDash CMS integration for OpenAnalytics.
- [Crosslink (`@meekmedia.bsky.social/crosslink`)](https://plugins.emdashcms.com/plugins/@meekmedia.bsky.social/crosslink) — Real-time internal link suggestions while writing, orphan page reports, and a related-posts JSON route.
- [Post Views (`@desidashlab.bsky.social/post-views`)](https://plugins.emdashcms.com/plugins/@desidashlab.bsky.social/post-views) — Privacy-first self-hosted post view counter for the admin dashboard and editor.
- [Dynamic QR (`@nookeshk.bsky.social/dynamic-qr`)](https://plugins.emdashcms.com/plugins/@nookeshk.bsky.social/dynamic-qr) — Generates customizable dynamic QR codes with scan analytics in EmDash.
- [emdash-seo-core](https://github.com/masonjames/emdash-seo-core) — Lightweight subset-first SEO metadata plugin for EmDash CMS.
- [statistics-em](https://github.com/6arshid/statistics-em) — Real-time visit analytics plugin tracking daily and historical page view breakdowns.
- [emdash-umami (tdhftw)](https://github.com/tdhftw/emdash-umami) — Umami analytics dashboard inside the EmDash admin, for self-hosted Umami or Umami Cloud.
- [jp-search](https://github.com/Ghost3nexus/emdash-jp-search) ([Registry](https://plugins.emdashcms.com/plugins/@tomorrowproof-ai.com/jp-search)) — Japanese bigram site search for Node deployments where built-in FTS5 search cannot run.

### Email & Notifications

- [emdash-plugin-cloudflare-email](https://github.com/velvee-ai/emdash-plugin-cloudflare-email) — Native Cloudflare Email Routing & Sending using direct Workers bindings (no external API keys).
- [emdash-plugin-resend](https://github.com/maikunari/emdash-plugin-resend) — Transactional and marketing email delivery via the Resend API.
- [emdash-plugin-postmark](https://github.com/drudge/emdash-plugin-postmark) — Fast, deliverable transactional email delivery through Postmark.
- [emdash-aws-ses](https://github.com/AB6162/emdash-aws-ses) — Amazon Simple Email Service (SES) SMTP transport.
- [emdash-postal](https://github.com/undefined-charity/emdash-postal) — Integration with self-hosted Postal mail servers for privacy-conscious applications.
- [emdash-mailing-list](https://github.com/WoofyIO/emdash-mailing-list) — Lightweight newsletter and mailing list management with double opt-in and Markdown broadcasts.
- [emdash-plugin-lettermint](https://github.com/jdevalk/emdash-plugin-lettermint) — Lettermint email service integration.
- [emdash-plugin-anymail](https://github.com/nexed-tech/emdash-plugin-anymail) ([npm](https://www.npmjs.com/package/emdash-plugin-anymail)) — Universal HTTP email dispatcher connecting Maileroo, Mailgun, Postmark, and Resend via lightweight fetch calls.
- [emdash-plugin-twilio-sms](https://github.com/Full-Stack-Tech/emdash-plugin-twilio-sms) — Twilio SMS plugin with broadcast messaging, STOP/opt-out compliance, delivery webhooks, and a form-submission bridge.
- [emdash-mailerlite](https://github.com/ecommerceave/emdash-mailerlite) ([Registry](https://plugins.emdashcms.com/plugins/@ecommerceave.com/emdash-mailerlite)) — MailerLite integration displaying subscribers, groups, campaign reports, and signup forms in the EmDash dashboard.
- [emdash-resend-email](https://github.com/vcode-sh/emdash-resend-email) ([npm](https://www.npmjs.com/package/emdash-resend-email), [Registry](https://plugins.emdashcms.com/plugins/@vcode.sh/resend)) — Resend email provider plugin handling magic links, user invites, account recovery, and plugin emails.
- [Forward Email (`@numoteq.com/forward-email`)](https://github.com/numoteq/js-packages) ([Registry](https://plugins.emdashcms.com/plugins/@numoteq.com/forward-email)) — Transactional email delivery for EmDash via the Forward Email HTTP API.
- [emdash-smtp](https://github.com/masonjames/emdash-smtp) ([npm](https://www.npmjs.com/package/emdash-smtp), [Registry](https://plugins.emdashcms.com/plugins/@masonjames.com/emdash-smtp)) — Full-parity SMTP and transactional email plugin with sender settings, fallback delivery, and private delivery logs.
- [Bulletin (`@meekmedia.bsky.social/bulletin`)](https://plugins.emdashcms.com/plugins/@meekmedia.bsky.social/bulletin) — Privacy-first newsletter subscriber manager with double opt-in and one-click post-to-email broadcasts.
- [emdash-discord-notifier](https://github.com/raghuchinnannan/emdash-discord-notifier) ([Registry](https://plugins.emdashcms.com/plugins/@raghuchinnannan.bsky.social/discord-notifier)) — Sends Discord webhook notifications and digests for published posts, comments, media uploads, and form submissions.
- [emdash-plugin-comment-notify](https://github.com/DavidPivert/emdash-plugin-comment-notify) ([Registry](https://plugins.emdashcms.com/plugins/@lasymphonieagency.com/comment-notify)) — Sandboxed plugin that emails site administrators when new comments are posted or held for moderation.
- [emdash-plugin-slack](https://github.com/lsngmin/emdash-plugin-slack) ([npm](https://www.npmjs.com/package/emdash-plugin-slack)) — Slack notification integration alerting teams when EmDash content is published.
- [emdash-plugin-compass-mail](https://github.com/ecropolis/emdash-plugin-compass-mail) — Email transport plugin delivering EmDash system and form emails through SendGrid or Resend.
- [emdash-plugin-emailit](https://github.com/dennisklappe/emdash-plugin-emailit) — Transactional email transport plugin powered by Emailit.
- [WhatsApp Chat Button (`@desidashlab.bsky.social/whatsapp-chat`)](https://plugins.emdashcms.com/plugins/@desidashlab.bsky.social/whatsapp-chat) ([npm](https://www.npmjs.com/package/@sneaps/whatsapp-chat)) — Floating click-to-chat WhatsApp button for EmDash sites.
- [emdash-resend](https://github.com/creimer808/emdash-resend) — Resend email provider configured from the admin settings page.
- [emdash-plugin-apimail](https://www.npmjs.com/package/@devbitme/emdash-plugin-apimail) — Transactional email over provider HTTP APIs: Brevo, Mailgun, Mailjet, Maileroo, Postmark, Mailchimp Transactional and more.
- [emdash-light-smtp](https://github.com/apsulis/emdash-light-smtp) ([npm](https://www.npmjs.com/package/@apsulis/emdash-light-smtp)) — Light, hardened SMTP provider for self-hosted Node.js EmDash with mandatory TLS.

### Forms, Surveys & CRM

- [emdash-forms-builder](https://github.com/hassantafreshi/emdash-forms-builder) — Drag-and-drop form creator with custom validation rules and field types.
- [emdash-freeform](https://github.com/solspace/emdash-freeform) — Advanced form creation suite for multi-step workflows.
- [emdash-inbox](https://github.com/proverbiallemon/emdash-inbox) — Admin mailbox UI for reviewing and responding to form submissions directly in EmDash.
- [emdash-cloudflare-form](https://github.com/tmyuu/emdash-cloudflare-form) — Contact form handler with Cloudflare Turnstile CAPTCHA and Cloudflare Email transport.
- [`@gatilab/emdash-core-forms`](https://www.npmjs.com/package/@gatilab/emdash-core-forms) — HTML-first forms plugin (port of WordPress Core Forms) with AJAX and no-JS submission, Turnstile spam protection, email/webhook actions, and a submissions inbox.
- [Forms (`@netdollar.dev/forms`)](https://plugins.emdashcms.com/plugins/@netdollar.dev/forms) — Contact forms, surveys, and multi-step forms with conditional logic, entry management, CSV export, and email alerts.
- [Contact Forms (`@bitdoze.com/emdashhq-contact-forms`)](https://plugins.emdashcms.com/plugins/@bitdoze.com/emdashhq-contact-forms) — Embeddable contact form builder with submission storage and site email provider delivery.
- [WB Polls (`@vapvarun.bsky.social/polls`)](https://plugins.emdashcms.com/plugins/@vapvarun.bsky.social/polls) — Interactive polls and voting blocks with single-vote enforcement and live result displays.
- [Product Roadmap (`@vapvarun.bsky.social/roadmap`)](https://plugins.emdashcms.com/plugins/@vapvarun.bsky.social/roadmap) — Public product roadmap and feature voting board with a shipped changelog.
- [Lead Follow-Up Desk (`@agenticecom.net/lead-desk`)](https://plugins.emdashcms.com/plugins/@agenticecom.net/lead-desk) — Lightweight sales CRM inside EmDash for tracking lead ownership, pipeline stages, follow-up dates, and private notes.
- [`@quickprice/emdash-leads`](https://www.npmjs.com/package/@quickprice/emdash-leads) — Interactive QuickPrice lead capture form block for EmDash sites.
- [action-pages](https://github.com/adpena/action-pages) ([npm](https://www.npmjs.com/package/@adpena/action-pages)) — Composable campaign action pages (petitions, fundraising, signups, CRM) running edge-native on Cloudflare Workers.
- [semics Events & E-sign](https://github.com/semics-uk/emdash-plugins) ([Events](https://plugins.emdashcms.com/plugins/@semics.co.uk/semics-events), [E-sign](https://plugins.emdashcms.com/plugins/@semics.co.uk/semics-esign)) — Free MIT event booking and ticketing, plus simple electronic signatures.

### E-Commerce, Payments & Memberships

- [DashCommerce](https://github.com/emdashCommerce/dashcommerce) ([npm](https://www.npmjs.com/package/@dashcommerce/core)) — Full-featured, WooCommerce-equivalent commerce plugin for EmDash on Cloudflare Workers and D1.
- [Otta by Urumi](https://urumi.ai/otta-is-the-ecommerce-plugin-for-cloudflares-em-dash) ([GitHub](https://github.com/UrumiAI/otta.sh)) — Open-source commerce layer for EmDash with a Node/Hono backend handling catalogs, cart, checkout, payments, and inventory; the first eCommerce plugin for the platform.
- [emdash-lms](https://github.com/tohaitrieu/emdash-lms) ([npm](https://www.npmjs.com/package/emdash-lms)) — Learning management system plugin supporting courses, memberships, quizzes, and digital certificates.
- [emdashlearn](https://github.com/emdash-learn/emdashlearn) — Open-source LMS plugin providing courses, lessons, and student progress tracking on the edge.
- [milo-emdash](https://www.npmjs.com/package/milo-emdash) — Sell subscriptions, memberships, one-off digital products, and protected downloads on EmDash with Stripe, coupons, taxes, and a member portal.
- [emdash-paid-access](https://github.com/masonjames/emdash-paid-access) — Stripe memberships and HTTP `x402` pay-per-read content paywall plugin for EmDash with an Astro companion component.
- [emdash-stripe-checkout](https://github.com/ecommerceave/emdash-stripe-checkout) ([Registry](https://plugins.emdashcms.com/plugins/@ecommerceave.com/emdash-stripe-checkout)) — Turnkey Stripe Checkout payment integration for EmDash stores.
- [dashcommerce-mercadopago](https://github.com/Jorguitouy/dashcommerce-mercadopago) — Mercado Pago (Checkout Pro) payment gateway provider for DashCommerce supporting Latin American storefronts.
- [Coffer (formerly EmDash-MoneroPay)](https://github.com/dwightsabeast/coffer) — Privacy-focused cryptocurrency payment plugin accepting Monero. Work in progress — not yet ready to take real payments.
- [emdash-kaspa-x402-adapter](https://github.com/KaspaScopio/emdash-kaspa-x402-adapter) — Community HTTP `x402` payment adapter integrating the Kaspa network with EmDash.
- [emdash-plugin-medusa](https://github.com/BlackSwampAI/emdash-plugin-medusa) — Native EmDash CMS plugin for live Medusa v2 commerce product references.
- [wscommerce](https://github.com/wsagency/wscommerce) — MIT-licensed EmDash commerce plugin on Cloudflare Workers with Stripe, Solo, e-racuni, and a WooCommerce REST compatibility layer.
- [emCommerce](https://github.com/cdurth/emCommerce) — E-commerce catalog and checkout plugin for EmDash CMS.
- [emdash-mika](https://github.com/bnomei/emdash-mika) ([npm](https://www.npmjs.com/package/@bnomei/emdash-mika)) — Agent-ready commerce primitives, cart state, digital downloads, and WebMCP storefront tools for EmDash.
- [DinkusKit Commerce Suite (`dinkus-commerce`, `dinkus-payments`, `inventory`, `coupons`, `bundles`)](https://plugins.emdashcms.com/plugins/@smokyco.bsky.social/dinkus-commerce) ([Payments](https://plugins.emdashcms.com/plugins/@smokyco.bsky.social/dinkus-payments), [Inventory](https://github.com/dinkuskit/inventory), [Coupons](https://github.com/dinkuskit/coupons), [Bundles](https://github.com/dinkuskit/bundles)) — Modular commerce kit for EmDash covering product catalogs, immutable inventory ledgers, BOGO promotions, mix-and-match bundles, and Stripe payments.
- [Carte](https://github.com/foreztgump/carte) — Restaurant commerce plugin family for EmDash featuring digital menus, table reservations, and Stripe online ordering.
- [Sella](https://github.com/codelified/Sella) — Shopify-like commerce for EmDash with a native plugin, storefront theme, and one-command scaffolder.
- [Coldtill Crypto Payments](https://github.com/Coldtill/emdash-crypto-payment-gateway) ([Registry](https://plugins.emdashcms.com/plugins/@coldtill.com/coldtill), [DashCommerce gateway](https://github.com/Coldtill/dashcommerce-crypto-payment-gateway)) — Accepts USDT, USDC, BTC, ETH, SOL and 200+ coins directly to the merchant's own wallets.
- [emdash-plugin-zarinpal](https://github.com/taleghanidev/emdash-plugin-zarinpal) — Zarinpal (Iran) payment gateway with payment links, server checkout, and verified callbacks on Workers and Node.js.
- [emdash-plugin-paystack](https://github.com/alexasomba/emdash-plugin-paystack) — Sandboxed Paystack payment plugin for African markets.
- [emdash-plugin-flutterwave](https://github.com/alexasomba/emdash-plugin-flutterwave) — Sandboxed Flutterwave payment plugin.
- [Moksa TapPay Payments](https://plugins.emdashcms.com/plugins/@moksaweb.com/moksa-tappay) — TapPay for Taiwan with cards, Apple Pay, Google Pay, Samsung Pay, Taiwan e-wallets, verified notifications, and refunds.
- [Moksa Subscriptions](https://plugins.emdashcms.com/plugins/@moksaweb.com/moksa-commerce-subscriptions) — Subscription plans on SKUs, renewal orders, dunning, a customer "My subscriptions" area, and MCP tools.
- [Moksa Order Emails](https://plugins.emdashcms.com/plugins/@moksaweb.com/moksa-commerce-notify) — Order lifecycle emails (confirmation, paid, shipped, pickup-ready, refunds, invoices) with a send log and resend.
- [emdash-restrict-with-stripe](https://github.com/masonjames/emdash-restrict-with-stripe) — Restricts content and sells access with Stripe.

### Authentication & Access Control

- [emdash-better-auth](https://github.com/theweekendprojects/emdash-better-auth) ([npm](https://www.npmjs.com/package/emdash-better-auth)) — Email/password and social (Google, GitHub) authentication powered by Better Auth, with prebuilt sign-in/sign-up pages and email verification.
- [emdash-plugin-password-auth](https://github.com/feronera/emdash-plugin-password-auth) — Turnkey email and password sign-in for the admin with first-admin setup, self-service change, and password reset (PBKDF2 via Web Crypto).
- [@hellocoop/emdash](https://github.com/hellocoop/emdash) ([npm](https://www.npmjs.com/package/@hellocoop/emdash)) — Hellō passwordless login and OpenID Connect identity provider integration.
- [emdash-admin-login-classic](https://github.com/marks-zyz/emdash-admin-login-classic) ([npm](https://www.npmjs.com/package/emdash-admin-login-classic)) — Classic WordPress-style email and password sign-in for the EmDash admin alongside passkeys and magic links.
- [emdash-auth-discord](https://github.com/leCielEtoile/emdash-auth-discord) — Discord OAuth login provider for EmDash with Discord server (guild) membership gating and role mapping.

### Security & Site Protection

- [CrowdSec (`@shane.bsky.shas.am/emdash-crowdsec`)](https://plugins.emdashcms.com/plugins/@shane.bsky.shas.am/emdash-crowdsec) — Displays CrowdSec alerts, active bans, and top security threats from your Local API inside the EmDash admin.
- [RankShield (`@rankshield/emdash-security`)](https://www.npmjs.com/package/@rankshield/emdash-security) — Behavioral threat defense and hardware-fingerprinting security plugin for EmDash.
- [plugin-emdash-sensitive-data-leak](https://github.com/sunak-tech/plugin-emdash-sensitive-data-leak) ([npm](https://www.npmjs.com/package/@snack222/plugin-emdash-sensitive-data-leak)) — Scans EmDash content on save for accidentally exposed API keys, tokens, and secrets, surfacing alerts in the admin UI.
- [emdash-captcha](https://github.com/Dullaz/emdash-captcha) — Pluggable bot-protection and CAPTCHA abstraction plugin for EmDash with first-class Cloudflare Turnstile support.
- [emdash-nospam](https://github.com/apsulis/emdash-nospam) ([npm](https://www.npmjs.com/package/@apsulis/emdash-nospam)) — CAPTCHA-free form anti-spam using a signed timing token, honeypot, per-IP rate limiting, and content checks, with a dashboard widget.

### Accessibility & Privacy

- [emdash-plugin-a11y](https://github.com/Full-Stack-Tech/emdash-plugin-a11y) — WCAG 2.2 AA accessibility auditing that reports contrast, structure, and media issues directly in the admin editor.
- [emdash-plugin-cookie-consent](https://github.com/adrianoamalfi/emdash-plugin-cookie-consent) — Customizable GDPR/CCPA cookie consent banner with category-level opt-in, theming, and an admin settings panel.
- [Cookie Consent (`@desidashlab.bsky.social/cookie-consent`)](https://plugins.emdashcms.com/plugins/@desidashlab.bsky.social/cookie-consent) — GDPR cookie consent banner with category-level blocking, Google Consent Mode support, and consent audit logging.
- [EmPrivacy](https://github.com/EmPlugins/EmPrivacy) ([npm](https://www.npmjs.com/package/@emplugins/emprivacy)) — Cookie consent banner, gated third-party embeds, and privacy notices tailored for GDPR, CCPA, and CIPA compliance.
- [Image Alt Text Manager (`@agenticecom.net/media-alt-text-queue`)](https://plugins.emdashcms.com/plugins/@agenticecom.net/media-alt-text-queue) — Audits the media library and content entries for images missing alt text and provides a queue for adding accessible descriptions.
- [accessibility-toolkit](https://github.com/susheel250/accessibility-toolkit) — WCAG 2.2 AA and Section 508 accessibility widget for EmDash.

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
- [Eventual (`eventual-emdash-sandbox`)](https://github.com/Vermeulen-Solutions/eventual-emdash-sandbox) ([Registry](https://plugins.emdashcms.com/plugins/@vermeulen.solutions/eventual)) — Sandboxed plugin for native multilingual events, rich text descriptions, recurrence rules, saved venues, and iCalendar feeds.
- [emdash-document-revisions](https://github.com/benbalter/emdash-document-revisions) — Port of WP Document Revisions by Ben Balter providing versioned document management stored privately in Cloudflare R2 and served via permission-checked permalinks.
- [emdash-cms-sheet-to-table](https://github.com/alamriku/emdash-cms-sheet-to-table) — Live, searchable, sortable data tables synced from Google Sheets with themes, frozen columns, and CSV/Excel/PDF export.
- [emdash-content-blocks](https://github.com/gatilab/emdash-content-blocks) — Rich editorial Portable Text blocks (FAQ, callout, expert opinion, stats, product review, pros/cons, comparison, checklist, social thread) with Astro renderers and JSON-LD.
- [Content Widgets (`@bitdoze.com/emdashhq-widgets`)](https://plugins.emdashcms.com/plugins/@bitdoze.com/emdashhq-widgets) — Portable Text article widgets including notices, accordions, tabs, steps, product boxes, embeds, cards, quotes, and TOC.
- [KnowX Knowledge Base (`@vapvarun.bsky.social/knowx`)](https://plugins.emdashcms.com/plugins/@vapvarun.bsky.social/knowx) — Searchable knowledge base and help center plugin with categories, article feedback ratings, and reader search analytics.
- [Listora (`emdash-listora`)](https://github.com/wbcomdesigns/emdash-listora) ([Registry](https://plugins.emdashcms.com/plugins/@vapvarun.bsky.social/listora)) — Moderated local business directory plugin with map integration, 10 listing types, member submissions, reviews, and listing claims.
- [WB Reviews (`@vapvarun.bsky.social/reviews`)](https://plugins.emdashcms.com/plugins/@vapvarun.bsky.social/reviews) — Star ratings and moderated user reviews for EmDash articles and pages.
- [`@sneaps/booking-embed`](https://www.npmjs.com/package/@sneaps/booking-embed) — Cal.com and Calendly booking widgets (floating button, element trigger, and inline calendar block) for EmDash sites.
- [emdash-plugin-stl-viewer](https://github.com/ebootheee/emdash-plugin-stl-viewer) ([npm](https://www.npmjs.com/package/emdash-plugin-stl-viewer)) — Interactive 3D preview block for STL and 3MF files in Portable Text powered by lazy-loaded Three.js.
- [emdash-plugin-highlightjs](https://github.com/adrianoamalfi/emdash-plugin-highlightjs) — Portable Text syntax highlighting plugin using Highlight.js with 12 themes, auto dark/light mode, and a copy button.
- [emdash-plugin-math](https://github.com/AK-103U/emdash-plugin-math) — Server-rendered LaTeX formula and math equation rendering for EmDash powered by KaTeX.
- [emdash-typographer](https://github.com/ravalkrushna1/emdash-typographer) ([Registry](https://plugins.emdashcms.com/plugins/@krushnaraval.bsky.social/typographer)) — Polishes smart quotes, dashes, ellipses, and spacing in the editor with a live diff preview before applying.
- [emdash-plugin-neodb](https://github.com/ann61c/emdash-plugin-neodb) — Embeds NeoDB rich media cards and a books/movies/music shelf in EmDash CMS.
- [bible-emdash-plugin](https://github.com/midvash/bible-emdash-plugin) — Auto-links scripture references (English, Portuguese, Spanish) with hover tooltips via the Midvash API.
- [emdash-i18n](https://github.com/alfgago/emdash-i18n) ([npm](https://www.npmjs.com/package/emdash-i18n-translations)) — Multi-locale translation manager with REST API, automatic caching, and translation coverage tracking.
- [emdash-plugin-bulk-upload](https://github.com/afonsojramos/emdash-plugin-bulk-upload) — Drag-and-drop bulk upload admin page that automatically creates draft entries for every uploaded media file.
- [emdash-header-footer-code](https://github.com/jithinsk/emdash-header-footer-code) — Injects analytics snippets, verification meta tags, chat widgets, and custom CSS/JS into the `<head>` or `<body>` without editing theme files.
- [emdash-plugin-404](https://github.com/azydeco/emdash-plugin-404) ([Registry](https://plugins.emdashcms.com/plugins/@azydeco.com/emdash-plugin-custom-404)) — Lets editors design and customize the site's 404 page directly in the EmDash admin while serving a real HTTP 404 status.
- [emdash-plugin-social-comments](https://github.com/siygle/emdash-plugin-social-comments) — Bluesky-powered federated comment threads for EmDash posts.
- [emdash-to-buffer-plugin](https://github.com/devjusty/emdash-to-buffer-plugin) ([Registry](https://plugins.emdashcms.com/plugins/@justy.dev/emdash-to-buffer)) & [EmDash to Buffer Plus](https://plugins.emdashcms.com/plugins/@shane.bsky.shas.am/emdash-to-buffer-plus) — Queue newly published EmDash posts to Buffer social channels with network-tailored formatting.
- [emdash-rss-aggregator](https://github.com/EngDawood/emdash-rss-aggregator) — RSS/Atom feed importer and aggregator that ingests external feeds as first-class EmDash content entries.
- [emdash-blocks](https://github.com/bnomei/emdash-blocks) — JSON block-list field widget for EmDash entries with normalized block props and per-block visibility toggles.
- [emdash-actions](https://github.com/bnomei/emdash-actions) ([npm](https://www.npmjs.com/package/@bnomei/emdash-actions)) — Action buttons and server-side task runner triggers for EmDash fields and admin dashboards.
- [emdash-plugin-r2-variants](https://github.com/rjstech2020/emdash-plugin-r2-variants) — Resizes each image once, stores variants in R2, and serves them without per-request Worker transforms.
- [emdash-plugin-r2](https://github.com/azydeco/emdash-plugin-r2) — Sandboxed plugin for browsing and using images from a Cloudflare R2 bucket.
- [Bluesky To EmDash](https://plugins.emdashcms.com/plugins/@connectobasan.com/bluesky-feed) — Syncs the site owner's Bluesky posts into an EmDash collection.
- [emdash-popcase](https://github.com/harryxu/emdash-popcase) — Native lightbox for body images and videos.
- [Emoji Reactions](https://github.com/toya-mimura/emdash-plugin-emoji-reactions) ([Registry](https://plugins.emdashcms.com/plugins/@toya-mimura.bsky.social/reactions)) — Emoji reactions on posts.
- [emdash-readable-resume](https://github.com/supertj/emdash-readable-resume) — Publishes a resume as a page in ReadableResume's Classic layout.
- [emdash-Featured-Post](https://github.com/joyce5438/emdash-Featured-Post) — Selects one or more featured posts.
- [emdash-schema-i18n](https://github.com/NimitzUA/emdash-schema-i18n) — Localizes dynamic schema, collection, and block-type labels in the admin UI.
- [emdash-author-box](https://github.com/masonjames/emdash-author-box) — Production-ready author box plugin for EmDash CMS.
- [emdash-table-of-contents](https://github.com/masonjames/emdash-table-of-contents) — Production-ready table of contents plugin with Portable Text and Astro component support.
- [emdash-social-sharing](https://github.com/masonjames/emdash-social-sharing) — Privacy-light social sharing plugin for EmDash CMS.
- [emdash-reading-time](https://github.com/masonjames/emdash-reading-time) — Polished, reusable reading-time badge for long-form content via a `readingTime` Portable Text block and Astro component.
- [emdash-page-list](https://github.com/masonjames/emdash-page-list) — Collection-backed and menu-backed page lists via a `pageList` Portable Text block and Astro component.

### Page & Visual Builders

- [EmVB](https://github.com/PerkyZZ999/EmVB) ([Website](https://emvb.dev)) — Visual drag-and-drop page builder plugin for EmDash CMS.
- [emdashcms-visual-builder](https://github.com/HaroonChelsea/emdashcms-visual-builder) ([npm](https://www.npmjs.com/package/@mhar00n/emdashcms-visual-builder)) — GrapesJS Core-powered visual site builder for EmDash CMS supporting responsive pages, headers, footers, and reusable components.
- [builderdash](https://github.com/lickybuay/builderdash) — Elementor-inspired native visual page builder plugin for EmDash with live preview, drag-and-drop blocks, and an inspector panel.
- [emdash-page-builder](https://github.com/undefined-charity/emdash-page-builder) — Word-processor-style inline visual page editor for editing EmDash pages directly in the site's frontend styles.
- [emdash-bento](https://github.com/bnomei/emdash-bento) ([npm](https://www.npmjs.com/package/@bnomei/emdash-bento)) — Visual Bento grid layout field widget for EmDash JSON fields using Block Builder.
- [emdash-plugin-site-blocks](https://github.com/Ariadne-Ops/emdash-plugin-site-blocks) — Drupal-style site-wide blocks with region placement.
- [simple-code-snippets](https://github.com/epictum/emdash-plugin-simple-code-snippets) — Adds JS, CSS, or HTML snippets to `<head>` or before `</body>`, validated on save.
- [emdash-plugin-code-injection](https://www.npmjs.com/package/@pagelyft/emdash-plugin-code-injection) — Injects site-wide HTML into the head, body start, and body end.

### Editorial Workflow & Maintenance

- [Editorial Review & Approvals (`@agenticecom.net/editorial-approvals`)](https://plugins.emdashcms.com/plugins/@agenticecom.net/editorial-approvals) — Multi-editor approval workflow recording review feedback, requested changes, sign-offs, and post-review edit flags.
- [Content Review Planner (`@agenticecom.net/content-review-freshness`)](https://plugins.emdashcms.com/plugins/@agenticecom.net/content-review-freshness) — Assigns content owners and review due dates to track pages overdue for editorial verification.
- [Content Expiry (`@agenticecom.net/content-expiry`)](https://plugins.emdashcms.com/plugins/@agenticecom.net/content-expiry) — Automatically unpublishes, trashes, or retags time-sensitive posts and offers on a scheduled expiration date.
- [Safe Bulk Find & Replace (`@agenticecom.net/safe-bulk-replace`)](https://plugins.emdashcms.com/plugins/@agenticecom.net/safe-bulk-replace) — Previews and applies bulk text replacements across entries as staged draft edits.
- [SiteGraph Lite (`@krushnaraval.bsky.social/sitegraph-lite`)](https://plugins.emdashcms.com/plugins/@krushnaraval.bsky.social/sitegraph-lite) — Maps internal page dependencies and detects broken internal links before content is modified or unpublished.
- [Link Guardian (`@meekmedia.bsky.social/link-guardian`)](https://plugins.emdashcms.com/plugins/@meekmedia.bsky.social/link-guardian) & [emdash-plugin-content-link-check](https://github.com/eisbachcode/emdash-plugin-content-link-check) — Scheduled link health checkers that flag broken links, redirect chains, and stale URLs in the admin.
- [Duplicate Media Finder (`@agenticecom.net/duplicate-media-report`)](https://plugins.emdashcms.com/plugins/@agenticecom.net/duplicate-media-report) & [Missing Image Finder (`@agenticecom.net/missing-media-references`)](https://plugins.emdashcms.com/plugins/@agenticecom.net/missing-media-references) — Media library cleanup tools for identifying duplicate uploads and broken media references across entries.
- [emdash-plugin-content-freshness](https://github.com/eisbachcode/emdash-plugin-content-freshness) — Scheduled content auditor that flags stale entries, missing SEO descriptions, forgotten drafts, and missed schedules.
- [emdash-simple-history](https://github.com/masonjames/emdash-simple-history) — Focused activity feed recording content create, update, and delete events, surfaced in an admin history page and dashboard widget.

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
- [relatinator](https://github.com/DBozhinovski/relatinator) — TF-IDF/BM25 related-content finder for Astro content collections.

---

## Developer Tools & Tooling

- [EmDash CLI](https://docs.emdashcms.com/reference/cli/) — Official command-line utility for project scaffolding, schema migrations, and database seeding.
- [create-emdash](https://www.npmjs.com/package/create-emdash) — Official `npm create emdash` scaffolding CLI for bootstrapping new EmDash + Astro projects in seconds.
- [`upgrade-emdash`](https://www.npmjs.com/package/upgrade-emdash) — Official CLI (`npx upgrade-emdash@latest`) that upgrades `emdash` and `@emdash-cms/*` dependencies, syncs agent skills, diffs core migrations, and generates an `.emdash/UPGRADE.md` work order for humans and coding agents.
- [Plugin CLI](https://docs.emdashcms.com/plugins/creating-plugins/cli/) ([npm](https://www.npmjs.com/package/@emdash-cms/plugin-cli)) — Official `emdash-plugin` CLI for scaffolding (`init`), building, bundling, validating `emdash-plugin.jsonc` manifests, managing Atmosphere sessions, and publishing signed releases to the AT Protocol registry.
- [Registry Client](https://docs.emdashcms.com/plugins/registry-client/) — Client library for programmatic querying and resolution against the AT Protocol plugin registry.
- [`@emdash-cms/registry-loader`](https://github.com/emdash-cms/emdash/tree/main/packages/registry-loader) — Astro live content loader for embedding plugin registry listings in any Astro site.
- [`@emdash-cms/x402`](https://www.npmjs.com/package/@emdash-cms/x402) — Official HTTP 402 payment protocol handler for building agentic, paid-per-call API endpoints.
- [`@emdash-cms/blocks`](https://www.npmjs.com/package/@emdash-cms/blocks) — Official declarative Block Kit SDK for building sandboxed plugin admin interfaces and widgets.
- [`@emdash-cms/cloudflare`](https://www.npmjs.com/package/@emdash-cms/cloudflare) — Official Cloudflare runtime adapter providing D1 (with read-replica session bookmarks), R2, KV cache, and Dynamic Worker Loader sandbox bindings.
- [emdash-kit](https://github.com/xPonential-Labs/emdash-kit) — Shared Cloudflare Worker entry point, Astro configuration helpers, and content utilities for EmDash sites.
- [emdash-run](https://github.com/joeblew999/emdash-run) — Fast local runner for EmDash development using `mise` and `pitchfork`.
- [emdash-platform-wfp](https://github.com/scottbuscemi/emdash-platform-wfp) — Multi-tenant prompt-to-site generator built on Cloudflare Workers for Platforms + EmDash.
- [emdash-plugin-github-backup](https://github.com/dennisklappe/emdash-plugin-github-backup) — Backs up collection content to a GitHub repository on every edit for file-based Git versioning.
- [GitHub Sync (`@inari.diy/github-sync`)](https://plugins.emdashcms.com/plugins/@inari.diy/github-sync) — Bi-directional GitHub repository synchronization that commits EmDash content changes as Markdown and syncs `git push` updates back.
- [emdash-plugin-deploy-trigger](https://github.com/leCielEtoile/emdash-plugin-deploy-trigger) — Triggers Cloudflare Pages deploy hooks on a configurable schedule from EmDash.
- [emdash-bot](https://github.com/emdash-cms/emdash-bot) — Official service that authors EmDash issues and pull requests, built on Pi Durable and Cloudflare.
- [emdash-8am](https://github.com/8amscott/emdash-8am) — 8AM Creative's toolkit with an admin plugin, Astro integration, shared components, and content sync.
- [DrDustinEdwards/astro](https://github.com/DrDustinEdwards/astro) — Astro and EmDash packages, including Enarratio charts.

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

- [emdash-docker (mariandenys)](https://github.com/mariandenys/emdash-docker) — Minimal Docker Compose setup that spins up a full local EmDash blog in three commands.
- [emdash-docker (rubengmez)](https://github.com/rubengmez/emdash-docker) — Multi-architecture OCI images automatically rebuilt against upstream EmDash releases.
- [docker-emdash (jstgnkl)](https://github.com/jstgnkl/docker-emdash) — Clean Dockerfile configuration for building self-hosted EmDash images.
- [EmdashDeploy](https://github.com/web-casa/EmdashDeploy) — Interactive VPS deployment script featuring automated Docker setup, Caddy reverse proxy, and backup utilities.
- [emdash-panel](https://github.com/bitdoze/emdash-panel) — Open-source (MIT) single-VPS hosting panel for EmDash with multi-site management, HTTPS, backups, metrics, and deployments.

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
- [`@emdash-cms/gutenberg-to-portable-text`](https://www.npmjs.com/package/@emdash-cms/gutenberg-to-portable-text) — Official AST parser converting WordPress Gutenberg blocks into Portable Text JSON.
- [hatena-to-emdash](https://github.com/ochanuco/hatena-to-emdash) — CLI tool to convert Hatena Blog Movable Type exports into EmDash-ready Markdown.
- [emdash-mt-import](https://github.com/kennyg/emdash-mt-import) — CLI importer translating standard Movable Type blog archives into EmDash seed JSON.
- [`@sneaps/import-export`](https://www.npmjs.com/package/@sneaps/import-export) — Native EmDash plugin to bulk import and export collection items as CSV or JSON.
- [Import (`@handyplugins.co/import`)](https://plugins.emdashcms.com/plugins/@handyplugins.co/import) — Sandboxed registry plugin for importing structured CSV and JSON datasets into EmDash collections.
- [Link Find & Replace (`@agenticecom.net/link-repair-migration`)](https://plugins.emdashcms.com/plugins/@agenticecom.net/link-repair-migration) — Previews and applies old-to-new URL replacements across content entries during domain or site migrations.

---

## Articles, Case Studies & Media

### Official Cloudflare Engineering & Announcement Posts

- [The Cloudflare Blog — Brought to you by EmDash (Cloudflare Blog, Aug 24, 2026)](https://blog.cloudflare.com/cloudflare-blog-uses-emdash/) — In-depth engineering case study detailing how Cloudflare migrated its primary corporate blog to EmDash as "Customer Zero", serving millions of live pageviews and withstanding DDoS attacks.
- [EmDash 1.0: the stable CMS with a secure plugin registry (Cloudflare Blog, Sept 28, 2026)](https://blog.cloudflare.com/emdash-cms-plugin-registry/) — Cloudflare's official stable 1.0 release announcement covering production readiness, sandboxed plugins, and the decentralized AT Protocol plugin registry.
- [Introducing EmDash — the spiritual successor to WordPress that solves plugin security (Cloudflare Blog, April 1, 2026)](https://blog.cloudflare.com/emdash-wordpress/) — The original launch post introducing the beta of EmDash as an open-source successor to WordPress running in sandboxed Worker isolates.
- [Introducing Clef-omni with full multimodality, plus a faster Clef and a cheaper Clef-flash (Cloudflare Blog, Oct 9, 2026)](https://blog.cloudflare.com/clef-faster-cheaper-multimodal/) — Details how Cloudflare's multimodal Clef decision model is used in production by EmDash to screen plugin registry submissions for phishing and abuse.
- [Everything we launched during Birthday Week 2026 (Cloudflare Blog, Oct 5, 2026)](https://blog.cloudflare.com/birthday-week-2026-wrap-up/) — Cloudflare's Birthday Week 2026 roundup highlighting EmDash 1.0, Clef decision models, and agent sandbox infrastructure.
- [One year later: the power of 1.1.1.1 interns (Cloudflare Blog, Oct 5, 2026)](https://blog.cloudflare.com/one-year-later-1111-interns/) — Behind-the-scenes look at how Cloudflare interns helped build and maintain EmDash 1.0 and power the Cloudflare Blog.
- [Cloudflare AI Search: give your agents a search engine for your data (Cloudflare Blog, Aug 6, 2026)](https://blog.cloudflare.com/ai-search-easier/) — Official breakdown of hybrid semantic + keyword search on EmDash sites using the Cloudflare AI Search integration.

### EmDash Team Technical Deep Dives

- [EmDash Build: an open source AI site builder (EmDash Blog, Sept 28, 2026)](https://emdashcms.com/blog/emdash-build) — Launch article by Noah Pham explaining the Agents SDK, Cloudflare Sandboxes, and git-backed Artifacts for prompt-based site creation.
- [Ship your plugin to the EmDash plugin registry (EmDash Blog, Sept 28, 2026)](https://emdashcms.com/blog/emdash-plugin-registry) — Practical guide by Scott Buscemi on AT Protocol signed publishing, Atmosphere accounts, and `@emdash-cms/plugin-cli`.
- [EmDash 1.0: an open source CMS for Astro (EmDash Blog, Sept 28, 2026)](https://emdashcms.com/blog/emdash-1-0) — Comprehensive 1.0 architecture overview by creator Matt Kane on why EmDash was built on Astro and how sandboxing eliminates security hazards.
- [EmDash is live (EmDash Blog, April 28, 2026)](https://emdashcms.com/blog/emdash-is-live) — First public release announcement detailing the 0.x roadmap and agent capabilities.
- [How EmDash uses Clef to moderate the plugin registry (EmDash Blog, Oct 7, 2026)](https://emdashcms.com/blog/how-emdash-uses-clef-to-moderate-the-plugin-registry) — Deep dive by Scott Buscemi on how EmDash's AT Protocol labeler uses Cloudflare's multimodal Clef decision model to screen plugin metadata, links, icons, and screenshots in 1.64s at p95.
- [EmDash 1.2: a redesigned editor, video blocks and domain moves (EmDash Blog, Oct 7, 2026)](https://emdashcms.com/blog/emdash-1-2) — Official 1.2 release notes by Matt Kane covering the frameless content editor, native `/video` Portable Text blocks with HTTP `206 Partial Content` byte-range streaming, numbered collection pagination, admin domain migration flow, 11+ new/updated admin locales, and the `upgrade-emdash` CLI.
- [EmDash 1.1: publishing calendar, richer embeds and faster sites (EmDash Blog, Oct 2, 2026)](https://emdashcms.com/blog/emdash-1-1) — Official 1.1 release announcement by Matt Kane introducing the Month/Agenda publishing calendar, isolated iframe HTML/CSS/JS blocks, `/iframe` embeds, Microsoft Entra ID OAuth provider, and the experimental `WebMcpSearch` browser-agent component.
- [EmDash 1.3: readable revision history and a better inline editor (EmDash Blog, Oct 15, 2026)](https://emdashcms.com/blog/emdash-1-3) — Release notes by Matt Kane. Saved revisions open with highlighted diffs and author attribution, and a new SEO setting asks AI crawlers not to train on the site. The on-page editor gains the admin toolbar, slash menu and image picker. Also covers fewer D1 round trips, contributor draft editing, and better WordPress imports.
- [EmDash 1.4: fewer lost edits and many small refinements (EmDash Blog, Oct 29, 2026)](https://emdashcms.com/blog/emdash-1-4) — Refinement release by Noah Pham with 75 changes from 22 contributors. Edits now save on leaving the editor, conflicting saves are detected, and D1 menu saves are atomic. Adds the `admin.hiddenNavItems` option, full Simplified Chinese, Brazilian Portuguese and Turkish admin translations, fewer DB queries, and a new first-party AI Search plugin.

### Community & Industry Analyses

- [EmDash CMS by Cloudflare — The Open-Source TypeScript Successor to WordPress (WP Poland, 2026)](https://wppoland.com/en/emdash-cloudflare-open-source-cms-wordpress-successor-2026/) — Architectural deep-dive comparing WordPress security vulnerabilities with EmDash's modern model.
- [EmDash CMS vs WordPress: An Honest Benchmark (SHIFT64, 2026)](https://shift64.com/blog/emdash-cms-vs-wordpress-honest-benchmark) ([Benchmark Suite](https://github.com/mateusz-zadorozny/shift64-emdash-cms-benchmark)) — Empirical comparison with 4,732 measurements covering latency, TTFB, memory usage, and throughput of EmDash on Cloudflare Workers versus WordPress on a VPS.
- [6 Reasons Why Cloudflare's EmDash Can't Compete With WordPress (Search Engine Journal, April 2026)](https://www.searchenginejournal.com/6-reasons-why-cloudflares-emdash-cant-compete-with-wordpress/571053/) — Roger Montti's analysis of EmDash's early developer-centric positioning versus WordPress's established consumer ecosystem.
- [EmDash 1.0 Challenges WordPress Freedom With Cloudflare Lock-In (Search Engine Journal, Sept 29, 2026)](https://www.searchenginejournal.com/emdash-1-0-challenges-wordpress-freedom-with-cloudflare-lock-in/591378/) — Critique of how closely the 1.0 release depends on Cloudflare infrastructure.
- [Cloudflare Says EmDash Version 1.0 Is Releasing Soon (Search Engine Journal)](https://www.searchenginejournal.com/cloudflare-says-emdash-version-1-0-is-releasing-soon/586951/) — Pre-launch coverage of the 1.0 roadmap ahead of Birthday Week.
- [Mullenweg To Cloudflare: Keep WordPress Out Of Your Mouth (Search Engine Journal, April 2026)](https://www.searchenginejournal.com/mullenweg-to-cloudflare-keep-wordpress-out-of-your-mouth/571119/) — Matt Mullenweg's response to EmDash's "spiritual successor to WordPress" positioning.
- [Cloudflare EmDash 1.0 Launches Decentralized Plugin Registry (CMSWire, Sept 30, 2026)](https://www.cmswire.com/digital-experience/cloudflare-releases-emdash-1-0-cms-with-decentralized-plugin-registry/) — Trade coverage of the 1.0 stable release and the AT Protocol plugin registry.
- [Cloudflare Introduces EmDash: TypeScript CMS Positioned as WordPress Successor (InfoQ, April 2026)](https://www.infoq.com/news/2026/04/cloudflare-emdash-wordpress/) — Engineering-focused news analysis of EmDash's architecture and sandboxed plugin model.
- [Inside Cloudflare's plan to position EmDash as a next-generation successor to WordPress (TechRadar, Apr 8, 2026)](https://www.techradar.com/pro/a-more-secure-scalable-platform-that-runs-on-modern-infrastructure-and-supports-ai-native-workflows-why-cloudflares-new-emdash-is-the-spiritual-successor-to-wordpress) — Interview-driven feature on EmDash's security, scalability, and AI-native goals.
- ['I think EmDash was created to sell more Cloudflare services' (TechRadar, Apr 3, 2026)](https://www.techradar.com/pro/i-think-emdash-was-created-to-sell-more-cloudflare-services-wordpress-co-founder-matt-mullenweg-gives-his-verdict-on-cloudflares-emdash) — Matt Mullenweg's verdict on EmDash.
- [Cloudflare's new CMS is not a WordPress killer, it's a WordPress alternative (CSO Online, Apr 2, 2026)](https://www.csoonline.com/article/4154115/cloudflares-new-cms-is-not-a-wordpress-killer-its-a-wordpress-alternative-2.html) — Security-industry take on the sandboxed plugin model.
- [Cloudflare's EmDash CMS sparks fight with WordPress founder Mullenweg (PPC Land, Apr 5, 2026)](https://ppc.land/cloudflares-emdash-cms-sparks-fight-with-wordpress-founder-mullenweg/) — Recap of the EmDash/WordPress positioning dispute.
- [EmDash CMS Review (2026): Cloudflare's WordPress Successor (Bitdoze, Sept 29, 2026)](https://www.bitdoze.com/emdash-cms-review/) — Review written six months in, after 1.0. Compares Cloudflare and self-hosted VPS deployment and covers operational footguns and who EmDash suits.
- [EmDash CMS review: enterprise fit vs Payload (wayf.ai, Sept 2026)](https://wayf.ai/blog/emdash-cms-review/) — Enterprise-focused comparison with Payload covering multitenancy gaps and encrypted plugin secrets.
- [EmDash CMS Review: We Migrated a Real WordPress Site (BAM Web Dev, Apr 2026)](https://bamwebdev.com/blog/emdash-wordpress-migration/) — Field report on migrating a production WordPress site. Custom post types became collections, but the plugin ecosystem gaps remain.
- [EmDash: a fresh take on CMS (Maciek Palmowski, Apr 2026)](https://maciekpalmowski.dev/blog/emdash-a-fresh-take-on-cms/) — Developer perspective on where EmDash beats, and loses to, plain Markdown content.
- [EmDash CMS review: Cloudflare vs WordPress? (WPJohnny, Apr 2026)](https://wpjohnny.com/emdash-cms-review-cloudflare-vs-wordpress/) — WordPress performance consultant's assessment of EmDash.
- [EmDash CMS: What Agencies Should Know (WP Umbrella, Apr 2026)](https://wp-umbrella.com/blog/emdash-launched/) — Agency-oriented briefing on EmDash's launch and its implications for WordPress maintenance businesses.
- [Cloudflare EmDash CMS: An Honest WordPress Take (Ben Ryan, Apr 2026)](https://benryan.com.au/blog/cloudflare-emdash-wordpress-alternative) — Australian agency's hands-on look at the April beta.
- [emdash CMS Review (2026): Honest Take (Gautam Khorana, May 2026)](https://gautamkhorana.com/blog/emdash-cms-honest-review-2026/) — What works and what doesn't in EmDash's AI-first, sandboxed-plugin design.

### Tutorials & Courses

- [tzu-chi-vibe-coding-emdash](https://github.com/phoenix581228/tzu-chi-vibe-coding-emdash) — Complete university curriculum artifact for teaching Vibe Coding with EmDash, including a course site, student starter kits, demo sites, and agent skills (MIT).
- [EmDash Getting Started: Build a Custom Collection and Render It in Astro (FounderMag, Oct 2026)](https://foundermag.co/tutorials/emdash-getting-started-custom-collection/) — Hands-on tutorial by Marcus Webb walking through EmDash 1.0+, custom CLI collection creation, `getEmDashCollection()` rendering, and Claude Code MCP OAuth setup.
- [EmDash CMS Tutorial: Build Your First Site (Bitdoze, Sept 29, 2026)](https://www.bitdoze.com/emdash-cms-tutorial/) — Multi-part practical guide to scaffolding, configuring, and querying an EmDash 1.0+ site locally with SQLite before deploying to Cloudflare Workers or Docker.
- [Build Your First EmDash Website: Complete Tutorial (Dashstro, 2026)](https://dashstro.com/learn/build-first-emdash-website) — End-to-end walkthrough of building a site with `npm create emdash@latest`, defining `seed.json`, and deploying to Cloudflare.
- [EmDash CMS: From First Look to Production (Bitdoze Video Course)](https://www.bitdoze.com/courses/emdash-cms/) — Free 5-lesson beginner course covering a hands-on review, AI-agent-built themes, free Cloudflare Workers deployment, email sending, and Docker benchmarks.
- [EmDash CMS deployment on Hetzner VPS (Node.js): First try (DEV, Oct 15, 2026)](https://dev.to/mandrasch/quick-test-of-emdash-cms-deployment-on-hetzner-vps-nodejs-518e) ([Source Code](https://github.com/mandrasch/emdash-demo-marketing-starter)) — Walkthrough of self-hosting the EmDash marketing starter on a Hetzner VPS with Node.js.

### Video Walkthroughs & Interviews

- [EmDash: The WordPress Successor That Fixes Plugin Security (Cloudflare TV)](https://cloudflare.tv/this-week-in-net/emdash-the-wordpress-successor-that-fixes-plugin-security/5vpEE7aP) — This Week in NET interview with the EmDash engineering team covering the project's origins, Astro integration, and Dynamic Workers isolation.
- [What Everyone Missed About EmDash (James Q Quick)](https://www.youtube.com/watch?v=hgOJH9bp75k) — Architectural analysis of why Cloudflare's sandboxed Dynamic Workers eliminate traditional CMS plugin vulnerabilities.
- [EmDash + Astro: The CMS Combo That Could Power Your Next Site (WPTuts)](https://www.youtube.com/watch?v=RTrbg5z_UBk) — Detailed walkthrough of the EmDash 1.0 admin interface, content modeling, and Astro frontend pairing.
- [WordPress is COOKED — Long Live EmDash! (WPTuts)](https://www.youtube.com/watch?v=0vmxzhRsZQI) — Hands-on first look exploring admin navigation, schema generation, and comparisons with WordPress developer workflows.
- [Cloudflare Just Killed WordPress?! (Mehul Mohan / codedamn)](https://www.youtube.com/watch?v=sBXC63ULDAE) — Technical overview of EmDash's architecture, serverless performance, and implications for modern web development.
- [Cloudflare Built a WordPress Killer. I Tested It (Nico | AI Ranking)](https://www.youtube.com/watch?v=ox_lYOyW7NY) — 19-minute hands-on video building an SEO-optimized website from scratch with EmDash CMS, Astro, Claude Code, and Cloudflare Workers.
- [CloudFlare Just Released a WordPress Killer — And We're Already Using It (TJ Robertson)](https://www.youtube.com/watch?v=0qMhYla9zBE) — Practical agency evaluation and walkthrough of adopting EmDash CMS in production.

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
