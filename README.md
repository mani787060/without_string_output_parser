# LangChain: Manual Response Handling
[![LangChain](https://img.shields.io/badge/Framework-LangChain-green)](https://www.langchain.com/)
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![Gemini](https://img.shields.io/badge/Model-Google%20Gemini-4285F4)](https://ai.google.dev/)

## 🏗️ Project Overview
This repository serves as a deep dive into the **`AIMessage`** object returned by LangChain models. While `StrOutputParser` is convenient for production chains, it hides the rich metadata provided by the LLM. This project demonstrates how to manually handle the raw response object to access content, token usage, and safety ratings—essential skills for debugging and monitoring AI applications.

---

## 🛠️ Key Technical Implementations

### 1. Raw Object Inspection
* **AIMessage Anatomy:** Accessing the `.content` attribute directly to retrieve the generated text.
* **Metadata Extraction:** Deep-diving into the `response_metadata` dictionary to view provider-specific information (e.g., Gemini's safety filters or stop reasons).

### 2. Manual Content Pipeline
* **Stateless Execution:** Running a `Prompt | Model` chain and capturing the resulting object.
* **Data Transformation:** Manually printing or saving the content without the abstraction of an output parser.

### 3. Debugging & Observability
* **Token Tracking:** Identifying how to find `prompt_tokens` and `completion_tokens` within the raw response for cost estimation.
* **Safety Monitoring:** Inspecting the safety attributes returned by the Google Generative AI SDK.

---

## 💻 Tech Stack
* **Language:** Python 3.9+
* **Orchestration:** LangChain (`langchain-core`, `langchain-google-genai`)
* **Model:** Google Gemini Pro
* **Environment:** `python-dotenv`

---

## 🚀 Getting Started

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/langchain-raw-response-handling.git](https://github.com/your-username/langchain-raw-response-handling.git)

2. **Install Dependencies:**
   ```bash
   pip install -U langchain-core langchain-google-genai python-dotenv

3.  **Setup API Key:**
    Create a .env file in the root directory:
    ```bash
    GOOGLE_API_KEY=your_gemini_key_here

4.Run the Implementation:
  ```bash
  python without_string_output_parser.py
   
