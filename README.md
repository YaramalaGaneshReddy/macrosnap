# 🥗 MacroSnap

> **Snap it. Track it. Text yourself the results.**

MacroSnap is an AI-powered nutrition buddy built with [Streamlit](https://streamlit.io/). Upload a photo of your meal or describe what you're eating — MacroSnap uses **Google Gemini** to instantly estimate calories and macros. When you're done for the day, hit one button and get your full nutrition summary sent straight to your **WhatsApp**.

---

## ✨ Features

- 📸 **Photo or text input** — snap a meal photo or type what you ate
- 🤖 **AI-powered macro estimation** — calories, protein, carbs & fat via Gemini
- 💬 **Conversational chat UI** — multi-turn session tracks your whole day
- 📲 **WhatsApp summary** — one-click daily summary sent via Twilio
- ⚡ **Zero sign-up** — just enter your name and WhatsApp number to start

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend / App | [Streamlit](https://streamlit.io/) |
| AI Model | [Google Gemini](https://ai.google.dev/) (`gemini-3.5-flash`) |
| Messaging | [Twilio WhatsApp API](https://www.twilio.com/whatsapp) |

---

## 🚀 Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/YaramalaGaneshReddy/macrosnap.git
cd macrosnap
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure secrets

Copy the example secrets file and fill in your own API keys:

```bash
cp .streamlit/secrets.toml.example .streamlit/secrets.toml
```

Then edit `.streamlit/secrets.toml`:

```toml
GEMINI_API_KEY = "your-gemini-api-key"

TWILIO_ACCOUNT_SID   = "ACxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
TWILIO_AUTH_TOKEN    = "your-twilio-auth-token"
TWILIO_WHATSAPP_FROM = "+14155238886"       # Twilio Sandbox number
TWILIO_CONTENT_SID   = "HXxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
```

### 4. Run the app

```bash
streamlit run app.py
```

Open [http://localhost:8501](http://localhost:8501) in your browser.

---

## 🔑 Getting Your API Keys

### Google Gemini
1. Go to [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Create a new API key
3. Paste it as `GEMINI_API_KEY`

### Twilio WhatsApp
1. Sign up at [twilio.com](https://www.twilio.com/)
2. Go to **Console → Messaging → Try it out → Send a WhatsApp message**
3. Join the sandbox by sending the join code from your WhatsApp
4. Copy your **Account SID**, **Auth Token**, and the **sandbox number**
5. Create a **WhatsApp Content Template** in the Twilio Console and copy the **Content SID**

---

## 📁 Project Structure

```
macrosnap/
├── app.py                        # Main Streamlit application
├── prompts.py                    # AI system prompt & message templates
├── requirements.txt              # Python dependencies
└── .streamlit/
    ├── secrets.toml              # 🔒 Your local secrets (never committed)
    └── secrets.toml.example      # Safe template to share
```

---

## 🔒 Security

- **Never commit** `.streamlit/secrets.toml` — it is listed in `.gitignore`
- Use the provided `secrets.toml.example` as a reference template
- Rotate your API keys immediately if they are ever accidentally exposed

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
