# 🍽️ NutriNavigator

### AI-Powered Personalized Diet, Restaurant & Workout Recommendation System

NutriNavigator is an AI-powered web application that generates personalized **diet recommendations, restaurant suggestions, meal ideas, and workout recommendations** based on an individual's lifestyle and dietary information.

The application uses **Flask** for the web interface, **LangChain** for prompt orchestration, and **Groq's Llama 3.3 70B model** to generate personalized recommendations.

---

## ✨ Features

* 🤖 **AI-powered recommendations**
* 🍴 Personalized restaurant suggestions
* ☀️ Breakfast recommendations
* 🌙 Dinner recommendations
* 💪 Workout recommendations
* 👤 Personalized according to age and gender
* ⚖️ Weight and height-based recommendations
* 🥗 Vegetarian / non-vegetarian preferences
* 🏥 Disease/health-condition input
* 🌎 Region-specific recommendations
* ⚠️ Allergy-aware recommendations
* 🍛 Food-preference customization
* 🎨 Clean and responsive Tailwind CSS interface
* 🚀 Simple Flask-based architecture

The application accepts information such as age, gender, weight, height, dietary preference, disease, region, allergies, and food type through a web form.

---

## 🏗️ Project Architecture

```text
NutriNavigator/
│
├── app.py
├── main.py
├── requirements.txt
├── README.md
├── .env
├── .gitignore
│
├── templates/
│   ├── index.html
│   └── result.html
│
└── static/
    └── ...
```

### Technology Stack

| Technology          | Purpose                              |
| ------------------- | ------------------------------------ |
| Python              | Core programming language            |
| Flask               | Web application framework            |
| LangChain           | LLM prompt and chain management      |
| Groq                | LLM API provider                     |
| Llama 3.3 70B       | Recommendation generation            |
| HTML5               | Frontend structure                   |
| Tailwind CSS        | Frontend styling                     |
| Regular Expressions | Parsing AI-generated recommendations |

The Flask application exposes a `/recommend` POST endpoint that receives the form data, executes the LLM chain, parses the generated sections, and renders the results page.

---

## 🔄 How It Works

```text
             ┌──────────────────┐
             │   User Opens App │
             └────────┬─────────┘
                      │
                      ▼
             ┌──────────────────┐
             │ Enter Personal   │
             │ & Food Details   │
             └────────┬─────────┘
                      │
                      ▼
             ┌──────────────────┐
             │ Flask /recommend │
             │      Endpoint    │
             └────────┬─────────┘
                      │
                      ▼
             ┌──────────────────┐
             │ LangChain Prompt │
             │    Template      │
             └────────┬─────────┘
                      │
                      ▼
             ┌──────────────────┐
             │ Groq + Llama 3.3 │
             │      70B         │
             └────────┬─────────┘
                      │
                      ▼
             ┌──────────────────┐
             │ AI Recommendations│
             └────────┬─────────┘
                      │
                      ▼
             ┌──────────────────┐
             │ Results Web Page │
             └──────────────────┘
```

The LLM is instructed to return four main recommendation categories:

* Restaurants
* Breakfast
* Dinner
* Workouts

---

## 📋 User Inputs

NutriNavigator currently accepts:

* **Age**
* **Gender**
* **Weight**
* **Height**
* **Vegetarian / Non-Vegetarian**
* **Disease / Health Condition**
* **Region**
* **Allergies**
* **Food Type / Preference**

These fields are submitted to the recommendation endpoint and passed into the AI prompt.

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/NutriNavigator.git
cd NutriNavigator
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

On macOS/Linux:

```bash
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure your API key

Create a `.env` file:

```env
GROQ_API_KEY=your_groq_api_key_here
```

**Never commit `.env` to GitHub.**

Add this to `.gitignore`:

```gitignore
.env
venv/
__pycache__/
*.pyc
```

### 5. Run the application

```bash
python app.py
```

Then open:

```text
http://127.0.0.1:5000
```

---

## 🔐 Environment Variables

The application should load the Groq API key from an environment variable rather than storing the secret directly in source code.

Example:

```python
import os
from dotenv import load_dotenv

load_dotenv()

llm_resto = ChatGroq(
    api_key=os.getenv("GROQ_API_KEY"),
    model="llama-3.3-70b-versatile",
    temperature=0.0
)
```

This is especially important before making the repository public.

---

## 📊 Recommendation Output

The result page organizes AI-generated recommendations into four sections:

### 🍴 Restaurants

Provides recommended restaurants based on the user's preferences and region.

### ☀️ Breakfast

Provides personalized breakfast suggestions.

### 🌙 Dinner

Provides personalized dinner suggestions.

### 💪 Workouts

Provides workout recommendations based on the supplied user information.

The frontend renders each recommendation category as a separate section.

---

## 🖥️ User Interface

The application uses Tailwind CSS to provide a clean responsive interface.

The main page presents the project as:

> **NutriNavigator: Personalized Diet, Restaurant & Workout Recommendations Using AI**

and provides a form for collecting the user's information.

---

## 🛠️ Future Improvements

Potential improvements include:

* [ ] Add calorie and macro-nutrient calculations
* [ ] Add lunch recommendations
* [ ] Add snack recommendations
* [ ] Generate complete weekly meal plans
* [ ] Add BMI calculation
* [ ] Add nutrition charts
* [ ] Add user authentication
* [ ] Store user profiles
* [ ] Add recommendation history
* [ ] Add database support
* [ ] Add restaurant API integration
* [ ] Add multilingual support
* [ ] Add downloadable meal plans
* [ ] Improve AI response validation
* [ ] Add automated tests
* [ ] Deploy with Docker
* [ ] Deploy to a cloud platform

---

## ⚠️ Disclaimer

NutriNavigator provides AI-generated recommendations for informational and educational purposes only.

The recommendations should **not be considered medical advice, diagnosis, or treatment**. Users with medical conditions, allergies, or specific nutritional requirements should consult a qualified healthcare professional or registered dietitian before making significant changes to their diet or exercise routine.

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch

```bash
git checkout -b feature/new-feature
```

3. Make your changes
4. Commit your changes

```bash
git commit -m "Add new feature"
```

5. Push your branch

```bash
git push origin feature/new-feature
```

6. Open a Pull Request

---


## ⭐ Support

If you find NutriNavigator useful, consider giving the repository a ⭐ on GitHub.

---

### Built with ❤️ using Python, Flask, LangChain, Groq, Llama, and Tailwind CSS.
