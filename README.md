# 🧠 Prompt Chaining Blog Generator – n8n Workflow

This workflow demonstrates **AI prompt chaining** in **n8n**, generating a high-quality blog post from a single input topic. It chains multiple LLM steps—outline generation, evaluation, full blog writing—and posts the final result to **Google Docs**.

---

## 📌 Features

- 📥 Accepts topic input via chat trigger
- ✍️ Generates a structured blog outline
- ✅ Evaluates and improves the outline
- 📝 Expands the refined outline into a full blog post
- 📄 Publishes to Google Docs
- 🤖 Uses the following LLMs:
  - 🧠 **OpenRouter (GPT-4o-mini)** – Outline evaluation
  - 🧠 **Anthropic Claude 3.5** – Full blog generation
  - 🧠 **DeepSeek Reasoner** – Reserved for reasoning or extra tasks

---

## 🧩 Workflow Structure

| Step | Node Name            | Purpose |
|------|----------------------|---------|
| 1    | `When chat message received` | Triggered when user sends a blog topic |
| 2    | `Outline Writer`     | Creates a blog outline based on the input |
| 3    | `Outline Evaluation` | Uses GPT-4o-mini (via OpenRouter) to enhance the outline |
| 4    | `Blog Writer`        | Expands the final outline into a full blog post |
| 5    | `Post to Docs`       | Saves the generated blog to Google Docs |
| 6    | `Claude 3.5`         | Provides creative writing power to Blog Writer |
| 7    | `4o mini`            | Provides critical evaluation for outline |
| 8    | `DeepSeek R1`        | Can be used for advanced reasoning or verification tasks |

---

## 🔧 Requirements

- Running instance of n8n
- Credentials/API keys set up for:
  - 🧠 OpenRouter (GPT-4o-mini)
  - 🧠 Anthropic Claude 3.5
  - 🧠 DeepSeek Reasoner
  - 📄 Google Docs OAuth2

---

## 🚀 How to Run

1. **Import** the JSON workflow into your n8n instance.
2. **Configure Credentials** for:
   - OpenRouter (for GPT-4o-mini)
   - Claude (Anthropic API key)
   - DeepSeek
   - Google Docs
3. **Activate the workflow**.
4. Send a topic to the webhook/chat endpoint (e.g., “The future of AI in healthcare”).
5. Watch the nodes execute:
   - Topic → Outline → Evaluation → Blog → Google Docs.

---

## 🧪 Example Input

```json
{
  "chatInput": "How AI is transforming personal finance management"
}
