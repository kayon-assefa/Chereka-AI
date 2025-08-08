# 🌍 Chereka AI – Ethiopia’s Culturally Intelligent AI Chatbot

> **Version:** 1.0.0 MVP  
> **Release Date:** August 2025  
> **Developed by:** Kayon Tech  
> **Tagline:** *The AI that understands Ethiopia.*

---

## 📌 Project Overview

**Chereka AI** is an Ethiopia-based AI chatbot designed to combine the power of advanced AI language models with deep cultural intelligence of Ethiopia.  
It supports **English**, **Amharic**, and **Afaan Oromo** languages fluently and can switch between them dynamically based on user preference or input.  

This chatbot features a voice mode for real-time spoken conversation, daily Ethiopian proverbs and cultural facts, and smart local context awareness, providing users a truly unique and engaging experience.

---

## 🎯 Problem Statement

Many existing AI chatbots:  
- Fail to support **Ethiopian local languages** like Amharic and Afaan Oromo properly.  
- Lack **cultural awareness**, providing generic or non-relevant responses.  
- Have generic UI/UX designs lacking Ethiopian identity and heritage.  
- Depend on costly APIs, limiting accessibility and scalability in Ethiopia.

Chereka AI solves these by:  
- Offering **multi-language support** with fluent Amharic and Afaan Oromo understanding and speech.  
- Including **daily Ethiopian proverbs and cultural tips** to educate and entertain users.  
- Featuring an Ethiopian-themed UI with **Habesha patterns** and cultural colors.  
- Using a **combination of free and freemium APIs** to keep costs low.  
- Implementing **voice chat mode** that allows natural conversation through speech.

---

## 🛠 Features

### Core AI & Language Features  
- 💬 **Conversational AI** powered by OpenAI GPT or Hugging Face models via API.  
- 🌐 **Smart Language Switching:** Auto-detects user language and switches among English, Amharic, and Afaan Oromo seamlessly.  
- 🗣 **Voice Mode:** Users can speak to the chatbot and hear voice responses in any supported language.  
- 📖 **Learning Mode:** The AI learns and improves daily by storing anonymized conversational context.  
- 📜 **Daily Ethiopian Cultural Facts & Proverbs:** Upon greeting, the bot shares a proverb and explains it if requested.  
- 📍 **Local Context Awareness:** Incorporates Ethiopian holidays, weather, time, news, and local events in conversations.  
- 🔄 **Translation Module:** Translates text bidirectionally between supported languages.  
- 🤖 **Sentiment Analysis:** Detects user mood and adapts responses for empathy.  
- 🧠 **Context Memory:** Keeps short-term conversation context for natural dialogue flow.

### Utility Features  
- ⏰ **Task Management:** Users can set reminders and to-do lists.  
- 📢 **Proactive Notifications:** Daily reminders of cultural events, news, and proverbs.  
- 🖼 **Rich Media Support:** Send/receive images, videos, and files.  
- 🎵 **Music Search:** Find Ethiopian and global music info using Musixmatch API.  
- 🌦 **Weather Updates:** Local Ethiopian weather via Visual Crossing Weather API.  
- 📰 **News Feed:** Ethiopian and global news powered by NewsAPI.  
- 🔘 **Quick Replies & Buttons:** UI elements for common tasks and faster responses.

---

## 🎨 UI/UX Design

- 🎨 **Themes:**  
  - Dark green Ethiopian theme with gold and black accents and subtle Habesha patterns.  
  - Clean white and green light theme with cultural accents.

- 🌀 **Central Circular Chat Indicator:** Inspired by ChatGPT’s typing animation to indicate processing.

- 🎙 **Voice Input Bar:** A microphone button integrated within the chat input for voice mode.

- 📱 **Responsive Design:** Fully functional on mobile, tablet, and desktop.

- 🔤 **Rich Text & Emojis:** Supports rich message formatting and emoji reactions.

---

## 🔧 Technical Architecture

```mermaid
graph TD
  User[User Interface (React)]
  Backend[Backend (FastAPI / Node.js)]
  AI_API[AI Model API (OpenAI / Hugging Face)]
  Translate_API[Translation API (LibreTranslate)]
  Voice_API[Text-to-Speech & Speech-to-Text API]
  News_API[News API]
  Weather_API[Weather API]
  Music_API[Musixmatch API]
  Firebase[Firebase (Auth, Realtime DB, Firestore)]
  Supabase[Supabase (Optional Media Storage)]

  User --> Backend
  Backend --> AI_API
  Backend --> Translate_API
  Backend --> Voice_API
  Backend --> News_API
  Backend --> Weather_API
  Backend --> Music_API
  Backend --> Firebase
  Backend --> Supabase
