<img width="550" height="250" alt="CelestialGlow_logo" src="https://github.com/user-attachments/assets/f461d2cb-42aa-4581-8999-6ecc64185fb9" />

# CelestialGlow
Your window to the cosmos.

**Celestial Glow** is a stargazing session booking application built with React and Django. 
Visitors can explore available sessions, book a time slot, and receive a personalized AI-generated booking confirmation. 
Google Calendar integration helps identify scheduling conflicts.

### Features
- **Session availability:** View upcoming stargazing sessions and their durations.
- **Online booking:** Reserve a session using a name and email address.
- **Double-booking prevention:** Prevent multiple bookings for the same time slot.
- **Google Calendar integration:** Check calendar availability and filter conflicting sessions.
- **AI booking confirmations:** Generate personalized confirmation messages using Google Gemini.
- **Timezone support:** Display session times in the Europe/Skopje timezone.
- **Admin dashboard:** Manage sessions and bookings through Django Admin.

### Tech Stack
- **Frontend:** React, JavaScript, Vite
- **Backend:** Python, Django, Django REST Framework
- **Database:** SQLite for local development
- **Calendar integration:** Google Calendar API and OAuth 2.0
- **AI integration:** Google Gemini API

### Project Structure
```bash
celestialglow/
├── celestialglow/          
├── celestialglowapp/       
├── frontend/              
├── manage.py
├── requirements.txt
├── .gitignore
└── README.md
```

### How to Run Locally
**Prerequisites:** Python, Node.js, and npm.

**1. Start the Django backend**

From the project root:
```bash
python -m venv venv
```
On Windows PowerShell, activate the environment:
```bash
.\venv\Scripts\Activate.ps1
```
Install dependencies and initialize the database:
 ```bash
pip install -r requirements.txt
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
 ```
The backend runs at http://127.0.0.1:8000/

**2. Start the React frontend**

Open a second terminal:
 ```bash
cd frontend
npm install
npm run dev
 ```
Open the URL provided by Vite, usually http://localhost:5173/

**3. Configure integrations**

For AI-generated confirmations, set your Gemini API key in Windows PowerShell:
```bash
$env:GEMINI_API_KEY = "YOUR_GEMINI_API_KEY"
 ```
Start Django from the same terminal so the application can access the environment variable.

Google Calendar requires a Google Cloud project, the Calendar API, OAuth credentials, and a configured callback URL.

**Keep API keys, OAuth credentials, and generated token files private!**

### AI Tools Used
- **Google Gemini API:** Powers the personalized booking confirmation messages.
- **ChatGPT and Claude:** Assisted with technical troubleshooting, debugging, and improving the integration between the frontend and backend.

### To Improve
- Add automated tests for booking validation and API endpoints.
- Expand booking management with cancellation and rescheduling.
- Implement e-mail notifications for booking confirmations and session reminders.

