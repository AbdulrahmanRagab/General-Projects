# 💬 OpenAI Chat Assistant - Streamlit Project  

## 🌟 Overview  
An interactive AI chatbot interface powered by OpenAI's language models. Features dynamic response configuration with model selection, creativity controls, and token management through an intuitive Streamlit interface.

---

## 🛠️ Technologies Used  

### Core Libraries  
- **Python**  
  ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)  
- **Streamlit**  
  ![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)  
- **OpenAI**  
  ![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)  
- **LangChain**  
  ![LangChain](https://img.shields.io/badge/LangChain-00A67D?style=for-the-badge&logo=langchain&logoColor=white)  
- **Python-dotenv**  
  ![Dotenv](https://img.shields.io/badge/python--dotenv-ECD53F?style=for-the-badge&logo=dotenv&logoColor=000)  

---

## 🎉 Demo

⚙️ **Key Features**

* **Model Selection**: Choose between GPT-4 and GPT-3.5 variants
* **Response Tuning**:

  * Temperature control (0.0–1.0) for creativity
  * Max tokens restriction (10–200) for controlling response length
* **Secure Authentication**: Password-style API key input
* **Real-Time Interaction**: Instant LLM responses upon input

🎥 **Live Preview**:
Run locally with the following command:

```bash
streamlit run app.py
```

---

## 🔮 Future Work → RAG Implementation Roadmap

### 📚 Knowledge Integration

* Vector DB integration: **Pinecone**, **FAISS**
* PDF/Web document loaders

### 🔄 Enhanced Context Handling

* Conversation memory support
* Chunking for long-context retention

### ☁️ Deployment

* Docker containerization
* Cloud hosting (AWS / GCP)

---

## 🛠️ How to Use

1. **Install dependencies**

   ```bash
   pip install streamlit openai langchain python-dotenv
   ```

2. **Create `.env` file** with your OpenAI API key:

   ```
   OPENAI_API_KEY=your_openai_key
   ```

3. **Run the app**

   ```bash
   streamlit run app.py
   ```

4. **Interact via UI**:

   * Enter API key in the sidebar
   * Choose model and response settings
   * Type your question and receive a response instantly

```
```
