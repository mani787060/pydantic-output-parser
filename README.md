# LangChain Pydantic Output Parser
[![LangChain](https://img.shields.io/badge/Framework-LangChain-green)](https://www.langchain.com/)
[![Pydantic](https://img.shields.io/badge/Validation-Pydantic%20v2-e92063)](https://docs.pydantic.dev/)
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)

## 🏗️ Project Overview
This repository demonstrates how to bridge the gap between AI's creative text and software's need for strict data types. Using the **`PydanticOutputParser`**, we force the LLM to adhere to a Python-native schema. This ensures that the extracted data is not just "valid JSON," but a valid instance of a Python class with the correct data types, ready for database insertion or API consumption.

---

## 🛠️ Key Technical Implementations

### 1. Model-Driven Architecture
* **Pydantic BaseModels:** Defining the "Source of Truth" for the data structure using standard Python classes.
* **Field Constraints:** Using `Field(description=...)` to provide the LLM with semantic guidance, effectively using the schema as a prompt engineering tool.

### 2. Automatic Instruction Generation
* **Format Injection:** Utilizing `parser.get_format_instructions()` to dynamically generate a schema description that the LLM understands perfectly.
* **Chain Orchestration:** Building a clean `Prompt | Model | Parser` pipeline using LangChain Expression Language (LCEL).

### 3. Runtime Type Safety
* **Validation at Scale:** Automatically converting strings to integers/floats and validating list lengths or string patterns during the parsing phase.
* **Object-Oriented AI:** Receiving an object that supports IDE autocompletion and type-checking, reducing developer error in downstream code.

---

## 💻 Tech Stack
* **Language:** Python 3.9+
* **Orchestration:** LangChain (`langchain-core`, `langchain-google-genai`)
* **Data Validation:** Pydantic v2
* **Model:** Google Gemini Pro
* **Environment:** `python-dotenv`

---

## 🚀 Getting Started

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/langchain-pydantic-validation-parser.git](https://github.com/your-username/langchain-pydantic-validation-parser.git)

2. **Install Dependencies:**
   ```bash
   pip install -U langchain-core langchain-google-genai pydantic python-dotenv

3. **Setup API Key:**
   Create a .env file in the root directory:
   ```bash
   GOOGLE_API_KEY=your_gemini_key_here

4. **Run the Implementation:**
   ```bash
   python pydantic_output_parser.py
