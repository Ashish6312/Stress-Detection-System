
AI-Ready Mental Wellness & Stress Monitoring System (Extended)
Includes:
1. Mood Tracking Dashboard (history & simple Chart.js visualization)
2. Relaxation / Suggestion Page (personalized tips)
3. Daily Reminder / Task System (CRUD tasks)
4. Anonymous Feedback / Journal Section (private or anonymous)
5. ML integration hooks (placeholder to load joblib model)

Setup:
- python -m venv venv
- venv\Scripts\activate  (Windows) OR source venv/bin/activate
- pip install -r requirements.txt
- python manage.py migrate
- python manage.py createsuperuser
- python manage.py runserver

Notes:
- ML model is not included. Save your model at predictor/model/stress_model.joblib and predictor/model/labels.json
- Dashboard uses Chart.js (CDN) for client-side visualization.
