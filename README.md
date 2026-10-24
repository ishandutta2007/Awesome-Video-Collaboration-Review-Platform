# Awesome-Video-Collaboration-Review-Platform

## Top Video Collaboration & Review Platform Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Self-Hosted Frame-Accurate Review, Client Approval Workflows & AI-Assisted Media Libraries*  

**Last updated: March 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Video Collaboration & Review**. These tools replace the email-chain-and-spreadsheet chaos of creative review with frame-accurate annotations, timestamped comments, version tracking, and client approval workflows — so feedback lands on the right frame instead of "around 1:42, maybe."



**Examples** include Shumai, Clapshot, ViTransfer, OpenFrame, Frame.io, and Vimeo Review (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, S3-compatible storage ownership, and AI-assisted review — ideal for agencies and post-production teams who need Frame.io-style collaboration without per-seat fees and with their media on their own infrastructure.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **Frame.io** — **The reference cloud review platform.** Frame-accurate comments, version stacking, share links with password and expiry controls, and deep Adobe integration (Premiere, After Effects). **Subscription-based** per-seat with storage tiers. **Trade-offs**: media lives on Adobe's infrastructure, per-seat costs scale with team size, and self-hosting is not an option. **Best for teams already inside Adobe's ecosystem** wanting the most polished commercial review experience.



- **Vimeo Review** — **Vimeo's review and approval layer.** Timestamped comments, version comparison, and shareable review pages on top of Vimeo's hosting. **Included with Vimeo paid plans**. **Best for teams already hosting on Vimeo** wanting review tools without a separate vendor.



- **Wipster** — **The review platform with content approval workflows.** Frame-accurate comments, version control, and approval gates aimed at marketing and creative teams. **Subscription-based**. **Best for marketing teams** needing formal sign-off chains on video assets.



- **Filestage** — **The proofing platform for video, design, and documents.** Multi-format review with version tracking and approval workflows. **Subscription-based**. **Best for agencies** reviewing mixed asset types in one place.



## Open-Source GitHub Projects



- **Shumai** — **The most complete open-source Frame.io alternative.** MIT licensed, **built with Bun and TypeScript**, created in mid-2026 and moving quickly through 0.1.x releases . **Frame-by-frame annotations and timestamped comments** on video and images, with **secure public share links and curated collections** for client delivery . **Role-based access controls** scoped at team and project level, **customizable asset metadata fields**, and **storage on local filesystem or any S3-compatible backend** (AWS S3, Cloudflare R2, MinIO) . **Distributed video transcoding runs as Temporal workflows** so large files process reliably in the background . **The AI layer is the differentiator**: a collaborative chat agent inside project workspaces, **semantic search over media using vector embeddings** (requires PostgreSQL with pgvector), and **automated metadata generation via Google Gemini** . **CLI** for managing projects, uploading files, and pushing new versions from the terminal . **The honest boundary**: **Shumai is a review and approval tool, not a generator or publisher** — it does not create content, write captions, or post to social platforms . **As an early-stage project moving through 0.x releases**, treat any single version's behavior as a snapshot . **Best for teams wanting a self-hosted Frame.io alternative** with AI-assisted media library features and full data ownership.



- **Clapshot** — **The pragmatic self-hosted review tool for local-hosting requirements.** Open-source, **Rust-based API server with Svelte web UI** . **Built for scenarios requiring local hosting** due to policy constraints (enterprise) or cost-benefit concerns against paid cloud services (small businesses) . **Video, audio, and image files plus subtitle tracks**, with **HTTP uploads or shared-folder ingestion** for large files that exceed proxy limits . **FFmpeg transcoding**, **commenting, drawing annotations, and threaded replies**, **real-time collaborative review sessions**, and **EDL import as comments with loop-between-points** . **Authentication agnostic** — integrate OAuth, JWT, Kerberos, Okta, or SAML via Nginx reverse proxy username pass-through . **SQLite database with file-based media storage** — minimal infrastructure footprint. **The honest limitation**: **desktop-first design with limited mobile support** — double-tap doesn't work on iOS/iPad, video controls may not function properly, and drawing annotations fail on mobile . **Best for enterprises and small businesses** needing a lightweight, policy-compliant review tool they can run on a spare Linux VM.



- **ViTransfer** — **The filmmaker-focused review and approval platform.** Self-hosted, **Docker-first** with a **3-minute Docker Hub deployment** . **Video upload with automatic transcoding to 720p/1080p**, **customizable watermarks for preview videos**, **timestamped comments**, and **client approval workflow with revision tracking** . **Password-protected projects**, **email notifications**, **analytics dashboard** tracking page visits and downloads, and **security logging** for access attempts . **Version management** lets you hide/show specific video versions, and **revision tracking** limits and tracks project revisions . **Technical stack**: Next.js 16, React 19, PostgreSQL with Prisma 6, Redis Queue with BullMQ for background video processing, FFmpeg, and **TUS protocol for resumable uploads** . **Requires at least 4GB RAM and 20GB+ free disk space** . **Best for filmmakers and video teams** wanting a production-ready self-hosted review platform with client-facing approval workflows and watermarking.



- **OpenFrame** — **The review and approval platform with Stripe and S3 integration options.** Open-source, **Docker-based** with PostgreSQL and MinIO in the default stack . **Feature flags let you disable hosted-only features** by default: `OPENFRAME_ENABLE_STRIPE=false` disables billing, `OPENFRAME_ENABLE_BUNNY_UPLOADS=false` hides Bunny uploads (URL-based providers like YouTube remain available), and `OPENFRAME_REQUIRE_INVITE_CODE=false` allows open registration . **S3-compatible uploads** can be enabled with presigned URLs to your own storage (Cloudflare R2, MinIO) — only one direct-upload backend can be active at a time . **Admin analytics** records first-touch attribution and funnel events into your own database, readable via `/admin/growth` or JSON API with a bearer token . **Best for teams wanting a self-hosted review platform** with optional billing and flexible storage backends, accepting the early-stage 0.1.0 versioning.



- **Loam (lawn)** — **The opinionated lightweight review platform from a team that uses it daily.** Open-source, created by Theo out of frustration with Frame.io "slowly regressing" . **Simple, fast, and reliable** by design — built for his team's daily use and open-sourced with no guarantee of long-term maintenance or PR acceptance . **Best for teams wanting a minimal, fast review tool** from a developer who built it for himself, accepting the explicit uncertainty about maintenance and roadmap .



### Additional Strong Open-Source Options



- **Gotenberg proxy (Shumai integration)** — Converts Office documents, Markdown, and HTML into PDF proxies for browser previewing alongside video and image review. Part of Shumai's document handling stack .

- **MemoRekall / Arvest** — Video annotation apps with time-linked annotations, multi-user environments, and IIIF compatibility. **Academic/research-focused** rather than production review workflows . Best for research and archival annotation.



**Frameworks for building custom systems**: Combine **Shumai** for the most complete Frame.io alternative with AI-assisted search and S3 storage ownership, **Clapshot** for minimal-footprint self-hosted review on a spare Linux VM with authentication-agnostic proxy integration, **ViTransfer** for filmmaker-focused approval workflows with watermarking and resumable uploads, and **OpenFrame** for optional Stripe billing and S3-compatible uploads — to build a video review stack tailored to your team size, storage requirements, and tolerance for early-stage software.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Video review tools differ significantly in maturity, storage model, and feature depth. **Shumai is the most feature-complete open-source option** with frame-accurate annotations, AI semantic search, and S3-compatible storage, but it's **early-stage (0.1.x)** and the behavior of any single version is a snapshot . **Clapshot is explicitly desktop-first with limited mobile support** — drawing annotations fail on mobile browsers . **ViTransfer requires at least 4GB RAM and 20GB+ disk space**, and the default admin credentials must be changed in production . **OpenFrame's hosted-only features (Stripe, Bunny uploads) are disabled by default** in the Docker example — enable them deliberately if needed . **Loam's author explicitly does not accept PRs and cannot guarantee maintenance** — adopt it as-is, not as a project you can shape . **Self-hosting shifts responsibility to you** — storage durability, database backups, and TLS configuration are your operations, not a vendor's.

- Self-hosted open-source solutions require proper S3-compatible storage configuration (or local filesystem for Clapshot), PostgreSQL with pgvector for Shumai's semantic search, and reverse proxy setup for HTTPS and authentication.



---



**Made for creative teams, agencies, and post-production professionals choosing review platforms they can own and control.**

Let's make video collaboration and review more open, frame-accurate, and storage-sovereign.
