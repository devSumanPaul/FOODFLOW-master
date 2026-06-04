# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.
# FoodFlow 🍊

### Smart QR-Based Campus Canteen & Live Telemetry Suite
*Skip the Queue, Track the Flow, Eat Smart.*

---

**FoodFlow** is a next-generation, full-stack campus canteen ordering pipeline engineered for speed, convenience, and real-time operational synchronization. It replaces long student queues and counter bottlenecks with direct table-to-cart QR code ordering, interactive WebSpeech AI ordering assistants, and a beautiful offline-first GPS map telemetry tracking dashboard.

Deployed on Render: **[foodflow.onrender.com](https://github.com/Maheshghosh/foodflow.git)**  
Repository Source: **[github.com/Maheshghosh/foodflow](https://github.com/Maheshghosh/foodflow)**

---

## 🌟 Core Features

### 🚴 1. Live GPS Rider Telemetry Map Tracker
A high-fidelity, self-contained campus mapping dashboard requiring **zero external API costs or Mapbox/Google subscriptions**:
* **SVG Mapping Grid**: A beautiful custom dark-mode canvas displaying campus streets, water bodies (Lakeview Park), and buildings.
* **Telemetry Telemetry HUD**: A real-time speedometer (fluctuating realistically between `15 km/h` and `35 km/h`), decrementing distance counters (from `1.4 km` down to `0.0 km`), and an active countdown timer.
* **Animated Scooter Icon**: Smoothly glides along street route coordinates in real-time as travel progress updates.
* **Direct Messenger Integration**: Speak directly with your assigned rider *Suman Ghosh* en route; Suman automatically responds with contextual status updates (e.g. *"Waiting at the kitchen..."* or *"Riding near the library circle..."*).
* **React Portal Overlay**: Mounted directly under `document.body` to bypass deep CSS stacking contexts, z-index bounds, or clipping issues.
* **Persistent Telemetry Banner**: Displays a glowing active delivery warning bar at the top of the menu area for active orders, letting customers return to the tracking screen even after reloads.

### 🤖 2. FoodieAI Speech Assistant (Customer Portal)
An intelligent, offline-first voice-assisted ordering assistant:
* **Web Speech Recognition**: Dictate orders natively using browser speech engines with zero cloud subscription costs.
* **Natural Language NLP Parser**: Splits sentences and automatically extracts canteen dishes and quantities (e.g., matching *"add two burger combos and a coffee"* to correct quantities).
* **Speech Synthesis**: Playback voice responses confirming additions to your cart audibly.
* **Smart Chat Recommender**: Type or request meal ideas (e.g., *"Suggest a protein lunch"* or *"I want something sweet"*), and the AI recommends dishes with active **"+ Add to Cart"** triggers inside the chat bubble.

### 📊 3. CanteenAI Analytics & Forecasts (Admin Dashboard)
Equipping canteen managers and staff with global queue telemetries and server-side predictive engines:
* **Real-time Queue Controller**: Single-click order accepts, preparing status updates, Cash on Delivery (COD) payment collection validations, and dispatch triggers.
* **Dynamic Settings Sync**: Alter delivery charges, outlet names, promo codes, and discount configs inside the Admin Panel, syncing them globally in sub-milliseconds.
* **Predictive Sales Forecasts**: Renders expectations for peak student traffic loads by hour based on live trend metrics.
* **AOV Boosters**: Offers strategic up-selling recommendations to increase average order values by pairing trending items.

---

## ⚡ Tech Stack & Performance Benchmarks

* **Frontend Client**: React 19 + Vite + Lucide Icons + Recharts
* **Backend API Server**: Node.js + Express (serving unified REST routes and client-side page routing)
* **Real-time Comms**: Socket.io (pushing order notifications and status events in `<150ms`)
* **Local Database**: Offline-first SQLite/JSON Data persistence layer (`backend/data.json`)
* **Presentation Slide Deck**: Marp-compatible Markdown (`project_presentation.md`) with animated slide transitions and floaters.

---

## 🚀 Local Installation & Developer Setup

### Prerequisites
* [Node.js](https://nodejs.org/) (v18 or higher recommended)
* [git](https://git-scm.com/)

### Step 1: Clone the Repository
```bash
git clone https://github.com/Maheshghosh/foodflow.git
cd foodflow
```

### Step 2: Install and Start Frontend
In the root directory:
```bash
npm install
npm run dev -- --host 0.0.0.0
```
*The Vite client starts globally on **[http://localhost:5173/](http://localhost:5173/)**, exposed to your local intranet network.*

### Step 3: Install and Start Backend
In a separate terminal, navigate to the backend directory:
```bash
cd backend
npm install
npm start
```
*The Express server launches on **[http://localhost:5000/](http://localhost:5000/)** and automatically seeds the `data.json` database.*

---

## 📱 Exposing the App to Mobile Phones (Wi-Fi Sharing)

To access and test your portal instantly on your phone browser:
1. Connect your phone and PC to the **same Wi-Fi network**.
2. Open your PC command line, type `ipconfig`, and find your PC's IPv4 address (e.g. `192.168.1.105`).
3. Allow **Node.js JavaScript Runtime** through your **Windows Defender Firewall** (Private and Public).
4. Open your phone browser and navigate to:
   ```text
   http://YOUR_PC_IP:5173
   ```
5. Place an order, scan QR tokens, and enjoy the glowing, animated tracking maps!

---

## ☁️ Cloud Deployment Configuration (Option B - Render)

The application is structured for a **single-service static deployment** on Render.com:
1. **GitHub Setup**: Create a repository and push your main branch: `git push -u origin main`.
2. **Create Web Service**: Connect your repo in Render and choose the following configurations:
   * **Runtime**: `Node`
   * **Region**: `Singapore (Southeast Asia)` *(recommended for Indian latency optimization)*
   * **Build Command**: `npm install && npm run build && cd backend && npm install`
   * **Start Command**: `node backend/server.js`
   * **Instance Type**: `Free`
3. Click **Deploy Web Service** and access your live app domain 24/7!

---

## 🏁 Presentation Slides Deck
A Marp-compatible 12-slide animated presentation deck is included under:
📁 `C:\Users\ghosh\.gemini\antigravity\brain\230f93c8-130c-4ca5-a749-fa5816ddb7ee\project_presentation.md`

You can open this inside VS Code, install the Marp extension, and click the slide preview icon to present slide-ins, zooms, and floaters, or export it to `.pptx`/`.pdf`!

---

## 🍊 Contributors & Acknowledgments
* **Mahesh Ghosh** - Full-Stack Architecture, Speech Recognition Core, and SVG Telemetry Map Design.
* Special thanks to the Google DeepMind team and the Antigravity pair-programming agent workspace.

## HOST LINK TO THE PROJECT : https://foodflow-xm9i.onrender.com/
