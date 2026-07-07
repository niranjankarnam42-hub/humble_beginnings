# AI Engineer / Forward Deployed Engineer — 6-Month Curriculum
**Target roles:** AI Engineer, Forward Deployed Engineer (FDE), Solutions Engineer, AI Deployment Engineer at enterprise B2B SaaS companies
**Stack focus:** AWS (Bedrock, SageMaker, Lambda, AgentCore) + Python + LLM application engineering
**Time commitment:** 25–30 hrs/week over ~26 weeks
**Your starting point:** Cursor user, basic Python, strong n8n/Make automation experience

---

## Why your background is an advantage (lean into this)

FDE roles are half engineering, half consulting. Companies like Palantir, OpenAI, Anthropic, Sierra, Glean, and Writer hire FDEs who can sit with an enterprise customer, understand a messy business process, and ship a working AI solution fast. You already do the second half — n8n/Make work *is* solution deployment, just low-code. Your entire 6 months is about replacing the low-code layer with real engineering (Python, AWS, production practices) while keeping your workflow-thinking as your differentiator.

Your positioning statement (use it everywhere): *"I've automated real business workflows for X years — now I build them as production AI systems on AWS."*

---

## Certification Path (the 2026 lineup)

AWS restructured its AI certifications recently. The old ML Specialty is retired (last exam date was March 31, 2026). Your path is now role-based and fits FDE work perfectly:

| # | Certification | When | Cost | Why |
|---|--------------|------|------|-----|
| 1 | **AWS Certified AI Practitioner (AIF-C01)** | End of Month 2 | $100 | Foundational — AI/ML/GenAI vocabulary, responsible AI, AWS AI services. Fast win, gets AWS on your resume early. 65 questions, 90 min, passing score 700. |
| 2 | **AWS Certified Machine Learning Engineer – Associate (MLA-C01)** | End of Month 5 | $150 | The core hands-on cert: SageMaker, deployment patterns (real-time/serverless/batch), MLOps pipelines, monitoring, IAM/security. Passing it also auto-renews your AI Practitioner. |
| 3 | **AWS Certified Generative AI Developer – Professional (AIP-C01)** | Month 7–9 (post-program stretch goal) | $300 | Brand new professional cert — production GenAI: Bedrock, RAG, vector stores, Knowledge Bases, Agents/AgentCore, guardrails, cost optimization. This is *the* FDE-relevant credential. 85 questions, 205 min. |

Optional insurance cert: **Solutions Architect – Associate (SAA-C03)** if you find enterprises you interview with care about general cloud architecture. Skip unless needed.

---

# SEMESTER 1 (Months 1–3): Engineering Foundations

## Month 1 — Python for Real + Engineering Fundamentals

**Goal:** Go from "basic Python" to "can build and ship a Python service." This is the single highest-leverage month.

**Courses/videos:**
- Harvard **CS50P (Python)** — free, rigorous, ~10 problem sets. Do all of it.
- **Corey Schafer** YouTube: Python OOP series, virtual environments, decorators
- **FastAPI official tutorial** (fastapi.tiangolo.com) — end to end
- Git & GitHub: **The Odin Project's Git module** or MIT's Missing Semester (lecture 6)

**Books:**
- *Python Crash Course* (Eric Matthes) — weeks 1–2 speed run
- *Fluent Python* (Luciano Ramalho) — buy it, use as a reference all 6 months, don't read cover to cover

**Skills checklist by end of month:**
- [ ] Python: functions, classes, typing, async basics, error handling, packaging (uv or pip)
- [ ] Build a REST API with FastAPI + Pydantic
- [ ] Git workflow: branches, PRs, meaningful commits (all projects on GitHub from day one)
- [ ] SQL basics (SQLite → Postgres): joins, indexes, simple schema design
- [ ] Docker: containerize a FastAPI app

**Project 1 (Week 3–4): "Kill an n8n workflow"**
Take one automation you've actually built in n8n or Make and rebuild it in pure Python: FastAPI webhook receiver → business logic → external API calls → Postgres. Containerize it. Write a README comparing the two approaches (cost, latency, maintainability). This is a *fantastic* portfolio piece and LinkedIn post because it tells your transition story.

---

## Month 2 — LLM Engineering Core + First AWS Exposure

**Goal:** Master the LLM application layer — the actual "AI engineer" skillset — and pass your first cert.

