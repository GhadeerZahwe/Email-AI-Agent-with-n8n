# 📧 Email Agent Workflow Assistant

This project is an **Email Workflow Assistant** built using **[n8n](https://n8n.io/)**.  
It acts as an **AI-powered personal email assistant** to handle messages, reply automatically, perform **live web searches via Perplexity AI**, manage Google Calendar events, and enforce strict business boundaries.

<img width="1914" height="870" alt="image" src="https://github.com/user-attachments/assets/eb66d964-3680-44a5-bfd4-72ca43b9fd4b" />

---

## 🚀 Overview

The **Email Agent Workflow Assistant** is designed to:
- **Reply to emails** with context-aware professional answers.  
- **Research topics** and provide **resources + live web search results** using **Perplexity AI**.  
- **Create, update, fetch, and delete calendar events** directly in Google Calendar.  
- **Respect privacy & business rules** (no sensitive data leaks, no meetings outside working hours).  
- **Automate communication** while staying reliable, structured, and professional.  

---

## 🧪 Testing Guide

1. **Ask about AI impact** → Expect research-based reply.  
<img width="1620" height="850" alt="a1" src="https://github.com/user-attachments/assets/7ae2be8c-e3cd-42cf-b7c2-4d2ac86a7fd0" />
<img width="1597" height="855" alt="a2" src="https://github.com/user-attachments/assets/31e0ab59-bbba-48c0-bd58-d84e9bcab3f3" />

2. **Request resources** → Agent performs **live web search** via Perplexity.  
<img width="1607" height="862" alt="a3" src="https://github.com/user-attachments/assets/9cb24194-5897-440b-996a-47902e6e7ee4" />

3. **Book meeting** → Suggests working-hour slots, creates event.  
<img width="1615" height="808" alt="a4" src="https://github.com/user-attachments/assets/2cbd7294-5de5-44b9-a5ae-2c72c8134e54" />

4. **Confirm meeting** → Event saved in Google Calendar.  
<img width="1615" height="622" alt="a5" src="https://github.com/user-attachments/assets/4875edcd-456e-4658-ab86-0e93d83e4331" />
<img width="1599" height="706" alt="a6" src="https://github.com/user-attachments/assets/3a7d5313-94ec-4ea3-af2c-cd0c6f3ec11d" />

5. **Update meeting** → Reschedules successfully.  
<img width="1611" height="804" alt="a7" src="https://github.com/user-attachments/assets/b882d1a3-e9de-4124-b87a-b8a988b1b24c" />
<img width="1617" height="804" alt="a8" src="https://github.com/user-attachments/assets/0709dbe2-8870-450e-b261-b516de296ca3" />

6. **Cancel meeting** → Removes event from Calendar.  
<img width="1618" height="662" alt="a9" src="https://github.com/user-attachments/assets/cf6cf7b6-6133-4898-8ad3-807e9e7345d1" />
<img width="1613" height="806" alt="a10" src="https://github.com/user-attachments/assets/75d97bc6-26c8-4b08-bbe9-d911cca2bb26" />

7. **Boundary Test**: ask for Sunday / 7 PM → Agent rejects & suggests alternatives.  
<img width="1598" height="850" alt="a12" src="https://github.com/user-attachments/assets/83685f66-ab97-4951-8dfe-eaa36ad77f03" />

8. **Privacy Test**: ask for attendees → Agent refuses politely.  
<img width="1612" height="757" alt="a11" src="https://github.com/user-attachments/assets/dfebff43-514a-481b-a86e-73c1999e1e43" />

---

## 🛠️ Technology Stack

- **[n8n](https://n8n.io/)** → Workflow automation engine.  
- **[OpenAI GPT-4 (via API)](https://platform.openai.com/)** → Natural language understanding & response generation (~$5 for testing).
  <img width="1561" height="692" alt="image" src="https://github.com/user-attachments/assets/4034cabc-c25b-47ef-8ef4-068fc327c78e" />
<img width="1898" height="771" alt="image" src="https://github.com/user-attachments/assets/c16b6d4c-ef60-4e8f-8cbc-133355446db3" />

- **[Perplexity API](https://www.perplexity.ai/)** → Live web search & research tool (~$5 for several thousand queries).
  <img width="1413" height="741" alt="image" src="https://github.com/user-attachments/assets/abd01f81-8919-4e8f-ade5-dffbd86975c9" />

- **[Google Cloud APIs](https://console.cloud.google.com/)** → Gmail & Calendar integration.
  <img width="1908" height="855" alt="image" src="https://github.com/user-attachments/assets/dddddc25-0806-4024-9dcb-62147b135d7b" />
  <img width="1910" height="881" alt="image" src="https://github.com/user-attachments/assets/cce63750-94fd-498e-8794-09f549d92229" />

- **[Coolify](https://coolify.io/)** → Self-hosted platform with OS panel.
  <img width="1919" height="778" alt="image" src="https://github.com/user-attachments/assets/c9d604e8-a3c2-4d5e-a2a5-a1d7baa28179" />
 <img width="1868" height="404" alt="image" src="https://github.com/user-attachments/assets/454d5307-a680-43eb-9d18-36edc44b7730" />

- **[Hostinger VPS](https://www.hostinger.com/vps-hosting)** → Server hosting (recommended plan: **KVM2**).
  <img width="1051" height="483" alt="image" src="https://github.com/user-attachments/assets/afcd98d8-7335-4bd0-968e-ef7c27ebd92d" />
  <img width="392" height="542" alt="image" src="https://github.com/user-attachments/assets/c8777a55-5a7f-4e81-865a-f5a81da84da4" />

- **[GoDaddy](https://www.godaddy.com/)** → Domain registration & DNS setup.  

---

## 📂 Workflow Sections

### 1. **Role & Context**
- The agent role: *AI-powered email & scheduling assistant*.  
- Processes incoming emails, interprets intent, and takes appropriate actions.  
- Always includes **context**:
  - Current date/time (Asia/Beirut).  
  - Email metadata (sender, subject, time received).  

---

### 2. **Instructions & Rules**
- ✅ Allowed:
  - Reply to professional emails.  
  - Provide research insights using **Perplexity AI**.  
  - Create, update, delete, and fetch Google Calendar events.  

- ❌ Restricted:
  - Do not share **sensitive meeting data**.  
  - Do not schedule meetings **outside business hours (9 AM–5 PM, Mon–Fri)**.  
  - Do not schedule meetings on weekends.  
  - Do not reply to **promotions, spam, or irrelevant content**.  

---

### 3. **Examples from Testing**
- 📩 **General Inquiry** → Agent replied with statistics & insights.  
- 🔎 **Resource Request** → Agent performed **live Perplexity search** and provided article links.  
- 📅 **Book Meeting** → Suggested available slots & created calendar event.  
- 🔄 **Update Meeting** → Rescheduled event successfully.  
- ❌ **Cancel Meeting** → Deleted calendar event on request.  
- 📂 **Fetch Meetings** → Retrieved upcoming events.  
- 🔒 **Privacy Test** → Refused to share confidential meeting attendees.  
- 🕒 **Boundary Test** → Rejected out-of-hours or weekend meetings.  

---

## 🌍 Hosting & Deployment

### Hosting Setup
- VPS: [Hostinger KVM2](https://www.hostinger.com/vps-hosting) → Balanced performance, price, scalability.  
- Choose a region closest to your users (e.g., France or Germany for Lebanon-based clients).  

### Coolify Installation
1. Deploy **Coolify OS with Panel**.  
2. Add project → `n8n` → set **Production** environment.  
3. Add **n8n with Postgres** (recommended for stability).  
4. Replace default domain with **GoDaddy custom domain**.  
5. Enable **SSL (https)**.  

### Activation & Security
- Request free **n8n license key** and activate via email.  
- Enable **2FA** in n8n for security.  
- Store sensitive keys in encrypted environment variables.  

---

## 📜 Notes on Workflow

- Workflow **triggers automatically** on incoming email (via Gmail Trigger / IMAP).  
- Generates AI responses using **OpenAI GPT + Perplexity**.  
- Performs **calendar operations** (create, update, delete, fetch).  
- **Critical checks**:
  - Reject spam/irrelevant messages.  
  - Block sensitive data leaks.  
  - Enforce business-hour scheduling.  

---

## 🔗 Useful Links
- **n8n** → https://n8n.io/  
- **OpenAI API** → https://platform.openai.com/  
- **Perplexity API** → https://www.perplexity.ai/  
- **Google Cloud APIs** → https://console.cloud.google.com/  
- **Hostinger VPS** → https://www.hostinger.com/vps-hosting  
- **GoDaddy Domains** → https://www.godaddy.com/  
- **Coolify** → https://coolify.io/  

---

## ✅ Why This Matters
- Automates **email replies & research** with AI.  
- Handles **end-to-end meeting scheduling** (create, update, cancel, fetch).  
- Enforces **privacy, security, and working-hour boundaries**.  
- Provides **scalable production deployment** with Postgres + VPS.  
- Fully **self-hosted**, ensuring control & privacy.

---

## 📂 Workflow Import & Setup

The **Email Agent Workflow** is provided as a **JSON file** that can be directly imported into **n8n**.  

### Steps to Import:
1. Open your **n8n instance** in a browser.  
2. Click on the **three dots** (top-right corner).  
3. Select **Import from File**.  
4. Choose the provided **workflow JSON file** and import.  

### Personalize the AI Agent:
- Open the **AI Agent node** inside n8n.  
- Update the **prompt** to be personalized for you.   

- Save the workflow after updating the prompt.  

### Start Using:
- Once imported and personalized, the workflow runs **automatically** on incoming emails.  
- Calendar operations, web searches, and AI replies are ready to use.  
- No further setup is required after API keys and environment variables are configured.


