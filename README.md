# Chereka AI 🌍🇪🇹  
**Version:** 1.0.0 (MVP)  
**Release Date:** [Insert Date]  

Chereka AI is an **Ethiopia-based conversational AI web application** built to reflect Ethiopian culture while maintaining the power of modern AI.  
It speaks **English**, **Amharic**, and **Afaan Oromo** fluently, switches languages based on user input, and includes a **voice mode** for both speaking and listening — just like ChatGPT, but with **local context awareness**.

---

## 🎯 Vision
Chereka aims to be the **first culturally intelligent AI assistant for Ethiopia**.  
While global AI models excel in English, they lack deep understanding of Ethiopian languages, traditions, and cultural context.  
Chereka bridges that gap by:
- Speaking Ethiopian languages fluently (starting with Amharic and Afaan Oromo).
- Understanding Ethiopian cultural context in conversations.
- Providing daily proverbs, cultural tips, and stories.
- Supporting local use cases while using free APIs to keep it accessible.

---

## 🛠 Problems Chereka Solves
1. **Language Barriers:**  
   Most AI assistants fail to understand or respond fluently in Ethiopian languages.
2. **Cultural Disconnect:**  
   Global AI lacks awareness of Ethiopian traditions, history, and values.
3. **Voice Accessibility:**  
   Many Ethiopians prefer voice interaction over typing due to ease and literacy differences.
4. **Cost Barriers:**  
   Chereka uses **free or low-cost APIs** to remain accessible to all.

---

## ✨ Core Features

### 1. Smart Language Switching
- Detects language from user input.  
- Default language: **English**.  
- If user speaks in Amharic or Afaan Oromo, AI automatically responds in that language.

### 2. Ethiopian Cultural Intelligence
- Includes **Habesha patterns** and Ethiopian color themes.  
- Understands cultural references, holidays, and traditions.  
- Adds cultural context to answers when relevant.

### 3. ChatGPT-Style Interface
- Circular typing indicator in the center (like ChatGPT).  
- Smooth typing animations.  
- Voice icon inside the input bar for voice mode.

### 4. Learning Mode
- Tracks new Amharic/Afaan Oromo phrases and improves responses over time.  
- Uses backend logging for unknown phrases to improve the AI.

### 5. Local Context Awareness
- Recognizes Ethiopian places, events, and current affairs.
- Can recommend locally relevant solutions.

### 6. Daily Cultural Fact & Proverb
- When the user says "Hi", Chereka:
  1. Shares a daily cultural tip or proverb.
  2. Asks if the user wants to know the meaning.
  3. Explains how it relates to the current conversation topic.

### 7. Translation Mode
- Can translate between English, Amharic, and Afaan Oromo instantly.

### 8. Voice Mode
- **Speech Recognition:** Uses the browser’s Web Speech API for real-time voice input.  
- **Text-to-Speech:** Reads responses aloud in the chosen language.  

---

## 🖌 UI/UX Design

- **Theme 1:** Dark green + gold Habesha patterns.  
- **Theme 2:** White + green accent.  
- Minimalist, modern, Ethiopian-inspired design.  
- Responsive layout for mobile and desktop.  
- Chat history scrollable like ChatGPT.  

---

## ⚙ Tech Stack

**Frontend:**  
- React (Vite)  
- TailwindCSS (styling)  
- Web Speech API (voice mode)  

**Backend:**  
- Node.js + Express (optional for API handling)  
- Hugging Face Inference API / OpenAI API (for AI responses)  
- Google Translate API (for language translation — free tier)  

**Database:**  
- Firebase (Authentication + Firestore for chat history, no storage)  

---

## 🔌 API Integration

1. **AI Model:**  
   - **Option 1:** Hugging Face Inference API (free for small requests).  
   - **Option 2:** OpenAI API (if budget allows for better accuracy).  
   - Route: `POST /api/chat` → sends prompt to AI → receives structured JSON.

2. **Language Detection:**  
   - Google Translate API or `franc-min` (free JS library for language detection).

3. **Voice Mode:**  
   - Web Speech API for browser-based speech-to-text and text-to-speech.

---

## 🏗 Backend Flow

1. **User sends message** →  
2. **Language detection** → if not English, auto-translate to English for AI processing →  
3. **AI generates response** →  
4. **If needed, translate back to user’s language** →  
5. **Send response to frontend** →  
6. **If voice mode enabled**, speak out the response.

---

## 🚀 MVP Version 1.0.0 Scope

- **Working chat interface** with AI API integration.  
- **Language detection** and translation for Amharic & Afaan Oromo.  
- **Voice input/output** with browser Web Speech API.  
- **Cultural tip & proverb system** triggered by "Hi".  
- **UI** with Ethiopian cultural themes.  

---

## 📅 Future Updates
- **Offline mode** for low-internet areas.  
- **Image recognition** for Ethiopian objects/places.  
- **Expanded language support** (Tigrinya, Somali).  
- **User profiles** with personalized cultural tips.

---

## 👨‍💻 Contributing
Developers should follow this structure:
- `/src/components` → UI components (ChatBox, VoiceButton, MessageList)  
- `/src/api` → API handling functions  
- `/src/utils` → Language detection, proverb list  
- `/public` → Assets (patterns, icons, logos)

---

## 📜 License
MIT License – Free to use with attribution.
