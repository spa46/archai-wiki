# Prompt Engineering


---

## What is a Prompt?
- **Structuring inputs (questions or commands)** to guide an AI model to produce accurate and relevant output.
- Helps reduce hallucinations, bias, and vague answers.
- Useful for anyone working with AI: developers, researchers, content creators, and more.

---

## Types of Prompts
There are several common types of prompts used with AI language models:

- **Zero-shot Prompting**: Give the model a task without examples.
- **Few-shot Prompting**: Show the model a few examples to guide its responses.
- **Chain-of-thought Prompting**: Ask the model to reason step-by-step.
- **Instruction-based Prompting**: Provide clear, structured instructions.
- **Role-based Prompting**: Assign a role or persona to the model.
- **Contextual or Dynamic Prompting**: Insert relevant background/context before the question.
- **Multi-turn Prompting**: Build context across a conversation.
- **Prompt Chaining (Modular Prompting)**: Break tasks into smaller steps, using outputs as new inputs.

For detailed definitions and examples, see [Types of Prompts](types-of-prompts.md).

---

## Why Prompt Engineering Matters
Prompt engineering means crafting prompts to guide AI models. The main goals:

- Improve accuracy and relevance of responses
- Minimize hallucinations (false information)
- Reduce ambiguity in instructions
- Encourage creative or insightful results when needed

---

## Principles of Good Prompt Engineering
Use these principles for better prompts:

- **Clarity**: Be specific and unambiguous.
- **Context**: Give background if needed.
- **Structure**: Use lists or clear formatting.
- **Examples**: Show what you want the AI to produce.
- **Role Play**: Ask the AI to act as an expert or persona if helpful.

---

## Tips for Better Prompts

1. **Be clear and specific**  
   > Bad: "Tell me about plants."  
   > Good: "What are the benefits of growing lettuce in a hydroponic NFT system indoors?"

      Include relevant **context, constraints, or goals** in your prompt.
      
      <br/>


2. **Provide a role or perspective (optional but powerful)**  
   > "Act as a data scientist.  
   > Can you explain how to fine-tune a transformer model using PyTorch?"  

      This helps the AI simulate a more **accurate tone** or **specialist mindset**.

      <br/>

3. **Break complex queries into steps**  
   > "I want to write a research paper.  
   > First, help me outline the key sections, then we can work on each section together."  

      Chunking improves focus and minimizes confusion.

      <br/>

4. **Set the format you want**  
   > "Give me a bullet-point summary."  
   > "Write it as a table with columns: Feature | Description | Pros | Cons."  

      This keeps answers structured and easy to digest.

      <br/>

5. **Use examples for clarification**  
   > "I want my writing to sound like this: 'The sunset poured gold over the quiet hills.'  
   > Can you improve my paragraph to match that style?"  

      Examples reduce hallucination and improve alignment with your intention.

      <br/>

6. **Specify what you don't want**  
   > "Don't include historical background — just focus on current applications of AI in healthcare."  

      This prevents unnecessary or off-topic output.

      <br/>

7. **Iterate and refine**  
   > Ask, review, then say:  
   > "This is close, but could you make it more formal / concise / technical?"  

      You don't have to get the perfect prompt the first time — **interactive refinement** is key.

---

## Pitfalls to Avoid

| Common Issue    | How to Fix                 |
|-----------------|---------------------------|
| Too vague       | Add details or constraints |
| Unclear task    | Explain expected output    |
| Overly long     | Break into steps           |

---

## Improving Your Prompts
Prompt engineering is experimental. You may need to:

- Rewrite from a new perspective
- Add constraints (e.g., word count, tone)
- Remove extra context

Test and revise your prompts for best results.

---

## Further Tips
- Use markdown formatting to structure prompts and outputs.
- Chain prompts: use one output as input for the next task.
- Ask the AI to explain its reasoning if you need clarity.

---

## Example Transformation

| Type           | Prompt Example |
| -------------- | -------------- |
| **Too vague** | "Tell me about AI" |
| **Better**    | "Explain how AI is used in fraud detection in financial institutions." |
| **Best**      | "Act as a security engineer.<br>Explain how machine learning helps detect fraud in banking systems,<br>including common algorithms and real-world challenges." |

---

## How to Reduce Hallucinations

- Ask for sources, assumptions, or step-by-step reasoning.
  - Example: "Can you give me a step-by-step explanation of how you arrived at this answer?"
- Request external verification if accuracy is critical.
- Avoid vague or open-ended questions unless you're brainstorming.

---

## Related Topics
- AI Hallucination
- Few-shot Learning
- Zero-shot Prompting
- Chain-of-Thought Prompting

---

## References

- [OpenAI Cookbook: Prompt Engineering](https://github.com/openai/openai-cookbook/blob/main/techniques_to_improve_reliability.md)
- [DeepLearning.AI: Prompt Engineering Guide](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/)
- [Google: Prompt Design](https://cloud.google.com/vertex-ai/docs/generative-ai/learn/prompt-design)
- [Prompt Engineering for AI Agents](https://www.oreilly.com/library/view/prompt-engineering-for/9781098153427/ch01.html)