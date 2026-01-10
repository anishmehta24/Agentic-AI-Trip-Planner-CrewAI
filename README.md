# 🌍 Agentic AI Trip Planner - Powered by CrewAI & LangChain 

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-1.28+-red.svg)
![CrewAI](https://img.shields.io/badge/CrewAI-1.6+-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)
![Status](https://img.shields.io/badge/Status-Production-success.svg)

**An intelligent, multi-agent AI travel planning system that creates personalized itineraries with real-time search capabilities**

[Live Demo](https://agentic-ai-trip-planner-crewai.streamlit.app/) • [Documentation](https://github.com/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI/wiki) • [Report Bug](https://github.com/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI/issues) • [Request Feature](https://github.com/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI/issues)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [UI Features](#-ui-features--tabs)
- [5-Tier Fallback System](#-5-tier-fallback-system)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [API Keys Setup](#-api-keys-setup)
- [Deployment](#-deployment)
- [Project Structure](#-project-structure)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 🎯 Overview

**Agentic AI Trip Planner** is a cutting-edge travel planning application that leverages the power of **multi-agent AI systems** to create comprehensive, personalized travel itineraries. Built with **CrewAI**, it employs specialized AI agents that collaborate to research destinations, find the best deals, and craft detailed day-by-day travel plans.
<img width="1249" height="871" alt="Screenshot 2025-12-03 164138" src="https://github.com/user-attachments/assets/e42f9229-c21c-46e7-bcb9-efb8aea2855f" />

### 🌟 What Makes It Special?

- **🤖 Multi-Agent AI System**: Three specialized AI agents work together (Location Expert, Guide Expert, Planner Expert)
- **🔄 5-Tier Fallback System**: Ensures 99.9% uptime with automatic failover across multiple LLM providers
- **🌐 Real-time Web Search**: Live data from the internet for flights, hotels, attractions, and events
- **📱 Beautiful UI**: Modern, responsive interface with glassmorphism design and gradient themes
- **💾 Search History**: Automatic saving and retrieval of all searches with rich card layouts
- **🎯 Interest-Based Planning**: Customizable itineraries based on 24+ travel interests
- **🌍 Global Coverage**: Support for 50+ countries and 500+ cities worldwide
---
## 🌐🎬 Live Demo
🚀 **Try it now:**
- **Streamlit Profile** - https://share.streamlit.io/user/ratnesh-181998
- **Project Demo** - https://agentic-ai-trip-planner-crewai-ykagvec2ng6raotrdaw6sp.streamlit.app/

---

## ✨ Key Features

### 🤖 AI-Powered Trip Planning
- **Intelligent Agents**: Three specialized AI agents collaborate to create comprehensive travel plans
  - **Location Expert**: Researches transportation, accommodation, costs, weather, and visa requirements
  - **Guide Expert**: Discovers attractions, restaurants, activities, and local events
  - **Planner Expert**: Creates detailed day-by-day itineraries with timings and budget breakdowns
<img width="1936" height="1351" alt="Screenshot 2025-12-03 230304" src="https://github.com/user-attachments/assets/f33d508d-79f4-4b2d-9a0e-762e310263c5" />

### 🔍 Comprehensive Search Capabilities
- **✈️ Flight Search**: Real-time flight options with pricing and schedules
- **🏨 Hotel Search**: Accommodation recommendations with ratings and prices
- **🚆 Train Search**: Railway options for intercity and international travel
- **🚌 Bus Search**: Budget-friendly bus routes and schedules

### 🎨 Advanced UI/UX
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile
- **Glassmorphism Effects**: Modern, translucent design elements
- **Gradient Themes**: Beautiful color gradients inspired by nature (sunrise/sunset)
- **Interactive Cards**: Rich destination cards with images and video previews
- **Dark/Light Modes**: Automatic theme adaptation

### 📊 Smart Features
- **Multi-Interest Selection**: Choose from 24+ travel interests
- **Traveler Customization**: Specify adults and children counts
- **Date Range Planning**: Flexible departure and return dates
- **Budget Estimation**: Automatic cost calculations per person
- **History Tracking**: All searches saved with metadata and timestamps

---

## 🛠️ Tech Stack

### **Core Technologies**

| Technology | Version | Purpose |
|------------|---------|---------|
| **Python** | 3.10+ | Primary programming language |
| **Streamlit** | 1.28+ | Web application framework |
| **CrewAI** | 1.6.1+ | Multi-agent AI orchestration |
| **LangChain** | 0.1.0+ | LLM integration and chaining |

### **AI/LLM Providers**

| Provider | Models | Tier |
|----------|--------|------|
| **Groq** | llama-3.3-70b, llama-3.1-8b, mixtral-8x7b, gemma2-9b | Tier 1-4 |
| **Google Gemini** | gemini-2.0-flash, gemini-1.5-pro | Tier 3-4 |
| **Ollama** | llama3.2 (local) | Tier 5 |

### **Search & Tools**

- **DuckDuckGo Search** (4.0+): Web search without API keys
- **Serper API**: Advanced Google search integration (optional)
- **Browserless API**: Web scraping capabilities (optional)

### **Data & Storage**

- **Python-dotenv**: Environment variable management
- **SQLite3**: Local database for caching
- **File System**: JSON/TXT storage for search history

### **Frontend**

- **HTML5/CSS3**: Custom styling and layouts
- **JavaScript**: Interactive elements (embedded in Streamlit)
- **Base64 Encoding**: Image handling and optimization

---

## 🏗️ Architecture

### Multi-Agent System Design

```
┌─────────────────────────────────────────────────────────────┐
│                     USER INPUT                               │
│  (Destination, Dates, Interests, Travelers)                 │
└────────────────────┬────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│                  CREW ORCHESTRATOR                           │
│              (CrewAI Sequential Process)                     │
└────────────────────┬────────────────────────────────────────┘
                     │
        ┌────────────┼────────────┐
        ▼            ▼             ▼
┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│   AGENT 1    │ │   AGENT 2    │ │   AGENT 3    │
│  Location    │ │    Guide     │ │   Planner    │
│   Expert     │ │   Expert     │ │   Expert     │
└──────┬───────┘ └──────┬───────┘ └──────┬───────┘
       │                │                │
       │ Web Search     │ Web Search     │ Synthesis
       │ Tools          │ Tools          │ Tools
       ▼                ▼                ▼
┌──────────────────────────────────────────────────────────────┐
│              KNOWLEDGE BASE & CONTEXT                         │
│  (Transportation, Hotels, Attractions, Events, Costs)        │
└────────────────────┬─────────────────────────────────────────┘
                     │
                     ▼
┌─────────────────────────────────────────────────────────────┐
│              FINAL ITINERARY OUTPUT                          │
│  (Day-by-day plan, Budget, Tips, Recommendations)           │
└─────────────────────────────────────────────────────────────┘
```

### 5-Tier Fallback Architecture

```
Request → Tier 1 (Groq llama-3.3-70b) ──✓──> Success
              │
              ✗ (Rate Limit/Error)
              │
              ▼
          Tier 2 (Groq llama-3.1-8b) ──✓──> Success
              │
              ✗
              ▼
          Tier 3 (Groq mixtral-8x7b) ──✓──> Success
              │
              ✗
              ▼
          Tier 4 (Google Gemini) ──✓──> Success
              │
              ✗
              ▼
          Tier 5 (Ollama Local) ──✓──> Success
```

---

## 🎨 UI Features & Tabs

### 1. 🤖 **AI Trip Planner** (Main Tab)
The core feature where users input their travel details and receive AI-generated itineraries.

**Features:**
- **Smart Location Selection**: Dropdown menus for 50+ countries and 500+ cities
- **Date Range Picker**: Flexible departure and return date selection
- **Traveler Configuration**: Separate inputs for adults and children
- **Interest Multiselect**: 24+ categories including:
  - 🏛️ Sightseeing & Landmarks
  - 🍕 Food & Dining
  - 🎨 Art & Museums
  - 🏖️ Beach & Relaxation
  - ⛰️ Adventure & Hiking
  - 🎭 Culture & History
  - 🛍️ Shopping
  - 🎉 Nightlife & Parties
  - And 16 more...

**Output Includes:**
- Comprehensive city introduction
- Day-by-day detailed itinerary with timings
- Restaurant recommendations with cuisine types
- Budget breakdown (flights, hotels, food, activities)
- Visa requirements and travel tips
- Weather forecast and packing suggestions
<img width="940" height="510" alt="image" src="https://github.com/user-attachments/assets/481abb62-1191-43c2-8742-67ceea9dbcca" />
<img width="940" height="504" alt="image" src="https://github.com/user-attachments/assets/cba55e88-e3f0-41d6-80f5-86b4fcca1fd3" />
<img width="940" height="504" alt="image" src="https://github.com/user-attachments/assets/b065db55-f1d0-4f87-997a-a7889b42ffa2" />
<img width="940" height="519" alt="image" src="https://github.com/user-attachments/assets/fc76bc13-3bee-4c21-acbe-dfe0b017591c" />
<img width="940" height="500" alt="image" src="https://github.com/user-attachments/assets/687b3758-13f3-45fb-9444-bbccc83f6b9e" />
<img width="940" height="501" alt="image" src="https://github.com/user-attachments/assets/fa819cff-5e76-40ce-9251-ed3cda9cd967" />
<img width="940" height="892" alt="image" src="https://github.com/user-attachments/assets/836e84eb-37fc-4522-82f3-dc2f0351550d" />
<img width="940" height="793" alt="image" src="https://github.com/user-attachments/assets/327645ab-5f68-4de0-bc99-cfa596191225" />
<img width="940" height="874" alt="image" src="https://github.com/user-attachments/assets/fabf64ca-03bc-4062-a7a4-cd100243bffe" />
<img width="940" height="874" alt="image" src="https://github.com/user-attachments/assets/046ef288-e347-4e1c-9f39-51d043d6e93a" />
<img width="940" height="497" alt="image" src="https://github.com/user-attachments/assets/03003716-091c-4f57-8bf1-8bf6d7e3f1b1" />
<img width="940" height="486" alt="image" src="https://github.com/user-attachments/assets/0bb33bb8-af8f-464d-9299-be1dd7e76c0c" />
<img width="940" height="493" alt="image" src="https://github.com/user-attachments/assets/d23e9bf0-7141-494e-ba09-d394cf4e15c0" />

### 2. 📜 **AI Trip Planner History**
View and manage all previously generated trip plans.

**Features:**
- **Rich Card Layout**: Beautiful gradient cards showing trip summaries
- **Metadata Display**: Destination, dates, creation timestamp, file size
- **Content Preview**: Expandable sections to view full itinerary
- **Download Options**: Export any plan as TXT file
- **Smart Sorting**: Newest plans first
- **Search Filters**: (Coming soon)
<img width="940" height="508" alt="image" src="https://github.com/user-attachments/assets/bf583f98-a122-4c4d-a7f7-7c71be57b63a" />

### 3. 🎯 **Explore by Interest**
Discover destinations based on specific travel interests.
<img width="2872" height="1467" alt="Screenshot 2025-12-06 190252" src="https://github.com/user-attachments/assets/5ea6b6bb-e355-45c4-b64f-b8e534f00ed1" />
<img width="2867" height="1532" alt="Screenshot 2025-12-06 190340" src="https://github.com/user-attachments/assets/847d0020-4807-4193-a088-163f3c1d92ad" />

**17 Interest Categories:**
1. 🏖️ Beach Destinations
  <img width="2601" height="1504" alt="Screenshot 2025-12-06 190421" src="https://github.com/user-attachments/assets/ba838453-433e-4fd1-aa6c-4bbf83a79712" />
  <img width="2505" height="1331" alt="Screenshot 2025-12-06 190446" src="https://github.com/user-attachments/assets/2eb86529-5ac7-4690-adbb-9b0bc8fd7484" />

2. ⛰️ Mountain & Adventure
   <img width="2614" height="1478" alt="Screenshot 2025-12-06 190522" src="https://github.com/user-attachments/assets/f63f1f56-bf84-4018-9640-ed7a7efc7580" />
   <img width="2587" height="1421" alt="Screenshot 2025-12-06 190557" src="https://github.com/user-attachments/assets/080df0fb-4940-49dd-a1ab-73ce3d6de685" />

3. 🏛️ Historical Sites
   <img width="2571" height="1504" alt="Screenshot 2025-12-06 190706" src="https://github.com/user-attachments/assets/63f34999-d615-4e85-af15-c327de85b05d" />

4. 🍕 Food & Culinary Tours
   <img width="2537" height="1480" alt="Screenshot 2025-12-06 190821" src="https://github.com/user-attachments/assets/20be8c88-9d26-44a5-931b-5de1364381c5" />

5. 🎨 Art & Culture
   <img width="2590" height="1483" alt="Screenshot 2025-12-06 190929" src="https://github.com/user-attachments/assets/d2405d83-8c20-4520-8fb9-7d42f28db9ba" />
   <img width="2541" height="1441" alt="Screenshot 2025-12-06 190951" src="https://github.com/user-attachments/assets/72023461-a429-4e0c-a234-cd382b2074d3" />

8. 🏙️ Urban Exploration
9. 🌳 Nature & Wildlife
10. 🏰 Castles & Palaces
11. 🎭 Festivals & Events
12. 🛍️ Shopping Havens
13. 🎉 Nightlife Hotspots
14. 📸 Photography Spots
15. 🧘 Wellness & Spa
16. 🏃 Sports & Fitness
17. 👨‍👩‍👧 Family-Friendly
18. 💑 Romantic Getaways
19. 🎓 Educational Tours

**Each Category Shows:**
- Curated destination cards with images
- Price ranges (flights + hotels)
- Best time to visit
- Top attractions
- Insider tips

### 4. ✈️ **Flights Search**
AI-powered flight search with real-time data.

**Features:**
- **Route Input**: From/To city selection
- **Date Selection**: Departure and return dates
- **Passenger Details**: Adults and children counts
- **Class Selection**: Economy, Business, First Class
- **AI Analysis**: Best deals, layover optimization, price trends
- **Results Include**:
  - Multiple airline options
  - Price comparisons
  - Flight duration and layovers
  - Booking links
  - Price alerts and recommendations
<img width="940" height="487" alt="image" src="https://github.com/user-attachments/assets/92d61353-efa6-4c7a-83ae-85e362fe8f5c" />
<img width="940" height="513" alt="image" src="https://github.com/user-attachments/assets/d315814e-3935-4fca-b9a5-e1d8bd2b184c" />
<img width="940" height="518" alt="image" src="https://github.com/user-attachments/assets/0e5212e5-5a6b-4489-95f7-b2f928785079" />
<img width="940" height="497" alt="image" src="https://github.com/user-attachments/assets/1582004f-8c20-4533-97bd-2f97718d7cff" />
<img width="940" height="497" alt="image" src="https://github.com/user-attachments/assets/7b23cd3a-a410-4a61-acb8-91bc76bf66f9" />

### 5. 📜 **Flight History**
Track all flight searches with detailed metadata.
<img width="940" height="509" alt="image" src="https://github.com/user-attachments/assets/b986fa5f-f462-4bb3-b31c-7dd1ac977e27" />
<img width="940" height="495" alt="image" src="https://github.com/user-attachments/assets/00fb7f1e-802e-4911-9b0a-578e62261f63" />

### 6. 🏨 **Hotels Search**
Comprehensive hotel search powered by AI.

**Features:**
- **Location-Based**: City/area selection
- **Check-in/Check-out Dates**: Flexible date ranges
- **Guest Configuration**: Rooms, adults, children
- **Amenity Filters**: WiFi, Pool, Gym, Breakfast, etc.
- **AI Recommendations**:
  - Best value hotels
  - Luxury options
  - Budget-friendly choices
  - Location-based suggestions
  - User ratings and reviews
<img width="940" height="500" alt="image" src="https://github.com/user-attachments/assets/d1b8932d-15a2-46f2-bef9-599300eb5d0e" />
<img width="940" height="493" alt="image" src="https://github.com/user-attachments/assets/161fdd7d-4e22-4043-b61c-89d4ed6e8f01" />
<img width="940" height="497" alt="image" src="https://github.com/user-attachments/assets/02e5adee-e119-4fda-b2cc-fecf88935f7b" />
<img width="940" height="508" alt="image" src="https://github.com/user-attachments/assets/b96b21fc-b2ff-4204-8df6-5305a5f6685f" />

### 7. 📜 **Hotel History**
Archive of all hotel searches with rich previews.
<img width="940" height="506" alt="image" src="https://github.com/user-attachments/assets/dfb955ad-388c-4665-9a3d-1d9e0e864667" />
<img width="940" height="511" alt="image" src="https://github.com/user-attachments/assets/6dcdd976-12ea-4670-9a7e-779d1d81bf6c" />
<img width="940" height="499" alt="image" src="https://github.com/user-attachments/assets/0683956b-da7e-48d7-b9c3-9b3eb29ab88c" />

### 8. 🚆 **Trains Search**
Railway options for intercity and international travel.

**Features:**
- **Route Planning**: Origin and destination stations
- **Schedule Search**: Date and time preferences
- **Class Selection**: Sleeper, AC, First Class, etc.
- **AI Insights**:
  - Fastest routes
  - Most scenic journeys
  - Budget options
  - Booking tips
<img width="940" height="495" alt="image" src="https://github.com/user-attachments/assets/00e4d024-f6af-4978-bce1-2249b4eb99f0" />
<img width="940" height="501" alt="image" src="https://github.com/user-attachments/assets/f579916f-aa23-449b-9625-58fe30369ef2" />
<img width="940" height="461" alt="image" src="https://github.com/user-attachments/assets/60a637df-3633-429f-aed2-2edde16d2f7c" />
<img width="940" height="498" alt="image" src="https://github.com/user-attachments/assets/05144b6c-5d58-4fc3-b997-cf957e7b304e" />
<img width="940" height="484" alt="image" src="https://github.com/user-attachments/assets/66bd0dd3-54f1-43bd-a22b-ff155fa3cce1" />

### 9. 📜 **Train History**
Historical train search records.
<img width="940" height="502" alt="image" src="https://github.com/user-attachments/assets/b312585f-b055-450f-9d7d-6b03966b375e" />
<img width="940" height="485" alt="image" src="https://github.com/user-attachments/assets/bfbca850-0541-4aba-9586-1ea7b7393577" />
<img width="940" height="485" alt="image" src="https://github.com/user-attachments/assets/2a740163-82c8-4830-898c-4428fa1b4576" />

### 10. 🚌 **Buses Search**
Budget-friendly bus travel options.

**Features:**
- **Route Search**: City-to-city bus services
- **Operator Comparison**: Multiple bus companies
- **Amenity Filters**: AC, WiFi, Sleeper, etc.
- **AI Recommendations**: Best operators, timing, pricing
<img width="940" height="503" alt="image" src="https://github.com/user-attachments/assets/278b7d9c-8d5e-4333-b017-391dcfc12a65" />
<img width="940" height="455" alt="image" src="https://github.com/user-attachments/assets/f4632b7c-c1f3-437f-bb31-b2f247fab0b9" />
<img width="940" height="510" alt="image" src="https://github.com/user-attachments/assets/287fbbf4-eacf-4d3f-a9eb-102128275932" />

### 11. 📜 **Bus History**
Archive of bus search results.
<img width="940" height="520" alt="image" src="https://github.com/user-attachments/assets/57a333fa-eb2c-4036-8343-9609296c4509" />
<img width="940" height="507" alt="image" src="https://github.com/user-attachments/assets/12ca1162-0914-4e20-aeed-878a476d0dbe" />
<img width="940" height="491" alt="image" src="https://github.com/user-attachments/assets/73d12dce-7ec9-472c-92d3-d466a6086873" />

### 12. 🌟 **Destinations**
Curated list of popular destinations worldwide.

**Features:**
- **Destination Cards**: Beautiful cards with images/videos
- **Quick Info**: Country, description, price range, hotel options
- **5-Second Video Previews**: Autoplay destination highlights
- **Interactive Filters**: By region, budget, season
- **Featured Destinations**:
  - Bora Bora, French Polynesia
  - Monaco, France
  - Jerusalem, Israel
  - Bologna, Italy
  - And many more...
<img width="2863" height="1513" alt="Screenshot 2025-12-06 192402" src="https://github.com/user-attachments/assets/cb6d381c-f14c-4048-b6c7-4d400cb4fbbc" />
<img width="2546" height="1401" alt="Screenshot 2025-12-06 192426" src="https://github.com/user-attachments/assets/5980c5a0-2ef6-496d-a864-7118d89763f9" />
<img width="2578" height="1456" alt="Screenshot 2025-12-06 192442" src="https://github.com/user-attachments/assets/1e0d251a-a1b8-4b88-9fc1-429a3be52b2a" />
<img width="2625" height="1449" alt="Screenshot 2025-12-06 192503" src="https://github.com/user-attachments/assets/5e7c68b7-c7ca-449b-a8f0-5f9a4f907535" />

### 13. 💡 **Travel Tips**
Expert advice and travel hacks.

**Categories:**
- **Pre-Trip Planning**: Visa, insurance, packing
- **During Travel**: Safety, communication, local customs
- **Budget Tips**: Money-saving strategies
- **Health & Safety**: Medical prep, emergency contacts
- **Cultural Etiquette**: Do's and don'ts by country
- **Tech Tips**: Apps, tools, connectivity
<img width="2856" height="1516" alt="Screenshot 2025-12-06 192536" src="https://github.com/user-attachments/assets/56c40e40-b40e-45c8-bfe4-7eb0ae46fd15" />
<img width="2480" height="1437" alt="Screenshot 2025-12-06 192558" src="https://github.com/user-attachments/assets/c0a6486e-eb3c-4c07-968e-1b75aa8ce780" />
<img width="2459" height="1403" alt="Screenshot 2025-12-06 192629" src="https://github.com/user-attachments/assets/cb8d1741-164f-40a0-98a5-5e91506aed16" />
<img width="2450" height="1416" alt="Screenshot 2025-12-06 192643" src="https://github.com/user-attachments/assets/26827701-3b16-4f25-8219-13fcf4be9808" />
<img width="2395" height="1453" alt="Screenshot 2025-12-06 192706" src="https://github.com/user-attachments/assets/e5f8aa4a-003a-4aad-a036-60eb663f2bd4" />

---

## 🔄 5-Tier Fallback System

Our revolutionary **5-Tier Fallback System** ensures **99.9% uptime** by automatically switching between LLM providers when issues occur.

### How It Works

| Tier | Provider | Model | Speed | Quality | Fallback Trigger |
|------|----------|-------|-------|---------|------------------|
| **1** | Groq | llama-3.3-70b-versatile | ⚡⚡⚡ | ⭐⭐⭐⭐⭐ | Rate limit, API error |
| **2** | Groq | llama-3.1-8b-instant | ⚡⚡⚡ | ⭐⭐⭐⭐ | Rate limit, API error |
| **3** | Groq | mixtral-8x7b-32768 | ⚡⚡⚡ | ⭐⭐⭐⭐⭐ | Rate limit, API error |
| **4** | Google | gemini-2.0-flash | ⚡⚡ | ⭐⭐⭐⭐ | Network error, auth failure |
| **5** | Ollama | llama3.2 (local) | ⚡ | ⭐⭐⭐ | All cloud providers fail |

### Benefits

- **Zero Downtime**: Automatic failover in milliseconds
- **Cost Optimization**: Uses free tiers first, paid tiers as backup
- **Offline Capability**: Tier 5 works without internet
- **User Transparency**: Real-time status updates during fallback
- **Smart Recovery**: Automatically returns to Tier 1 when available

### Visual Alerts

The system provides high-visibility alerts during fallback:
- 🚨 **Red Alert**: Tier 1 failure, switching to Tier 2-3
- ⚠️ **Orange Alert**: Cloud providers failed, switching to Tier 5
- ✅ **Green Success**: Operation completed successfully

---

## 🚀 Installation

### Prerequisites

- **Python 3.10 or higher**
- **pip** (Python package manager)
- **Git** (for cloning repository)
- **Ollama** (optional, for Tier 5 local LLM)

### Step 1: Clone Repository

```bash
git clone https://github.com/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI.git
cd Agentic-AI-Trip-Planner-CrewAI
```

### Step 2: Create Virtual Environment

```bash
# Windows
python -m venv .venv
.venv\Scripts\activate

# macOS/Linux
python3 -m venv .venv
source .venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Set Up Environment Variables

Create a `.env` file in the root directory:

```bash
cp .env.example .env
```

Edit `.env` with your API keys (see [API Keys Setup](#-api-keys-setup))

### Step 5: Run the Application

```bash
streamlit run ratnesh_app_ULTIMATE.py
```

The app will open in your browser at `http://localhost:8501`

---

## ⚙️ Configuration

### Environment Variables

Create a `.env` file with the following variables:

```env
# Required for Tier 1-3 (Groq)
GROQ_API_KEY=your_groq_api_key_here

# Required for Tier 4 (Google Gemini)
GOOGLE_API_KEY=your_google_api_key_here

# Optional - Advanced Search (if using Serper)
SERPER_API_KEY=your_serper_api_key_here

# Optional - Web Scraping (if using Browserless)
BROWSERLESS_API_KEY=your_browserless_api_key_here

# Optional - Ollama Configuration (Tier 5)
OLLAMA_HOST=http://localhost:11434
```

### LLM Provider Selection

In the sidebar, you can choose:
- **Auto (5-Tier Fallback)**: Recommended - uses all tiers
- **Groq Only**: Fast, requires API key
- **Google Only**: Uses Gemini models
- **Ollama Only**: Offline mode, requires local Ollama

---

## 🔑 API Keys Setup

### 1. Groq API Key (Free)

1. Visit [Groq Console](https://console.groq.com/)
2. Sign up for a free account
3. Navigate to API Keys section
4. Create a new API key
5. Copy and paste into `.env` file

**Free Tier**: 30 requests/minute, 14,400 requests/day

### 2. Google Gemini API Key (Free)

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with Google account
3. Click "Create API Key"
4. Copy and paste into `.env` file

**Free Tier**: 60 requests/minute

### 3. Serper API Key (Optional)

1. Visit [Serper.dev](https://serper.dev/)
2. Sign up for free account
3. Get API key from dashboard
4. Copy and paste into `.env` file

**Free Tier**: 2,500 searches/month

### 4. Ollama Setup (Optional - Tier 5)

For offline capability:

```bash
# Install Ollama
# Visit https://ollama.ai/ and download for your OS

# Pull the model
ollama pull llama3.2

# Verify it's running
ollama list
```

---

## 📖 Usage

### Basic Trip Planning

1. **Open the App**: Navigate to `http://localhost:8501`
2. **Select Locations**: Choose from/to country and city
3. **Set Dates**: Pick departure and return dates
4. **Configure Travelers**: Enter number of adults and children
5. **Choose Interests**: Select from 24+ travel interests
6. **Generate Plan**: Click "🚀 Generate Travel Plan"
7. **Review Output**: Get detailed day-by-day itinerary
8. **Save/Download**: Plans auto-save to `trip_plans/` folder

### Flight/Hotel/Train/Bus Search

1. Navigate to respective tab
2. Enter route details (from/to)
3. Select dates and passenger count
4. Click search button
5. Review AI-generated options
6. Download results or view in history

### Explore by Interest

1. Go to "🎯 Explore by Interest" tab
2. Browse 17 interest categories
3. Click on any category to see curated destinations
4. View destination cards with images, prices, and details

---

## 🌐 Deployment

### Deploy to Streamlit Cloud

1. **Push to GitHub**:
```bash
git add .
git commit -m "Ready for deployment"
git push origin main
```

2. **Configure Git LFS** (for large files):
```bash
git lfs install
git lfs track "*.png" "*.jpg" "*.mp4"
git add .gitattributes
git commit -m "Add Git LFS tracking"
git push
```

3. **Deploy on Streamlit**:
   - Visit [Streamlit Cloud](https://streamlit.io/cloud)
   - Connect your GitHub repository
   - Select `ratnesh_app_ULTIMATE.py` as main file
   - Add environment variables (API keys)
   - Click "Deploy"

### Environment Variables on Streamlit Cloud

In Streamlit Cloud settings, add:
```
GROQ_API_KEY=your_key
GOOGLE_API_KEY=your_key
SERPER_API_KEY=your_key (optional)
```

---

## 📁 Project Structure

```
Agentic-AI-Trip-Planner-CrewAI/
│
├── ratnesh_app_ULTIMATE.py      # Main Streamlit application
├── TravelAgents.py               # AI agent definitions
├── TravelTasks.py                # Task definitions for agents
├── TravelTasks_LEGACY.py         # Legacy detailed tasks
├── TravelTools.py                # Search and web tools
│
├── requirements.txt              # Python dependencies
├── .env.example                  # Environment variable template
├── .gitignore                    # Git ignore rules
├── .gitattributes                # Git LFS configuration
│
├── images/                       # Destination images
│   ├── bologna.png
│   ├── borabora.png
│   ├── jerusalem.png
│   └── monaco.png
│
├── trip_plans/                   # Saved trip itineraries
├── Flight_Search_History/        # Flight search archives
├── Hotel_Search_History/         # Hotel search archives
├── Train_Search_History/         # Train search archives
├── Bus_Search_History/           # Bus search archives
│
├── docs/                         # Documentation files
│   ├── 5_TIER_SYSTEM.md
│   ├── DEPLOYMENT.md
│   ├── QUICK_START.md
│   └── API_SETUP.md
│
└── README.md                     # This file
```

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### Reporting Bugs

1. Check [existing issues](https://github.com/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI/issues)
2. Create a new issue with:
   - Clear title and description
   - Steps to reproduce
   - Expected vs actual behavior
   - Screenshots (if applicable)
   - Environment details (OS, Python version)

### Suggesting Features

1. Open a [feature request](https://github.com/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI/issues/new)
2. Describe the feature and its benefits
3. Provide use cases and examples

### Pull Requests

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines

- Follow PEP 8 style guide
- Add docstrings to functions
- Write unit tests for new features
- Update documentation
- Test on multiple Python versions (3.10, 3.11, 3.12)

---

## 📄 License

This project is licensed under the **MIT License** - see below for details:

```
MIT License

Copyright (c) 2024 Ratnesh Singh

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### Third-Party Licenses

This project uses the following open-source libraries:
- **Streamlit** - Apache License 2.0
- **CrewAI** - MIT License
- **LangChain** - MIT License
- **Groq SDK** - Apache License 2.0
- **Google Generative AI** - Apache License 2.0

---

## 📞 Contact

**RATNESH SINGH**  
*Data Scientist | AI/ML Engineer | 4+ Years Experience*

- 📧 **Email**: [rattudacsit2021gate@gmail.com](mailto:rattudacsit2021gate@gmail.com)
- 💼 **LinkedIn**: [linkedin.com/in/ratneshkumar1998](https://www.linkedin.com/in/ratneshkumar1998/)
- 🐙 **GitHub**: [github.com/Ratnesh-181998](https://github.com/Ratnesh-181998)
- 📱 **Phone**: +91-947XXXXX46

### Project Links

- 🌐 **Live Demo**: [Streamlit App](https://agentic-ai-trip-planner-crewai-ykagvec2ng6raotrdaw6sp.streamlit.app/)
- 📖 **Documentation**: [GitHub Wiki](https://github.com/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI/wiki)
- 🐛 **Issue Tracker**: [GitHub Issues](https://github.com/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI/issues)
- 💬 **Discussions**: [GitHub Discussions](https://github.com/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI/discussions)

---

## 🙏 Acknowledgments

Special thanks to:
- **CrewAI Team** - For the amazing multi-agent framework
- **Streamlit** - For the intuitive web app framework
- **Groq** - For lightning-fast LLM inference
- **Google** - For Gemini AI models
- **Ollama** - For local LLM capabilities
- **Open Source Community** - For continuous inspiration and support

---

## 📊 Stats & Metrics

![GitHub Stars](https://img.shields.io/github/stars/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI?style=social)
![GitHub Forks](https://img.shields.io/github/forks/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI?style=social)
![GitHub Issues](https://img.shields.io/github/issues/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI)
![GitHub Pull Requests](https://img.shields.io/github/issues-pr/Ratnesh-181998/Agentic-AI-Trip-Planner-CrewAI)

---

## 🗺️ Roadmap

### Version 2.0 (Upcoming)

- [ ] **Real-time Booking Integration**: Direct booking for flights, hotels, trains
- [ ] **Multi-language Support**: 10+ languages
- [ ] **Mobile App**: React Native version
- [ ] **Social Features**: Share itineraries, collaborate with friends
- [ ] **AI Chat Assistant**: Conversational interface for planning
- [ ] **Price Alerts**: Notifications for price drops
- [ ] **Offline Mode**: Full functionality without internet
- [ ] **Advanced Analytics**: Travel insights and statistics

### Version 1.5 (In Progress)

- [x] 5-Tier Fallback System
- [x] Interest-based exploration
- [x] Search history with rich cards
- [ ] User authentication
- [ ] Saved favorites
- [ ] Export to PDF/Google Calendar

---

<div align="center">

**Made with ❤️ by Ratnesh Singh**

⭐ **Star this repo if you find it helpful!** ⭐

[⬆ Back to Top](#-agentic-ai-trip-planner---powered-by-crewai)

</div>

---




<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=24,20,12,6&height=3" width="100%">


## 📜 **License**

![License](https://img.shields.io/badge/License-MIT-success?style=for-the-badge&logo=opensourceinitiative&logoColor=white)

**Licensed under the MIT License** - Feel free to fork and build upon this innovation! 🚀

---

# 📞 **CONTACT & NETWORKING** 📞


### 💼 Professional Networks

[![LinkedIn](https://img.shields.io/badge/💼_LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ratneshkumar1998/)
[![GitHub](https://img.shields.io/badge/🐙_GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Ratnesh-181998)
[![X](https://img.shields.io/badge/X-000000?style=for-the-badge&logo=x&logoColor=white)](https://x.com/RatneshS16497)
[![Portfolio](https://img.shields.io/badge/🌐_Portfolio-FF6B6B?style=for-the-badge&logo=google-chrome&logoColor=white)](https://share.streamlit.io/user/ratnesh-181998)
[![Email](https://img.shields.io/badge/✉️_Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:rattudacsit2021gate@gmail.com)
[![Medium](https://img.shields.io/badge/Medium-000000?style=for-the-badge&logo=medium&logoColor=white)](https://medium.com/@rattudacsit2021gate)
[![Stack Overflow](https://img.shields.io/badge/Stack_Overflow-F58025?style=for-the-badge&logo=stack-overflow&logoColor=white)](https://stackoverflow.com/users/32068937/ratnesh-kumar)

### 🚀 AI/ML & Data Science
[![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://share.streamlit.io/user/ratnesh-181998)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black)](https://huggingface.co/RattuDa98)
[![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/rattuda)

### 💻 Competitive Programming
[![LeetCode](https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black)](https://leetcode.com/u/Ratnesh_1998/)
[![HackerRank](https://img.shields.io/badge/HackerRank-00EA64?style=for-the-badge&logo=hackerrank&logoColor=black)](https://www.hackerrank.com/profile/rattudacsit20211)
[![CodeChef](https://img.shields.io/badge/CodeChef-5B4638?style=for-the-badge&logo=codechef&logoColor=white)](https://www.codechef.com/users/ratnesh_181998)
[![Codeforces](https://img.shields.io/badge/Codeforces-1F8ACB?style=for-the-badge&logo=codeforces&logoColor=white)](https://codeforces.com/profile/Ratnesh_181998)
[![GeeksforGeeks](https://img.shields.io/badge/GeeksforGeeks-2F8D46?style=for-the-badge&logo=geeksforgeeks&logoColor=white)](https://www.geeksforgeeks.org/profile/ratnesh1998)
[![HackerEarth](https://img.shields.io/badge/HackerEarth-323754?style=for-the-badge&logo=hackerearth&logoColor=white)](https://www.hackerearth.com/@ratnesh138/)
[![InterviewBit](https://img.shields.io/badge/InterviewBit-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://www.interviewbit.com/profile/rattudacsit2021gate_d9a25bc44230/)


---

## 📊 **GitHub Stats & Metrics** 📊



![Profile Views](https://komarev.com/ghpvc/?username=Ratnesh-181998&color=blueviolet&style=for-the-badge&label=PROFILE+VIEWS)





<img src="https://github-readme-streak-stats.herokuapp.com/?user=Ratnesh-181998&theme=radical&hide_border=true&background=0D1117&stroke=4ECDC4&ring=F38181&fire=FF6B6B&currStreakLabel=4ECDC4" width="48%" />




<img src="https://github-readme-activity-graph.vercel.app/graph?username=Ratnesh-181998&theme=react-dark&hide_border=true&bg_color=0D1117&color=4ECDC4&line=F38181&point=FF6B6B" width="48%" />

---

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=24&duration=3000&pause=1000&color=4ECDC4&center=true&vCenter=true&width=600&lines=Ratnesh+Kumar+Singh;Data+Scientist+%7C+AI%2FML+Engineer;4%2B+Years+Building+Production+AI+Systems" alt="Typing SVG" />

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=18&duration=2000&pause=1000&color=F38181&center=true&vCenter=true&width=600&lines=Built+with+passion+for+the+AI+Community+🚀;Innovating+the+Future+of+AI+%26+ML;MLOps+%7C+LLMOps+%7C+AIOps+%7C+GenAI+%7C+AgenticAI+Excellence" alt="Footer Typing SVG" />


<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=120&section=footer" width="100%">


