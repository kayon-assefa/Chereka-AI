
# Chereka AI

---

## 📜 Project Overview & Vision

Chereka AI is an Ethiopia-based AI web application designed to bridge the language and cultural gap in modern AI tools. Unlike most AI platforms that primarily serve English-speaking users, Chereka integrates **Amharic**, **Afaan Oromo**, and **English** into a unified intelligent assistant capable of natural conversation, voice interaction, and localized services.

**Launch Goal:** 2026  
**Current Version:** AP1  
**Core Objective:** Provide an accessible, culturally relevant AI experience for Ethiopia while maintaining global usability standards.

### Vision

By 2026, Chereka aims to:  
- Be the **primary AI assistant** for Ethiopians across sectors such as education, business, government, and personal productivity.  
- Offer **accurate, natural, and context-aware** communication in Amharic and Afaan Oromo.  
- Integrate **Ethiopian-specific knowledge** including local news, culture, and educational curriculum.  
- Support **offline-capable features** to serve areas with limited internet connectivity.  
- Become a platform that **learns and evolves daily** to reflect Ethiopia’s dynamic culture and needs.

---

## 🏗 System Architecture (Frontend + Backend + APIs + Database)

### Frontend
- **Framework:** React (with Vite) for fast, modular development.  
- **UI Styling:** TailwindCSS combined with custom Ethiopian cultural themes.  
- **State Management:** Redux Toolkit or Zustand for predictable and scalable state.  
- **Voice Features:** Uses Web Speech API for speech recognition and client-side streaming for low-latency voice interaction.

### Backend
- **Framework:** Node.js with Express.js for REST API development.  
- **Hosting:** Serverless platforms such as Vercel or Firebase Cloud Functions.  
- **Security:** HTTPS with JWT-based authentication, rate limiting, and input validation.  
- **AI Processing:** Backend proxies requests to AI providers like OpenAI GPT or Hugging Face, with caching layers to reduce API costs and improve latency.

### APIs
- **Chat AI:** OpenAI GPT API or Hugging Face transformer models for conversational AI.  
- **Text-to-Speech (TTS):** ResponsiveVoice API, Mozilla TTS, or LibreTTS for natural voice output.  
- **Translation:** LibreTranslate API or Google Cloud Translation for multilingual support.  
- **News:** NewsAPI to aggregate Ethiopian and global news sources.  
- **Weather:** OpenWeatherMap or Visual Crossing Weather API for location-based weather info.  
- **Music:** Musixmatch API for music search and metadata.

### Database
- **Authentication & Profiles:** Firebase Authentication.  
- **Chat History & Preferences:** Supabase or Firestore for persistent storage.  
- **Memory Storage:** Optimized structures to maintain conversational context across sessions.

---

## 🗂 Feature-by-Feature Technical Explanation

### 1. Chat
- Users can interact via text or voice inputs.  
- Inputs are sent to the backend API, which communicates with the AI model.  
- Responses are optionally translated based on detected user language.  
- Conversations are saved to user history for continuity and learning.

### 2. Voice Mode
- Captures user speech with Web Speech API and converts it to text.  
- Text is processed by AI and converted back to speech using TTS APIs.  
- Language detection ensures correct voice profiles and dialects are used.

### 3. Translation
- Automatically detects input language among Amharic, Afaan Oromo, and English.  
- Uses translation APIs for real-time language switching and multi-language support.  
- Ensures AI responses are delivered in the user’s preferred language seamlessly.

### 4. News
- Fetches current Ethiopian and international news headlines through NewsAPI.  
- AI summarizes or contextualizes news articles to make them easier to understand.  
- Provides localized cultural insights related to the news.

---

## 🧠 AI & NLP Implementation Details

### Model Choices
- Primary AI models include OpenAI’s GPT-4.1 or GPT-3.5 for high-quality reasoning and generation.  
- Backup models use Hugging Face’s open-source transformer models (e.g., BLOOM, LLaMA 2) for offline or cost-effective scenarios.

### Prompt Engineering
- Customized system prompts guide the AI’s tone, politeness, and bilingual capabilities.  
- Contextual prompts enable memory of past interactions to maintain coherent conversations.

### Safety Layers
- Offensive language filters prevent inappropriate content.  
- Topic restrictions block sensitive or harmful subjects.

### Caching
- Frequently asked questions and common queries are cached for instant responses.  
- Caches stored in Redis or Firestore to balance performance and cost.

---


## 🗣 Voice Mode & Language Handling (Amharic, Afaan Oromo, English)

### Input Flow
1. User speech is captured via the **Web Speech API** for real-time voice recognition.  
2. Speech is transcribed into text in the client app.  
3. Language detection algorithms analyze the transcription to determine whether the input is in Amharic, Afaan Oromo, or English.  
4. The transcribed and detected language text is sent to the backend AI for processing.

