# LangChain: Without String Output Parser

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![LangChain](https://img.shields.io/badge/Framework-LangChain-green)](https://www.langchain.com/)
[![Google Gemini](https://img.shields.io/badge/LLM-Google%20Gemini-4285F4)](https://ai.google.dev/)
[![Generative AI](https://img.shields.io/badge/Focus-Generative%20AI-purple)](https://ai.google.dev/)

## 📌 Project Overview

This project explores how to work directly with the response returned by a chat model in LangChain **without using `StrOutputParser`**.

Chat models typically return an `AIMessage` object rather than a plain Python string. This object contains the generated content and may include additional information, such as response metadata and token usage.

By accessing the response directly, developers can better understand how LangChain represents model outputs and how to inspect information useful for debugging and application development.

## 🎯 Learning Objectives

- Understand the `AIMessage` response object in LangChain.
- Extract generated text using the `.content` attribute.
- Learn the difference between a raw model response and a plain string.
- Explore response metadata when it is available.
- Understand why manual response handling can be useful when debugging LLM applications.

## 🛠️ Key Concepts

### 1. Understanding the AIMessage Object

When a chat model is invoked, the returned response may contain more than just generated text.

For example:

```python
response = model.invoke("Explain Generative AI in simple words.")

print(response)
print(response.content)
```

- `response` represents the model's response object.
- `response.content` accesses the generated content.

The exact structure and available fields depend on the model integration and response type.

### 2. Manual Response Handling

Without an output parser, you can access the required information directly from the response object.

This approach is useful when you want to inspect the raw response or access additional information beyond the generated text.

### 3. Response Metadata

Depending on the provider and model integration, the response may expose metadata through attributes such as `response_metadata` and `usage_metadata`.

For example:

```python
print(response.response_metadata)
print(response.usage_metadata)
```

These fields may contain information about the model response, token usage, or provider-specific details. Their availability and structure can vary, so inspect the actual response before relying on particular keys.

### 4. Manual Handling vs. StrOutputParser

| Aspect | Manual Response Handling | StrOutputParser |
|---|---|---|
| Output | Model response object | Parsed text string |
| Text extraction | Access `.content` directly | Performed by the parser |
| Metadata access | Available through the response object when provided | Not the primary purpose |
| Best suited for | Inspection and debugging | Clean text-processing pipelines |

Both approaches are useful. The right choice depends on whether you need the complete response object or only the generated text.

## 🧰 Tech Stack

- **Language:** Python
- **LLM Framework:** LangChain
- **Model Provider:** Google Gemini
- **Core Concepts:** `AIMessage`, response content, and metadata
- **Environment Configuration:** `python-dotenv` (if used by the implementation)

## 🚀 Getting Started

### Prerequisites

- Python installed on your system
- Required project dependencies
- A Google Gemini API key if the script calls Gemini

### 1. Clone the Repository

```bash
git clone https://github.com/mani787060/without_string_output_parser.git
```

### 2. Navigate to the Project Directory

```bash
cd without_string_output_parser
```

### 3. Install Dependencies

If your implementation uses LangChain with Google Gemini and environment variables, install the required packages:

```bash
pip install -U langchain-core langchain-google-genai python-dotenv
```

### 4. Configure Your API Key

If your script uses `python-dotenv`, create a `.env` file in the project directory:

```env
GOOGLE_API_KEY=your_gemini_api_key
```

Keep your API key private and never upload your `.env` file to GitHub.

### 5. Run the Python Script

```bash
python without_string_output_parser.py
```

If your Python file has a different name, replace the filename in the command.

## 📚 Key Takeaways

Working directly with LangChain's model response helps you understand the structure behind generated text and the metadata that may accompany it.

This knowledge provides a useful foundation for debugging, monitoring, and building Generative AI applications. It also helps explain why output parsers such as `StrOutputParser` are useful when a workflow needs only clean text.

