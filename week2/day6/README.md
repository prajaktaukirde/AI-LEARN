# Day 6: Production Prompt Engineering

Prompt engineering is the #1 skill separating people who build AI apps from people who play with ChatGPT. Learn the structured, production-grade approach that survives real users and edge cases.

## Concepts Learned
* **Production-Grade Prompting (Episode 07)**: Structuring prompts systematically using a 6-section template to make LLM outputs consistent, reliable, and deterministic inside application code.

## Key Topics Covered
* Why prompts that work in ChatGPT's conversational interface break when integrated into codebase APIs.
* **The 6-Section Prompt Anatomy**:
  1. **ROLE**: Define the LLM's persona (e.g., Support Assistant).
  2. **TASK**: The primary objective (e.g., classify an issue).
  3. **CONSTRAINTS**: Explicit boundaries (e.g., choose from only three categories).
  4. **OUTPUT FORMAT**: The precise output shape required (e.g., output one word only).
  5. **EXAMPLES (Few-shot)**: Demonstrations of input/output pairs to guide behavior.
  6. **FALLBACK**: Instructions for when inputs do not match standard criteria (e.g., output `OTHER`).
* Markdown (`#SECTION`) vs. XML (`<section>`) tags to structure prompt data.
* Why positive instructions ("do this") beat negative instructions ("don't do that").

## Interview Preparation
> [!NOTE]
> **Q**: How do you write LLM prompts that are reliable enough to be used in production software?
> 
> **A**: We avoid open-ended natural language. Instead, we use a structured template (containing Role, Task, Constraints, Output Format, Examples, and Fallback instructions) bounded by tags (Markdown headers or XML tags). We also provide explicit edge-case fallbacks and utilize few-shot examples to align the LLM’s responses with our system's expectations.