### Output Flow
1. The AI generates a response in text form, respecting the detected or user-selected language.  
2. If voice mode is enabled, the text response is sent through a **Text-to-Speech (TTS)** API to produce natural audio output.  
3. The audio is streamed back to the user and played in the client app.  
4. If voice mode is disabled, the text response is displayed as usual.

### Language Handling Rules
- Conversations maintain the same language once detected unless the user explicitly switches languages.  
- AI responses are automatically translated if the conversation language and the AI’s internal language differ.  
- Accents and dialects specific to Amharic and Afaan Oromo are supported via customized voice models.  
- Language fallback ensures fallback to English if the system cannot confidently interpret the input language.

---

## 🌐 API Integration Guides

## 🌐 API Integration Guides — Providers & Importance

- **Chat AI API**  
  Provider: OpenAI (GPT-4.1 / GPT-3.5) or HuggingFace Models  
  Importance: Core natural language understanding and response generation, enabling intelligent, context-aware conversations in multiple languages.

- **Text-to-Speech (TTS) API**  
  Provider: FreeTTS, Coqui, or Google Text-to-Speech  
  Importance: Converts AI text responses into natural spoken language, essential for voice mode and accessibility.

- **Translation API**  
  Provider: LibreTranslate (self-hosted/free) or Google Translate API  
  Importance: Enables dynamic language translation between Amharic, Afaan Oromo, and English, ensuring smooth multilingual interaction.

- **News API**  
  Provider: NewsAPI or custom Ethiopian news scrapers  
  Importance: Supplies localized and global news updates, keeping users informed about relevant topics.

- **Weather API**  
  Provider: OpenWeatherMap  
  Importance: Provides real-time weather data tailored to user locations, enhancing contextual AI responses.

- **Music API**  
  Provider: Spotify Web API or YouTube Music scraping (legal compliance required)  
  Importance: Integrates music search and playback features, allowing personalized entertainment suggestions.

---

🔒 Authentication & Security
Uses Firebase Authentication to manage user sign-up, sign-in, and secure session management.

Supports email/password login as well as social login providers (Google, Facebook).

All API requests require JWT tokens for authentication to protect user data and API integrity.

Backend enforces rate limiting and input validation to prevent abuse and injection attacks.

HTTPS is enforced across all endpoints for secure data transmission.

User data encryption at rest and in transit complies with best security practices.

📦 Database Structure (Firebase & Supabase)
Firebase Authentication
Stores user identity, credentials, and login sessions.

Handles email verification and password resets securely.

Supabase (PostgreSQL)
Users Table: Stores user profile information, preferences, and language settings.

Chats Table: Records conversation histories with timestamp, language, and AI response metadata.

Notifications Table: Tracks user reminders and notifications settings.

Music Preferences: User favorite tracks, playlists, and interaction history.

News Preferences: User-selected news categories and saved articles.

Firestore (Optional for real-time)
Stores ephemeral session data for instant UI updates.

Supports offline persistence for chat messages and notifications.

⚡ Real-time Features (Notifications, Reminders, Memory)
Push notifications for new messages, reminders, and system updates using Firebase Cloud Messaging.

Real-time chat updates using Firestore listeners or Supabase real-time subscriptions.

Memory system retains conversational context across sessions, enabling personalized responses.

User-configurable reminders and to-do lists synced across devices.

Notifications include proactive alerts about news, weather, and cultural events.

🎨 UI/UX Design Guidelines
Use Ethiopian cultural colors and motifs to create a familiar and inviting interface.

Ensure accessibility for all users, including those with disabilities (WCAG 2.1 compliance).

Responsive design for mobile, tablet, and desktop screens.

Smooth transitions and feedback animations for voice interactions and AI responses.

Minimalist and intuitive navigation with clear language switching options.

Dark mode support to reduce eye strain.

🚀 Deployment Instructions (Vercel, Netlify, Firebase Hosting)
Frontend React app is built using npm run build and deployed to Vercel or Netlify for global CDN delivery.

Backend API deployed as serverless functions on Vercel or Firebase Cloud Functions.

Firebase Authentication and Firestore configured via Firebase Console with proper security rules.

Environment variables managed securely through deployment platform settings (API keys, secrets).

CI/CD pipelines set up using GitHub Actions for automated testing and deployment.

📈 Analytics & Feedback Collection
Integration with Google Analytics or Matomo for user behavior tracking.

Custom telemetry to log feature usage and error reports.

In-app feedback forms to collect user suggestions and bug reports.

Usage data analyzed to guide future feature development and optimizations.

🔮 Future Improvements
Expand AI capabilities to support more Ethiopian languages and dialects.

