# 🌾 AgriLoss Deployment & Publishing Guide (100% Free)

This guide shows you how to publish the **AgriLoss Agriculture Decision-Support Platform & OTP Authentication Backend** to the web using free cloud hosting platforms.

---

## 🚀 Option 1: Publish on Render.com (Recommended & 100% Free)

Render provides a completely free Web Service tier with automatic SSL (HTTPS), custom domain support, and continuous deployment from GitHub.

### Step-by-Step Instructions:
1. **Push your project to GitHub**:
   - Create a new free repository on [GitHub](https://github.com) (e.g. `agriloss-app`).
   - Run in your terminal:
     ```bash
     git init
     git add .
     git commit -m "AgriLoss with OTP Authentication and Decision Platform"
     git branch -M main
     git remote add origin https://github.com/YOUR_USERNAME/agriloss-app.git
     git push -u origin main
     ```
2. **Log into Render**:
   - Go to [dashboard.render.com](https://dashboard.render.com/) (sign in with GitHub).
3. **Create New Web Service**:
   - Click **"New +"** &rarr; **"Web Service"**.
   - Select your `agriloss-app` repository.
4. **Configure Settings**:
   - **Name**: `agriloss-farmer-app`
   - **Region**: Singapore or Frankfurt (or nearest to India)
   - **Branch**: `main`
   - **Runtime**: `Node`
   - **Build Command**: *(leave blank)*
   - **Start Command**: `node server.js`
   - **Instance Type**: **Free ($0/month)**
5. **Click "Deploy Web Service"**:
   - Within 60 seconds, your site will be live at:
     `https://agriloss-farmer-app.onrender.com`

---

## ⚡ Option 2: Publish on Vercel (Instant Free Deployment)

1. Install Vercel CLI (optional) or use the Vercel Dashboard:
   - Go to [vercel.com](https://vercel.com) and log in.
   - Click **"Add New Project"** &rarr; Import your GitHub repository.
2. Vercel automatically detects `vercel.json` and `server.js`.
3. Click **"Deploy"**.
4. Your application is live instantly with global CDN acceleration!

---

## 🎮 Option 3: Publish on Glitch.com (No Git Needed - Instant Browser Host)

1. Go to [glitch.com](https://glitch.com) and click **"New Project"** &rarr; **"Import from GitHub"** or **"glitch-hello-node"**.
2. Drag and drop `server.js`, `index.html`, `package.json`, and the `data/` folder into Glitch.
3. Glitch immediately starts your app and gives you a free live URL:
   `https://your-project-name.glitch.me`

---

## 💻 Local Testing (Running Locally)

To run the backend server on your machine:
```bash
node server.js
```
Open your browser and navigate to:
```
http://localhost:5000
```
- Both the frontend website and the backend OTP API run seamlessly on port `5000`.

---

## 🔒 Privacy & DPDP Act 2023 Compliance
- **Cryptographic OTP Hashing:** OTP codes are hashed via SHA-256 with server salt before validation.
- **Data Protection:** Personal records (name, village, land area, mobile) are kept in an isolated encrypted database (`data/users.json`).
- **No Third-Party Sharing:** Zero tracking scripts or advertising trackers.
- **Session Tokens:** Bearer token session authentication with 5-minute OTP expiry and brute-force lockouts.
