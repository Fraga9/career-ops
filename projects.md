# Projects Portfolio — Héctor Eduardo Garza Fraga

**Last Updated:** 2026-04-13  
**Total Projects:** 9 shipped + 1 in development + 1 research paper (11 total)

---

## Project 1: VibeMatch — AI Music Recommendation Engine

**Status:** Shipped (Live)  
**URL:** https://www.vibematchs.me/  
**GitHub:** https://github.com/Fraga9/vibematch  
**Timeline:** 3 months (July-September 2025)

### What It Does
Real-time music recommendation engine using Graph Neural Networks to discover compatible artists based on listening patterns. Analyzes 338K+ tracks and 6.9K+ artists to generate personalized recommendations with 1.0 precision at top-10.

### Tech Stack
- **Frontend:** Next.js 15, React, Tailwind CSS
- **Backend:** FastAPI, Python
- **ML:** PyTorch, LightGCN (Graph Neural Networks)
- **Vector DB:** Qdrant (embeddings + semantic search)
- **Deployment:** Vercel (frontend), AWS (backend)
- **Infrastructure:** Docker, GitHub Actions CI/CD

### Key Metrics (Hero Metrics)
- **Precision@10:** 1.0 (perfect ranking accuracy at top-10 recommendations)
- **Recall@10:** 0.64 (captures 64% of relevant artists per user)
- **Vector Search Latency:** 10ms (99th percentile query time)
- **End-to-End Latency:** 800ms (user perceives sub-second response)
- **Dataset Scale:** 338K+ tracks, 6.9K+ artists, 2M+ play relationships
- **Active Users:** N/A (portfolio project, but live demo available)

### Key Achievements
1. **GNN Architecture:** Engineered LightGCN with 3-hop neighborhood aggregation to learn collaborative filtering embeddings from sparse interaction data
2. **Latency Optimization:** Reduced vector search from 50ms → 10ms via HNSW indexing tuning and batch query optimization
3. **Production Stability:** Deployed on AWS with 99.9% uptime, automatic failover, and rate limiting
4. **Frontend Polish:** Responsive design (mobile/desktop), real-time UI updates, animated artist cards with Spotify integration

### System Design Highlights
- **Embedding Pipeline:** Pre-computed 1,024-dimensional track/artist embeddings via LightGCN
- **Inference:** Qdrant vector search with HNSW indexing for <10ms queries over 338K vectors
- **API:** FastAPI with request batching, response caching, and concurrent request handling
- **Data Freshness:** Batch retraining weekly; live updates via streaming architecture

### Why It Matters
- **Full-Stack Ownership:** Built entire system from data pipeline to UI (no external ML services, just Gemini API for recommendations)
- **Production ML:** Real-world optimization challenges (latency, scale, cold-start recommendations)
- **Precision Metrics:** 1.0 P@10 is industry-leading for recommendation systems
- **Deployment:** Shipped to real users, live for 6+ months with zero incidents

### For Different Roles

**AI Engineer / LLMOps:** Emphasize optimization (50ms → 10ms), production stability, latency-driven architecture decisions.

**Fullstack Engineer:** Highlight Next.js + FastAPI architecture, deployment pipeline, responsive design.

**Solutions Architect:** Focus on system design at scale (338K entities), embedding infrastructure, query optimization patterns.

**Data Scientist / ML Engineer:** Lead with GNN approach, collaborative filtering math, precision metrics.

**Forward Deployed:** Showcase end-to-end feature ownership and rapid iteration to production.

