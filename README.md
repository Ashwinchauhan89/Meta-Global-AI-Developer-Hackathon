# MeetingMind AI

### Intelligent Meeting Assistant | Meta Global AI Developer Hackathon 2026

**Transform lengthy meetings into actionable intelligence.**

MeetingMind AI is an intelligent, AI-powered meeting assistant designed to transform unstructured meeting recordings and transcripts into meaningful summaries, documented decisions, assigned action items, and interactive question-answering experiences.

Built for the **Meta Global AI Developer Hackathon 2026**, the project explores how advanced AI models can simplify meeting workflows, improve accountability, and make important information accessible and verifiable.

The core philosophy behind MeetingMind AI is simple:

> Don't just summarize meetings. Understand them, extract what matters, and make every important insight verifiable.

---

## Project Overview

Meetings often contain valuable information hidden inside lengthy discussions, scattered conversations, and unstructured notes.

MeetingMind AI addresses this problem by combining speech recognition, large language models, and evidence-based information retrieval to turn meeting conversations into structured knowledge.

Users can upload meeting recordings or transcripts and receive:

- **Smart Summaries:** Concise summaries highlighting important discussions and key takeaways.
- **Action Items:** Automatically identified tasks, responsible individuals, and deadlines.
- **Decision Tracking:** Documented decisions with their supporting rationale.
- **Evidence-Based Q&A:** Ask questions about meetings and receive contextual answers linked to original transcript segments and timestamps.

## Key Features

### 1.  Smart Meeting Summaries
- Generate concise and context-aware meeting summaries.
- Extract key discussion points.
- Highlight important topics and outcomes.
- Reduce the time required to review lengthy meetings.

### 2.  Automated Action Item Extraction
- Identify tasks discussed during meetings.
- Extract assigned individuals and responsibilities.
- Detect mentioned deadlines.
- Organize tasks into structured records.

### 3.  Decision Tracking
- Automatically identify important decisions.
- Capture the rationale behind decisions.
- Maintain a structured record of meeting outcomes.
- Distinguish confirmed decisions from suggestions.

### 4.  Evidence-Based Meeting Q&A
- Ask natural-language questions about meeting discussions.
- Retrieve relevant transcript segments.
- Generate context-aware answers.
- Provide source references and timestamps for verification.

### 5.  Audio Transcription
- Upload meeting recordings.
- Convert audio into text using Whisper.cpp.
- Preprocess audio using FFmpeg.
- Generate downloadable transcripts.

### 6. AI-Powered Intelligence
- Integrate Meta Model API for advanced language understanding.
- Generate structured meeting intelligence.
- Support contextual reasoning and information extraction.
- Minimize unsupported AI-generated claims through source validation.

---

##  Technology Stack

| Category | Technologies |
|---|---|
| Programming Language | Python |
| AI Models | Meta Muse Spark, Ollama |
| Speech Recognition | Whisper.cpp |
| Audio Processing | FFmpeg |
| Backend Framework | FastAPI (planned) |
| UI Framework | Gradio (current implementation) |
| API Integration | Meta Model API, OpenAI Python SDK |
| Data Processing | NumPy, Pandas |
| Database | PostgreSQL + pgvector (planned) |
| AI Retrieval | Retrieval-Augmented Generation (RAG) (planned) |
| Version Control | Git & GitHub |

##  System Architecture

The proposed MeetingMind AI architecture follows a modular processing pipeline.

```text
                  MEETING INPUT
                        |
             +----------+----------+
             |                     |
        Audio Upload          Transcript Upload
             |                     |
             v                     |
        FFmpeg Processing           |
             |                     |
             v                     |
        Whisper.cpp                 |
             |                     |
             +----------+----------+
                        |
                        v
                TRANSCRIPT ENGINE
                        |
                        v
                META AI INTELLIGENCE
                   Muse Spark
                        |
          +-------------+-------------+
          |             |             |
          v             v             v
       Summary      Decisions     Action Items
          |             |             |
          +-------------+-------------+
                        |
                        v
                EVIDENCE ENGINE
                 RAG + pgvector
                        |
                        v
                INTERACTIVE Q&A
                        |
                        v
                MEETING DASHBOARD
```

*Note: This represents the target architecture. Some components are planned enhancements and are not yet implemented in the current repository.*

---

##  Current Implementation

The initial application provides an audio transcription and summarization pipeline.

### Current Processing Workflow

1. Upload an audio recording through the Gradio interface.
2. Convert the recording into 16 kHz mono WAV format using FFmpeg.
3. Transcribe the recording using Whisper.cpp.
4. Send the generated transcript to a locally hosted Ollama model.
5. Generate an AI-powered meeting summary.
6. Download the transcript as a text file.

### AI Model Integration Roadmap

| Component | Implementation |
|---|---|
| Whisper.cpp | Existing transcription pipeline |
| FFmpeg | Existing audio preprocessing |
| Ollama | Existing summarization integration |
| Meta Model API | Planned AI integration |
| Muse Spark | Planned meeting intelligence |
| Evidence-based RAG | Planned retrieval system |
| pgvector | Planned vector storage |

---

##  Project Structure

```text
Meta-Global-AI-Developer-Hackathon/
│
├── main.py
│
├── requirements.txt
│
├── run_meeting_summarizer.sh
│
├── README.md
│
├── whisper.cpp/              # Generated during setup
│   ├── models/               # Downloaded Whisper models
│   └── main                  # Compiled executable
│
└── .venv/                    # Python virtual environment
```

##  Installation and Setup

### Prerequisites

Make sure you have installed:

- Python 3.9+
- Git
- FFmpeg
- Ollama
- C++ build tools for Whisper.cpp

