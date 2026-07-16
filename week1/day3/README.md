# Day 3: Token Awareness & Cost Control

Going deep on what tokens actually are, why they determine your API bill, and how to manage them like a production engineer.

## Concepts Learned
* **Token awareness for cost control (Episode 04)**: Understanding input vs. output token counts, the `max_tokens` parameter as an emergency brake, reading token usage statistics from API responses, and calculating the exact dollar cost of API usage.

## Key Topics Covered
* What a token is (sub-word units parsed by byte-pair encoding tokenizers).
* Why short inputs can sometimes cost more than expected.
* Input (prompt) tokens vs. output (completion) tokens (and why output tokens cost more).
* Using `max_tokens` to prevent runaway costs from infinite loops or long generations.
* Inspecting the `finish_reason` (e.g., `stop` vs. `length`) to catch truncated outputs in production.
* Why multilingual prompts (Hindi, Hinglish, etc.) consume more tokens due to tokenization fragmentation.

## Interview Preparation
> [!NOTE]
> **Q**: How would you reduce LLM costs in production?
> 
> **A**: Cost reduction can be achieved through:
> 1. **Prompt Optimization**: Keeping system and user prompts concise to minimize input tokens.
> 2. **Output Constraints**: Setting appropriate `max_tokens` limits.
> 3. **Model Selection**: Using smaller, optimized models (e.g., Llama 3-8B vs. 70B) for simpler tasks.
> 4. **Caching**: Caching common responses or using prompt caching capabilities.
> 5. **Summarization**: Truncating or summarizing chat history in multi-turn conversations instead of sending the full history.
