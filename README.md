# 🧠 Prompt Chaining Blog Generator – n8n Workflow

This workflow demonstrates **AI prompt chaining** in **n8n**, generating a high-quality blog post from a single input topic. It chains multiple LLM steps—outline generation, evaluation, full blog writing—and posts the final result to **Google Docs**.



![image](https://github.com/user-attachments/assets/3c98ae0b-4d18-44dd-8ecd-35b60b986a5b)


---

## 📌 Features

- 📥 Accepts topic input via chat trigger
- ✍️ Generates a structured blog outline
- ✅ Evaluates and improves the outline
- 📝 Expands the refined outline into a full blog post
- 📄 Publishes to Google Docs
- 🤖 Uses the following LLMs via **OpenRouter**:
  - 🧠 **GPT-4o-mini (OpenRouter)** – Outline evaluation
  - 🧠 **GPT-4o-mini (OpenRouter)** – Blog content generation

---

## 🧩 Workflow Structure

| Step | Node Name                 | Purpose |
|------|---------------------------|---------|
| 1    | `When chat message received` | Triggered when user sends a blog topic |
| 2    | `Outline Writer`          | Creates a blog outline based on the input |
| 3    | `Outline Evaluation`      | Uses GPT-4o-mini to enhance the outline |
| 4    | `Blog Writer`             | Expands the final outline into a full blog post |
| 5    | `Post to Docs`            | Saves the generated blog to Google Docs |
| 6    | `4o mini`                 | Powers outline evaluation via OpenRouter |
| 7    | `4o mini (again)`         | Powers blog writing via OpenRouter |

---

## 🔧 Requirements

- Running instance of **n8n**
- Credentials/API keys set up for:
  - 🧠 **OpenRouter** (for GPT-4o-mini)
  - 📄 **Google Docs OAuth2**

---

## 🚀 How to Run

1. **Import** the JSON workflow into your n8n instance.
2. **Configure Credentials** for:
   - **OpenRouter** (GPT-4o-mini)
   - **Google Docs**
3. **Activate the workflow**.
4. Send a topic to the webhook/chat endpoint (e.g., “The future of AI in healthcare”).
5. The nodes will run as follows:
   - Topic → Outline → Evaluation → Blog → Google Docs

---

## 🧪 Example Input

```json
{
  "chatInput": "How AI is transforming personal finance management"
}
