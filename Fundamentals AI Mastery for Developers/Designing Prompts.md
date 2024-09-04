- Text Summarization
- Role Playing
- Code Generation
- Reasoning

# Prompt Engineering Techniques
1. Few-shot Prompts - provide exemplars in prompts to steer model towards better performance
2. Chain-of-Thought Prompting - instruct model to reason about the task when responding. (like explain your answer)
3. Zero-shot Chain-of-Thought Prompting - adding "think step-by-step" to the original prompt
4. Self-Consistency - aims to improve on the naive greedy decoding used in CoT prompting. The idea is to sample multiple reasoning paths through Few-shot CoT, and use generations to select most consistent answer.
5. Generate Knowledge Prompting - using additional knowledge
6. Program-aided Language Model - uses LLM to read problems and generate programs as intermediate reasoning steps. It offloads solution step to a runtime.
7. ReAct - framework where LLMs are used to generate both reasoning traces and task-specific actions in an interleaved manner
# Prompt Elements
1. Instructions 
2. Context
3. Input data
4. Output Indicator

# Tools & IDEs
- Dyno
- LangChain
- DUST
- Promptable