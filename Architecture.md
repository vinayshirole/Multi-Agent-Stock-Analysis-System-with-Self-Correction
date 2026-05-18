# Multi-Agent Stock Analysis System

## Overview
LangGraph-based system with 5 specialized agents:
- Manager: Orchestration
- Research: Company info via web search
- Data: Financial metrics via APIs
- Report: Synthesis
- Critic: Self-correction

## Flow
1. User query → Manager
2. Manager → Research (company background)
3. Manager → Data (financial metrics)
4. Manager → Report (synthesize findings)
5. Manager → Critic (validate + correct)
6. If critique fails → Report (revise) [max 2 iterations]
7. Return final report

## State
- `query`: User input
- `research_data`: Company info
- `financial_data`: Metrics
- `report`: Initial report
- `critique`: Validation results
- `revision_needed`: Boolean
- `revision_count`: Int
- `final_report`: Output
- `confidence_score`: 0-1

## Tools
- Web search (for research agent)
- Alpha Vantage API (for data agent)

## Evaluation Metrics
- Accuracy (fact-checking)
- Completeness (coverage)
- Latency (P95)
- Self-correction rate

## Tech Stack
- LangGraph (orchestration)
- Groq API (LLM)
- FastAPI (API layer)
- Docker (deployment)