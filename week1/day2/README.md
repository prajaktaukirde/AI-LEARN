# Day 2: System Prompts & Temperature

Understanding the controls that separate basic ChatGPT users from engineers building production AI products.

## Concepts Learned
* **System prompts to control LLM behavior (Episode 03)**: Using the `system` role to set instructions, persona, output format, and rules that guide the LLM's behavior and response style.
* **Temperature 0 for consistent scoring (Episode 03)**: Controlling randomness in LLM generations. Setting `temperature=0` forces the LLM to choose the most likely next token, ensuring consistent, reproducible, and deterministic responses essential for scoring and data extraction.

## Key Topics Covered
* The three message roles: `system`, `user`, `assistant` — and what each one does.
* Why the `system` role is the biggest lever in prompt engineering.
* Controlling randomness using the `temperature` parameter (ranging from `0.0` to `2.0`).
* Real-world examples of when to use `temperature=0` (consistent evaluation, extraction, parser) vs `0.7+` (creative writing, chatbots).

## Interview Preparation
> [!NOTE]
> **Q**: How would you make an LLM's answers more consistent?
> 
> **A**: Set the `temperature` parameter to `0`. This reduces randomness by choosing the highest probability tokens at each step of text generation. Additionally, using strict system instructions and formatting constraints (like JSON schema) helps lock down the output format.