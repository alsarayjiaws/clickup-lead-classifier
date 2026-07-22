# AI Lead Scoring & ClickUp CRM Integration

## Overview
This repository serves as an architectural showcase for an automated Lead Scoring and CRM Routing system. It ingests customer conversations, evaluates their purchase intent using LLMs, and seamlessly organizes the data within ClickUp for the sales team.

*Note: Source code is restricted under NDA. This document outlines the system architecture and business impact.*

## System Architecture & Data Flow

1. **Ingestion & Orchestration:** The pipeline is orchestrated using **n8n**, which listens for completed chat transcripts (e.g., from WhatsApp or other conversational channels).
2. **Context Analysis (Python & LLM):** 
   - A custom **Python** service receives the raw conversation payload.
   - It utilizes an LLM to read the entire transcript, generate a concise summary, and evaluate the lead.
3. **Multi-Tier Lead Classification:** The lead is scored against pre-defined, business-specific criteria (e.g., *Hot, Warm, Cold, Irrelevant*).
4. **CRM Injection:** Using the **ClickUp API**, the system automatically creates a new Task/Lead Profile in the appropriate ClickUp List based on their score. The task is populated with the customer's contact info, the AI-generated summary, and priority tags.

## Technical Stack
- **Workflow Orchestration:** n8n
- **Core Processing:** Python
- **AI/NLP:** Large Language Models (LLM) for summarization and intent classification
- **Integrations:** REST APIs, ClickUp API
- **Data Engineering:** JSON parsing, Webhook management

## Business Value
- **Prioritized Sales Efforts:** Sales representatives no longer waste time reading full chat histories or pursuing cold leads; they immediately see the AI summary and the lead's "temperature."
- **Data Centralization:** Eliminated manual data entry by automatically creating detailed client profiles in ClickUp.
- **Improved Conversion Rates:** "Hot" leads are instantly routed and tagged for immediate follow-up.