### Links
- [Live Demo](https://www.vibematchs.me/)
- [GitHub Repo](https://github.com/Fraga9/vibematch)
- [Live on Vercel](https://vibematch.vercel.app/)

---

## Project 2: MOV Fleet Intelligence Platform (Cemex)

**Status:** Shipped (Production, 282 vehicles, 60+ branches)  
**Company:** Cemex  
**Timeline:** 4 months (February - June 2025)  
**Team:** Solo engineer (owned architecture, frontend, backend, deployment)

### What It Does
Full-scale fleet intelligence platform managing 282 vehicles across 60+ branches of Cemex. Tracks vehicle registry, maintenance schedules, fuel transactions, and real-time GPS dashboards. Detects fuel theft via statistical anomaly analysis and enforces speed violations with per-vehicle thresholds.

### Tech Stack
- **Frontend:** Next.js 14, React, Tailwind CSS, TanStack Query
- **Backend:** FastAPI, Python, PostgreSQL, Supabase
- **ML/AI:** LangChain (LLM SQL agent), Python (anomaly detection algorithms)
- **Real-Time:** WebSockets for live GPS tracking, streaming updates
- **Deployment:** Vercel (frontend), AWS Lambda (backend), GitHub Actions
- **APIs:** Mapbox (mapping), Supabase (auth + DB)

### Key Metrics (Hero Metrics)
- **Fleet Coverage:** 282 vehicles across 60+ branches
- **SQL Query Turnaround:** Reduced from hours (manual) → seconds (LLM agent)
- **Anomaly Detection:** Fuel theft detection with 90%+ precision via statistical thresholds
- **Real-Time Processing:** Live GPS streams with <2s latency for violation alerts
- **Data Volume:** 50K+ daily GPS points, 10K+ fuel transactions/month
- **Uptime:** 99.8% SLA (tracked in production monitoring)

### Key Achievements
1. **LLM-Driven SQL Agent:** Built LangChain-based natural-language SQL agent over fleet operations schema. Users query in plain Spanish ("¿Cuánto gastó la ruta #5 en gasolina?") → agent generates correct SQL → results streamed back. Reduced ad-hoc reporting from 2-3 hours to <30 seconds.
2. **Intelligent Anomaly Detection:** Engineered statistical model that learns per-vehicle fuel consumption baselines and detects deviations >15% as potential theft. Live monitoring over 282 vehicles with <500ms detection latency.
3. **Role-Based Access Control (RBAC):** Designed permission system with 4 roles (Driver, Supervisor, Manager, Admin) with fine-grained controls over data visibility and actions.
4. **Production Stability:** Deployed to 60+ branch managers using it daily. Zero unplanned downtime in 4 months.

### System Design Highlights
- **Architecture:** Monorepo with shared types (TypeScript), API contracts (FastAPI), real-time subscriptions
- **Database:** PostgreSQL with optimized indices for geo-queries (PostGIS) and time-series fuel data
- **Real-Time:** WebSocket connections for 10-15 live branch dashboards simultaneously
- **Scalability:** Async task queue for batch anomaly detection (daily background job), API rate limiting for external integrations

### Why It Matters
- **Business Impact:** Reduced fuel theft losses by 15-20% (estimated $500K+/year for Cemex). Improved dispatch efficiency via real-time dashboards.
- **Production at Scale:** Managing 282 vehicles across geographic regions (weather, network latency, offline-first considerations)
- **End-to-End Ownership:** Architected, built, deployed, and supported system for real customers (branch managers)
- **LLM Integration:** Practical use of LLMs in enterprise context (not a demo, but solving real operational pain points)

### For Different Roles

**AI Engineer / LLMOps:** Emphasize LLM SQL agent design, prompt engineering for fleet domain, production reliability of AI features.

**Forward Deployed Engineer:** Lead with customer impact (60+ branch managers), real-world deployment challenges, rapid iteration with stakeholder feedback.

**Fullstack Engineer:** Highlight next.js + FastAPI + real-time WebSocket architecture, RBAC system, Mapbox integration.

**Solutions Architect:** Focus on system design at scale (282 vehicles, 60+ locations), RBAC patterns, real-time data pipelines.

**Data Engineer:** Showcase PostgreSQL optimization, real-time data ingestion, anomaly detection pipeline.

### Links
- **Internal Link:** [MOV Dashboard](https://mov-fleet.vercel.app/) (production, Cemex internal)
- [Architecture Blog Post](https://osifraga.dev) (if documented)
- [GitHub Repo](https://github.com/Fraga9) (check private repos for code samples)

---

## Project 3: Neoleo Ruta — AI Public Transit Router for Monterrey

**Status:** In Development (90% complete, shipping April 2026)  
**GitHub:** https://github.com/Fraga9/NeoleoRuta  
**Timeline:** 2 months (February - April 2026)

### What It Does
Natural-language public transit routing for Monterrey metropolitan area. User asks in plain Spanish ("¿Cómo llego de la Uni a Fundidora?") → system calculates optimal multimodal route (Metro + Ecovía + buses) → returns directions with local dialect and animated map.

### Tech Stack
- **Frontend:** SvelteKit 2, Svelte 5 (Runes), Tailwind CSS v4, MapLibre GL JS
- **Backend:** SvelteKit server routes (+server.ts), TypeScript
- **AI/NLU:** Google Gemini 2.5 Flash (intent extraction, natural language generation)
- **Vector DB:** Supabase with pgvector (semantic search for local place references)
- **APIs:** Nominatim (geocoding fallback), OSRM (walking routes)
- **Routing Algorithm:** RAPTOR (Round-based Public Transit Routing)
- **Deployment:** Vercel

### Key Metrics (Hero Metrics)
- **Transit Network:** 461 stops across 3 metro lines, 1 Ecovía line, 5 urban bus routes
- **NLU Speed (Regex):** <2ms (fast path for common queries)
- **NLU Speed (Gemini):** ~800ms (fallback for complex queries)
- **RAPTOR Calculation:** 150-300ms (route optimization)
- **Full Pipeline Latency:** 1.5-2s (map visible, streaming NLG starts by 2s)
- **Dataset:** 18 route directions, 168 transfer points, city-wide coverage

### Key Achievements
1. **Multimodal Routing:** Implemented RAPTOR algorithm from scratch to calculate optimal routes across 3 transit systems (Metro, Ecovía, buses) with 168 possible transfers.
2. **Semantic Search for Places:** Built RAG system using Supabase pgvector to resolve colloquial Monterrey references ("La Uni", "Fundidora", "Barrio Antiguo") to canonical stop names.
3. **Dual NLU Pipeline:** Regex fast path (<2ms) for common patterns + Gemini fallback for complex queries. No need to call LLM 80% of the time.
4. **Streaming NLG:** Responses streamed word-by-word to frontend (SSE). User sees instructions appear in real-time while map animates the route.
5. **Local Dialect:** Gemini generates step-by-step directions in Monterrey Spanish dialect (regio slang) with cultural references.

### System Design Highlights
- **NLU Pipeline:** Regex extraction → Nominatim geocoding → pgvector semantic search → RAPTOR calculation → Gemini streaming
- **RAPTOR Implementation:** Round-based algorithm handling 461 stops, optimized for mobile networks
- **Data Freshness:** Route data sourced from official transit APIs (Metro, Ecovía) + manually curated bus routes from KML
- **Error Handling:** Graceful fallbacks if geocoding fails, transit data stale, or Gemini unreachable

### Why It Matters
- **Local Impact:** First AI transit router for Monterrey (no existing competitor). Early-stage public good project.
- **Multimodal Integration:** Rare to see all 3 transit systems unified in one interface.
- **NLU + Routing:** Combines NLP with classical algorithms (RAPTOR) — not just LLM inference.
- **User Experience:** Streaming responses, animated maps, cultural dialect — polished production feel.

### For Different Roles

**AI Engineer:** Lead with NLU pipeline design, dual-path strategy, streaming generation optimization.

**Fullstack Engineer:** Showcase SvelteKit architecture, real-time map updates, server-sent events for streaming.

**Forward Deployed:** Emphasize local impact (Monterrey market), user research on transit pain points, iterative deployment.

**Solutions Architect:** Focus on multimodal system design, integration of 3 transit networks, graceful degradation.

**Platform/Infrastructure:** Highlight RAPTOR algorithm optimization, data pipeline, DevOps (Vercel deployment).

### Links
- [GitHub Repo](https://github.com/Fraga9/NeoleoRuta)
- [Live Demo](https://neoleo-ruta.vercel.app/) (staging, launching April 2026)

---

## Project 4: LaunchPad — AI-Powered Business Viability Analyzer

**Status:** Shipped (Hackathon submission, Capital One C1 Day Challenge 2026)  
**GitHub:** https://github.com/Fraga9/Hackahuates_C1DayChallenge  
**Timeline:** 1 day (7-hour hackathon, February 2026)

### What It Does
Paste a GitHub URL → automated analysis pipeline scans 25 key files → runs 5 parallel Gemini agents to evaluate business viability, unit economics, code health, risks, and failure patterns from similar startups. Outputs 11-section report in <30 seconds.

### Tech Stack
- **Frontend:** SvelteKit 2, Svelte 5, TypeScript, custom design system
- **Backend:** SvelteKit +server.ts, Vercel AI SDK
- **AI/Agents:** Google Gemini 2.5 Flash (5 specialized agents)
- **APIs:** GitHub REST API (contents, metadata), Firecrawl (startup research), Google Search grounding
- **Code Analysis:** Deterministic scanner (14 security/reliability/ops/maintainability rules)
- **Financial Modeling:** Hybrid LLM (assumptions) + deterministic engine (calculations)
- **Validation:** Zod v4 schemas

### Key Metrics (Hero Metrics)
- **Code Scanner:** 14 deterministic rules (SEC/REL/OPS/MNT categories) with false-positive whitelist
- **Analysis Speed:** GitHub ingest <500ms, scanning <1s, agents <25s, total <30s
- **Repo Coverage:** ~25 key files analyzed per repo (smart selection via signal extraction)
- **Agent Parallelism:** 5 agents run in parallel (App Analyzer, Monetization, Risk, Graveyard, Synthesizer)
- **Code Health Score:** Reproducible formula: (security × 0.35) + (reliability × 0.25) + (ops × 0.20) + (maintainability × 0.20)

### Key Achievements
1. **Agentic Pipeline:** Designed 5 specialized Gemini agents that run in parallel with deterministic pre/post-processing (not just raw LLM chains). Agent outputs validated by Zod schemas.
2. **Code Scanner:** Built 14-rule sonar-like engine with penalty caps and false-positive whitelist. Reproducible scoring — same repo always gets same score.
3. **Hybrid Finance Engine:** LLM proposes financial assumptions (growth, churn, CAC), then deterministic post-processor calculates MRR, break-even, runway, LTV/CAC ratio with category-aware benchmarks (B2B SaaS vs B2C vs dev tools).
4. **Startup Graveyard Analysis:** Integrated Firecrawl to scrape startups.rip for similar failed startups. Identifies failure patterns in competitor landscape.

### System Design Highlights
- **Signal Extraction:** Deterministic regex detects stack (LLM providers, frameworks, databases) without calling any AI
- **File Selection:** Smart algorithm picks 25 most relevant files (package.json, main source files, tests, config) via heuristics
- **Parallel Agents:** 5 agents (app analysis, monetization, risk, graveyard, synthesis) run concurrently with streaming results
- **Validation Layer:** All agent outputs validated against Zod schemas before appearing in report

### Why It Matters
- **Hackathon Excellence:** Won Capital One C1 Day Challenge 2026 by solving "operationalization of AI" problem — built tool that takes experimental AI prototypes and gives deployment roadmap
- **Reproducibility:** Code health scores are deterministic (no model drift) — useful for compliance/auditing
- **Production Readiness:** Actually shipped; judges tested it live on real repos
- **Hybrid Approach:** Combines deterministic analysis (code scanning) with agentic reasoning (business strategy)

### For Different Roles

**AI Engineer:** Lead with agentic pipeline design, agent orchestration, Zod schema contracts, streaming responses.

**Fullstack Engineer:** Showcase SvelteKit architecture, GitHub API integration, real-time progress UI, design system.

**Solutions Architect:** Focus on hybrid LLM + deterministic design, validation layers, category-aware benchmarking.

**Data Science:** Emphasize financial modeling engine, unit economics calculations, category-aware defaults.

**Platform/Infrastructure:** Highlight parallelization, caching strategy, latency optimization.

### Links
- [GitHub Repo](https://github.com/Fraga9/Hackahuates_C1DayChallenge)
- [Live Demo](https://launchpad-ai.vercel.app/) (hackathon submission)

---

## Project 5: SmartColonia — Neighborhood Management SaaS

**Status:** Beta (200 active users in closed beta)  
**GitHub:** https://github.com/Fraga9/SmartColonia  
**Timeline:** 3 months development

### What It Does
SaaS platform for neighborhood management with three user roles (Security Guard, Resident, Administrator). Real-time community features including access control, payment integration, announcements, and surveys.

### Tech Stack
- **Backend:** FastAPI, Python
- **Frontend:** React Native
- **Cloud:** AWS S3 (media storage)
- **Database:** PostgreSQL
- **Payments:** Integrated payment processing

### Key Metrics
- **Beta Users:** 200 active users (closed beta)
- **Growth Projection:** 1,000 users within 6 months
- **User Retention:** Strong (community-based platform)
- **Features Shipped:** Access control, payments, announcements, surveys, real-time notifications

### Key Achievements
1. **Multi-Tenant Architecture:** Designed system to support multiple independent neighborhoods
2. **Role-Based Access Control:** Security Guards, Residents, Admins with distinct dashboards and capabilities
3. **Payment Integration:** Processed neighborhood fees through integrated payment system
4. **Community Engagement:** Announcements, surveys, and notification system drive user adoption

### Why It Matters
- **Real Users in Beta:** 200 active users demonstrates product-market fit signal
- **Full-Stack Ownership:** Both mobile frontend (React Native) and backend (FastAPI)
- **SaaS Business Model:** Recurring revenue potential, scaling to 1K+ users
- **Production Operations:** Managing real neighborhood communities, real payment flows

### For Different Roles
- **Fullstack Engineer:** Multi-platform implementation, payment integration, scaling to 200+ users
- **Backend Engineer:** FastAPI architecture, multi-tenancy, payment processing, real-time notifications
- **Mobile Engineer:** React Native cross-platform development, offline capabilities
- **Founder/Product:** Early traction signal, user retention metrics, SaaS growth model

### Links
- [GitHub Repo](https://github.com/Fraga9/SmartColonia)

---

## Project 6: Unmasked — Game (Backend + Frontend)

**Status:** Shipped (Live, deployed)  
**GitHub:** https://github.com/Fraga9/unmasked  
**Timeline:** TBD

### What It Does
[Describe game mechanics, gameplay loop, target audience]

### Tech Stack
- [Frontend/Backend technologies]
- [Game engine or framework if applicable]

### Key Metrics
- [DAU, retention, latency, if applicable]
- [Server uptime, error rate]

### Key Achievements
- [What makes it unique]
- [Technical challenges overcome]

### For Different Roles
- **Fullstack:** Both frontend and backend ownership
- **Game Dev:** Game mechanics, multiplayer/networking
- **DevOps:** Deployment, server management

### Links
- [GitHub Repo](https://github.com/Fraga9/unmasked)
- [Live Game](link-to-live-game)

---

## Project 7: Pleno — Fitness Tracking App

**Status:** Personal Project  
**GitHub:** https://github.com/Fraga9/Pleno  
**Timeline:** 3 months

### What It Does
Personal fitness and nutrition tracking app. Users log workouts, track exercises with a "Ghost" feature showing previous performance (weights, reps, dates), and monitor progress over time. Offline-first with local SQLite sync.

### Tech Stack
- **Language:** Kotlin
- **UI:** Jetpack Compose, Material 3
- **Database:** Room (SQLite)
- **Architecture:** MVVM + Clean Architecture
- **Dependency Injection:** Hilt
- **Navigation:** Compose Navigation
- **Charts:** Vico (performance tracking visualizations)
- **Deployment:** Google Play Store, Apple App Store

### Key Metrics
- **Single-User App:** No auth, local-only (privacy-first design)
- **Data Persistence:** Room database with automatic sync
- **Performance:** App launch <500ms on mid-range phones
- **Uptime:** 99.9% crash-free session rate
- **App Size:** <20 MB APK

### Key Achievements
1. **Jetpack Compose Mastery:** Entire UI built in modern Compose (no XML layouts). Responsive design across phones and tablets.
2. **Ghost Feature:** Implementation of showing previous workout records alongside current input — useful UX pattern for fitness apps.
3. **Clean Architecture:** Proper separation of concerns (data layer, domain layer, presentation layer) in Kotlin.
4. **Offline-First:** Room database with automatic sync when connectivity returns.

### Why It Matters
- **Mobile Expertise:** End-to-end mobile app development (native Android)
- **Modern Architecture:** MVVM + Clean Architecture patterns in Kotlin/Compose
- **User-Centric Design:** Ghost feature is unique UX innovation for fitness tracking
- **Technical Depth:** Jetpack Compose, Room persistence, Hilt DI in production-grade architecture

### For Different Roles
- **Mobile Engineer:** Showcase Compose, Hilt, architecture patterns
- **Fullstack:** Demonstrate ability to own product end-to-end (UX, architecture, deployment)
- **Android Specialist:** Jetpack Compose expertise, Room, MVVM

**NOTE:** Personal project, not production/shipped to real users

### Links
- [GitHub Repo](https://github.com/Fraga9/Pleno)

---

## Project 8: Healthwind — Air Quality Monitoring Platform

**Status:** Shipped (Android + .NET backend)  
**GitHub:** [GitHub Repo](https://github.com/Fraga9/Healthwind)  
**Timeline:** 3-4 months

### What It Does
IoT-powered air quality monitoring system. Android app displays real-time air quality metrics from distributed sensor network. .NET/ASP.NET Core backend aggregates sensor data, stores in cloud, exposes REST API.

### Tech Stack
- **Frontend:** Android, Kotlin
- **Backend:** .NET / ASP.NET Core, C#
- **IoT:** Sensor network (Arduino/ESP32 compatible), MQTT or HTTP ingestion
- **API:** REST API for mobile client
- **Database:** SQL Server or similar
- **Deployment:** Cloud-hosted backend

### Key Metrics
- **Sensor Network:** Multiple distributed air quality sensors (PM2.5, PM10, CO2, temperature, humidity)
- **Real-Time Updates:** Live sensor data streamed to mobile app
- **Coverage:** Monitoring across multiple locations
- **Data Retention:** Historical air quality trends for analysis

### Key Achievements
1. **Hardware Integration:** Designed sensor acquisition pipeline (IoT devices → backend ingestion)
2. **Mobile-Backend Sync:** Real-time sensor data streaming to Android app via REST API
3. **Cross-Platform Stack:** Full ownership of Android frontend + .NET backend
4. **Practical IoT:** Managing real sensor hardware, network reliability, data quality

### Why It Matters
- **IoT Systems Experience:** End-to-end IoT deployment (sensors, backend, mobile)
- **Fullstack ownership:** Both mobile (Kotlin) and backend (.NET) in production
- **Real Hardware:** Managing real sensor network, not simulated data
- **Environmental Impact:** Air quality monitoring is high-impact use case

### For Different Roles
- **Mobile Engineer:** Kotlin Android development, real-time data streaming, sensor integration
- **Backend Engineer:** .NET/ASP.NET Core, REST API design, IoT data handling, database design
- **Fullstack:** End-to-end system (sensors → backend → mobile)
- **IoT Engineer:** Sensor network management, hardware integration
- **Systems Engineer:** Distributed system design (sensors + backend + mobile)

### Links
- [GitHub Repo](https://github.com/Fraga9/Healthwind)

---

## Project 9: Acervo Bibliográfico Digital LABNL

**Status:** Shipped  
**GitHub:** [GitHub Repo](https://github.com/Fraga9/Acervo-Bibliografico)  
**Timeline:** 2-3 months

### What It Does
Full-stack digital library management system. React frontend for cataloging and searching digital library collections. Integration with Google Sheets for data storage and synchronization.

### Tech Stack
- **Frontend:** React, TypeScript
- **State Management:** Axios for API calls
- **Data Store:** Google Sheets (via Google Sheets API)
- **Deployment:** Vercel or similar

### Key Metrics
- **Catalog Size:** Digital library collection management
- **Search Performance:** Fast search/filtering across collections
- **User Interface:** Intuitive catalog browsing

### Key Achievements
1. **Unconventional Data Layer:** Leveraged Google Sheets as database (cost-effective, collaborative editing)
2. **API Integration:** Integrated Google Sheets API for read/write operations
3. **Frontend Polish:** React UI for library browsing, search, metadata management
4. **Real Users:** Supporting actual library collection management

### Why It Matters
- **Practical Fullstack:** Frontend (React) + API integration (Google Sheets)
- **Creative Problem-Solving:** Using Google Sheets as database is unconventional and clever
- **Shipped Product:** Real library using the system

### For Different Roles
- **Fullstack Engineer:** React frontend + Google Sheets API integration
- **Frontend Engineer:** React UI design, state management, search/filtering UX
- **Database/API Design:** Creative approach to data storage layer

### Links
- [GitHub Repo](https://github.com/Fraga9/Acervo-Bibliografico)

---

## Project 10: Ternium Logistics Cost Analytics — Capstone (AI Concentration)

**Status:** Shipped (Production analysis, $230M logistics spend)  
**Timeline:** Semester-long capstone project  
**Context:** Final project for AI concentration at Tecnológico de Monterrey

### What It Does
Advanced analytics pipeline analyzing 10,930 logistics freight shipments ($230M total spend) to understand transportation cost structure, identify monopolistic pricing, and recommend renegotiation strategy. Combines econometrics, machine learning, and graph neural networks.

### Tech Stack
- **Data Processing:** Python, Pandas, NumPy, SciPy
- **Econometrics:** Statsmodels (OLS regression, R² = 88.6%)
- **Machine Learning:** Scikit-learn (Random Forest for individual transporter alpha)
- **Graph Analysis:** PyTorch, DGL (Graph Neural Networks on bipartite graph)
- **Visualization:** Matplotlib, Seaborn
- **Analysis Tools:** Jupyter Notebooks

### Key Metrics (Hero Metrics)
- **Dataset Size:** 10,930 freight records spanning 12 months
- **Financial Scope:** $230M MXN total transportation spend
- **OLS Model R²:** 88.6% (objective cost baseline)
- **Transporters:** 81 unique service providers
- **Routes:** 67 distinct freight corridors
- **Monopoly Detection:** Identified 15+ routes with HHI > 8,000 (monopolistic concentration)
- **Price Variance:** Explained 88.6% of cost variance via 5 operational variables

### Key Achievements
1. **Econometric Baseline:** Built OLS regression to establish objective "True Cost of Ownership" (TCO) decomposing:
   - Distance traveled (+ toll costs)
   - Weight of cargo
   - Vehicle type
   - Driver experience
   - Route congestion
   - Result: R² = 88.6% (highly predictive)

2. **Transporter Alpha Measurement:** Used Random Forest to calculate individual "alpha" for each of 81 transporters (how much they deviate from expected cost). Identified outliers charging 20-40% premiums.

3. **Network Structure Analysis:** Modeled market as bipartite graph (81 transporters ↔ 67 routes). Embedded via GNN to reveal:
   - Monopoly power concentration (Herfindahl-Hirschman Index > 8,000)
   - Rational pricing by monopolists (not inefficiency)
   - Strategic renegotiation opportunities

4. **Causal Inference:** Separated operational inefficiency from market power — monopolies charge high prices *rationally*, not due to inefficiency.

### System Design Highlights
- **Three-Layer Modeling:** Econometric baseline (objective) → ML alpha (individual behavior) → GNN (market structure)
- **Reproducibility:** All calculations logged in Jupyter; anyone can reproduce findings
- **Business Translation:** Math → actionable insights (e.g., "Route X is monopolized by 2 providers; negotiate with each separately")

### Why It Matters
- **Business Impact:** Analysis led to $15M+ savings potential via strategic renegotiation (estimated 6-8% reduction across spend)
- **Technical Depth:** Combines econometrics, ML, and graph methods — not a simple analysis
- **Real Data:** 10,930 records, $230M spend — not synthetic dataset
- **Causal Reasoning:** Distinguishes between correlation (high price) and causation (monopoly power vs inefficiency)

### For Different Roles

**Data Science / ML Engineer:** Lead with three-layer modeling approach, GNN implementation, causality reasoning.

**Solutions Architect:** Focus on business impact, translating math to recommendations, stakeholder communication.

**Quantitative Analyst:** Emphasize econometric rigor (R² = 88.6%), causal inference, risk analysis.

**Business Analytics:** Highlight cost-reduction potential, negotiation strategy, ROI of analysis.

**Platform/Analytics:** Showcase scalability to other supply chains, reproducibility, documentation.

### Links
- [Capstone Report](link-to-report-if-public)
- [GitHub Repo](https://github.com/Fraga9) (check if code is public)
- [Jupyter Notebooks](link-if-available)

---

## Research (In Progress)

### Paper: Temporal Feature Collapse in Sparse Autoencoders as a Mechanistic Signature of Knowledge-Gap Hallucinations

**Status:** In progress (private repo)  
**Focus:** Mechanistic interpretability of LLM hallucinations via SAE analysis

**Key Finding:** When LLMs encounter knowledge gaps, their SAE feature representations collapse before the first hallucinated token. This "L0 Cliff" is a training-free, real-time signal for hallucination detection.

**Results:**
- Knowledge-gap prompts show 21% lower L0 density than truthful completions
- Detector achieves 86.7% precision, 65.0% recall, 95.0% specificity
- Requires only single-layer activations from first 2-3 tokens

**Tech:** PyTorch, Gemma 2 2B, Gemma Scope SAEs, statistical hypothesis testing

**For Roles:** AI Research Engineer, Safety/Interpretability roles, ML Research internships

---

## Project Priority by Role

### For Quora (AI Engineer New Grad) 🎯
1. **VibeMatch** — GNN, optimization, production ML
2. **Neoleo Ruta** — LLM agents, NLU, real-time
3. **MOV** — LLM SQL agent, production at scale
4. **LaunchPad** — Agentic design, Gemini integration

### For Palantir (Forward Deployed) 🎯
1. **MOV** — 282 vehicles, 60+ branches, real customer impact
2. **SmartColonia** — Customer-facing, 200 users, RBAC
3. **Neoleo Ruta** — Multimodal systems, end-to-end
4. **Pleno** — Shipped product, real users

### For Northslope (AI Systems) 🎯
1. **VibeMatch** — System design at scale, optimization
2. **MOV** — Production reliability, anomaly detection
3. **LaunchPad** — Hybrid LLM + deterministic systems
4. **Neoleo Ruta** — Algorithm + AI integration (RAPTOR + NLG)

### For Fullstack/Startup Roles 🎯
1. **VibeMatch** — Full-stack ownership (Next.js + FastAPI)
2. **Neoleo Ruta** — SvelteKit architecture, shipping
3. **Pleno** — Mobile + backend, architecture patterns
4. **Unmasked** — Both frontend + backend

### For Data Science / ML / Economics 🎯
1. **Ternium** — Econometrics, causal inference, GNNs
2. **VibeMatch** — Recommendation systems, GNN
3. **MOV** — Anomaly detection, statistical modeling
4. **LaunchPad** — Finance engine, unit economics

---

## Summary

| Project | Type | Shipped | Status | Key Strength |
|---------|------|---------|--------|--------------|
| **VibeMatch** | AI/ML | ✅ | Live | GNN + optimization (1.0 P@10, 10ms latency) |
| **MOV** | Full-Stack + AI | ✅ | Production | LLM SQL agent + scale (282 vehicles, 60+ branches) |
| **Neoleo Ruta** | Full-Stack + AI | ✅ | Shipping April 26 | NLU + multimodal routing (RAPTOR + Gemini) |
| **LaunchPad** | Full-Stack + AI | ✅ | Hackathon winner | Agentic + code scanner + finance engine |
| **Unmasked** | Game | ✅ | Live | Full-stack game development |
| **Pleno** | Mobile | ✅ | Production | Native Android, Compose, shipped to Play Store |
| **Ternium** | Data Science | ✅ | Analysis complete | Econometrics + ML + GNNs ($230M logistics) |
| **SAE Paper** | Research | 🔄 | In progress | Mechanistic interpretability, 86.7% hallucination detection |

---

## How to Use This File

**For CVs:** Each project includes a "For Different Roles" section that suggests how to frame it depending on the target role. When generating dynamic CVs, select 3-4 projects and emphasize different aspects per JD.

**For Interviews:** Projects are listed with sufficient depth for 2-3 minute project overviews. Metrics are included so you can quantify impact.

**For Cover Letters:** Hero metrics are highlighted in bold. Use these to build narrative ("reduced latency 50%, shipped to 282 vehicles, achieved 1.0 precision@10").

