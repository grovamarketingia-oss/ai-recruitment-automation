# 🤖 AI Recruitment Automation Workflow

An intelligent recruitment automation workflow built with **n8n**, **OpenAI**, **Tally Forms**, **Google Sheets**, and **WhatsApp (Evolution API)**.

This workflow automatically collects candidate applications, evaluates applicants using Artificial Intelligence, classifies them according to predefined hiring criteria, stores qualified candidates, and sends real-time notifications to recruiters.

---

## 🚀 Features

### 📋 Candidate Application Collection

Candidates submit their information through a Tally Form, including:

* Personal information
* Contact details
* Work availability
* Experience level
* Professional skills
* Salary expectations
* Supporting documents
* Employment status

---

### 🧠 AI-Powered Candidate Evaluation

The workflow uses OpenAI to automatically analyze:

* Work experience
* Technical and professional skills
* Availability
* Motivation
* Communication quality
* Salary expectations
* Equipment readiness
* Overall profile consistency

The AI generates:

* Candidate score (1–100)
* Classification
* Evaluation observations

---

### 🎯 Automatic Classification

Candidates are categorized into one of three groups:

| Classification    | Description                                                         |
| ----------------- | ------------------------------------------------------------------- |
| APTO              | Candidate meets the requirements and can continue to the next stage |
| POSIBLEMENTE APTO | Requires manual review                                              |
| NO APTO           | Does not meet minimum requirements                                  |

---

### 📊 Candidate Tracking

Qualified candidates are automatically stored in Google Sheets, including:

* Name
* Email
* Phone number
* Evaluation date
* AI score
* Classification
* Observations
* Uploaded documents

---

### 📱 WhatsApp Notifications

When a candidate is classified as **APTO**, the workflow automatically sends a WhatsApp notification to the recruitment team using Evolution API.

Notification includes:

* Candidate name
* Contact information
* Evaluation score
* Recruitment status

---

### 🔒 Session Management

After processing a candidate, the workflow automatically closes the active recruitment session to prevent unnecessary interactions.

---

## 🏗 Workflow Architecture

```text
Tally Form
    │
    ▼
Data Processing
    │
    ▼
OpenAI Evaluation
    │
    ▼
Candidate Classification
    │
    ├── APTO
    │      │
    │      ▼
    │   Google Sheets
    │      │
    │      ▼
    │   WhatsApp Notification
    │      │
    │      ▼
    │   Close Session
    │
    ├── POSIBLEMENTE APTO
    │      │
    │      ▼
    │   Google Sheets
    │
    └── NO APTO
           │
           ▼
      End Workflow
```

---

## 🛠 Technologies Used

| Technology    | Purpose                |
| ------------- | ---------------------- |
| n8n           | Workflow orchestration |
| OpenAI        | Candidate evaluation   |
| Tally Forms   | Application collection |
| Google Sheets | Candidate database     |
| Evolution API | WhatsApp integration   |
| JSON          | Workflow definition    |

---

## 📂 Workflow Components

### Tally Trigger

Receives candidate submissions directly from Tally Forms.

### Data Transformation

Converts all form responses into a structured format suitable for AI processing.

### OpenAI Agent

Responsible for:

* Extracting candidate information
* Evaluating qualifications
* Generating scores
* Creating observations
* Assigning classifications

### Google Sheets Integration

Stores recruitment records for future review and reporting.

### Evolution API Integration

Sends real-time WhatsApp notifications for qualified candidates.

---

## 📈 Evaluation Criteria

The AI evaluates candidates based on:

### Availability

* Immediate availability
* Work schedule compatibility
* Work modality

### Experience

* General professional experience
* Position-specific experience

### Skills

* Technical competencies
* Professional strengths
* Certifications and education

### Motivation

* Interest in the position
* Career objectives

### Practical Readiness

* Equipment availability
* Current employment situation

### Overall Consistency

* Response quality
* Profile coherence
* Hiring feasibility

---

## 📄 AI Response Format

The AI returns a structured JSON response:

```json
{
  "nombre": "",
  "correo": "",
  "telefono": "",
  "fecha": "",
  "puntaje": 0,
  "clasificacion": "",
  "observaciones": ""
}
```

---

## ⚙️ Requirements

Before importing the workflow, configure:

### OpenAI

* API Key
* Model access

### Tally

* Form ID
* Webhook configuration

### Google Sheets

* OAuth Credentials
* Spreadsheet ID
* Sheet permissions

### Evolution API

* Instance Name
* API Credentials
* WhatsApp Number

---

## 🔧 Installation

### 1. Import Workflow

Import the JSON file into your n8n instance.

### 2. Configure Credentials

Set up:

* OpenAI
* Google Sheets
* Tally
* Evolution API

### 3. Update IDs

Replace:

* Form IDs
* Spreadsheet IDs
* WhatsApp destination numbers

### 4. Activate Workflow

Enable the workflow in n8n.

---

## 📌 Example Process

1. Candidate submits application.
2. n8n receives the form submission.
3. OpenAI evaluates the profile.
4. Candidate receives a score.
5. Candidate is classified.
6. Qualified candidates are saved to Google Sheets.
7. Recruiters receive WhatsApp notifications.
8. Session is automatically closed.

---

## 🎯 Benefits

* Reduces manual screening effort
* Standardizes candidate evaluation
* Improves response times
* Creates centralized candidate records
* Enables real-time recruiter notifications
* Scales recruitment operations efficiently

---

## 📜 License

This project is distributed under the MIT License.

---

## 👨‍💻 Author

Created to automate and streamline recruitment processes using AI, workflow automation, and real-time communication tools.
