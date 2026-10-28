# Jev as a Judge

This notebook checks whether a doctor's scheduling assistant failed to understand an indirect or underspecified request. Each judge receives the doctor's message and the assistant's predicted intent, then answers **TRUE** if that specific failure occurred or **FALSE** otherwise. FALSE does not mean the answer is correct in every respect.

It compares three approaches:

- **Jev alone:** judges every case.
- **GPT-5 alone:** independently judges every case.
- **Jev with GPT-5 fallback:** uses GPT-5 when Jev's confidence is below 0.70 or its response is invalid.

Both judges use the same rules and six worked examples, without seeing the human labels or each other's answers. The notebook explores confidence thresholds on **21 practice cases**, then compares the approaches on **150 separate evaluation cases**. It reports accuracy, failure precision and recall, cost, escalation rates, and unresolved cases, and saves results for inspecting disagreements.

[Open in Colab](https://colab.research.google.com/github/The-Gen-Academy/Jev-as-a-Judge/blob/main/jev_vs_llm_judge.ipynb), provide TypeSafe and OpenAI API keys when prompted, and run the cells in order. Live API calls incur costs.

Colab loads helper code, prompts, and data from a [pinned course revision](https://github.com/The-Gen-Academy/Mastering-Agentic-AI-Week4-Session1/tree/92869cfbc04c3083ea8c99408189305ecfc6520f/AI-Evals-Principles/routing_agent_evals).
