<img width="550" height="250" alt="CelestialGlow_logo" src="https://github.com/user-attachments/assets/f461d2cb-42aa-4581-8999-6ecc64185fb9" />

# CelestialGlow
Your window to the cosmos.

**Celestial Glow** is a stargazing session booking application built with React and Django. 
Visitors can explore available sessions, book a time slot, and receive a personalized AI-generated booking confirmation. 
Google Calendar integration helps identify scheduling conflicts.

## Features
- **Session availability:** View upcoming stargazing sessions and their durations.
- **Online booking:** Reserve a session using a name and email address.
- **Double-booking prevention:** Prevent multiple bookings for the same time slot.
- **Google Calendar integration:** Check calendar availability and filter conflicting sessions.
- **AI booking confirmations:** Generate personalized confirmation messages using Google Gemini.
- **Timezone support:** Display session times in the Europe/Skopje timezone.
- **Admin dashboard:** Manage sessions and bookings through Django Admin.

## Tech Stack
- **Frontend:** React, JavaScript, Vite
- **Backend:** Python, Django, Django REST Framework
- **Database:** SQLite for local development
- **Calendar integration:** Google Calendar API and OAuth 2.0
- **AI integration:** Google Gemini API

## Project Structure
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

## How to Run Locally
**Prerequisites:** Python, Node.js, and npm.

### 1. Start the Django backend
Open a terminal in the project root directory (the folder containing manage.py).
**Step I:** Create a virtual environment (recommended) 
```bash
python -m venv venv
```
**Step II:** Activate the virtual environment
```bash
.\venv\Scripts\Activate.ps1
```
**Step III:** Install the required dependencies
```bash
pip install -r requirements.txt
```
**Step IV:** Prepare the database
```bash
python manage.py makemigrations           
python manage.py migrate
```
**Step 	V:** Create an administrator account
```bash
python manage.py createsuperuser
```
**Step VI:** Start the development server
```bash
python manage.py runserver
 ```
**Step VII:** The backend will be available at the endpoints and pages:
```bash
- Django Admin: http://127.0.0.1:8000/admin/    # Log In to Django Admin using the superuser credentials created in Step V.
- Bookings: http://127.0.0.1:8000/bookings/     # Handles booking requests.
- Slots: http://127.0.0.1:8000/slots/           # Retrieves available stargazing sessions.
```

### 2. Start the React frontend
Open a second terminal:
 ```bash
cd frontend     # Navigate to the frontend directory
npm install     # Install the frontend dependencies
npm run dev     # Start the development server
 ```
Open the URL provided by Vite, usually http://localhost:5173/

### 3. Configure integrations for AI-generated confirmations,
**Step 1:** Obtain a Gemini API key from Google AI Studio.
**Step 2:** Open Windows PowerShell in the project root directory and set the environment variable:
```bash
$env:GEMINI_API_KEY = "YOUR_GEMINI_API_KEY"
 ```
**Step 3:** Start the Django backend from the same PowerShell terminal
```bash
python manage.py runserver
```
Google Calendar requires a Google Cloud project, the Calendar API, OAuth credentials, and a configured callback URL.
**Keep API keys, OAuth credentials, and generated token files private!**

## AI Tools Used
- **Google Gemini API:** Powers the personalized booking confirmation messages.
- **ChatGPT and Claude:** Assisted with technical troubleshooting, debugging, and improving the integration between the frontend and backend.

## To Improve
- Add automated tests for booking validation and API endpoints.
- Implement e-mail notifications for booking confirmations and session reminders.
- Expand booking management with cancellation and rescheduling.


