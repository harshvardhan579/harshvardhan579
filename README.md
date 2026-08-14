<div align="center">

# Harshvardhan Singh

### AI / Software Engineer

**I build LLM and computer-vision products end-to-end — with the guardrails, tests, and failure semantics that make them safe to actually run.**

FastAPI · Next.js / React · PostgreSQL · Docker · TypeScript
&nbsp;·&nbsp; **1,072 automated tests** in my most recent project alone &nbsp;·&nbsp; **3 live demos** below

[![LinkedIn](https://img.shields.io/badge/LinkedIn-harshvardhan2-0A66C2?style=for-the-badge)](https://linkedin.com/in/harshvardhan2)
[![Email](https://img.shields.io/badge/Email-Get_in_touch-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:harshvardhan1singh1@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-harshvardhan579-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/harshvardhan579)

</div>

---

## Selected work at a glance

| Project | One line | Stack | |
| --- | --- | --- | --- |
| **[APILoom](https://github.com/harshvardhan579/apiloom)** | Plain-English REST procedures become reviewed, reusable runbooks with a full audit trail. | FastAPI · Next.js 16 · PostgreSQL · Docker | [Code](https://github.com/harshvardhan579/apiloom) |
| **[CivicPulse](https://github.com/harshvardhan579/civicpulse)** | A bounded, human-reviewed AI workflow where a human correction never overwrites the model. | React 19 · FastAPI · PostgreSQL 18 · Railway | **[Live](https://frontend-production-d0ad.up.railway.app)** · [Code](https://github.com/harshvardhan579/civicpulse) |
| **[Pocket Arcade](https://github.com/harshvardhan579/arcade-game)** | Five original browser games, zero runtime assets, production-grade test suite. | TypeScript · Phaser 3 · Vercel · Supabase | **[Live](https://arcade-game-five.vercel.app/)** · [Code](https://github.com/harshvardhan579/arcade-game) |
| **[NewsVerify](https://github.com/harshvardhan579/news_verify)** | Multimodal claim assessment grounded in retrieved evidence the model cannot invent. | GPT-4o · LangChain · SerpApi · Streamlit | [Code](https://github.com/harshvardhan579/news_verify) |
| **[AI Form Evaluator](https://github.com/harshvardhan579/form_eval_app)** | Real-time exercise-form coaching from pose landmarks — raw video never leaves the browser. | MediaPipe · FastAPI WebSockets · React | **[Live](https://form-eval-app.vercel.app)** · [Code](https://github.com/harshvardhan579/form_eval_app) |
| **[Hybrid ML Scheduler](https://github.com/harshvardhan579/hybrid-ml-scheduler)** | Six GPU/CPU scheduling strategies raced live against a brute-force optimal baseline. | Python · FastAPI · WebSockets · DQN / RF | [Code](https://github.com/harshvardhan579/hybrid-ml-scheduler) |

<sub>Also on this profile: PostgreSQL-backed CLI systems, OS simulations, and C/C++ systems coursework.</sub>

---

## Featured builds

### APILoom — local-first AI API runbooks with reviewed execution

> Getting an LLM to write an API call is the easy part. The hard part is making that call **reviewable before it fires, repeatable afterwards, and honest about what happened** when it dies halfway through a mutation.

[![Code](https://img.shields.io/badge/Code-Repository-181717?style=for-the-badge&logo=github)](https://github.com/harshvardhan579/apiloom)
![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-16-000?style=for-the-badge&logo=next.js)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

![APILoom Studio showing a saved two-step GET runbook with typed inputs, search, favourites, and run controls](https://raw.githubusercontent.com/harshvardhan579/apiloom/main/assets/screenshots/studio.png)

- **Planning is separated from execution.** OpenAI function calling is validated into a Pydantic workflow schema and saved as a runbook. Re-running it needs no further model call — execution is deterministic and inspectable.
- **Mutations require explicit, one-use approval.** The preview token is bound to the plan revision, the resolved-input digest, and the connection versions; changing any of them invalidates it.
- **SSRF-aware destination policy.** Private, loopback, link-local, and cloud-metadata addresses are denied and re-checked at connection time. Redirects aren't followed, and URL authorities can't be interpolated.
- **Honest failure semantics.** If a mutation is interrupted after transmission may have begun, the run records `UNKNOWN_OUTCOME` instead of pretending it failed safely.
- **Built to be operated.** Alembic migrations, startup reconciliation of stale runs, retention purge, health and readiness probes, and Fernet-encrypted credentials bound to an exact origin.

<details>
<summary><b>Engineering detail</b> — CI gates, execution model, and the trust boundary</summary>

<br>

**Quality gates in CI:** `ruff` · `mypy` · `pytest` at ≥80% enforced coverage · `bandit` · `pip-audit` against hash-pinned dependency locks · frontend typecheck, lint, and `npm audit`. A deterministic mutation-deadline regression is designed to be run 50× in a row to prove it isn't flaky.

**Execution model:** dependencies must point backwards and form a valid acyclic plan; steps run sequentially with bounded requests and responses, total deadlines, cancellation, and idempotency-aware retries. Safe steps retry transient failures automatically; mutations retry *only* with an explicit idempotency key.

**Trust boundary:** self-hosted, single-user, loopback-bound by default, with PostgreSQL never published to the host. Sensitive header names and injected connection values are redacted in storage, and exports refuse to run when heuristics detect literal secrets. The scope is stated in the repo as an explicit non-goal list rather than left implied.

</details>

<br>

### CivicPulse — bounded AI workflows with a human who always has the last word

> Two workflows on one persistent domain model, built around a single rule: **the system records what the model said and what the human decided, separately, forever.** All data is synthetic; no outbound sending of any kind exists.

[![Live Demo](https://img.shields.io/badge/Try-Live_Demo-00C7B7?style=for-the-badge)](https://frontend-production-d0ad.up.railway.app)
[![Code](https://img.shields.io/badge/Code-Repository-181717?style=for-the-badge&logo=github)](https://github.com/harshvardhan579/civicpulse)
![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-18-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

![A completed CivicPulse message run showing status and figures, the guidance given, and the bounded AI workflow recorded step by step: generation, AI critique, deterministic claim check, bounded revision, and the outstanding human review](https://raw.githubusercontent.com/harshvardhan579/civicpulse/main/docs/screenshots/message-run-review-1440x900.png)

- **A five-stage bounded workflow:** generate → AI critique → *deterministic* claim check → at most one revision → human review. The claim check is plain code, not a model — it flags numbers that never appeared in the brief.
- **The workflow module never receives a database session.** That makes "no transaction is held open across a provider call" a structural property of the architecture rather than a code-review convention. A run costs at most three provider calls no matter how many variants it produces.
- **Human corrections are stored *beside* the model's label, never on top of it**, so the dashboard shows classifier output and corrected output side by side — and disagreement between them stays measurable.
- **Privacy enforced by import rules.** No module under `app/survey` may import `langchain` or `openai`, because survey text shouldn't leave the machine. Survey responses carry no respondent ID — not even a pseudonymous one — so answers can't be linked across datasets.
- **1,072 automated tests:** 550 backend (pytest), 427 frontend (Vitest), 95 end-to-end (Playwright), plus eight hand-written Alembic migrations on a single head.

<details>
<summary><b>Engineering detail</b> — a production bug found by measurement, not by testing</summary>

<br>

Rate limits were keyed on the unforgeable end of `X-Forwarded-For`. In production the limiter silently **stopped binding**, because the edge terminates TLS on a rotating fleet: 40 requests in 11 seconds all passed a limit of 30/minute. It was caught by measuring the live deployment, not by any test — and the fix and the reasoning are both written up in [`docs/DECISIONS.md`](https://github.com/harshvardhan579/civicpulse/blob/main/docs/DECISIONS.md).

Other decisions recorded there, mistakes included: the model never sees a UUID (it gets temporary references and identity is resolved from a stored snapshot); every Alembic revision is hand-written after autogenerate missed things more than once; versioned JSON contracts are frozen once written and dispatched on read rather than edited in place.

**Deployed on deterministic stand-in providers, deliberately.** A recruiter clicking the link sees the same thing every time, an unauthenticated demo can't spend money on a stranger's request, and nothing anyone types is shipped to a third party. Startup **fails closed** if public demo mode is ever configured with a live provider.

</details>

<br>

### Pocket Arcade — five original browser games, zero runtime assets

> A games project judged as production software: deterministic logic engines, a real leaderboard backend, and a validation pipeline that catches visual regressions pixel by pixel.

[![Live Demo](https://img.shields.io/badge/Play-Live_Demo-4DFFE1?style=for-the-badge)](https://arcade-game-five.vercel.app/)
[![Code](https://img.shields.io/badge/Code-Repository-181717?style=for-the-badge&logo=github)](https://github.com/harshvardhan579/arcade-game)
![TypeScript](https://img.shields.io/badge/TypeScript-strict-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Phaser](https://img.shields.io/badge/Phaser-3.90-8A4FFF?style=for-the-badge)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=for-the-badge&logo=supabase&logoColor=white)

![The Pocket Arcade home screen showing five games with procedurally drawn emblems, local high scores, and theme controls](https://raw.githubusercontent.com/harshvardhan579/arcade-game/main/docs/images/pocket-arcade-home.png)

- **The architecture boundary is enforced, not requested.** Pure deterministic `*Logic.ts` engines are fully separated from Phaser renderers by a custom import-boundary check that runs in CI.
- **Zero runtime assets** — no images, sprites, fonts, or audio files ship. Every visual is procedural and all audio is synthesized with WebAudio.
- **A real backend, not a mock.** The global leaderboard runs on Vercel Functions and Supabase Postgres with server-side name validation, profanity and reserved-name filtering, score-plausibility checks, salted-IP rate limiting, and a service-role key that never reaches the client.
- **Validation across four layers:** Vitest logic tests, Playwright desktop *and* mobile e2e, pixel-signature canvas regression tests for rendering drift, plus lint, typecheck, and a secret-grep safety check.
- **Product polish that survives contact with real devices:** responsive touch controls, a mobile no-scroll layout check in CI, dark/light themes, and reduced-motion support.

**Games:** Neon Serpent · Bounce Circuit · Star Courier · Lane Rush · Circuit Stack

---

## More projects

### [NewsVerify](https://github.com/harshvardhan579/news_verify) — multimodal fact-checking assistant

Accepts an image and an optional claim, uses GPT-4o for visual analysis, generates three distinct verification queries, runs them concurrently through SerpApi, and returns a **typed** `likely supported` / `likely misleading` / `inconclusive` assessment for human review.

The design decision worth reading: **evidence is addressed by ID.** Retrieved results are normalized, deduplicated, capped, and labelled `E001…`; the model may only cite those IDs, and the application resolves them back to URLs the search API actually returned. A hallucinated link cannot reach the UI. Reverse-image search is off by default because enabling it publishes the image publicly — an opt-in, not a default.

`Python` `LangChain` `GPT-4o` `Pydantic structured output` `asyncio` `Streamlit` `SerpApi`

### [AI Form Evaluator](https://github.com/harshvardhan579/form_eval_app) — real-time exercise coaching from pose landmarks

MediaPipe Pose runs **in the browser**; only landmark coordinates cross the WebSocket, so raw video never reaches the server. A FastAPI service scores them with explicit joint-angle state machines, and the dashboard overlays the skeleton and live angle so every cue can be traced back to the signal that produced it.

Engineering choices that matter: form faults must persist **five consecutive frames** before being reported, and a sustained fault counts as one incident rather than hundreds. Backpressure exists on both ends — the client keeps one request outstanding, the server drains its queue and processes only the newest landmark frame while preserving control messages in order. Coordinates are normalized against torso length, so feedback doesn't drift with the user's distance from the camera.

`Python` `FastAPI` `WebSockets` `MediaPipe` `React` `NumPy` `Web Speech API`

### [Hybrid ML Scheduler](https://github.com/harshvardhan579/hybrid-ml-scheduler) — six scheduling strategies, raced live

A simulation framework for heterogeneous GPU/CPU task scheduling. Every generated task is scheduled by **all six strategies simultaneously** — Round Robin, Random, Greedy, a Random Forest hybrid, a DQN agent, and a brute-force **Oracle** that grid-searches the optimal GPU fraction.

That Oracle is the point: the learned schedulers are scored against the *actual optimum*, not just against each other. Results stream to a React dashboard over WebSockets with time, energy, and cost metrics, and the hybrid model retrains on accumulated execution history every 50 tasks.

`Python` `FastAPI` `WebSockets` `scikit-learn` `Deep Q-Learning` `React`

---

## How I engineer

- **Boundaries enforced by tooling, not by discipline.** An import-boundary check keeps game logic out of the renderer. A workflow module that structurally cannot hold a database session can't hold one open across a network call. A survey package forbidden from importing LLM clients can't leak survey text. Rules a linter enforces survive; rules in a style guide don't.
- **Tests are the definition of done.** 1,072 across CivicPulse; four validation layers on Pocket Arcade; enforced coverage floors, static typing, dependency auditing, and secret scanning wired into CI rather than run by hand.
- **Systems should be honest about failure.** `UNKNOWN_OUTCOME` when a mutation may have landed. Analysis that clears every label rather than leaving half a dataset classified. A verdict of `inconclusive` when the evidence doesn't support one.
- **Decisions get written down, including the wrong ones.** My repos document why things are built the way they are, what the limitations are, and which bugs only showed up in production.
- **AI tooling is leverage, not an excuse.** I use it heavily and I don't treat generated code as done until it builds, passes tests, and survives real use.
- **I want the whole path:** idea → system design → implementation → validation → deployment → the boring reliability work that makes it usable.

---

## Toolkit

**Languages**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

**AI / ML / Computer vision**
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0097A7?style=flat-square)

**Backend & data**
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Pydantic](https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat-square&logo=sqlalchemy&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-5FA04E?style=flat-square&logo=node.js&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-FF4438?style=flat-square&logo=redis&logoColor=white)
![Alembic](https://img.shields.io/badge/Alembic-6BA81E?style=flat-square)
![WebSockets](https://img.shields.io/badge/WebSockets-010101?style=flat-square)

**Frontend**
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Phaser](https://img.shields.io/badge/Phaser_3-8A4FFF?style=flat-square)

**Infrastructure & tooling**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat-square&logo=vercel&logoColor=white)
![Railway](https://img.shields.io/badge/Railway-0B0D0E?style=flat-square&logo=railway&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?style=flat-square&logo=supabase&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

**Testing & quality**
![Pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Vitest](https://img.shields.io/badge/Vitest-6E9F18?style=flat-square&logo=vitest&logoColor=white)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat-square)
![mypy](https://img.shields.io/badge/mypy-2A6DB2?style=flat-square)
![Ruff](https://img.shields.io/badge/Ruff-D7FF64?style=flat-square&logo=ruff&logoColor=black)
![ESLint](https://img.shields.io/badge/ESLint-4B32C3?style=flat-square&logo=eslint&logoColor=white)
![Bandit](https://img.shields.io/badge/Bandit-FFC107?style=flat-square)

---

## What I'm looking for

Roles where I own a product from system design through to the deployment that other people depend on:

**AI Engineer** &nbsp;·&nbsp; **Software Engineer, AI Products** &nbsp;·&nbsp; **Machine Learning Engineer** &nbsp;·&nbsp; **Backend / Full-Stack Engineer** &nbsp;·&nbsp; **Applied Computer Vision Engineer** &nbsp;·&nbsp; **Research / Prototype Engineer**

I'm most interested in teams building with LLMs and agents, computer vision, developer tools, data-heavy products, or the infrastructure underneath AI workflows — especially where correctness, auditability, and safe failure actually matter.

---

<div align="center">

### Let's talk

[![LinkedIn](https://img.shields.io/badge/LinkedIn-harshvardhan2-0A66C2?style=for-the-badge)](https://linkedin.com/in/harshvardhan2)
[![Email](https://img.shields.io/badge/Email-harshvardhan1singh1%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:harshvardhan1singh1@gmail.com)

**Open to opportunities** — the fastest way to see how I work is to [try CivicPulse](https://frontend-production-d0ad.up.railway.app) or [read the APILoom source](https://github.com/harshvardhan579/apiloom).

</div>
