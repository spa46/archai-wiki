# MCP Use Cases (Expanded)

## 1. Multi-Model AI Assistants

**Scenario:**  
You want to build an assistant that can answer general questions, write stories, and solve math problems. You have two LLMs (e.g., GPT-4 for creative tasks, Llama for Q&A) and a calculator tool.

**How it works:**
- The MCP server registers each model and tool as a resource.
- The client (assistant) routes user requests to the appropriate resource based on intent.

**Example Flow:**
1. User: "Write a poem about the sea."  
   → Routed to GPT-4 resource.
2. User: "What is the capital of France?"  
   → Routed to Llama resource.
3. User: "Calculate 23 * 47."  
   → Routed to Calculator tool.

**Sample Code:**
```python
# Client-side routing logic
if "poem" in user_input:
    response = client.complete(prompt=user_input, resource="GPT4Resource")
elif "capital" in user_input:
    response = client.complete(prompt=user_input, resource="LlamaResource")
elif "calculate" in user_input:
    math_expr = user_input.replace("calculate", "").strip()
    response = client.run_tool(input=math_expr, resource="CalculatorResource")
```

---

## 2. Tool-Augmented LLMs

**Scenario:**  
You want your LLM to answer questions and also execute Python code when needed (e.g., for math or data processing).

**How it works:**
- The LLM is prompted to call the PythonExecutor tool via MCP when it detects a code execution request.

**Example Flow:**
1. User: "What is the result of 2**8 + 10?"
2. LLM: Recognizes this as a computation, sends `"2**8 + 10"` to the PythonExecutor tool.
3. Tool returns `266`.
4. LLM responds: "The result is 266."

**Sample Code:**
```python
# Tool resource
class PythonExecutorResource(ToolResource):
    def run(self, input, context):
        try:
            return str(eval(input))
        except Exception as e:
            return f"Error: {e}"

# LLM prompt template
prompt = (
    "If the user asks for a calculation, call the PythonExecutor tool. "
    "Otherwise, answer normally.\n"
    f"User: {user_input}"
)
```

---

## 3. Contextual Memory Sharing

**Scenario:**  
You want the assistant to remember the user's name and preferences across multiple interactions.

**How it works:**
- The MCP context object stores user data.
- Each resource can access and update the context.

**Example Flow:**
1. User: "My name is Alice."
   - Context updated: `{"user_name": "Alice"}`
2. User: "Remind me to call Bob tomorrow."
   - Context updated: `{"reminders": ["call Bob tomorrow"]}`
3. User: "What's my name?"
   - Assistant retrieves `user_name` from context and replies: "Your name is Alice."

**Sample Code:**
```python
# Accessing context in a resource
def complete(self, prompt, context):
    if "my name" in prompt:
        return f"Your name is {context.get('user_name', 'unknown')}."
    # ... other logic ...
```

---

## 4. Agent Frameworks and Orchestration

**Scenario:**  
You want to automate a workflow: research a topic, summarize findings, and send an email.

**How it works:**
- Each step is handled by a different MCP resource (WebSearch, Summarizer, EmailSender).
- An orchestrator client coordinates the workflow.

**Example Flow:**
1. User: "Research the latest AI trends and email me a summary."
2. Orchestrator:
   - Calls WebSearch resource for "latest AI trends".
   - Passes results to Summarizer resource.
   - Sends summary to EmailSender resource.

**Sample Code:**
```python
search_results = client.run_tool(input="latest AI trends", resource="WebSearchResource")
summary = client.complete(prompt=search_results, resource="SummarizerResource")
client.run_tool(input=summary, resource="EmailSenderResource")
```

---

## 5. Standardized Prompt Engineering

**Scenario:**  
You want to ensure all prompts sent to LLMs follow a consistent format for better results.

**How it works:**
- Use MCP’s prompt formatting utilities or templates.
- Store and reuse prompt templates for different tasks.

**Example Flow:**
1. User: "Summarize this article."
2. Client applies a prompt template:  
   `"Summarize the following text in 3 sentences:\n{article_text}"`
3. Sends formatted prompt to the LLM resource.

**Sample Code:**
```python
prompt_template = "Summarize the following text in 3 sentences:\n{content}"
formatted_prompt = prompt_template.format(content=article_text)
response = client.complete(prompt=formatted_prompt, resource="LLMResource")
```

---

## Reference

For more implementation details and code, see [Sample AI-Application-with-MCP.md](./Sample%20AI-Application-with-MCP.md).
