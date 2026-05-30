Phase 1 — Intuition math (just enough)

Scalars, vectors, and matrices — what they are\
Matrix multiplication — how it works conceptually\
What "dimensions" mean in data\
Dot product — what it measures\
Probability basics — distributions, mean, variance\
What a function is (input → output) and what "optimizing" a function means\
Softmax — turning numbers into probabilities\
Log and exponential functions — why they show up everywhere in ML\


Phase 2 — How LLMs work\

What a neural network is — layers, weights, activations\
How a model "learns" — forward pass, loss, backward pass (conceptual only)\
What training data is and why it shapes model behavior\
Tokenization — how text becomes numbers, BPE, why "1000 words ≠ 1000 tokens"\
What an embedding is — vectors as meaning\
Self-attention — how a model relates words to each other\
The transformer architecture — conceptual overview\
Context window — what it is, what happens when you exceed it\
KV cache — why it exists, what it saves\
Pre-training vs fine-tuning vs RLHF — what each changes\
Base model vs instruct model vs chat model — the differences\
Hallucination — why it happens mechanically\
Temperature and sampling — top-k, top-p, greedy decoding\


Phase 3 — Prompt engineering

System prompt vs user message vs assistant turn
Zero-shot prompting
Few-shot prompting — when and how many examples
Chain-of-thought prompting — why step-by-step reasoning helps
Instruction clarity — specificity, constraints, negative instructions
Structured output — getting consistent JSON, XML, schema from a model
Prompt templating — variables in prompts, dynamic construction
Prompt injection — what it is, how attacks work
Prompt evaluation — how to know if a prompt is actually good
Prompt regression testing — catching prompt quality over time

-----------------security ---------------
Prompt injection
Indirect prompt injection
Jailbreak attacks
System prompt leakage
Prompt isolation
Input sanitization
Secure prompt design
Role separation

Phase 4 — LLM APIs

REST API basics as applied to LLMs — messages array, roles, parameters
Key parameters — temperature, max_tokens, stop sequences, top_p
Anthropic Claude API — messages endpoint, auth, rate limits
OpenAI API — same concepts, different SDK
Streaming responses — how SSE works, chunked delivery
Token counting — how to estimate cost before calling
Retry logic for LLMs — 429s, exponential backoff, jailbreak-safe retries
Prompt caching — Anthropic's cache_control, when it saves money
Batch API — async inference for non-realtime workloads
Spring AI — ChatClient, prompt templates, advisors in Java
LangChain4j — Java alternative, model abstraction layer

-----------------------------------Add Evaluation Foundations

At this stage you're making model calls and can start measuring quality.

Golden datasets
Test datasets
LLM-as-a-judge
Offline evaluation
Online evaluation
Output scoring
Evaluation pipelines
Regression testing automation
Add Security Foundations
API key management
Rate limiting
Secure secrets handling
Tenant isolation basics
Data privacy considerations
PII detection

Phase 5 — RAG (Retrieval-Augmented Generation)

Why RAG exists — what hallucination + stale knowledge problems it solves
The RAG pipeline end-to-end — indexing phase and query phase
Document loaders — PDFs, HTML, databases, APIs as source
Chunking — what it is and why it matters
Fixed-size chunking — character splits, token splits
Recursive chunking — splitting by structure (headings, paragraphs)
Semantic chunking — splitting by meaning shift
Chunk overlap — why you add it, how much
Embedding models — what they do, how to pick one
OpenAI embeddings vs open-source (BGE, E5, Nomic) — tradeoffs
Vector databases — what they store and how ANN search works
pgvector — Postgres extension, good starting point
Pinecone — managed vector DB, production use
Qdrant — self-hosted alternative
Weaviate — hybrid-native, good for mixed workloads
Cosine similarity vs dot product vs Euclidean — when to use each
Retrieval — top-k search, similarity threshold
BM25 keyword search — how it works
Hybrid search — combining vector + BM25, RRF fusion
Reranking — cross-encoder rerankers, Cohere rerank API
Metadata filtering — filtering by date, source, category before retrieval
Parent-child chunking — store small chunks, retrieve large parent
HyDE — generating a hypothetical answer to improve retrieval
Query rewriting — expanding or reformulating the user query
Multi-query retrieval — running multiple query variants in parallel
Self-RAG — model decides when to retrieve, evaluates its own output
Corrective RAG — detecting bad retrieval and re-querying
RAG evaluation — faithfulness, answer relevance, context precision
RAGAS — the framework for measuring RAG pipeline quality


-------------------------Data Engineering for AI---------------------



-------------Document Processing----------------------

PDF parsing
OCR fundamentals
HTML extraction
Web scraping basics
Data normalization


-----------Data Quality----------------------

Deduplication
Data cleaning
Noise removal
Metadata enrichment
Document classification