### Step 1: Clone the Repository

```bash
git clone https://github.com/Ashwinchauhan89/Meta-Global-AI-Developer-Hackathon.git

cd Meta-Global-AI-Developer-Hackathon
```

### Step 2: Install Ollama

Download Ollama:

https://ollama.com/download

Download a language model:

```bash
ollama pull llama3.2
```

Start the Ollama server:

```bash
ollama serve
```

Keep the server running while using the application.

### Step 3: Configure the Setup Script

Open `run_meeting_summarizer.sh` and configure:

```bash
WHISPER_MODEL="small"
PYTHON_SCRIPT="main.py"
```

Available Whisper models include:

- base
- small
- medium
- large
- large-V3

### Step 4: Run the Automated Setup

Make the script executable:

```bash
chmod +x run_meeting_summarizer.sh
```

Execute:

```bash
./run_meeting_summarizer.sh
```

The setup script automatically:

1. Creates a Python virtual environment.
2. Installs required Python packages.
3. Checks for FFmpeg.
4. Clones Whisper.cpp.
5. Builds Whisper.cpp.
6. Downloads the selected Whisper model.
7. Launches the Gradio application.

### Step 5: Access the Application

Open the URL displayed in your terminal:

```text
http://127.0.0.1:7860
```

---

##  Meta Model API Integration

MeetingMind AI is designed to explore Meta's AI ecosystem through the Meta Model API.

### API Configuration

Create an account:

https://dev.meta.ai/

Configure your API credentials securely using environment variables.

```env
MODEL_API_KEY=your_meta_api_key
MODEL_API_BASE_URL=https://api.meta.ai/v1
```

Install the Python SDK:

```bash
pip install openai
```

### Initialize Meta API Client

```python
import os
from openai import OpenAI

client = OpenAI(
    api_key=os.getenv("MODEL_API_KEY"),
    base_url=os.getenv("MODEL_API_BASE_URL")
)
```

The Meta Model API integration is intended to power:

- Intelligent meeting summaries.
- Decision and action item extraction.
- Contextual meeting analysis.
- Evidence-based question answering.

**Important:** The API integration and supported model identifiers should be validated against the current Meta developer documentation before deployment.

---

##  Evidence-Based Intelligence

A major differentiator of MeetingMind AI is its focus on trust and traceability.

Traditional summarization systems often provide answers without showing where the information originated.

MeetingMind AI aims to address this through an evidence-based retrieval pipeline.

### Example

**Original Meeting Transcript**

```text
[00:02:15] Rahul:
We should launch the new website by Friday.

[00:02:23] Ashwin:
I will complete the frontend by Thursday.

[00:02:35] Rahul:
Approved. Ashwin owns the frontend delivery.
```

**User Question:**

Who is responsible for completing the frontend?

**MeetingMind AI Response:**

```text
Ashwin is responsible for completing
the frontend by Thursday.

Supporting Evidence:
Speaker: Rahul
Timestamp: 00:02:35

Source:
"Ashwin owns the frontend delivery."
```

This approach allows users to verify generated information against the original conversation.

### Evidence Validation Strategy

1. Preserve original transcript segments and timestamps.
2. Generate embeddings for transcript chunks.
3. Retrieve relevant segments using semantic search.
4. Generate answers using retrieved evidence.
5. Validate source references against stored transcript records.
6. Display answers with clickable timestamps.

If supporting evidence cannot be found, the system should explicitly communicate that the information is unavailable.

---

## Development Roadmap

| Phase | Development | Status |
|---|---|---|
| Phase 1 | Audio upload and preprocessing | Existing |
| Phase 2 | Whisper.cpp transcription | Existing |
| Phase 3 | Ollama summarization | Existing |
| Phase 4 | Meta Model API integration | Planned |
| Phase 5 | Structured meeting summaries | Planned |
| Phase 6 | Action item extraction | Planned |
| Phase 7 | Decision tracking | Planned |
| Phase 8 | Evidence-based RAG | Planned |
| Phase 9 | Interactive meeting Q&A | Planned |
| Phase 10 | Full-stack dashboard | Planned |

##  Privacy and Security

Meeting recordings and transcripts may contain confidential information.

MeetingMind AI aims to follow these security principles:

- Secure handling of uploaded recordings.
- Protection of API credentials through environment variables.
- Server-side API execution.
- Access control for meeting records.
- Validation of uploaded files.
- No exposure of confidential meeting content in public repositories.

Never commit API keys, credentials, private recordings, or sensitive transcripts to GitHub.

##  Future Enhancements

- Live meeting transcription.
- Zoom, Google Meet and Microsoft Teams integration through Recall.ai.
- Speaker diarization.
- Real-time meeting intelligence.
- Cross-meeting semantic search.
- Interactive transcript timeline.
- Automated task reminders.
- PDF and Markdown report exports.
- Multi-language meeting support.
- Next.js + FastAPI production dashboard.

## Hackathon

**Meta Global AI Developer Hackathon 2026**

Building with Meta's AI ecosystem to explore practical applications of intelligent systems.

The project aims to demonstrate how AI can transform unstructured conversations into structured, actionable, and verifiable knowledge.

##  Developer

**Ashwin Chauhan**

Computer Science & Engineering | Full-Stack Developer | AI/ML Enthusiast

- GitHub: [@Ashwinchauhan89](https://github.com/Ashwinchauhan89)
- Project: [MeetingMind AI](https://github.com/Ashwinchauhan89/Meta-Global-AI-Developer-Hackathon)

##  License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

**MeetingMind AI — From Conversations to Clarity.**

*Built with AI. Designed for Trust. Focused on Action.*