Add offline-first features with local model inference for low connectivity areas.

Implement more advanced sentiment analysis and emotion recognition.

Integrate with Ethiopian government services for digital ID verification.

Introduce voice biometric authentication for security.

Expand music and news partnerships with local Ethiopian content providers.
---
## 🔒 Authentication & Security

- **Authentication Provider:** Firebase Authentication  
- **Purpose:** Securely manages user sign-up, sign-in, and identity verification with email/password, social logins, and multi-factor authentication options.  
- **Security Measures:**  
  - HTTPS for encrypted communication  
  - JWT tokens for session management  
  - Rate limiting to prevent abuse  
  - Data validation and sanitization to avoid injection attacks  

---

## 📦 Database Structure (Firebase & Supabase)

- **Firebase Authentication:** User identity and access management.  
- **Firestore / Realtime Database:** Stores user profiles, chat history, preferences, and AI conversation context for memory retention.  
- **Supabase:** Alternative to Firebase for relational data, used to manage more complex queries, analytics, and backup.  
- **Data Privacy:** User data is encrypted at rest and in transit, with access restricted based on roles.  

---

## ⚡ Real-time Features (Notifications, Reminders, Memory)

- **Notifications:** Real-time alerts sent to users for reminders, chat replies, or system updates using Firebase Cloud Messaging.  
- **Reminders & To-Do Lists:** User task management integrated within the AI, allowing natural language commands to set or modify reminders.  
- **Memory / Context Awareness:**  
  - Maintains session context for multi-turn conversations.  
  - Stores relevant user preferences and past queries for personalized interactions.  
  - Uses caching and database storage to improve responsiveness and learning over time.  

---

## 🎨 UI/UX Design Guidelines

- **Design Philosophy:** Minimalist and culturally relevant UI inspired by Ethiopian art and color schemes.  
- **Accessibility:** Support for multiple languages and voice interaction to cater to users with diverse needs.  
- **Responsiveness:** Mobile-first design ensuring smooth performance on smartphones and desktops.  
- **Interactive Elements:** Quick reply buttons, rich media support (images, videos, files), and easy navigation to improve user engagement.  

---

## 🚀 Deployment Instructions (Vercel, Netlify, Firebase Hosting)

- **Frontend Deployment:** Use Vercel or Netlify for seamless React app deployment with automatic CI/CD integration.  
- **Backend Deployment:** Host Node.js backend on Vercel serverless functions or Firebase Functions for scalability.  
- **Database Hosting:** Firebase provides managed backend services with real-time syncing; Supabase can be self-hosted or cloud-hosted for flexibility.  
- **Environment Variables:** Secure API keys and secrets using environment variables on deployment platforms.  
- **Monitoring:** Set up performance and error monitoring (e.g., Sentry, Firebase Crashlytics).  
---
## 📈 Analytics & Feedback Collection

- **Tools Used:** Google Analytics, Firebase Analytics, or Matomo for user interaction tracking.  
- **Purpose:** To monitor user engagement, feature usage, and identify bottlenecks or issues.  
- **Feedback Loop:**  
  - In-app feedback forms for users to report bugs or suggest features.  
  - Usage data helps prioritize improvements and optimize AI responses.  
- **Privacy:** Analytics configured to respect user privacy and comply with local regulations.

---

## 🔮 Future Improvements

- **Multilingual Expansion:** Add support for more Ethiopian languages and dialects.  
- **Offline Mode:** Implement offline-capable AI features for low-connectivity regions.  
- **Enhanced Memory:** More sophisticated context retention with personalized AI models.  
- **Custom AI Models:** Train Ethiopia-specific datasets for better cultural and domain accuracy.  
- **Integration with National Services:** Connect with government APIs for official data and services.  
- **User Community Features:** Forums, chat rooms, and social sharing for collaborative learning.  
- **Advanced Security:** Implement end-to-end encryption and stronger authentication options.

---

## 🤝 Contributing

We welcome contributions from the community!  
- **How to Contribute:**  
 - You can invest on chereka starting form 5,000 ETB - 100,000 ETB.
 - To invest you can contact [Chereka co](https://t.me/chereka_co_bot)
- **Bug Reports & Feature Requests:** Use GitHub Issues to report bugs or request new features.  

---

## 📞 Contact Information

- **Email:** contact@chereka.et  
- **Website:** [Website](https://chereka.et)  
- **GitHub:** [Github](https://github.com/ckayon-assefa)  
- **Twitter:** [twitter](https://twitter.com/kayonassefaduki)  
- **LinkedIn:** [linkedin](https://linkedin.com/in/kayonassefa)

---

## 📄 License

This project is licensed under the **Kayon Tech** — see the [LICENSE](LICENSE) file for details.
