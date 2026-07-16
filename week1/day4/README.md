# Day 4: Structured Output with Pydantic & JSON Mode

LLMs return unstructured text, but production systems need structured, predictable, and validated data. In this day, we bridge the gap.

## Concepts Learned
* **Pydantic models for structured output (Episode 05)**: Defining strict data schemas using Pydantic classes to validate LLM outputs and cast them directly to typed Python objects.
* **JSON mode for reliable parsing (Episode 05)**: Forcing the LLM to return valid JSON matching the requested schema, eliminating parsing failures.

## Key Topics Covered
* Why raw text LLM outputs fail in real-world software applications.
* Defining data structure schemas with `Pydantic` and exporting them to JSON schema via `.model_json_schema()`.
* Passing the schema inside the `system` prompt to instruct the LLM on output shape.
* Enabling `"type": "json_object"` in the API request's `response_format` configuration.
* Parsing and loading raw JSON strings using `json.loads` and instantiating Pydantic model objects for type validation and IDE autocompletion.
* Handling validation errors gracefully in production code.

## Interview Preparation
> [!NOTE]
> **Q**: How do you guarantee that an LLM output is in JSON and matches your system's data structure?
> 
> **A**: We request a JSON object from the LLM by enabling `response_format={"type": "json_object"}` in the API call. We pass a structured schema (generated using a Pydantic model) in the system instructions. Finally, we load the returned JSON string and run it through Pydantic's validation. If validation fails, we can handle it with fallback mechanisms or re-prompting.