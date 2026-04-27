# NxtMock-Mock_Interview_Platform
Project Introduction:

a full-stack AI-powered mock interview platform that simulates realistic technical interviews. 
The platform generates personalized questions from your resume, conducts voice-based interviews with an AI interviewer named Natalie,
supports live coding challenges, and delivers detailed performance feedback.

What Are We Solving?

An AI interviewer available 24/7 that:
- Asks relevant, role-specific questions
- Listens to your verbal answers
- Evaluates your code submissions
- Gives instant, detailed feedback


Architecture Overview:

┌─────────────────────────────────────────────────────────┐
│                    React Frontend                        │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌─────────┐ │
│  │  Setup   │→ │Interview │→ │ Feedback │  │ History │ │
│  │  Page    │  │  Page    │  │  Page    │  │  Page   │ │
│  └──────────┘  └──────────┘  └──────────┘  └─────────┘ │
│       ↓              ↓             ↓            ↓       │
│  ┌──────────────────────────────────────────────────┐   │
│  │            Axios API Service Layer               │   │
│  └──────────────────────────────────────────────────┘   │
└─────────────────────────┬───────────────────────────────┘
                          │ HTTP REST API
┌─────────────────────────┴───────────────────────────────┐
│                   Express Backend                        │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌─────────┐ │
│  │  Routes  │→ │Controllers│→│ Services │→ │ Models  │ │
│  └──────────┘  └──────────┘  └──────────┘  └─────────┘ │
│                      ↓                                   │
│  ┌──────────────────────────────────────────────────┐   │
│  │         External AI Services                      │   │
│  │  ┌─────────┐  ┌──────────┐  ┌───────────────┐   │   │
│  │  │ Gemini  │  │ Murf AI  │  │  AssemblyAI   │   │   │
│  │  │  (LLM)  │  │  (TTS)   │  │   (STT)       │   │   │
│  │  └─────────┘  └──────────┘  └───────────────┘   │   │
│  └──────────────────────────────────────────────────┘   │
│                      ↓                                   │
│  ┌──────────────────────────────────────────────────┐   │
│  │              MongoDB Atlas                        │   │
│  │  ┌──────┐  ┌───────────┐  ┌──────────┐          │   │
│  │  │Users │  │Interviews │  │ Resumes  │          │   │
│  │  └──────┘  └───────────┘  └──────────┘          │   │
│  └──────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────┘
