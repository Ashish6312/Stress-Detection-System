# 🧠 AI-Powered Mental Wellness & Stress Detection System

A comprehensive Django-based web application for mental health monitoring and stress detection using Machine Learning. Features include ML-based stress prediction, mood tracking, task management, journaling, and wellness resources.

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Django](https://img.shields.io/badge/Django-5.2-green)
![ML](https://img.shields.io/badge/ML-Scikit--learn-orange)
![License](https://img.shields.io/badge/License-MIT-yellow)

## 🌟 Features

### 🤖 ML-Based Stress Detection
- **Random Forest Classifier** with 95% accuracy
- Analyzes 15 physiological features (BVP, EDA, Respiration, Temperature)
- Real-time predictions with confidence scores
- Trained on WESAD dataset

### 📊 Interactive Dashboard
- Real-time stress trend visualization with Chart.js
- Mood tracking with historical data
- ML prediction history with confidence scores
- Comprehensive analytics and statistics

### 📋 Stress Assessment Questionnaire
- 10 comprehensive questions covering:
  - Daily overwhelm and coping ability
  - Mood swings and anxiety
  - Concentration and decision-making
  - Sleep patterns
  - Exercise frequency
  - Work/academic pressure
  - Social media usage
  - Physical symptoms
  - Substance consumption
  - Emotional support
- Interactive line-filling interface
- Instant results with recommendations

### 😊 Mood Tracking
- Daily mood scale (1-10)
- Notes and observations
- Pattern recognition over time
- Visual mood history

### ✅ Task Management
- Create and organize daily tasks
- Set due dates and priorities
- Track completion status
- Reduce stress through better organization

### 📝 Personal Journal
- Private or anonymous entries
- Community sharing option
- Safe space for self-reflection
- Confidential and secure

### 📚 Wellness Resources
- Breathing exercises
- Stress management articles
- Professional support links
- Emergency helplines

## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- pip package manager
- Git

### Local Installation

1. **Clone the repository**
```bash
git clone https://github.com/Ashish6312/Stress-Detection-System.git
cd Stress-Detection-System/stress_project_extended
```

2. **Run Quick Start (Windows)**
```cmd
quickstart.bat
```

**OR Manual Setup:**

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Setup and train ML model
python setup_ml.py

# Create superuser (optional)
python manage.py createsuperuser

# Run the server
python manage.py runserver
```

3. **Access the application**
```
http://localhost:8000
```

## 🌐 Deployment to Render

### Quick Deploy

1. **Push to GitHub** (Already done!)
```bash
git add .
git commit -m "Ready for deployment"
git push origin main
```

2. **Deploy on Render**
   - Go to [Render Dashboard](https://dashboard.render.com)
   - Click "New +" → "Blueprint"
   - Connect your GitHub repository
   - Render will auto-detect `render.yaml`
   - Click "Apply" to deploy

3. **Configure Environment Variables**
   - `SECRET_KEY` - Auto-generated
   - `DATABASE_URL` - Auto-configured
   - `ALLOWED_HOSTS` - Add your Render URL

4. **Create Superuser**
   - Go to Render Shell
   - Run: `python manage.py createsuperuser`

### Manual Render Setup

1. **Create PostgreSQL Database**
   - New + → PostgreSQL
   - Name: `stress-detection-db`
   - Copy Internal Database URL

2. **Create Web Service**
   - New + → Web Service
   - Connect repository
   - **Build Command:** `./build.sh`
   - **Start Command:** `gunicorn stress_project.wsgi:application`

3. **Environment Variables**
   - `SECRET_KEY`: Generate secure key
   - `DEBUG`: `False`
   - `DATABASE_URL`: Paste from step 1
   - `ALLOWED_HOSTS`: Your Render URL
   - `PYTHON_VERSION`: `3.11.0`

## 📁 Project Structure

```
Stress-Detection-System/
├── model/                          # ML model and training data
│   ├── model.ipynb                # Jupyter notebook
│   ├── data/
│   │   └── merged.csv             # Training dataset
│   └── trained_model.sav          # Saved model
│
├── stress_project_extended/       # Django application
│   ├── predictor/                 # Main app
│   │   ├── model/                 # Trained ML model
│   │   │   ├── train_model.py    # Training script
│   │   │   ├── stress_model.joblib
│   │   │   ├── labels.json
│   │   │   └── features.json
│   │   ├── ml_predictor.py       # Prediction logic
│   │   ├── models.py             # Database models
│   │   ├── views.py              # View functions
│   │   ├── forms.py              # Form definitions
│   │   ├── urls.py               # URL routing
│   │   └── static/               # CSS, JS files
│   │
│   ├── templates/                # HTML templates
│   │   └── predictor/
│   │       ├── base.html
│   │       ├── home.html
│   │       ├── dashboard.html
│   │       ├── ml_predict.html
│   │       ├── ml_result.html
│   │       ├── questions.html
│   │       ├── result.html
│   │       ├── mood_add.html
│   │       ├── tasks_list.html
│   │       ├── journal_list.html
│   │       ├── journal_add.html
│   │       └── resources.html
│   │
│   ├── stress_project/           # Django settings
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   │
│   ├── manage.py
│   ├── requirements.txt
│   ├── build.sh                  # Render build script
│   ├── render.yaml               # Render config
│   ├── runtime.txt               # Python version
│   └── Procfile                  # Process file
│
└── README.md                     # This file
```

## 🎯 Usage Guide

### 1. Sign Up / Login
- Create a new account or login
- Secure authentication system

### 2. ML Stress Prediction
- Navigate to "ML Prediction"
- Enter physiological sensor data
- Get instant prediction with confidence scores

**Sample Data for Testing:**
```
BVP: mean=0.025, std=0.015, peak_freq=1.2
EDA: phasic_mean=0.05, phasic_min=0.01, smna_min=0.02, tonic_mean=0.1
Resp: mean=0.3, std=0.05
TEMP: mean=32.5, std=0.2, slope=0.001
Demographics: age=27, height=175, weight=70
```

### 3. Take Stress Assessment
- Click "Questionnaire"
- Answer 10 comprehensive questions
- Click on the interactive scale (0-10)
- Get instant results with recommendations

### 4. Track Your Mood
- Add daily mood entries (1-10 scale)
- Add notes about your day
- View mood history on dashboard

### 5. Manage Tasks
- Create daily tasks
- Set due dates
- Mark as complete
- Stay organized

### 6. Journal Your Thoughts
- Write private or anonymous entries
- Share with community (optional)
- Reflect on your mental health journey

### 7. Access Resources
- Breathing exercises
- Stress management tips
- Emergency support links

## 🧪 ML Model Details

### Algorithm
- **Type:** Random Forest Classifier
- **Accuracy:** 94.92%
- **Features:** 15 physiological and demographic features
- **Dataset:** WESAD (Wearable Stress and Affect Detection)

### Features Used
1. BVP_mean, BVP_std, BVP_peak_freq
2. EDA_phasic_mean, EDA_phasic_min, EDA_smna_min, EDA_tonic_mean
3. Resp_mean, Resp_std
4. TEMP_mean, TEMP_std, TEMP_slope
5. age, height, weight

### Prediction Classes
- **Amused (0):** Relaxed, positive emotional state
- **Neutral (1):** Baseline, normal state
- **Stressed (2):** High stress, negative emotional state

## 🛠️ Technologies Used

### Backend
- **Django 5.2** - Web framework
- **Python 3.11** - Programming language
- **SQLite/PostgreSQL** - Database
- **Gunicorn** - WSGI server

### Machine Learning
- **Scikit-learn** - ML library
- **NumPy** - Numerical computing
- **Pandas** - Data manipulation
- **Joblib** - Model serialization

### Frontend
- **Bootstrap 5** - CSS framework
- **Chart.js** - Data visualization
- **JavaScript** - Interactivity
- **HTML5/CSS3** - Structure and styling

### Deployment
- **Render** - Cloud platform
- **WhiteNoise** - Static file serving
- **PostgreSQL** - Production database

## 📊 Features Highlights

### Beautiful UI
- Modern gradient design
- Smooth animations and transitions
- Responsive layout (mobile, tablet, desktop)
- Interactive elements

### Real-time Updates
- Live clock on dashboard
- Instant ML predictions
- Dynamic form validation
- Interactive scales

### Security
- Login required for sensitive features
- User data isolation
- CSRF protection
- Secure cookies in production
- HTTPS enabled

### Performance
- Optimized database queries
- Static file compression
- Efficient ML model loading
- Fast response times

## 🔧 Configuration

### Environment Variables

**Required for Production:**
- `SECRET_KEY` - Django secret key
- `DEBUG` - Set to `False` in production
- `DATABASE_URL` - PostgreSQL connection string
- `ALLOWED_HOSTS` - Comma-separated list of allowed hosts

**Optional:**
- `PYTHON_VERSION` - Python version (default: 3.11.0)

### Database

**Development:** SQLite (default)
**Production:** PostgreSQL (recommended)

## 🧪 Testing

### Test ML Model
```bash
cd stress_project_extended
python test_model.py
```

### Run Django Tests
```bash
python manage.py test
```

### Check for Issues
```bash
python manage.py check
```

## 📝 API Endpoints

- `/` - Home page
- `/signup/` - User registration
- `/login/` - User login
- `/logout/` - User logout
- `/dashboard/` - User dashboard
- `/ml-predict/` - ML prediction form
- `/questions/` - Stress questionnaire
- `/mood/add/` - Add mood entry
- `/tasks/` - Task management
- `/journal/` - Journal entries
- `/journal/add/` - Add journal entry
- `/resources/` - Wellness resources
- `/admin/` - Admin panel

## 🐛 Troubleshooting

### Model Not Loading
```bash
cd stress_project_extended
python setup_ml.py
```

### Database Errors
```bash
python manage.py migrate
```

### Static Files Not Loading
```bash
python manage.py collectstatic --no-input
```

### Import Errors
```bash
pip install -r requirements.txt
```

### Port Already in Use
```bash
python manage.py runserver 8080
```

## 🚀 Performance Optimization

### For Production
- Use PostgreSQL instead of SQLite
- Enable caching (Redis/Memcached)
- Use CDN for static files
- Optimize database queries
- Enable gzip compression

### Render Free Tier
- Services spin down after 15 min inactivity
- First request takes ~30 seconds
- 512 MB RAM limit
- Shared CPU

### Upgrade Options
- **Starter:** $7/month (always-on)
- **Standard:** $25/month (better performance)

## 📈 Future Enhancements

- [ ] Real-time sensor integration
- [ ] Mobile app (React Native)
- [ ] REST API for third-party integration
- [ ] Advanced analytics and insights
- [ ] Personalized recommendations
- [ ] Multi-language support
- [ ] Social features and community
- [ ] Therapist dashboard
- [ ] Export data functionality
- [ ] Integration with wearables

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Developer

**Ashish Kumar**
- GitHub: [@Ashish6312](https://github.com/Ashish6312)
- Project: [Stress Detection System](https://github.com/Ashish6312/Stress-Detection-System)

## 🙏 Acknowledgments

- WESAD dataset for training data
- Django framework and community
- Scikit-learn library
- Bootstrap for UI components
- Chart.js for visualizations
- Render for hosting platform

## 📞 Support

For issues, questions, or suggestions:
1. Open an issue on GitHub
2. Check existing documentation
3. Review troubleshooting section
4. Contact via GitHub

## 🌟 Star This Repository

If you find this project helpful, please give it a ⭐ on GitHub!

---

**Made with ❤️ for Mental Wellness**

Visit: [Live Demo](https://stress-detection-system-q3q4.onrender.com/) (Update with your Render URL)

---

## 📸 Screenshots

### Home Page
Beautiful landing page with feature highlights

### Dashboard
Comprehensive overview with charts and statistics

### ML Prediction
Interactive form for physiological data input

### Stress Assessment
10-question interactive questionnaire with line-filling interface

### Results
Detailed results with confidence scores and recommendations

---

## 🎓 Educational Purpose

This project is developed for educational and research purposes to demonstrate:
- Django web development
- Machine Learning integration
- Full-stack development
- Cloud deployment
- UI/UX design principles
- Mental health awareness

---

**Ready to improve mental wellness? Get started now!** 🚀
