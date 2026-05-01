# Wanderlust AI: The Cinematic Travel Platform

> **Transforming raw travel planning into an immersive, editorial experience.**

Welcome to the public documentation for **Wanderlust AI**, a high-end, AI-driven editorial platform that transforms raw travel data into an immersive, cinematic story.

In a digital landscape saturated with utilitarian booking engines and generic listicles, this platform was conceived as a disruptor. Most travel planners focus on the "how" (logistics) and the "how much" (budget). Our platform shifts the focus entirely to the "why"—the narrative, the atmosphere, and the hidden pulse of a destination. It leverages cutting-edge AI orchestration via LangGraph, a performance-tuned FastAPI backend, and a premium Next.js frontend designed with a "glass-editorial" aesthetic.

---

![image alt](https://github.com/aryanvaghsiya11-a11y/Wanderlust-AI-The-Cinematic-Travel-Platform/blob/4c2e680c2b209d69a874e9042c20d43c64abc016/wanderlust.png)

## 🌍 Core Philosophy: Experience-First Travel

Wanderlust AI treats travel as an art form. Traditional trip planners rely on static databases and outdated reviews, offering the same "Top 10" lists to millions of travelers, resulting in crowded tourist traps. By moving away from the traditional "Chatbot" paradigm and embracing an "Editor" paradigm, we inspire journeys that are deeply personal and culturally profound.

Our engine performs live web research to ensure your story is uniquely yours, built on three pillars:

* **Purpose:** Traveling with intention to transform sightseeing into self-discovery, allowing you to follow your inner compass.
* **Presence:** The ability to be fully present, separating tourists who collect photos from travelers who collect moments that reshape their inner landscape.
* **Connection:** Forging bonds with the world, strangers, and the people you travel with—proving that human beings everywhere share fundamental desires to be seen and understood.

---

## 🏛️ System Architecture: The Dual-Engine

The project is architected as a decoupled system to ensure scalability and a clean separation of concerns.

### The AI Backend: Python & LangGraph Orchestration
The backend is a complex State Machine built on LangGraph, completely moving past simple REST APIs or sequential LLM calls.

* **Cyclic Logic:** It re-evaluates a day's itinerary if the travel intensity is too high.
* **State Persistence:** It passes "Aura" and "Atmosphere" tokens across different nodes to maintain thematic consistency.
* **Parallel Research:** It fetches local weather, hidden gems, and transport options simultaneously.
* **FastAPI Foundation:** Handles the entry point, validation via Pydantic, and streaming responses.
* **Mock APIs (`mock_apis.py`):** Sophisticated simulations of real-world travel APIs (Flights, Hotels, Weather) allow for rapid development without incurring heavy costs.

### The Frontend: Next.js & Framer Motion
The frontend (`app-frontend`) is a Next.js 14+ application utilizing the App Router, designed with a premium "glass-editorial" aesthetic.

* **Cinematic Motion:** Every transition is handled by Framer Motion to ensure the UI feels fluid and alive.
* **Streaming UI:** Uses Server-Sent Events (SSE) to display real-time progress of the AI's "thinking" process.
* **Zero-Clutter Design:** A strict adherence to editorial layouts, removing intrusive buttons and functional clutter in favor of typography and imagery.

---

## 🧠 The AI "Brain": Narrative Engineering

The heart of the project lies in the `/app/graph` directory, where requests follow a meticulously designed flow.

* **The Researcher Node:** Instead of just finding hotels, it searches for seasonal intel (e.g., maple leaves in Kyoto), off-the-beaten-path hidden gems, and specific local culinary flavors.
* **The Synthesis Node (`synthesis.py`):** Acting as the "Chief Editor," it mandates unique headlines (e.g., "Miso-Glazed Mornings in a Zen Garden") and forbids generic titles. It ensures every activity includes a "Local Secret" or a "Travel Tip".
* **Prompt Amplification:** To overcome LLM "laziness," we disabled token limits in the synthesis node and explicitly demand the AI to "be expansive and verbose".
* **Multi-Modal Transport & Pacing:** Intelligently handles flights for long distances and trains for regional connectivity. If it detects a day with intense walking, it automatically triggers a "Wellness & Relaxation" slot to balance energy.

---

## 🎨 Design System: Glassmorphism & Typography

Following strict design guidelines, the platform avoids generic "tech purple" or "standard blue".

* **Deep Blacks & Surfaces:** The base utilizes `#000000` alongside semi-transparent glass layers.
* **Aura Colors:** Each destination is assigned a dynamic "Aura Color" (e.g., Cherry Blossom Pink for Japan) that tints the entire UI.
* **High-Contrast Typography:** It pairs Inter for readability with a custom serif Heading Italic for a Vogue-like, editorial feel.
* **The Utilitarian Trap Pivot:** We made the bold decision to strip away all budget-related UI. By removing the price tag, users focus on the value of the experience itself rather than the cost.

---

## ✨ Feature Spotlight: The Immersive Suite

* **Cinema Mode (`CinemaMode.tsx`):** A full-screen, high-impact slideshow that pulls the theme, headlines, and highlights of each day into a cinematic presentation to preview the trip.
* **Local Intel Widget (`LocalIntel.tsx`):** Built to fill the visual gap left by the removed budget charts, this uses a shuffle algorithm to rotate through Hidden Gems, Local Tips, and Must-Try Foods. It uses `AnimatePresence` to cross-fade between items, acting like a living concierge.
* **Audio Narration (`useAudioNarrator.ts`):** The AI literally speaks to you using high-quality speech synthesis, acting as a passionate travel companion providing an audio walkthrough of the trip.
* **Jet Lag Assistant (`useJetLag.ts`):** A sophisticated hook that calculates time offsets and provides a biological adaptation strategy (e.g., "Avoid caffeine for the next 4 hours").
* **Global Currency Support (`currencyUtils.ts`):** A robust formatting engine using `Intl.NumberFormat` supports real-time currency switching between USD and INR, catering specifically to the global luxury market.

---

## 📂 Codebase & File Structure

This repository acts as a public showcase for our private frontend and backend codebases.

### Frontend Directory (`app-frontend/src`)
* `/components/generation`: Complex result pages and streaming UI logic.
* `/components/itinerary`: Modular components for the sidebar, days, and special widgets.
* `/hooks`: Custom React hooks for fatigue scoring, jet lag, and SSE streaming.
* `/utils`: Currency conversion and general helpers.

### Backend Directory (`travelplan/app`)
* `/graph`: The LangGraph state machine definition.
* `/services`: Mock data providers and core logic.
* `/schemas`: Pydantic models ensuring strict data contracts between Python and TypeScript.

### Appendix: Key File Map

| File | Purpose |
| :--- | :--- |
| `ItineraryResult.tsx` | Main editorial layout and narrative orchestrator. |
| `synthesis.py` | The backend logic that generates the story. |
| `LocalIntel.tsx` | Discovery widget for hidden gems and foods. |
| `CinemaMode.tsx` | Full-screen cinematic preview experience. |
| `usePlanStream.ts` | Handles the real-time SSE connection to the backend. |
| `currencyUtils.ts` | Global formatting and conversion engine. |
| `types/itinerary.ts` | The source of truth for all data structures. |
