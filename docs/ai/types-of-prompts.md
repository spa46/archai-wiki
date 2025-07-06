# Types of Prompts

This page describes common types of prompts used with AI language models. Each type includes a definition, example, and when to use it.

---

## 1. Zero-shot Prompting
**What it is:** You give the model a task without examples.

**Example:**
> Translate this sentence into French: I love pizza.

**When to use:** Simple or well-known tasks.

---

## 2. Few-shot Prompting
**What it is:** You show the model a few examples of how you want it to respond.

**Example:**
> Translate into French:
> - I love pizza. → J'adore la pizza.
> - She is happy. → Elle est heureuse.
> - He is tired. →

**When to use:** To guide the model with patterns.

---

## 3. Chain-of-thought Prompting
**What it is:** You explicitly ask the model to reason step-by-step.

**Example:**
> If a train leaves the station at 3 PM and travels for 2 hours, what time does it arrive? Let's think step by step.

**When to use:** Math, logic, and complex reasoning.

---

## 4. Instruction-based Prompting
**What it is:** You give very clear, structured instructions.

**Example:**
> Summarize this paragraph in 2 sentences focusing only on the main idea.

**When to use:** For high precision or consistent format.

---

## 5. Role-based Prompting
**What it is:** You assign a role or persona to the model.

**Example:**
> You are a professional lawyer. Explain this legal term in simple language.

**When to use:** To match tone, expertise, or audience.

---

## 6. Contextual or Dynamic Prompting
**What it is:** You insert relevant background/context before the question.

**Example:**
> In the context of European history during the 19th century, explain the causes of the French Revolution.

**When to use:** When the task depends heavily on prior information.

---

## 7. Multi-turn Prompting
**What it is:** Building context across a conversation.

**Example:**
> First message sets up a scenario, second message asks a specific question.

**When to use:** For dialogue, memory-based reasoning, tutoring, etc.

---

## 8. Prompt Chaining (Modular Prompting)
**What it is:** Breaking tasks into smaller steps and using the output of one as the input of the next.

**When to use:** For complex tasks like code generation, document parsing, etc. 