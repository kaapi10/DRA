# 👁️ Drishti AI Eye Agent — Dr. Agarwals

A Claude-powered AI ophthalmology agent with 5 modules:
- **Symptom Triage** — AI chat that triages, routes, and recommends care
- **Vision Tests** — Snellen, Colour Vision, Dry Eye OSDI, Amsler Grid
- **LASIK Checker** — 6-question eligibility wizard
- **Eye Photo Screen** — Claude Vision analyses uploaded eye photos
- **Book Appointment** — All Chennai branches + slot booking

---

## 🚀 Local Setup

### 1. Clone / download this folder

```bash
cd drishti-backend
```

### 2. Install dependencies

```bash
npm install
```

### 3. Set up your API key

```bash
cp .env.example .env
```

Open `.env` and replace `your_api_key_here` with your actual Anthropic API key:

```
ANTHROPIC_API_KEY=sk-ant-xxxxxxxxxxxxxx
PORT=3000
```

Get your key at: https://console.anthropic.com

### 4. Run locally

```bash
npm start
```

Open → **http://localhost:3000**

---

## 🌐 Deploy to Render (Recommended — free tier)

Render is the easiest way to deploy this with a persistent URL.

### Step-by-step:

1. Push this folder to a **GitHub repo** (make sure `.env` is in `.gitignore` ✅)

2. Go to [render.com](https://render.com) → **New Web Service**

3. Connect your GitHub repo

4. Configure:
   - **Environment:** Node
   - **Build Command:** `npm install`
   - **Start Command:** `node server.js`

5. Add environment variable:
   - Key: `ANTHROPIC_API_KEY`
   - Value: your key from console.anthropic.com

6. Click **Deploy**

Your Drishti agent will be live at `https://your-app.onrender.com` in ~2 minutes.

---

## 🌐 Deploy to Railway (Alternative)

1. Go to [railway.app](https://railway.app) → **New Project → Deploy from GitHub**

2. Connect your repo

3. Add variable: `ANTHROPIC_API_KEY=sk-ant-...`

4. Railway auto-detects Node.js and deploys. Done.

---

## 🌐 Deploy to Netlify (Static + Functions)

Netlify requires restructuring into serverless functions. Use Render or Railway for simpler deployment.

---

## 📁 Project Structure

```
drishti-backend/
├── server.js          ← Express server + API proxy
├── package.json
├── .env.example       ← Copy to .env and add your key
├── .env               ← NOT committed to git
├── .gitignore
├── netlify.toml
├── README.md
└── public/
    └── index.html     ← Full Drishti frontend (all 5 modules)
```

---

## 🔒 Security Notes

- The Anthropic API key lives only on the server — never exposed in the browser
- CORS is enabled for all origins (restrict in production if needed)
- No patient data is stored — all conversations are in-memory only
- Eye photos are processed and discarded — not saved to disk or database

---

## 📞 Emergency Override

The agent always surfaces Dr. Agarwals emergency line (**044-4444-5555**) for urgent symptoms regardless of AI response.

---

## 🏥 Built for Dr. Agarwals Eye Hospital
**Drishti** — AI-powered eye care, as easy as texting.
