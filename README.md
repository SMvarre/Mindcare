# Mindcare
MindEase is a privacy-first mental wellness app for mood tracking, journaling, and self-care, operating offline-first with local data storage
MindEase: A Privacy-First Mental Wellness Application
MindEase is designed to be a calm, professional, and distraction-free space for users to track their mood, reflect, and engage in gentle self-care. This application prioritizes user privacy and performance, operating offline-first with all data stored locally on the device.
This is a hackathon-ready demo, optimized for mobile-first web, with a clean architecture for future scalability, including potential AI features.
Features
1.  Onboarding: Minimal screens explaining the privacy-first, offline-first philosophy, with optional name input and guest access.
2.  Quiet Daily Check-In: A simple slider (0-100) for "Mood Level" and an optional text note. Data is saved locally.
3.  Reflection Journal: Text-based journaling with optional prompts and a date-wise timeline view of past entries.
4.  Emotional Stability Index: A weekly emotional balance score presented as a minimal line/bar chart, focusing on trends.
5.  Gentle Self-Care Tracker: A daily checklist for self-care activities (e.g., drink water, short walk, breathing pause) with soft completion indicators and no gamification.
6.  Focus Mode: An optional grayscale UI toggle to reduce visual distractions.
7.  Privacy & Performance: Offline-first architecture, local storage by default, no social sharing, no ads, no paid APIs, fast launch, and smooth scrolling.
Tech Stack
*   Frontend: Vanilla JavaScript, HTML, CSS (mobile-first web)
*   Backend: Python (Flask microframework)
Architecture
Frontend (JavaScript)
The frontend is built using vanilla JavaScript to ensure minimal overhead and fast performance. It follows a component-based structure, managing UI rendering, user interactions, and local data storage. Themes (Light, Dark, Focus) are applied dynamically using CSS custom properties.
Backend (Python - Flask)
1.  Data Storage: The backend uses an in-memory dictionary as a simple data store for the hackathon demo. In a production environment, this would be replaced with a persistent local database (e.g., SQLite).
2.  Endpoints: Provides REST-style JSON endpoints for:
    *   POST /mood_checkin: Stores daily mood and notes.
    *   POST /journal_entry: Stores journal entries.
    *   GET /emotional_index: Calculates and returns weekly emotional stability based on mood data.
3.  Analysis: Handles the logic for aggregating mood data to derive the emotional stability index. This is designed to be extensible for future AI/ML integrations (e.g., sentiment analysis of journal entries).
JavaScript ↔ Python Integration
The frontend communicates with the Python backend via standard HTTP requests (POST for data submission, GET for analytics). Data is exchanged exclusively in JSON format. This clear separation of concerns ensures that the frontend is responsible for UI/UX, while the backend handles data processing, storage (for analysis), and computational logic.
Folder Structure
mindease/
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/       (Reusable UI components)
│   │   ├── styles/           (Theme definitions)
│   │   ├── utils/            (Storage and API helpers)
│   │   ├── pages/            (Application views/screens)
│   │   ├── App.js            (Main application logic and routing)
│   │   └── index.js          (Entry point)
├── backend/
│   ├── app.py                (Flask application, API endpoints)
│   ├── data_store.py         (In-memory data store for demo)
│   ├── analysis.py           (Logic for emotional index calculation)
│   ├── requirements.txt      (Python dependencies)
├── README.md
Steps to Run Locally
1. Backend Setup
Navigate to the backend directory:
cd mindease/backend
Install Python dependencies:
pip install -r requirements.txt
Run the Flask application:
python app.py
The backend will run on http://127.0.0.1:5000.
2. Frontend Setup
Navigate to the frontend directory:
cd mindease/frontend
This is a vanilla JavaScript application, so no build step is strictly required for development. You can serve it using any simple HTTP server. If you have Node.js installed, http-server is a good option:
Install http-server globally (if you don't have it):
npm install -g http-server
Serve the public directory:
http-server public
The frontend will typically be accessible at http://127.0.0.1:8080 (or another port if 8080 is taken).
3. Access the Application
Open your web browser and navigate to the frontend's address (e.g., http://127.0.0.1:8080).
Ensure both the frontend and backend servers are running for full functionality. Enjoy MindEase!