**Courses/videos:**
- **Anthropic and OpenAI official docs + cookbooks** — read these before any framework. Prompting, tool use/function calling, structured outputs, streaming.
- **DeepLearning.AI short courses** (free, 1–2 hrs each): "Building Systems with the ChatGPT API", "LangChain: Chat with Your Data", "Building and Evaluating Advanced RAG", "Functions, Tools and Agents"
- **Andrej Karpathy — "Intro to Large Language Models"** (1 hr) + "Deep Dive into LLMs" for intuition. You don't need to train models, but you must explain them to enterprise stakeholders.
- **AWS Skill Builder: AI Practitioner Exam Prep Plan** (free tier) + **Stephane Maarek's AIF-C01 Udemy course** for the cert

**Books:**
- ***AI Engineering* (Chip Huyen)** — this is your textbook for the entire program. Read chapters 1–6 this month.
- *Hands-On Large Language Models* (Jay Alammar & Maarten Grootendorst) — visual, excellent for embeddings/transformers intuition

**Skills checklist:**
- [ ] Prompt engineering: system prompts, few-shot, chain-of-thought, structured JSON output
- [ ] Embeddings + vector search (start local: pgvector or Chroma)
- [ ] Build RAG from scratch (no framework) — chunking, retrieval, citation
- [ ] Tool use / function calling — build an agent loop by hand before touching a framework
- [ ] Basic evals: golden datasets, LLM-as-judge, why "it looks good" isn't a metric

**Project 2 (Week 7–8): Document Q&A RAG system**
Ingest a pile of real enterprise-style docs (SEC filings, policy PDFs, product manuals). Build RAG with citations, a simple eval harness (20–30 test questions with expected answers), and a Streamlit or Next.js front end. The eval harness is what separates you from every other RAG tutorial project — talk about retrieval accuracy numbers.

**🎓 CERT: Take AWS AI Practitioner exam in the last week of Month 2.**

---

## Month 3 — AWS Core Infrastructure

**Goal:** Become genuinely comfortable deploying things on AWS. This is where "AWS-driven stack" becomes real.

**Courses/videos:**
- **Adrian Cantrill's SAA-C03 course** (best deep AWS teaching, even if you skip the exam) *or* Stephane Maarek's SAA course for speed
- **AWS Skill Builder:** Serverless learning plan, hands-on labs
- **freeCodeCamp AWS tutorials** on YouTube for specific services

**Services to master (in priority order for AI work):**
1. **IAM** — roles, policies, least privilege (enterprises will grill you on this)
2. **S3** — storage, presigned URLs, event triggers
3. **Lambda + API Gateway** — serverless APIs
4. **DynamoDB + RDS/Aurora Postgres** (with pgvector)
5. **ECS Fargate** — running containers
6. **Step Functions + SQS/EventBridge** — orchestration (this will feel like n8n in code — big unlock for you)
7. **CloudWatch** — logging, metrics, alarms
8. **VPC basics** — enough to explain private networking to a security team

**Infrastructure as Code:**
- Learn **AWS CDK (Python)** — define infra in the language you know. Terraform is fine too; CDK keeps you in one language.

**Project 3 (Week 11–12): Serverless AI pipeline on AWS**
Rebuild Project 2's RAG system as a proper AWS deployment: S3 upload → EventBridge → Lambda ingestion → Aurora pgvector → API Gateway + Lambda query endpoint → CloudWatch dashboards. Deploy everything with CDK. Include a cost breakdown in the README (enterprises always ask "what does this cost per month?" — FDEs who can answer win deals).

---

# SEMESTER 2 (Months 4–6): Production GenAI + FDE Skills

## Month 4 — Amazon Bedrock Deep Dive + Agents

**Goal:** Own the AWS GenAI stack — the exact tooling enterprise customers deploy.

**Courses/videos:**
- **AWS Skill Builder:** Amazon Bedrock learning path, "Building Generative AI Applications on AWS"
- **AWS Workshops** (workshops.aws): Bedrock Agents workshop, Knowledge Bases workshop, AgentCore workshop
- AWS re:Invent talks on YouTube: search "Bedrock architecture," "generative AI enterprise patterns"
- **DeepLearning.AI: "Serverless LLM apps with Amazon Bedrock"**

**Topics:**
- Bedrock model invocation, Converse API, model selection & cost tradeoffs (Claude vs Nova vs Llama)
- **Knowledge Bases** (managed RAG) vs custom RAG — when to use which (classic FDE judgment call)
- **Bedrock Agents & AgentCore** — action groups, orchestration, memory, deployment
- **Guardrails** — PII redaction, content filtering, grounding checks (enterprises care about this more than accuracy)
- Vector stores on AWS: OpenSearch Serverless vs Aurora pgvector vs Kendra
- Observability & evals: Langfuse or Arize Phoenix wired into your stack

