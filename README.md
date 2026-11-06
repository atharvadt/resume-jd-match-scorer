# Resume–JD Match Scorer

A full-stack web application that analyzes resumes against job descriptions using Natural Language Processing (NLP), keyword matching, and TF-IDF scoring. It extracts text from PDF resumes, evaluates keyword relevance, and provides a match score along with suggestions for improvement.

## Overview

Resume–JD Match Scorer helps users identify how closely their resume aligns with a particular job description. Users can upload a PDF resume, enter a job description, and receive an analysis highlighting missing keywords and potential areas for improvement.

## Features

- **PDF Resume Upload:** Upload resumes in PDF format.
- **Text Extraction:** Extract resume content using PDF parsing.
- **Keyword Matching:** Compare resume keywords against job description keywords.
- **TF-IDF Scoring:** Apply TF-IDF to calculate keyword relevance.
- **Match Score:** Generate a combined resume–job description matching score.
- **Improvement Suggestions:** Identify missing keywords and provide suggestions to improve resume relevance.
- **Interactive Dashboard:** Display analysis results through a simple dashboard.

## Tech Stack

| Category | Technologies |
|---|---|
| Frontend | React.js, JavaScript, Tailwind CSS |
| Backend | Node.js, Express.js |
| NLP | Natural, Tokenization, TF-IDF |
| PDF Processing | pdf-parse |
| File Upload | Multer |
| Deployment | Render |

## Application Workflow

1. User uploads a PDF resume.
2. User enters the target job description.
3. The React frontend sends both inputs to the Express backend.
4. The backend extracts text from the uploaded PDF.
5. Resume and job description text are converted into tokens.
6. Relevant keywords are identified and compared.
7. TF-IDF is used to calculate keyword relevance.
8. A combined matching score and missing-keyword suggestions are returned.
9. The frontend displays the results on the dashboard.

## Scoring Methodology

The application uses a weighted scoring approach combining keyword matching and TF-IDF relevance.

**Components:**

- Keyword Matching Score: Measures the proportion of job description keywords found in the resume.
- TF-IDF Score: Calculates the relevance weights of job description keywords in the resume text.

**Final Score:**

`Final Score = (0.7 × Keyword Score + 0.3 × TF-IDF Score) × 100`

The result is rounded to the nearest integer and capped at 100.

*Note: This is a heuristic resume-to-job-description matching score, not an official ATS score or a prediction of hiring success.*

## Project Structure

```text
resume-jd-match-scorer/
│
├── backend/
│   ├── server.js
│   ├── package.json
│   └── package-lock.json
│
├── public/
│   ├── index.html
│   └── manifest.json
│
├── src/
│   ├── components/
│   │   ├── Navbar.js
│   │   ├── ScoreCard.js
│   │   └── Suggestions.js
│   │
│   ├── pages/
│   │   ├── Dashboard.js
│   │   └── Upload.js
│   │
│   ├── App.js
│   └── index.js
│
├── package.json
└── README.md
```

## Getting Started

### Prerequisites

- Node.js
- npm
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/atharvadt/resume-jd-match-scorer.git

cd resume-jd-match-scorer
```

### 2. Install Frontend Dependencies

```bash
npm install
```

### 3. Install Backend Dependencies

```bash
cd backend
npm install
```

### 4. Start the Backend

```bash
node server.js
```

The backend runs on:

```text
http://localhost:5000
```

### 5. Start the Frontend

Open another terminal in the project root directory:

```bash
npm start
```

The frontend runs on:

```text
http://localhost:3000
```

**Backend Configuration:** The frontend currently sends requests to the deployed Render backend. For local development, update the API endpoint in `src/pages/Upload.js` to `http://localhost:5000/analyze`.

## Future Enhancements

- Improve keyword extraction and semantic matching.
- Add detailed skill-wise matching analysis.
- Support additional resume formats.
- Improve scoring methodology.
- Enhance dashboard visualizations.
- Add downloadable analysis reports.

## Author

**Atharva Deepak Thakare**

- GitHub: [@atharvadt](https://github.com/atharvadt)
- LinkedIn: [@atharvadt](https://www.linkedin.com/in/atharvadt)

---

*Built using React.js, Node.js, Express.js, and Natural Language Processing.*
