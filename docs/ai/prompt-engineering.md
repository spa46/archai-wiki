# Prompt Engineering

> **Review:**
> This page provides a comprehensive and practical introduction to prompt engineering for AI language models. It covers the definition of prompts, core goals, key principles, prompt styles, common pitfalls, and iteration strategies. The use of examples and actionable tips makes it accessible for both beginners and intermediate users. The "before & after" example is especially effective for illustrating best practices. Consider expanding with more advanced techniques or real-world case studies in the future.

---

## What is a Prompt?
A prompt is the input or instruction given to a language model. It can be a question, a command, or even a few words to start a conversation or generate content.

---

## Why Prompt Engineering Matters
Prompt engineering is the practice of crafting effective prompts to guide the behavior of AI language models. The main goals are:
- Improve the accuracy and relevance of AI responses
- Minimize hallucinations (AI-generated false information)
- Reduce ambiguity in instructions
- Maximize creative or insightful results when desired

---

## Principles of Good Prompt Engineering
Follow these principles to create effective prompts:

- **Clarity**: Be specific and unambiguous with your instructions.
- **Context**: Provide background information if needed.
- **Structure**: Use bullet points, lists, or clear formatting to organize your prompt.
- **Examples**: Show examples of what you want the AI to produce.
- **Role Play**: Ask the AI to "act as" an expert, teacher, or specific persona if relevant.

---

## Types of Prompts

1. **Instructional Prompt**  
   Example: `Summarize this article in 3 bullet points.`

2. **Few-shot Example Prompt**  
   Example: `Translate the following: 'Hello' → 'Hola', 'Goodbye' → 'Adiós'. Translate: 'Thank you' → ?`

3. **Role-based Prompt**  
   Example: `You are an English grammar expert. Correct the following sentence...`

---

## Avoiding Common Pitfalls

| Common Issue    | How to Fix                       |
|-----------------|----------------------------------|
| Too vague       | Add details or constraints       |
| Unclear task    | Explain the expected output      |
| Overly long     | Break complex prompts into steps |

---

## Iteration is Key
Prompt engineering is experimental. You may need to:
- Rewrite the prompt from another perspective
- Add constraints (such as word count or tone)
- Remove unnecessary context

Test and revise your prompts to get the best results.

---

## Further Tips
- Use markdown formatting (if supported) to structure prompts and outputs.
- Chain prompts: use one output as input for the next task.
- Ask the AI to explain its reasoning if you need clarity.

---

## Example - Before & After

**Bad Prompt**  
> Tell me about Paris.

**Better Prompt**  
> Give me a brief travel guide to Paris for first-time visitors, including top 3 attractions, best time to visit, and one local food to try.

---

## Related Topics
- AI Hallucination
- Few-shot Learning
- Zero-shot Prompting
- Chain-of-Thought Prompting