**Book:** Continue *AI Engineering* (Huyen) chapters 7–10 — inference optimization, architecture, feedback loops.

**Project 4 (Weeks 15–16): Enterprise support agent on Bedrock**
Build a customer-support agent with Bedrock Agents/AgentCore: answers from a Knowledge Base, calls tools (create ticket, look up order status in DynamoDB, escalate to human), guardrails for PII, full conversation logging, and an eval suite. Record a 3-minute demo video walking through it like you're presenting to a client's VP of Support. That video is a portfolio centerpiece.

---

## Month 5 — MLOps, Production Hardening + MLA-C01 Cert

**Goal:** Speak "production" fluently and pass the ML Engineer Associate exam.

**Courses/videos:**
- **AWS Skill Builder: MLA-C01 Exam Prep Plan** (includes practice exams and SimuLearn labs)
- **Stephane Maarek + Frank Kane's MLA-C01 Udemy course**
- SageMaker essentials: training jobs, endpoints (real-time/serverless/batch), Pipelines, Model Registry, Model Monitor — you need this for the exam even though your day job will be Bedrock-heavy

**Production topics:**
- CI/CD: GitHub Actions deploying CDK stacks
- Testing LLM apps: unit tests, eval gates in CI, regression suites
- Cost optimization: prompt caching, model routing (cheap model first, escalate), batch inference
- Security: Secrets Manager, KMS encryption, VPC endpoints for Bedrock, audit logging
- Monitoring: latency/token dashboards, drift detection, feedback capture

**Book:** *Designing Machine Learning Systems* (Chip Huyen) — skim for MLOps mental models, focus ch. 7–9.

**Project 5 (Weeks 19–20): Productionize Project 4**
Add CI/CD with eval gates (deploys blocked if eval scores regress), monitoring dashboards, cost-per-conversation tracking, load testing, and a proper architecture diagram. Write a "production readiness review" doc like you'd hand a customer's platform team.

**🎓 CERT: Take MLA-C01 in the last week of Month 5.**

---

## Month 6 — Capstone + FDE Soft Skills + Job Hunt Launch

**Goal:** One flagship project that simulates a real FDE engagement, plus interview readiness.

