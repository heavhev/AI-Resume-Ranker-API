# AI Resume Ranker API: Enhance Your Recruitment Process with AI

![AI Resume Ranker](https://img.shields.io/badge/AI%20Resume%20Ranker-API-brightgreen.svg)  
[![GitHub Releases](https://img.shields.io/badge/Releases-v1.0.0-blue.svg)](https://github.com/heavhev/AI-Resume-Ranker-API/releases)

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
- [API Documentation](#api-documentation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Overview

The **AI Resume Ranker API** provides a robust solution for evaluating resumes against job descriptions. Built using cutting-edge technology, this API utilizes Sentence Transformers to deliver precise ranking of PDF resumes. It features secure API key authentication, a live dashboard, and an interactive "try-it-now" interface, inspired by the developer experience of Stripe and Paystack.

This tool is essential for recruiters and HR professionals looking to streamline their hiring process and ensure they find the best candidates quickly and efficiently.

## Features

- **Semantic Ranking**: Ranks resumes based on their relevance to job descriptions.
- **PDF Parsing**: Easily extracts text from PDF resumes for analysis.
- **Secure Authentication**: Protects your data with API key authentication.
- **Live Dashboard**: Monitor API usage and performance in real-time.
- **Interactive Interface**: Try out the API with a user-friendly interface.
- **Developer Friendly**: Designed for easy integration into existing systems.

## Technologies Used

- **Python**: The core programming language for the API.
- **Flask**: The web framework that powers the API.
- **Sentence Transformers**: For semantic understanding and ranking of resumes.
- **PDF Parsing Libraries**: To handle and extract text from PDF files.
- **Docker**: For containerization and easy deployment.
- **PostgreSQL**: For storing user data and resume information.

## Getting Started

To get started with the AI Resume Ranker API, follow these steps:

1. **Clone the Repository**: 
   ```bash
   git clone https://github.com/heavhev/AI-Resume-Ranker-API.git
   cd AI-Resume-Ranker-API
   ```

2. **Install Dependencies**:
   Make sure you have Python installed. Then, install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Environment Variables**:
   Create a `.env` file in the root directory and add your API key:
   ```plaintext
   API_KEY=your_api_key_here
   ```

4. **Run the Application**:
   Start the API server:
   ```bash
   python app.py
   ```

5. **Access the Dashboard**:
   Open your browser and navigate to `http://localhost:5000` to access the live dashboard.

## API Documentation

The API provides several endpoints to interact with the resume ranking system. Below are the key endpoints:

### 1. Upload Resume

- **Endpoint**: `POST /upload`
- **Description**: Upload a PDF resume for ranking.
- **Parameters**:
  - `file`: The PDF file to be uploaded.
- **Response**:
  - `status`: Success or failure message.
  - `resume_id`: Unique identifier for the uploaded resume.

### 2. Rank Resume

- **Endpoint**: `POST /rank`
- **Description**: Rank a resume against a job description.
- **Parameters**:
  - `resume_id`: The ID of the uploaded resume.
  - `job_description`: The job description text.
- **Response**:
  - `rank`: The rank score of the resume.
  - `feedback`: Suggestions for improvement.

### 3. Get Dashboard Data

- **Endpoint**: `GET /dashboard`
- **Description**: Retrieve usage statistics and performance metrics.
- **Response**:
  - `usage`: Current API usage stats.
  - `performance`: Metrics related to ranking performance.

## Usage

Here’s how you can use the API in your application:

### Example: Uploading a Resume

```python
import requests

url = "http://localhost:5000/upload"
files = {'file': open('resume.pdf', 'rb')}
response = requests.post(url, files=files)

print(response.json())
```

### Example: Ranking a Resume

```python
import requests

url = "http://localhost:5000/rank"
data = {
    "resume_id": "12345",
    "job_description": "Looking for a software engineer with experience in Python."
}
response = requests.post(url, json=data)

print(response.json())
```

## Contributing

We welcome contributions to enhance the AI Resume Ranker API. To contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Make your changes and commit them (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature/YourFeature`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contact

For questions or feedback, please reach out to the project maintainer:

- **Name**: [Your Name]
- **Email**: your.email@example.com
- **GitHub**: [Your GitHub Profile](https://github.com/yourusername)

For the latest releases, visit the [Releases](https://github.com/heavhev/AI-Resume-Ranker-API/releases) section.

---

Feel free to explore and integrate the AI Resume Ranker API into your recruitment processes. This tool aims to simplify the hiring experience and enhance the quality of candidate selection.