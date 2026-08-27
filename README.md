::: {align="center"}
# 🎥 AI Video Assistant

### Transcribe • Summarise • Chat with Your Videos

An AI-powered video intelligence application that converts YouTube
videos or local media into searchable transcripts, concise summaries,
and context-aware answers using **Whisper** and **Retrieval-Augmented
Generation (RAG)**.

`<br>`{=html}

[![Python](https://img.shields.io/badge/Python-3.12+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![OpenAI
Whisper](https://img.shields.io/badge/Whisper-Speech%20to%20Text-412991?style=for-the-badge&logo=openai&logoColor=white)](https://github.com/openai/whisper)
[![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/)
[![LangChain](https://img.shields.io/badge/LangChain-RAG-1C3C3C?style=for-the-badge&logo=chainlink&logoColor=white)](https://www.langchain.com/)
[![YouTube](https://img.shields.io/badge/YouTube-Supported-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://www.youtube.com/)
:::

------------------------------------------------------------------------

## 📌 Overview

**AI Video Assistant** is a Streamlit-based application designed to make
long-form video content easier to understand and interact with.

Instead of watching an entire video to find one piece of information,
users can provide a **YouTube URL or local video/audio file** and let
the application:

-   🎵 Extract and process audio
-   📝 Transcribe speech using **OpenAI Whisper**
-   ✂️ Process long audio through manageable chunks
-   🧠 Generate an AI-powered summary
-   🔎 Build a searchable knowledge base using **RAG**
-   💬 Answer questions based on the video's actual content
-   📄 Display the complete transcript

------------------------------------------------------------------------

## ✨ Key Features

  -----------------------------------------------------------------------
  Feature                             Description
  ----------------------------------- -----------------------------------
  🎬 **YouTube Support**              Analyze videos directly from a
                                      YouTube URL

  📁 **Local Files**                  Process supported local video/audio
                                      files

  🎙️ **Whisper Transcription**        Convert spoken content into text

  ✂️ **Audio Chunking**               Split long audio into smaller
                                      chunks for reliable processing

  🧠 **AI Summarization**             Extract important points and
                                      actionable insights

  🔍 **Semantic Search**              Retrieve relevant transcript
                                      sections based on meaning

  💬 **Context-Aware Q&A**            Ask questions about the analyzed
                                      video

  📜 **Full Transcript**              View the generated transcript

  🏷️ **Automatic Title Generation**   Generate a meaningful session title

  🖥️ **Streamlit UI**                 Clean interactive interface with
                                      live pipeline status
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 🏗️ How It Works

``` text
                    ┌──────────────────────┐
                    │   YouTube URL /      │
                    │   Local Video File   │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Audio Extraction   │
                    │   & Pre-processing   │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Audio Chunking     │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │ Whisper Transcription│
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │ Transcript Cleaning  │
                    │   & Text Splitting   │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │ Embeddings + Vector  │
                    │       Store          │
                    └──────────┬───────────┘
                               │
                    ┌──────────┴───────────┐
                    ▼                      ▼
          ┌─────────────────┐     ┌─────────────────┐
          │   Summarizer    │     │   RAG Q&A       │
          └─────────────────┘     └────────┬────────┘
                                           │
                                           ▼
                                  ┌─────────────────┐
                                  │ Context-Aware   │
                                  │     Answer      │
                                  └─────────────────┘
```

------------------------------------------------------------------------

## 🧠 RAG Pipeline

The question-answering system follows a Retrieval-Augmented Generation
workflow:

``` text
User Question
      │
      ▼
Query Processing
      │
      ▼
Vector Similarity Search
      │
      ▼
Relevant Transcript Chunks
      │
      ▼
Context + Question
      │
      ▼
LLM / Answer Generation
      │
      ▼
Final Answer
```

This allows the assistant to answer questions using information
retrieved from the **analyzed video transcript**, rather than relying
only on general model knowledge.

------------------------------------------------------------------------

## 🛠️ Tech Stack

### Frontend / UI

-   **Streamlit**

### AI / Machine Learning

-   **OpenAI Whisper** --- speech-to-text transcription
-   **PyTorch** --- deep learning backend
-   **RAG** --- retrieval-based question answering

### LLM / NLP

-   **LangChain**
-   Embeddings
-   Vector similarity search

### Video / Audio Processing

-   **yt-dlp** --- YouTube media extraction
-   Audio chunking and preprocessing

### Development

-   Python
-   VS Code
-   Git & GitHub
-   Virtual environment

------------------------------------------------------------------------

## 📂 Project Structure

``` text
ai-video-assistant/
│
├── app.py                    # Streamlit application
│
├── core/
│   ├── rag_engine.py         # RAG pipeline and Q&A
│   ├── vector_store.py       # Vector store creation/retrieval
│   └── ...                   # Core processing modules
│
├── models/
│   └── ...                   # Model-related files/configuration
│
├── downloads/
│   └── ...                   # Temporary downloaded media
│
├── .env                     # Environment variables (do not commit)
├── .gitignore
├── requirements.txt
└── README.md
```

> **Note:** Keep downloaded media, model files, API keys, caches, and
> other generated files out of Git unless they are intentionally part of
> the project.

------------------------------------------------------------------------

## 🚀 Getting Started

### 1. Clone the repository

``` bash
git clone https://github.com/YOUR_USERNAME/ai-video-assistant.git
cd ai-video-assistant
```

### 2. Create a virtual environment

#### Windows

``` bash
python -m venv venv
```

Activate it in Git Bash:

``` bash
source venv/Scripts/activate
```

Or in PowerShell:

``` powershell
.\venv\Scripts\Activate.ps1
```

### 3. Install dependencies

``` bash
pip install -r requirements.txt
```

If `torchvision` is required by your installed Transformers/vision
stack:

``` bash
pip install torch torchvision
```

### 4. Configure environment variables

Create a `.env` file in the project root and add the API keys required
by your configured LLM/embedding provider.

Example:

``` env
OPENAI_API_KEY=your_api_key_here
```

> Never commit `.env` or expose API keys publicly.

### 5. Run the application

``` bash
streamlit run app.py
```

The application will normally open at:

``` text
http://localhost:8501
```

------------------------------------------------------------------------

## 🎯 How to Use

### Step 1 --- Provide Input

Enter either:

-   A YouTube video URL
-   A supported local video/audio file path

### Step 2 --- Select Language

Choose the language spoken in the video.

### Step 3 --- Analyse

Click **Analyse**.

The application processes the video through:

``` text
Audio Processing
      ↓
Transcription
      ↓
Title Generation
      ↓
Summarization
      ↓
Vector Store / Retrieval
      ↓
Question Answering
```

### Step 4 --- Explore

After processing, you can:

-   Read the generated summary
-   Expand the full transcript
-   Ask questions about the video
-   Retrieve information from specific parts of the content

------------------------------------------------------------------------

## 💡 Example Questions

After analyzing a video, try questions such as:

``` text
What are the main topics discussed?

What are the key takeaways?

What action items were mentioned?

Explain the most important concept discussed in the video.

What examples were given?

Summarize the speaker's main argument.

What recommendations were provided?
```

------------------------------------------------------------------------

## ⚡ Performance Notes

Whisper transcription can be computationally intensive, especially on a
CPU.

If you see a message such as:

``` text
FP16 is not supported on CPU; using FP32 instead
```

this is a **warning, not necessarily an error**. Whisper automatically
falls back to FP32 when running on CPU.

Processing time depends on:

-   Video duration
-   Whisper model size
-   CPU/GPU availability
-   Audio quality
-   Number of chunks
-   LLM/API response time

For local CPU execution, longer videos can take several minutes.

------------------------------------------------------------------------

## 🧩 Troubleshooting

### `streamlit: command not found`

Make sure the virtual environment is activated:

``` bash
source venv/Scripts/activate
```

Then install Streamlit:

``` bash
pip install streamlit
```

Run:

``` bash
streamlit run app.py
```

------------------------------------------------------------------------

### `ModuleNotFoundError: No module named 'torchvision'`

Install it inside the active virtual environment:

``` bash
pip install torchvision
```

Verify:

``` bash
python -c "import torch, torchvision; print(torch.__version__); print(torchvision.__version__)"
```

------------------------------------------------------------------------

### YouTube JavaScript runtime warning

`yt-dlp` may warn that a JavaScript runtime is unavailable.

If audio extraction still succeeds, the application can continue
processing. For improved YouTube compatibility, install a supported
JavaScript runtime such as **Deno** and restart the terminal so its PATH
is refreshed.

------------------------------------------------------------------------

### Whisper appears stuck

Check the terminal for progress such as:

``` text
Transcribing chunk 1/2...
Loading Whisper model...
Whisper model loaded.
```

CPU transcription can take time. Avoid stopping the Streamlit process
while Whisper is actively processing.

------------------------------------------------------------------------

## 🔐 Security

Do not commit sensitive information.

Make sure your `.gitignore` includes entries such as:

``` gitignore
.env
venv/
__pycache__/
*.pyc
downloads/
*.mp3
*.mp4
*.wav
.streamlit/secrets.toml
```

------------------------------------------------------------------------

## 🌱 Future Improvements

-   [ ] Support more video platforms
-   [ ] GPU acceleration
-   [ ] Timestamp-based transcript navigation
-   [ ] Better citation/source tracking for answers
-   [ ] Multi-language summarization
-   [ ] Conversation memory
-   [ ] Export transcript and summaries
-   [ ] Persistent vector database
-   [ ] Authentication and user sessions
-   [ ] Cloud deployment
-   [ ] Improved YouTube extraction reliability

------------------------------------------------------------------------

## 📊 Project Pipeline

``` text
Input
  │
  ├── YouTube URL
  └── Local File
       │
       ▼
Audio Extraction
       │
       ▼
Audio Chunking
       │
       ▼
Whisper
       │
       ▼
Transcript
       │
       ├──────────────► Summarization
       │
       ▼
Text Chunking
       │
       ▼
Embeddings
       │
       ▼
Vector Store
       │
       ▼
Retriever
       │
       ▼
Question + Context
       │
       ▼
AI Answer
```

------------------------------------------------------------------------

## 🎓 Why This Project?

Long-form videos contain valuable information, but manually searching
through hours of content is inefficient.

This project demonstrates how multiple AI components can be combined
into a practical application:

**Speech Recognition → NLP → Embeddings → Vector Search → RAG →
Generative AI**

It is designed as a practical demonstration of building an end-to-end AI
application rather than using a single AI model in isolation.

------------------------------------------------------------------------


::: {align="center"}
### ⭐ If you find this project useful, consider giving it a star!

**Built with Python, Whisper, RAG & Streamlit ❤️**
:::
