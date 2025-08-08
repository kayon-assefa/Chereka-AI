# 🌟 Chereka AI – Ethiopia’s Culturally Intelligent AI Assistant

## 📌 Overview
**Chereka AI** is an Ethiopia-based conversational AI platform designed to reflect and preserve Ethiopian culture while offering intelligent, real-time, multilingual assistance.  
It is built with **React (frontend)**, **Firebase/Supabase (authentication & database)**, and **free/low-cost AI APIs** for text, translation, and voice processing.

Unlike generic AI assistants, Chereka understands **Amharic** 🇪🇹 and **Afaan Oromo** fluently, responds with Ethiopian cultural references, and can even share daily proverbs with explanations.  
It’s *like ChatGPT but with an Ethiopian soul* ❤️.

---

## 🎯 Problem Statement
While global AI assistants like ChatGPT or Google Bard are powerful, they lack:
- Deep integration with **Ethiopian culture** and local context.
- True **multilingual** conversation in **Amharic & Afaan Oromo**.
- **Daily cultural education** (proverbs, history, and traditions).
- **Offline & free**-friendly options for emerging markets.

**Chereka AI solves this by:**
1. Offering **Smart Language Switching** – English default, automatic Amharic/Afaan Oromo responses when requested or detected.
2. Incorporating **Ethiopian Cultural Intelligence** – knowledge of traditions, history, proverbs, and local news.
3. Supporting **voice interaction** with local language TTS/STT.
4. Being **API-flexible** to allow scaling from free APIs to premium ones.

---

## ✨ Core Features

### 🗣 Smart Language Switching
- Default language: **English**
- Auto-switch when Amharic or Afaan Oromo is detected.
- Supports **mixed-language conversations**.

### 🎭 Ethiopian Cultural Intelligence
- Answers with Ethiopian context.
- Daily proverb when a user says "Hi" – also asks user to guess the meaning.
- Explains the proverb and relates it to the topic being discussed.
- Can share Ethiopian history facts and traditional knowledge.

### 📚 Learning Mode
- Learns new words and phrases in Amharic/Afaan Oromo daily from conversations.
- Improves with repeated use.

### 📍 Local Context Awareness
- News (Ethiopian sources via NewsAPI)
- Weather updates (Visual Crossing Weather API)
- Local time & holidays
- Cultural event reminders

### 🎤 Voice Mode
- **Voice-to-Text (STT)** for speaking to the AI.
- **Text-to-Speech (TTS)** for listening to AI responses.
- Multiple free/paid TTS options.

### 🔄 Translation
- **LibreTranslate API** for free translation.
- Falls back to Google Cloud Translation API for advanced translations.
- Context-aware translations (avoiding literal errors).

### 📅 Proactive Notifications
- Reminds users of Ethiopian holidays/events.
- Weather alerts.
- Daily cultural fact push.

### 📝 Task Management
- Reminders
- To-do lists
- Event scheduling

### ⚡ Rich Chat Experience
- Quick reply buttons
- Rich media (images, videos, files)
- Sentiment analysis for empathetic responses
- Memory of past conversations for context

---

## 🛠 Tech Stack

### **Frontend**
- React + Vite
- Tailwind CSS
- Ethiopian cultural UI with **dark green/white themes** and Habesha patterns
- Chat interface similar to ChatGPT (central conversation bubble, voice input in typing bar)

### **Backend**
- **FastAPI** or **Node.js/Express**
- API orchestration to connect:
  - Chat APIs (text generation)
  - Translation APIs
  - TTS/STT APIs
  - News, Weather, Music APIs
- Handles context storage (Firebase Firestore or Supabase)

### **Database & Auth**
- Firebase Authentication
- Firebase Realtime Database or Firestore
- Supabase as an alternative to avoid Firebase Storage costs

---

## 🌐 APIs Used

### **Chat APIs**
- [OpenAI GPT API](https://platform.openai.com/) (Paid – fallback to free models)
- [Hugging Face Inference API](https://huggingface.co/inference-api) (Free)
- [Cohere API](https://cohere.com/)
- [AI21 Studio API](https://www.ai21.com/studio)
- [Google Dialogflow](https://cloud.google.com/dialogflow)

### **Translation APIs**
- [LibreTranslate API](https://libretranslate.com/) (Free)
- [Google Cloud Translation API](https://cloud.google.com/translate)
- [Microsoft Translator Text API](https://azure.microsoft.com/en-us/products/cognitive-services/translator/)
- [Hugging Face Translation Models](https://huggingface.co/models)

### **Voice APIs**
- [ResponsiveVoice API](https://responsivevoice.org/api/)
- [Google Cloud TTS API](https://cloud.google.com/text-to-speech)
- [Mozilla TTS (Self-hosted)](https://github.com/mozilla/TTS)
- [LibreTTS (Self-hosted)](https://github.com/fttx/libretts)
- [Voxygen TTS API](https://www.voxygen.fr/)

### **Other APIs**
- [NewsAPI](https://newsapi.org/) – Ethiopian & global news
- [Visual Crossing Weather API](https://www.visualcrossing.com/weather-api) – Weather data
- [Musixmatch API](https://developer.musixmatch.com/) – Music search

---

## 🔄 Backend Flow (MVP)
1. **User sends a message** (text or voice).
2. If **voice**, STT API converts to text.
3. Detect language → Switch to Amharic/Afaan Oromo/English if needed.
4. Message sent to chosen **Chat API** (Hugging Face GPT-2/3 for free tier, OpenAI GPT for premium).
5. If translation is needed, call LibreTranslate/Google Translate.
6. AI response generated and stored in Firebase/Supabase (for context).
7. If **voice mode is enabled**, send response to TTS API and return audio.
8. UI displays chat bubbles, quick replies, and rich media.

---

## 🎨 UI/UX Highlights
- **Dark Green Theme** + **White-Green Theme**
- **Habesha patterns** for borders & dividers
- ChatGPT-style central chat bubble with "circle thing" animation
- Voice input button inside typing bar
- Ethiopian font styling for Amharic text

---

## 📈 Analytics & Feedback
- Track usage statistics in Firebase Analytics
- Sentiment analysis to improve empathy
- User feedback collection for feature updates

---

## 🧠 Unique Features Other AIs Don’t Have
- Daily Ethiopian proverb & meaning quiz
- Contextual Amharic & Afaan Oromo conversation
- Cultural event reminders
- Offline/self-hosted TTS & translation options for free use
- Learning mode to improve over time

---

## 🚀 Versioning
- **v1.0.0 (MVP)** – Core chat, translation, voice, and cultural features.
- **v1.1.0** – Add task management & proactive notifications.
- **v1.2.0** – Sentiment analysis, richer media, improved learning mode.
- **v2.0.0** – Full offline/self-hosted support for rural areas.

---

## 📌 Future Improvements
- Offline Ethiopian cultural database
- Multi-user group conversations
- Integration with payment APIs for premium features
- AI-generated Amharic/Afaan Oromo voice cloning

---

## 📜 License
MIT License – Free to use, modify, and distribute with attribution.

---
