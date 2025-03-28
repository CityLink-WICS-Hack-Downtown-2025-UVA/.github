# 🌆 CityLink

**CityLink** is a full-stack web application that connects travelers heading to the same city. Through real-time chatrooms, AI-powered recommendations, and collaborative tools, CityLink helps users **explore smarter and connect faster** — making every trip a shared experience.

---

## 🚀 Features

- 🗘️ **City-Based Exploration**  
  Select a city from the dropdown and instantly join a real-time chatroom with others visiting the same location.

- 💬 **Live Group Chatrooms**  
  Converse with multiple travelers headed to the same city. Plan outings, share recommendations, or just chat.

- 🤖 **AI-Powered Travel Assistant**  
  Use the built-in chatbot to receive dynamic, up-to-date suggestions for places to visit and restaurants to try — including filtering for specific requests like "Asian food."

- 🔗 **Google Maps Integration**  
  Recommendations come with direct map links for instant access and directions.

- 🎨 **Dark Mode / Light Mode Toggle**  
  Enjoy a fully themed experience with seamless transitions between dark and light modes.

- 📱 **Responsive Layout**  
  Designed for desktops with fluid UI behavior: collapse the chatbot, expand the chatroom and recommendation sections dynamically.

- 👥 **Username Customization**  
  Set your display name in the chatroom to personalize your experience.

---

## 📸 Demo

> [(https://youtu.be/i_3cvCmcomc)]

---

## 🛠️ Tech Stack

### Frontend
- **React.js** (with `useState`, `useEffect`, and routing via `react-router-dom`)
- **CSS Modules** with custom theming (light/dark mode)
- **WebSocket Integration** for real-time messaging
- **Axios** for RESTful API requests
- **Google Fonts**: Inter, Poppins, Quicksand

### Backend
- **Flask** (Python)
- **OpenAI GPT-4o** for dynamic recommendations
- **Custom recommendation formatting + parsing**
- **CORS** and environment-secured `.env` API key loading

### WebSocket Server
- Node-based WebSocket server handling multiple city-specific rooms with chat history and live user count.

---

## 🧠 How It Works

1. User selects a city to explore — either by choosing from the dropdown or by clicking directly on the interactive Google Map on the homepage.
2. Redirected to a city-specific room showing:
   - Group chat with live users
   - Top 5 place and restaurant recommendations (generated by GPT)
3. User can:
   - Chat in real time with other travelers who are also exploring the same city
   - Toggle the AI-powered chatbot to refine recommendations (e.g., “Update to only Asian restaurants”)
   - Click the location links to open Google Maps directions for any recommended place or restaurant
4. UI responds smoothly with dynamic layout resizing when chatbot is toggled on/off.
5. User experience is theme-aware with fonts, borders, and color transitions.

---

## 📁 Project Structure

front-end (React Client)
```bash
src/
│
├── ChatBotComponent.js       # AI assistant interface — talks to OpenAI API via ai-recommendation
├── ChatComponent.js          # Real-time chat interface — connects to WebSocket server
├── ChatPage.js               # Main page — combines chat, recommendations, and chatbot
├── CitySearch.js             # Google Maps search UI — lets users select a city visually
├── reverseGeocoder.js        # Converts clicked map coordinates into city names
│
├── Styles/
│   ├── ChatComponent.css     # Styles for chat and chatbot UI
│   ├── ChatPage.css          # Styles for layout, dark/light themes, recommendation styling
│   └── fonts.css             # Custom font imports via Google Fonts
```

ai-recommendation (AI Backend)
```bash
openai_recommendation.py      # Flask app that handles:
                              # - ChatGPT-based travel recommendations
                              # - Structured format parsing
                              # - API for frontend chatbot to update recommendations
```
websocket-server (Live Chat Backend)
```bash
server.js                    # WebSocket server handling:
                             # - Real-time chat message broadcasting
                             # - Room-based user management (per city)
                             # - Chat history persistence in memory
```

---

## 📌 Setup Instructions

### 1. Frontend
```bash
cd front-end
npm install
npm start
```

### 2. Backend (Flask + OpenAI)
```bash
cd ai-recommendation
pip install -r requirements.txt
flask run --port=5001
```

### 3. WebSocket Server
```bash
cd websocket-server
npm install
node server.js
```

---


## ✨ Future Ideas

- Push notifications for trending events
- Direct DMs between users
- User profile pages with itineraries

---

> “CityLink – Chat. Connect. Explore.” 🌍
