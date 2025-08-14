# The "Digital Skeptic" AI
This application performs a **"skeptical analysis"** of any online news article using the **LangGraph** framework and **Groq LLM**.  
It fetches the article content, identifies key claims, analyzes language and tone, detects potential red flags, generates counter-arguments, and produces a **Markdown report** to help readers think critically.

---

## 📌 Features
- **FrameWork** – Langgraph (Code-Based agentic Framework)
- **Article Fetching** – Uses `BeautifulSoup` to scrape and clean article text.
- **Core Claim Extraction** – Summarizes the 3–5 main factual claims.
- **Language & Tone Analysis** – Classifies writing style (neutral, emotional, opinionated, etc.).
- **Bias Detection** – Flags possible signs of poor reporting.
- **Counter-Argument Simulation** – Summarizes from an opposing viewpoint to reveal biases.
- **Verification Questions** – Suggests targeted questions for fact-checking.
- **Markdown Output** – Generates a structured, readable analysis report.

---

**This is the graph flow, which I have implemented.**

<img width="272" height="829" alt="Image" src="https://github.com/user-attachments/assets/159b80c0-3c5f-48e2-bd2b-69d4a42495c7" />

## 🚀 How to Test the Application
- You will need an Groq API key. So, please put it in your .env file.
- Install the libraries mentioned in the requirements.txt.
- I have specifically used **LLaMA-4 Scout** model becuase of it's longest context window(10 million tokens). I recommend you to use it because we are doing a high intellectual task.
- After all this steps, you can properly run this code successfully.


## 🛠️ Approach

1. **Data Extraction**  
   - The tool takes a **URL** as input.
   - Uses `requests` + `BeautifulSoup` to retrieve HTML and extract article text and title.

2. **LangGraph Workflow**  
   - Each analysis step is a **LangGraph node**:
     1. Fetch Article Content
     2. Extract Core Claims
     3. Analyze Language & Tone
     4. Detect Potential Red Flags
     5. Simulate Counter-Argument
     6. Generate Verification Questions
     7. Compile Markdown Report
   - Nodes are connected in sequence, and state is passed through all steps.

3. **LLM Analysis**  
   - **Groq LLaMA-4 Scout** (`meta-llama/llama-4-scout-17b-16e-instruct`) is used to:
     - Identify factual claims
     - Analyze tone and bias
     - Generate counter-arguments
     - Formulate verification questions

4. **Report Generation**  
   - All results are compiled into a **Markdown report** with:
     - Article title in the header
     - Separate sections for each analysis category

---