------------------Ingestion Pipelines----------------------
Batch ingestion
Incremental indexing
Change detection
Event-driven ingestion
Streaming ingestion


-------------------Storage Design----------------------
Raw document storage
Processed document storage
Chunk storage
Metadata stores


-----------------Advanced Retrieval----------------------
Knowledge graphs
Graph databases
Graph RAG
Entity extraction
Relationship extraction
Neo4j basics

---------------RAG Security----------------------
RAG poisoning
Retrieval poisoning
Document trust levels
Access control for retrieval
Source verification


Phase 6 — Function calling and agents

What function calling is — tools, JSON schema definition
How the tool use loop works — model calls tool, you execute, return result
Parallel tool calls — model calling multiple tools in one turn
Tool design — writing good tool descriptions the model can reason about
The ReAct pattern — Thought, Action, Observation loop
Agent memory — in-context vs external, episodic vs semantic
Planning agents — breaking a goal into sub-tasks
Orchestrator + subagent pattern — multi-agent delegation
LangGraph — state machines for agents, branching and looping
Agent loops — detecting infinite loops, max iteration limits
Human-in-the-loop — pausing for approval mid-agent run
MCP (Model Context Protocol) — Anthropic's standard for tool/context integration
MCP servers and clients — how to build and connect them

--------------Advanced Agent Architectures----------------------


Planner-executor pattern
Reflection pattern
Critic pattern
Supervisor agents
Swarm architectures
Agent handoffs
Durable execution
Stateful workflows

------------------Agent Security----------------------

Tool poisoning
Tool permission models
Sandboxed execution
Human approval gates
Agent loop protection
Tool allowlists
Tool audit trails


------------------Agent Evaluation----------------------
Agent success rate
Task completion metrics
Tool call accuracy
Multi-step evaluation
Agent benchmark design


Phase 7 — Production AI systems

LLM caching — exact cache hits, semantic caching, when each applies
Redis for LLM response caching — key design, TTL strategy
Async LLM calls — non-blocking inference in a Java backend
Queue-based inference — decoupling request from LLM response
Latency breakdown — time-to-first-token vs total latency, where time goes
Speculative decoding — how it reduces latency (conceptual)
Parallel tool execution — running multiple agent tools concurrently
LLM observability — what to log, trace IDs across agent steps
LangSmith / Langfuse — tracing multi-step agent runs
OpenTelemetry for LLM systems — spans, traces, metrics

---------------------AI Observability----------------------



Prompt tracing
Agent tracing
Retrieval tracing
Cost tracing
Token analytics
Latency analytics
Error categorization

Guardrails — input and output validation, content filtering
Structured output validation — schema enforcement, retry on bad output
Prompt versioning — treating prompts as code artifacts
A/B testing prompts — measuring quality improvement

-------------------------------AI Evaluation Engineering----------------------

Evaluation Systems
Golden datasets
Benchmark creation
Human evaluation workflows
Pairwise comparison testing
Win-rate measurement
Hallucination measurement
Faithfulness evaluation
Answer relevance evaluation

-----------------------------Continuous Evaluation----------------------
CI/CD evaluation pipelines
Pre-deployment testing
Production evaluation
Canary testing
Regression detection

Multi-tenant LLM systems — isolating prompts and data per tenant
Cost monitoring — per-user token tracking, spend alerts
Fine-tuning decision — when it beats RAG + prompting, when it doesn't
LoRA and QLoRA — parameter-efficient fine-tuning (conceptual)
Data preparation for fine-tuning — format, quality, quantity rules
Self-hosted inference — vLLM, Ollama, TGI
Quantization — GGUF, AWQ, GPTQ — what they trade off
GPU vs CPU inference — when self-hosting makes sense vs API

------------------------------------AI Infrastructure----------------------

This should be its own major section inside Phase 7.

----------------------------GPU Fundamentals----------------------
GPU architecture basics
CUDA fundamentals (conceptual)
VRAM management
Throughput vs latency
----------------------------Inference Serving----------------------
Model serving basics
Dynamic batching
Continuous batching
Request scheduling
Load balancing
-------------------------Infrastructure Tools----------------------
Ollama
vLLM
TGI
TensorRT-LLM
KServe
-----------------------------Deployment----------------------
Kubernetes for AI
Autoscaling
Multi-region deployments
Model gateways
Service meshes
---------------------------Monitoring----------------------
GPU utilization
Memory utilization
Queue depth
Throughput metrics
SLA monitoring
-------------------------------Production Security----------------------

This should be the final section of the roadmap.

---------------------------------Enterprise AI Security----------------------
Authentication
Authorization
RBAC
Multi-tenant isolation
Audit logging
Data encryption
Compliance basics
---------------------------AI Threat Models----------------------
Prompt attacks
Data leakage
Tool abuse
Agent abuse
Model abuse
-------------------------------Governance----------------------
AI policy enforcement
Human review workflows
Risk classification
Compliance monitoring
