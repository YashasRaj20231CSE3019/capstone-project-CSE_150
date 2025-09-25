# NewsLensAI - AI-Powered News Analysis Platform

A Flask-based web application that provides AI-powered sentiment analysis and community feedback for news stories. Features include multi-dimensional feedback ratings, bias detection, and real-time analytics.

## Features

- **AI Sentiment Analysis**: Automated sentiment analysis of feedback comments
- **Multi-dimensional Feedback**: Rate accuracy, bias, relevance, and local impact
- **Story Management**: Submit and manage news stories with image uploads
- **Analytics Dashboard**: Real-time insights and statistics
- **Responsive Design**: Works on desktop and mobile devices

## Prerequisites

- Python 3.11 or higher
- pip (Python package installer)

## Installation

### Windows

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd NewsLensAI
   ```

2. **Create virtual environment**
   ```bash
   python3 -m venv venv
   ```

3. **Activate virtual environment**
   ```bash
   venv\Scripts\activate

   pip3 install vaderSentiment
   ```

4. **Install dependencies**
   ```bash
   pip3 install -r requirements.txt
   ```

### macOS

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd NewsLensAI
   ```

2. **Create virtual environment**
   ```bash
   python3 -m venv venv
   ```

3. **Activate virtual environment**
   ```bash
   source venv/bin/activate

   pip3 install vaderSentiment
   ```

4. **Install dependencies**
   ```bash
   pip3 install -r requirements.txt
   ```

## Running the Application

### Start the Server

1. **Activate virtual environment** (if not already activated)
   - Windows: `venv\Scripts\activate`
   - macOS: `source venv/bin/activate`

2. **Run the application**
   ```bash
   python3 app.py
   ```

3. **Access the application**
   - Open your web browser
   - Go to: `http://localhost:5000`

### Stop the Server

- **Windows**: Press `Ctrl + C` in the terminal
- **macOS**: Press `Ctrl + C` in the terminal

### If the server doesn't stop

- **Windows**:
  ```bash
  taskkill /f /im python.exe
  ```
- **macOS**:
  ```bash
  pkill -f python
  ```

## Project Structure

```
NewsLensAI/
├── app.py                 # Main application entry point
├── database.py            # Database configuration
├── models.py              # Database models
├── routes.py              # Application routes
├── ai_analysis.py         # AI sentiment analysis
├── requirements.txt       # Python dependencies
├── venv/                  # Virtual environment
├── instance/
│   └── news_lens.db      # SQLite database
├── static/                # Static files (CSS, JS, images)
│   ├── css/
│   ├── js/
│   ├── uploads/          # User uploaded images
│   ├── hero.jpeg         # Hero section image
│   └── ai.jpeg           # AI analysis image
└── templates/             # HTML templates
```

## Database

The application uses SQLite database stored in `instance/news_lens.db`. The database is automatically created when you first run the application.

### Database Tables

- **news_story**: Stores news articles with metadata
- **feedback**: Stores user feedback and ratings
- **story_category**: Stores story categories

## File Uploads

The application supports three types of image uploads for stories:
- **Main Image**: Primary story image (recommended: 1200x800px)
- **Thumbnail**: Small preview image (recommended: 400x300px)
- **Gallery Image**: Additional image for gallery view (recommended: 800x600px)

Uploaded files are stored in `static/uploads/` directory.

## Troubleshooting

### Port 5000 already in use

**Windows:**
```bash
netstat -ano | findstr :5000
taskkill /PID <PID> /F
```

**macOS:**
```bash
lsof -ti:5000 | xargs kill -9
```

### Virtual environment issues

**Windows:**
```bash
deactivate
Remove-Item -Recurse -Force venv
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

**macOS:**
```bash
deactivate
rm -rf venv
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### Database issues

Delete the database file and restart:
```bash
rm instance/news_lens.db
python app.py
```

## Development

### Adding new features

1. Create feature branch
2. Make changes
3. Test locally
4. Submit pull request

### Code structure

- **Routes**: Define in `routes.py`
- **Models**: Define in `models.py`
- **Templates**: Add to `templates/` directory
- **Static files**: Add to `static/` directory

## License

This project is licensed under the YASHLINKS License.
