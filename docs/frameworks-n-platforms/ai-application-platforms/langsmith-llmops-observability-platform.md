---
id: frameworks-n-platforms/ai-application-platforms/langsmith-llmops-observability-platform.md
title: LangSmith - LLM Observability, Evaluation & Deployment
sidebar_label: LangSmith - LLM Observability, Evaluation & Deployment
---

<div style="text-align: right;">
    <a href="https://kranthib.github.io/tech-pulse/" style="display: inline-block; padding: 6px 14px; background-color: #2054a6; color: white; text-decoration: none; border-radius: 3px; font-size: 14px; font-weight: 500; transition: background-color 0.3s;">Back to Home →</a>
</div>


Table of contents
=================

<!--ts-->
   * [Introduction](#introduction)
   * [The Four Pillars of LangSmith](#the-four-pillars-of-langsmith)
      * [1. Observability](#1-observability)
      * [2. Evaluation](#2-evaluation)
      * [3. Deployment](#3-deployment)
      * [4. LangGraph Studio](#4-langgraph-studio)
   * [Understanding LLMOps](#understanding-llmops)
      * [DevOps vs MLOps vs LLMOps](#devops-vs-mlops-vs-llmops)
      * [Why LLMOps is Different](#why-llmops-is-different)
   * [The LLMOps Challenge](#the-llmops-challenge)
   * [Model Switching Strategy](#model-switching-strategy)
      * [Step 1: Prototype](#step-1-prototype)
      * [Step 2: A/B Testing](#step-2-ab-testing)
   * [Human-in-the-Loop and LLM-as-Judge](#human-in-the-loop-and-llm-as-judge)
   * [The GenAI Application Stack](#the-genai-application-stack)
   * [Pricing and Free Tier](#pricing-and-free-tier)
   * [Getting Started with LangSmith](#getting-started-with-langsmith)
   * [Developer-Friendly Ecosystem](#developer-friendly-ecosystem)
<!--te-->

## Introduction

**LangSmith** is the platform that completes the LangChain ecosystem, providing enterprise-grade tools for managing the full lifecycle of LLM applications in production.

> **Free Tier Available**: LangSmith offers a generous free tier with **50,000 traces per month** for developers getting started.

```
┌─────────────────────────────────────────────────────────────────────────┐
│                        LangSmith Platform                               │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐    │
│   │             │  │             │  │             │  │             │    │
│   │OBSERVABILITY│  │ EVALUATION  │  │ DEPLOYMENT  │  │  LANGGRAPH  │    │
│   │             │  │             │  │             │  │   STUDIO    │    │
│   │   Debug &   │  │  Iterate    │  │  Ship &     │  │   Visual    │    │
│   │   Monitor   │  │  Prompts    │  │  Scale      │  │   Agent     │    │
│   │   Traces    │  │  & Models   │  │  Agents     │  │   Builder   │    │
│   │             │  │             │  │             │  │             │    │
│   └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘    │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

## The Four Pillars of LangSmith

### 1. Observability

**Debug and monitor in-depth traces** of your LLM applications.

```
┌─────────────────────────────────────────────────────────────────────────┐
│                          Trace Example                                  │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  Request ID: abc123                                                     │
│  Total Latency: 2.3s                                                    │
│  Total Tokens: 1,247                                                    │
│  Cost: $0.0089                                                          │
│                                                                         │
│  ┌────────────────────────────────────────────────────────────────┐     │
│  │ Chain: customer_support_agent                                  │     │
│  │ Duration: 2.3s                                                 │     │
│  │ ├── Retriever: document_search                                 │     │
│  │ │   Duration: 0.4s                                             │     │
│  │ │   Documents Retrieved: 5                                     │     │
│  │ │   └── [doc1.pdf, doc2.pdf, doc3.pdf...]                      │     │
│  │ │                                                              │     │
│  │ ├── LLM: gpt-4                                                 │     │
│  │ │   Duration: 1.8s                                             │     │
│  │ │   Input Tokens: 847                                          │     │
│  │ │   Output Tokens: 400                                         │     │
│  │ │   ├── System Prompt: "You are a helpful..."                  │     │
│  │ │   ├── User Input: "How do I reset my password?"              │     │
│  │ │   └── Output: "To reset your password, follow..."            │     │
│  │ │                                                              │     │
│  │ └── Tool: send_email                                           │     │
│  │     Duration: 0.1s                                             │     │
│  │     Status: Success                                            │     │
│  └────────────────────────────────────────────────────────────────┘     │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

**Key Observability Features:**
- **End-to-end tracing** of every request
- **Token usage** and **cost tracking**
- **Latency breakdown** per component
- **Error tracking** and debugging
- **Prompt/response** inspection
- **Feedback collection** from users

### 2. Evaluation

**Iteration on prompts and models** with systematic evaluation.

```python
from langsmith import Client
from langsmith.evaluation import evaluate

client = Client()

# Create evaluation dataset
dataset = client.create_dataset("customer_support_eval")

# Add examples
client.create_examples(
    inputs=[
        {"query": "How do I reset my password?"},
        {"query": "What's your refund policy?"},
        {"query": "I can't log into my account"}
    ],
    outputs=[
        {"expected": "Password reset instructions"},
        {"expected": "Refund policy explanation"},
        {"expected": "Account troubleshooting steps"}
    ],
    dataset_id=dataset.id
)

# Run evaluation
results = evaluate(
    my_llm_chain,
    data=dataset,
    evaluators=[
        "correctness",
        "helpfulness",
        "relevance"
    ]
)
```

**Built-in Evaluators:**
- ✅ **Correctness** — Is the answer factually correct?
- ✅ **Helpfulness** — Does it help the user?
- ✅ **Relevance** — Is it relevant to the query?
- ✅ **Coherence** — Is it well-structured?
- ✅ **Safety** — Is it appropriate?
- ✅ **Custom** — Define your own metrics

### 3. Deployment

**Ship and scale agents in production** with confidence.

- **Version control** for prompts and chains
- **A/B testing** capabilities
- **Rollback** mechanisms
- **Performance monitoring** dashboards
- **Alerting** on anomalies
- **LangGraph Cloud** for durable, stateful workflows

### 4. LangGraph Studio

**Visual IDE for building and debugging LangGraph workflows.**

```
┌─────────────────────────────────────────────────────────────────────────┐
│                        LangGraph Studio                                 │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   ┌─────────────────────────────────────────────────────────────────┐   │
│   │                    Visual Workflow Builder                      │   │
│   │                                                                 │   │
│   │     ┌─────┐     ┌─────────┐     ┌─────────┐     ┌─────┐         │   │
│   │     │START│────▶│Classify │────▶│ Process │────▶│ END │         │   │
│   │     └─────┘     └────┬────┘     └────┬────┘     └─────┘         │   │
│   │                      │               │                          │   │
│   │                      ▼               │                          │   │
│   │                 ┌─────────┐          │                          │   │
│   │                 │ Search  │──────────┘                          │   │
│   │                 └─────────┘                                     │   │
│   │                                                                 │   │
│   └─────────────────────────────────────────────────────────────────┘   │
│                                                                         │
│   Features:                                                             │
│   • Drag-and-drop node creation                                         │
│   • Real-time state inspection                                          │
│   • Step-through debugging                                              │
│   • Interrupt and resume workflows                                      │
│   • One-click deployment to LangGraph Cloud                             │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

**LangGraph Studio enables:**
- **Visual debugging** — See exactly where workflows fail
- **Time-travel debugging** — Step back through state changes
- **Interrupt & resume** — Test human-in-the-loop flows
- **State inspection** — View state at any point in the graph
- **One-click deploy** — Push to LangGraph Cloud instantly

## Understanding LLMOps

### DevOps vs MLOps vs LLMOps

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    Evolution of Operations                              │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                         DevOps                                  │    │
│  │  ┌──────────────────────────────────────────────────────────┐   │    │
│  │  │                                                          │   │    │
│  │  │    CI (Continuous Integration)                           │   │    │
│  │  │           +                                              │   │    │
│  │  │    CD (Continuous Deployment)                            │   │    │
│  │  │                                                          │   │    │
│  │  └──────────────────────────────────────────────────────────┘   │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                              │                                          │
│                              ▼                                          │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                         MLOps                                   │    │
│  │  ┌──────────────────────────────────────────────────────────┐   │    │
│  │  │                                                          │   │    │
│  │  │    CI + CD                                               │   │    │
│  │  │           +                                              │   │    │
│  │  │    Continuous Monitoring                                 │   │    │
│  │  │           +                                              │   │    │
│  │  │    Continuous Training                                   │   │    │
│  │  │    (Monitor model output, retrain on the go)             │   │    │
│  │  │                                                          │   │    │
│  │  └──────────────────────────────────────────────────────────┘   │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                              │                                          │
│                              ▼                                          │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │                    LLMOps / GenAIOps                            │    │
│  │  ┌──────────────────────────────────────────────────────────┐   │    │
│  │  │  More specific to Generative LLM models because:         │   │    │
│  │  │                                                          │   │    │
│  │  │    1. They are NON-DETERMINISTIC                         │   │    │
│  │  │    2. They are WAY MORE COMPLEX than traditional ML      │   │    │
│  │  │                                                          │   │    │
│  │  │  Main Tasks:                                             │   │    │
│  │  │    • Cost Estimation                                     │   │    │
│  │  │    • Tracking (when/how does it break?)                  │   │    │
│  │  │    • Systematic Evaluation                               │   │    │
│  │  │    • Human-in-the-Loop                                   │   │    │
│  │  │    • LLM-as-Judge                                        │   │    │
│  │  │                                                          │   │    │
│  │  └──────────────────────────────────────────────────────────┘   │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

### Why LLMOps is Different

The **main difference between MLOps and LLMOps** is that it's **not a continuous training pipeline** that you can just run the same way you would with a traditional machine learning model.

**Key LLMOps Challenges:**

| Challenge | Description |
|-----------|-------------|
| **Cost Estimation** | How much will this actually cost to use these large language models? |
| **Failure Analysis** | When does it break? How does it break? |
| **Tracking** | Store all prompts and outputs for analysis |
| **Systematic Evaluation** | Can't do "vibe eval" in production |
| **Non-Determinism** | Same input can yield different outputs |

## The LLMOps Challenge

> **You cannot do a "vibe eval" in production**

When building LLM applications in production, you cannot just look at prompts and outputs and say "this is good" or "this is not performing well."

**What you need:**

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    Production Evaluation System                         │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   ┌─────────────────────────────────────────────────────────────────┐   │
│   │                     EVALUATION DATABASE                         │   │
│   │                                                                 │   │
│   │  ┌─────────────┐   ┌─────────────┐   ┌─────────────────────┐    │   │
│   │  │   Prompts   │   │   Outputs   │   │   Evaluation Set    │    │   │
│   │  │   Tried     │   │   Received  │   │   (Your Use Case)   │    │   │
│   │  └─────────────┘   └─────────────┘   └─────────────────────┘    │   │
│   │                                                                 │   │
│   │  Similar to training/test set in traditional ML                 │   │
│   │  Used to QUANTIFY performance                                   │   │
│   │                                                                 │   │
│   └─────────────────────────────────────────────────────────────────┘   │
│                                                                         │
│   Example Evaluation Set:                                               │
│   ┌─────────────────────────────────────────────────────────────────┐   │
│   │  Input                       │ Expected Output     │ Criteria   │   │
│   │  ────────────────────────────│─────────────────────│────────────│   │
│   │  "Reset my password"         │ Step-by-step guide  │ Accuracy   │   │
│   │  "Refund my order #123"    │ Refund process      │ Helpfulness│   │
│   │  "Product not working"       │ Troubleshooting     │ Relevance  │   │
│   └─────────────────────────────────────────────────────────────────┘   │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

## Model Switching Strategy

**Example Scenario:** You have GPT-4.0 running in production, and new models are getting released every week. When should you switch? How do you justify making that model switch?

> **This is where observability is super, super critical.**

**No one switches directly from Model 1 to Model N.**

### Step 1: Prototype

```
┌─────────────────────────────────────────────────────────────────────────┐
│                      Prototype Phase                                    │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   ┌──────────────────────────────────────────────────────────────────┐  │
│   │                    Development Environment                       │  │
│   │                                                                  │  │
│   │    ┌────────────────┐                                            │  │
│   │    │  Your Eval Set │                                            │  │
│   │    │  (100 examples)│                                            │  │
│   │    └───────┬────────┘                                            │  │
│   │            │                                                     │  │
│   │            ▼                                                     │  │
│   │    ┌──────────────────────────────────────────────────────┐      │  │
│   │    │              Run Evaluation                          │      │  │
│   │    │                                                      │      │  │
│   │    │   ┌─────────────┐        ┌─────────────┐             │      │  │
│   │    │   │  GPT-4.0    │   vs   │  GPT-4.1    │             │      │  │
│   │    │   │  (Current)  │        │   (New)     │             │      │  │
│   │    │   └─────────────┘        └─────────────┘             │      │  │
│   │    │                                                      │      │  │
│   │    │   Score: 85%             Score: 92%                  │      │  │
│   │    │   Latency: 1.2s          Latency: 0.9s               │      │  │
│   │    │   Cost: $0.03            Cost: $0.02                 │      │  │
│   │    │                                                      │      │  │
│   │    └──────────────────────────────────────────────────────┘      │  │
│   │                                                                  │  │
│   │    Decision: New model shows improvement → Proceed to A/B Test   │  │
│   │                                                                  │  │
│   └──────────────────────────────────────────────────────────────────┘  │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

### Step 2: A/B Testing

```
┌─────────────────────────────────────────────────────────────────────────┐
│                        A/B Testing Phase                                │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   ┌──────────────────────────────────────────────────────────────────┐  │
│   │                    Production Environment                        │  │
│   │                                                                  │  │
│   │         Total Users: 100,000                                     │  │
│   │                                                                  │  │
│   │    ┌────────────────────────────────────────────────────────┐    │  │
│   │    │                    Traffic Router                       │   │  │
│   │    └────────────────────────┬───────────────────────────────┘    │  │
│   │                             │                                    │  │
│   │              ┌──────────────┴──────────────┐                     │  │
│   │              │                             │                     │  │
│   │              ▼                             ▼                     │  │
│   │    ┌─────────────────┐          ┌─────────────────┐              │  │
│   │    │  Control Group  │          │ Treatment Group │              │  │
│   │    │   (99,000)      │          │    (1,000)      │              │  │
│   │    │                 │          │                 │              │  │
│   │    │   ┌─────────┐   │          │   ┌─────────┐   │              │  │
│   │    │   │ GPT-4.0 │   │          │   │ GPT-4.1 │   │              │  │
│   │    │   │(Current)│   │          │   │  (New)  │   │              │  │
│   │    │   └─────────┘   │          │   └─────────┘   │              │  │
│   │    │                 │          │                 │              │  │
│   │    └─────────────────┘          └─────────────────┘              │  │
│   │                                                                  │  │
│   │    Monitor & Compare:                                            │  │
│   │    • User satisfaction                                           │  │
│   │    • Task completion rate                                        │  │
│   │    • Error rates                                                 │  │
│   │    • Response quality                                            │  │
│   │                                                                  │  │
│   │    If Treatment outperforms → Gradually increase traffic         │  │
│   │    1,000 → 5,000 → 25,000 → 50,000 → 100,000                     │  │
│   │                                                                  │  │
│   └──────────────────────────────────────────────────────────────────┘  │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

## Human-in-the-Loop and LLM-as-Judge

There are **two different approaches** for continuous improvement in LLMOps:

### 1. Human-in-the-Loop

```
┌─────────────────────────────────────────────────────────────────────────┐
│                      Human-in-the-Loop                                  │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   ┌────────────┐    ┌────────────┐    ┌────────────┐                    │
│   │   LLM      │───▶│  Response  │───▶│   Human    │                    │
│   │  Output    │    │            │    │ Evaluator  │                    │
│   └────────────┘    └────────────┘    └─────┬──────┘                    │
│                                              │                          │
│                                              ▼                          │
│                                       ┌────────────┐                    │
│                                       │  Feedback  │                    │
│                                       │  Database  │                    │
│                                       └─────┬──────┘                    │
│                                              │                          │
│                     ┌────────────────────────┴────────────────────┐     │
│                     │                                             │     │
│                     ▼                                             ▼     │
│              ┌────────────┐                              ┌────────────┐ │
│              │   RLHF     │                              │ Supervised │ │
│              │Fine-tuning │                              │ Fine-tuning│ │
│              └────────────┘                              └────────────┘ │
│                                                                         │
│   Use Case: High-stakes decisions, compliance, quality assurance        │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

### 2. LLM-as-Judge

```
┌─────────────────────────────────────────────────────────────────────────┐
│                        LLM-as-Judge                                     │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   ┌────────────┐    ┌────────────┐    ┌────────────┐                    │
│   │   LLM      │───▶│  Response  │───▶│   Judge    │                    │
│   │  Output    │    │            │    │    LLM     │                    │
│   └────────────┘    └────────────┘    └─────┬──────┘                    │
│                                              │                          │
│                                              ▼                          │
│                                       ┌────────────┐                    │
│                                       │   Score:   │                    │
│                                       │  0-10 with │                    │
│                                       │ explanation│                    │
│                                       └────────────┘                    │
│                                                                         │
│   Evaluation Criteria:                                                  │
│   • Accuracy                                                            │
│   • Helpfulness                                                         │
│   • Relevance                                                           │
│   • Safety                                                              │
│   • Coherence                                                           │
│                                                                         │
│   Use Case: Scalable evaluation, rapid iteration, cost-effective        │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

**LangSmith supports both approaches** with built-in evaluators and custom evaluation pipelines.

## The GenAI Application Stack

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    GenAI Application Stack                              │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  ┌─────────────────────────────────────────────────────────────────┐    │
│  │              Generative AI Apps & Flow Builders                 │    │
│  │                       (Superset)                                │    │
│  │  ┌─────────────────────────────────────────────────────────┐    │    │
│  │  │           Prompt Management & Optimization              │    │    │
│  │  │  ┌─────────────────────────────────────────────────┐    │    │    │
│  │  │  │       Test Data Curation & Evaluation           │    │    │    │
│  │  │  │  ┌─────────────────────────────────────────┐    │    │    │    │
│  │  │  │  │   LLM Call Debugging, Tracing,          │    │    │    │    │
│  │  │  │  │         Monitoring                      │    │    │    │    │
│  │  │  │  │  ┌─────────────────────────────────┐    │    │    │    │    │
│  │  │  │  │  │                                 │    │    │    │    │    │
│  │  │  │  │  │            LLMs                 │    │    │    │    │    │
│  │  │  │  │  │     (Foundation Models)         │    │    │    │    │    │
│  │  │  │  │  │                                 │    │    │    │    │    │
│  │  │  │  │  └─────────────────────────────────┘    │    │    │    │    │
│  │  │  │  │                                         │    │    │    │    │
│  │  │  │  └─────────────────────────────────────────┘    │    │    │    │
│  │  │  │                                                 │    │    │    │
│  │  │  └─────────────────────────────────────────────────┘    │    │    │
│  │  │                                                         │    │    │
│  │  └─────────────────────────────────────────────────────────┘    │    │
│  │                                                                 │    │
│  └─────────────────────────────────────────────────────────────────┘    │
│                                                                         │
│  LangSmith covers ALL these layers!                                     │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

**All of these performance metrics are covered under LangSmith**, and you'll be able to easily implement and track them.

## Pricing and Free Tier

LangSmith offers flexible pricing for teams of all sizes:

| Plan | Traces/Month | Key Features |
|------|--------------|--------------|
| **Free** | 50,000 | Tracing, basic evaluation, 1 seat |
| **Plus** | 500,000 | Team collaboration, advanced eval, 5 seats |
| **Enterprise** | Unlimited | SSO, SLA, dedicated support |

> **Start free** and scale as your application grows. No credit card required.

## Getting Started with LangSmith

```python
# Install LangSmith
# pip install langsmith

import os
from langsmith import Client
from langchain_openai import ChatOpenAI
from langchain.prompts import ChatPromptTemplate

# Set up environment
os.environ["LANGCHAIN_TRACING_V2"] = "true"
os.environ["LANGCHAIN_API_KEY"] = "your-langsmith-api-key"
os.environ["LANGCHAIN_PROJECT"] = "my-first-project"

# Initialize client
client = Client()

# Your LLM calls are now automatically traced!
llm = ChatOpenAI(model="gpt-4")
prompt = ChatPromptTemplate.from_template("Tell me about {topic}")
chain = prompt | llm

# This call is automatically traced in LangSmith
response = chain.invoke({"topic": "LangSmith"})

# View traces at: https://smith.langchain.com
```

### Creating an Evaluation Dataset

```python
from langsmith import Client

client = Client()

# Create dataset
dataset = client.create_dataset(
    dataset_name="customer_support_qa",
    description="Q&A pairs for customer support evaluation"
)

# Add examples
examples = [
    {
        "input": {"question": "How do I reset my password?"},
        "output": {"answer": "Go to Settings > Security > Reset Password"}
    },
    {
        "input": {"question": "What's your refund policy?"},
        "output": {"answer": "Full refund within 30 days of purchase"}
    }
]

for example in examples:
    client.create_example(
        inputs=example["input"],
        outputs=example["output"],
        dataset_id=dataset.id
    )
```

### Running Evaluations

```python
from langsmith.evaluation import evaluate

# Define your chain/agent
def my_agent(inputs: dict) -> dict:
    question = inputs["question"]
    # Your agent logic here
    response = chain.invoke({"question": question})
    return {"answer": response.content}

# Run evaluation
results = evaluate(
    my_agent,
    data="customer_support_qa",  # Dataset name
    evaluators=[
        "qa",           # Question-answering accuracy
        "cot_qa",       # Chain-of-thought QA
        "context_qa",   # Context relevance
    ],
    experiment_prefix="v1.0"
)

# View results in LangSmith UI
print(f"View results: {results.experiment_url}")
```

## Developer-Friendly Ecosystem

> **The entire LangChain ecosystem is not only for AI engineers or Data engineers** - it's built with application developers in mind.

```
┌─────────────────────────────────────────────────────────────────────────┐
│                    Language Support                                     │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   ┌──────────────────────────────────────────────────────────────────┐  │
│   │                                                                  │  │
│   │   ┌─────────────┐        ┌─────────────┐        ┌─────────────┐  │  │
│   │   │             │        │             │        │             │  │  │
│   │   │   Python    │        │ JavaScript  │        │ TypeScript  │  │  │
│   │   │             │        │             │        │             │  │  │
│   │   │  Full.      │        │  Full.      │        │  Full       │  │  │
│   │   │  Support    │        │  Support    │        │  Support    │  │  │
│   │   │             │        │             │        │             │  │  │
│   │   └─────────────┘        └─────────────┘        └─────────────┘  │  │
│   │                                                                  │  │
│   └──────────────────────────────────────────────────────────────────┘  │
│                                                                         │
│   This makes it MUCH EASIER to integrate with backend systems!          │
│                                                                         │
│   • Node.js applications                                                │
│   • React/Next.js frontends                                             │
│   • Express/Fastify APIs                                                │
│   • Python FastAPI/Flask backends                                       │
│   • Django applications                                                 │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

---

## Summary

| Component | Purpose | Key Features |
|-----------|---------|--------------|
| **Observability** | Debug & Monitor | Traces, costs, latency, errors |
| **Evaluation** | Iterate & Improve | Datasets, metrics, A/B testing |
| **Deployment** | Ship & Scale | Version control, rollbacks, alerts |
| **LangGraph Studio** | Visual Builder | Drag-drop, debug, one-click deploy |

---

## Quick Reference

```python
# Essential environment variables
import os
os.environ["LANGCHAIN_TRACING_V2"] = "true"
os.environ["LANGCHAIN_API_KEY"] = "your-api-key"
os.environ["LANGCHAIN_PROJECT"] = "project-name"

# Essential imports
from langsmith import Client
from langsmith.evaluation import evaluate

# Get started at: https://smith.langchain.com
```

---



