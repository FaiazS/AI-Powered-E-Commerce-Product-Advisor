# 🛒 AI-Powered E-Commerce Product Advisor (LangChain + Groq)

An intelligent, conversational product advisor built with **LangChain**, **Groq (LLaMA-3.3-70B)**, **Pandas**, and **SQL-based memory**, capable of understanding natural language shopping queries, dynamically filtering product data, and making smart recommendations — just like your favorite online retail assistant!

---

## 🚀 Features

✅ Conversational product search powered by Groq + LLaMA-3  
✅ Intelligent product filtering via LLM-to-Pandas translation  
✅ Context-aware memory using SQLite (LangChain `RunnableWithMessageHistory`)  
✅ Rich Markdown output for beautifully formatted recommendations  
✅ Handles multi-turn queries like:
  - “I’m looking for a laptop”
  - “What features does it have?”
  - “Anything under 300?”
  - “What have we discussed so far?”

---

## 🧠 Tech Stack

| Layer         | Tool/Library                            |
|---------------|------------------------------------------|
| LLM Backend   | [Groq API](https://console.groq.com/) + [LLaMA-3.3-70B] |
| Chain Engine  | [LangChain](https://www.langchain.com/) |
| Chat History  | SQLite via LangChain `SQLChatMessageHistory` |
| Data Handling | `pandas` CSV filtering with `eval` logic |
| Output        | `rich` for Markdown-based CLI rendering |
| Platform      | Google Colab (💻 no setup needed!)       |

---

## 📊 Dataset Schema

The assistant reasons over the following table structure:

| Product ID | Product Name | Category        | Price\_USD | Description | Rating            |
| ---------- | ------------ | --------------- | ---------- | ----------- | ----------------- |
| str        | str          | \['Books', ...] | int        | str         | float (1.0 - 5.0) |

---

## 🧩 Core Logic

### 1. Natural Language → Pandas Query

User says:

> "Show me electronics under $200 with rating > 4"

LLM replies:

"products_dataframe[
  (products_dataframe['Category'] == 'Electronics') &
  (products_dataframe['Price_USD'] < 200) &
  (products_dataframe['Rating'] > 4)
]"

### 2. Pandas Result → Product Recommendations

LLM reads the filtered result and responds with:

  -Product name

  -Price

  -Rating

  -Description

  -Reason for recommendation

### 3. Rephrasing Follow-ups with Memory
   
Handles chat history to support:

 -“Tell me more about that one”

 -“Is it available in black?”

 -“What have we discussed so far?”
 
---

## 🗺️ System Architecture 

![image](https://github.com/user-attachments/assets/7f785a27-c8a2-4e86-a140-d1d5c020c032)

---

🧠 Author
---

Faiaz Ahmed
Seller Partner Support Associate @ Amazon
Aspiring AI Engineer | E-Commerce Innovator

---

🌟 Star This Repo
If this helped you learn LangChain + Groq + conversational AI, please give it a ⭐!
