# Day 1: First LLM API Call

Today we make our first LLM API call in Python using the free Groq API to communicate with `llama-3.3-70b-versatile`.

## Concept Learned
* **LLM API calls with Groq (Episode 02)**: Understanding how to instantiate a Groq client, pass messages, and retrieve text completion responses programmatically.

## Key Topics Covered
* Creating a Python virtual environment with `uv`
* Making your first LLM API call with the Groq API
* Understanding message roles: `system`, `user`, `assistant`
* Safely handling API keys with `.env` files and `python-dotenv`
* Pushing code to GitHub safely (preventing API key leaks via `.gitignore`)
* Understanding common failure modes and exceptions

## Interview Preparation
> [!NOTE]
> **Q**: Walk me through what happens when you send a prompt to an LLM.
> 
> **A**: The client sends an HTTP POST request containing the API key, model, and message history (list of role/content objects) to the LLM provider's endpoint (e.g., Groq). The API validates the key, processes the input text into tokens, passes them to the model, streams/generates the output tokens, and returns a JSON response containing the text completion, token usage statistics, and finish reason.