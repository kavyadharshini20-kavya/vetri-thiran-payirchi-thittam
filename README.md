# FitBuddy - AI Fitness Plan Generator (FastAPI + Gemini)

## Setup (VS Code)
1. Open the `fitbuddy` folder in VS Code (File > Open Folder). Install the **Python** extension.
2. Terminal > New Terminal, then:
   ```
   python -m venv venv
   venv\Scripts\activate          # Windows
   source venv/bin/activate       # macOS / Linux
   pip install -r requirements.txt
   ```
3. Select the interpreter: Ctrl+Shift+P > "Python: Select Interpreter" > the `venv` one.
4. Copy `.env.example` to `.env` and paste your key from https://aistudio.google.com/app/apikey
5. Run from the project root (the `fitbuddy` folder):
   ```
   uvicorn app.main:app --reload
   ```
6. Open http://127.0.0.1:8000 (app) and http://127.0.0.1:8000/docs (API docs).

## Endpoints
| Method | Path | Purpose |
|---|---|---|
| GET | `/` | Input form |
| POST | `/generate-workout` | Form submit: plan + tip + save |
| POST | `/submit-feedback` | Form submit: update plan |
| GET | `/view-all-users` | Admin dashboard |
| POST | `/delete-user/{id}` | Admin delete |
| POST | `/generate-workout/gemini` | API: plan only |
| GET | `/nutrition-tip?goal=...` | API: Flash tip |
| POST | `/generate-plan` | API: save user + plan |
| POST | `/update-plan/{user_id}` | API: feedback update |
