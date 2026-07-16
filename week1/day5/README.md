# Day 5: Resume Parser & Matcher (Capstone Project)

A real-world candidate scoring application that automatically parses PDF and DOCX resumes, extracts details using a structured schema, and scores candidates against an automated Job Description evaluation prompt.

In this episode, we build:
* **A resume evaluator** that takes any job description as text input.
* **Automatic parsing** of PDF and Word resumes (converting them to clean text).
* **Pydantic schemas** to extract structured data from both the Job Description (JD) and the resume.
* **Intelligent matching** by sending both to an LLM.
* **A match verdict + final score + reasoning** returned for each candidate.

---

## Concepts Applied
* **LLM API calls with Groq (Episode 02)**: Used to perform multi-stage analysis: first extracting structured information from a Job Description, then parsing individual resumes, and finally comparing them to compute similarity scores.
* **System prompts to control LLM behavior (Episode 03)**: Structured roles defining the persona of an expert HR assistant, parser, and recruiter to evaluate candidates objectively.
* **Temperature 0 for consistent scoring (Episode 03)**: Applied across all evaluation API calls to ensure matching scores are consistent, deterministic, and free of hallucinations.
* **Token awareness for cost control (Episode 04)**: Implemented rate-limiting pauses (`time.sleep`) and structured schema templates to optimize prompt sizes and avoid API rate limits.
* **Pydantic models for structured output (Episode 05)**: Defined schemas like `JobD`, `Resume`, `Experience`, and `MatchResult` to validate all structured LLM responses.
* **JSON mode for reliable parsing (Episode 05)**: Configured client requests to strictly output JSON objects matching the schema definitions for programmatic loading.

## Key Features & Code Structure
* **File Reading Support**: Parsing `.pdf` (via `pypdf`) and `.docx` (via `python-docx`) files.
* **Dual-Stage LLM Evaluation**:
  1. Parse the Job Description and candidate resumes into structured Pydantic objects.
  2. Perform comparison matching (`final_score`) to produce a `MatchResult` with percentage and verdict.
* **Sorting & Analytics**: Ranks candidates to identify the top and lowest matches.