**FDE skill-building (this month's "seminar"):**
- *The Mom Test* (Rob Fitzpatrick) — customer discovery questioning. Short, essential.
- *The Trusted Advisor* (Maister) — how consultants build credibility. Skim.
- Watch Palantir/OpenAI/Anthropic FDE talks and blog posts on what the role actually involves; study solutions-engineering demo videos on YouTube (search "solutions engineer demo best practices")
- Practice: give your Project 4 demo to 3 real humans, collect feedback, iterate

**CAPSTONE (Weeks 21–25): Full simulated FDE engagement**
Pick a realistic enterprise scenario (e.g., "a regional insurance company wants to automate claims-document intake and triage"). Deliver the complete FDE artifact set:
1. **Discovery doc** — invented stakeholder interviews, current process map, pain points, success metrics
2. **Solution architecture** — diagram + written design doc with AWS service choices *justified* (why Bedrock KB over custom RAG, why Fargate over Lambda, etc.)
3. **Working system** — deployed on AWS, agentic, with guardrails and evals
4. **Cost model** — monthly run-rate at 3 usage tiers
5. **Executive demo video** (5 min) + **technical deep-dive video** (10 min)
6. **Case study writeup** — publish on a personal site/blog

**Week 26: Job hunt sprint**
- Resume rewritten around projects + certs (quantify: eval scores, latency, cost savings)
- Target list: 30 companies with FDE/AI deployment/solutions roles (Palantir, OpenAI, Anthropic, Sierra, Glean, Writer, Decagon, Harvey, plus AWS Partners and AI consultancies — partners *love* AWS certs)
- 10 tailored applications + 15 warm outreach DMs to FDEs/hiring managers referencing your capstone

---

## Weekly Schedule Template (university style, ~27 hrs)

| Time | Mon | Tue | Wed | Thu | Fri | Sat | Sun |
|------|-----|-----|-----|-----|-----|-----|-----|
| **9:00–11:00** | 📖 Lecture block (course videos + notes) | 📖 Lecture block | 📖 Lecture block | 📖 Lecture block | 🎓 Cert study / practice exams | 🔨 Project deep work (3–4 hrs) | Rest / light reading |
| **11:00–13:00** | 🔨 Lab: code-along + exercises | 🔨 Lab | 🔨 Lab | 🔨 Lab | 🚢 Ship it: finish + deploy something | 🔨 Project deep work | — |
| **Evening (1 hr)** | 📚 Book reading | ✍️ Draft content | 📚 Book reading | ✍️ Post + engage | 🎥 Record demo/GIF for the week's work | 💬 Community (Discord/forums, comment on 5 posts) | 🗓️ Weekly review: what shipped, what's next, update learning log |

Rules: mornings are theory, middays are hands-on, Fridays end with something *deployed*, and every week produces at least one public artifact.

---

## Social Media & Networking Plan ("build in public")

**Platform strategy:** LinkedIn is primary (that's where enterprise AI hiring happens), X/Twitter secondary (AI engineering community). Same content, adapted format.

**Weekly cadence (non-negotiable, starts Week 1):**
- **2 LinkedIn posts/week** (Tue + Thu):
  - Tue: what you learned — a concrete technical insight, with a code snippet or diagram ("Rebuilt my n8n lead-router in Python + Lambda. Here's the cost difference at 10k runs/month...")
  - Thu: build-in-public progress — screenshot, demo GIF, eval numbers, architecture diagram
- **3–4 X posts/week:** shorter versions, plus replies in the AI engineering community
- **Daily (20 min):** thoughtful comments on 5 posts from AI engineers, FDEs, AWS heroes, and target-company employees. Comments build your network faster than posts.

**Monthly:**
- 1 long-form article (LinkedIn article or personal blog): Month 1 "From n8n to Python: what changes and what doesn't" · Month 2 "I built RAG without a framework — here's what the frameworks hide" · Month 3 "What my first AWS deployment taught me about serverless" · Month 4 "Bedrock Knowledge Bases vs custom RAG: an honest comparison" · Month 5 "Adding eval gates to CI for an LLM app" · Month 6 capstone case study
- 1 demo video per completed project (Loom/YouTube, embedded in posts)
- Connect with 40 relevant people/month (FDEs, solutions engineers, AI leads at target companies) — always with a personalized note referencing their work

**Milestone posts (high-impact moments):**
- Cert pass announcements (Months 2 and 5) — these consistently get reach
- Each project launch with demo video
- Capstone case study — pin it to your profile

**6-month targets:** 50+ posts, 6 articles, 5 demo videos, ~1,500 quality connections, and a profile that reads "AI Engineer building enterprise GenAI on AWS" instead of "aspiring."

---

## Master Resource List

**Books**
1. *AI Engineering* — Chip Huyen (primary textbook)
2. *Python Crash Course* — Eric Matthes (Month 1)
3. *Fluent Python* — Luciano Ramalho (reference)
4. *Hands-On Large Language Models* — Alammar & Grootendorst (Month 2)
5. *Designing Machine Learning Systems* — Chip Huyen (Month 5, skim)
6. *The Mom Test* — Rob Fitzpatrick (Month 6)

**Courses**
- CS50P (Harvard, free) · FastAPI docs tutorial · DeepLearning.AI short courses · AWS Skill Builder exam prep plans · Maarek/Cantrill/Frank Kane Udemy for certs · AWS Workshops (workshops.aws)

**YouTube**
- Andrej Karpathy · Corey Schafer · freeCodeCamp AWS · AWS re:Invent sessions · Be A Better Dev (AWS)

**Communities**
- AWS Community Builders program (apply once you have content!) · r/AWSCertifications · Latent Space podcast/Discord · local AWS User Group meetups (go monthly — in-person beats everything for FDE-track networking)

---

## Progress Tracker

| Milestone | Target date | Done |
|-----------|-------------|------|
| Project 1: n8n → Python rebuild | End Week 4 | ☐ |
| Project 2: RAG + eval harness | End Week 8 | ☐ |
| 🎓 AWS AI Practitioner | End Month 2 | ☐ |
| Project 3: Serverless AWS pipeline (CDK) | End Week 12 | ☐ |
| Project 4: Bedrock enterprise agent | End Week 16 | ☐ |
| Project 5: Production hardening | End Week 20 | ☐ |
| 🎓 ML Engineer – Associate | End Month 5 | ☐ |
| Capstone shipped + case study published | End Week 25 | ☐ |
| 10 applications + 15 warm outreach | End Week 26 | ☐ |
| 🎓 GenAI Developer – Professional (stretch) | Month 7–9 | ☐ |
