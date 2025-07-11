# Types of Prompts

This page describes common types of prompts used with AI language models. Each type includes a definition, example, and when to use it.

---

## 1. Zero-shot Prompting
Ask the model to perform a task without providing any examples.

**Use:** Simple or well-known tasks.

**Example**  
> Q: Translate this sentence into French: I love pizza.  
> A: J'adore la pizza.

---

## 2. Few-shot Prompting
Show a handful of examples to illustrate the desired pattern or response.

**Use:** To guide the model with patterns.

**Example**  
> Q:  
> Translate into French:  
> – I love pizza. → J'adore la pizza.  
> – She is happy. → Elle est heureuse.  
> – He is tired. →  
> A: Il est fatigué.

---

## 3. Chain-of-thought Prompting
Encourage the model to reason through problems step-by-step and make its thinking process explicit.

**Use:** Math, logic, and complex reasoning.

**Example**  
> Q: If a train leaves the station at 3 PM and travels for 2 hours, what time does it arrive? Let's think step by step.  
> A: The train leaves at 3 PM. It travels for 2 hours. 3 PM plus 2 hours is 5 PM. So, the train arrives at 5 PM.

**Use:** Math, logic, and complex reasoning.

---

## 4. Instruction-based Prompting
Give clear, structured directions for the model to follow.

**Use:** For high precision or consistent format.

**Example**  
> Q: Summarize this paragraph in 2 sentences focusing only on the main idea.  
> A: The paragraph discusses the importance of teamwork in achieving goals. It emphasizes that collaboration leads to better results than working alone.

**Use:** For high precision or consistent format.

---

## 5. Role-based Prompting
Assign a specific role or persona to shape the response style or expertise.

**Use:** To match tone, expertise, or audience.

**Example**  
> Q: You are a professional lawyer. Explain this legal term in simple language: "Habeas Corpus".  
> A: "Habeas Corpus" is a legal term that means a person has the right to be brought before a judge if they are being held in jail, to make sure their detention is lawful.

**Use:** To match tone, expertise, or audience.

---

## 6. Contextual or Dynamic Prompting
Provide relevant background information or context before asking the main question.

**Use:** When the task depends heavily on prior information.

**Example**  
> Q: In the context of European history during the 19th century, explain the causes of the French Revolution.  
> A: The French Revolution was caused by social inequality, economic hardship, and the influence of Enlightenment ideas, which led people to demand more rights and a fairer government.

**Use:** When the task depends heavily on prior information.

---

## 7. Multi-turn Prompting
**What it is:** Building context across a conversation.

**Example**  
> Q: (Turn 1) Imagine you are a travel agent. I want to visit Italy.  
> A: (Turn 1) That sounds wonderful! What cities in Italy are you interested in visiting?  
> Q: (Turn 2) I'm interested in Rome and Venice. What are the must-see attractions?  
> A: (Turn 2) In Rome, you should visit the Colosseum, the Vatican, and the Trevi Fountain. In Venice, don't miss St. Mark's Basilica, the Grand Canal, and a gondola ride.

**Use:** For dialogue, memory-based reasoning, tutoring, etc.

---

## 8. Prompt Chaining (Modular Prompting)
**What it is:** Breaking tasks into smaller steps and using the output of one as the input of the next.

**Example**  
> Q (Step 1): Extract all dates from this text: "The conference was held on March 3, 2022, and the next meeting is scheduled for July 15, 2023."  
> A (Step 1): March 3, 2022; July 15, 2023  
> Q (Step 2): For each date, summarize the event that happened.  
> A (Step 2):  
> - March 3, 2022: The conference was held.  
> - July 15, 2023: The next meeting is scheduled.

**Use:** For complex tasks like code generation, document parsing, etc. 