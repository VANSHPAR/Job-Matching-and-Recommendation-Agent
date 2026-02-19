# 📄 AI Job Search & Matching Agent (n8n)

## Overview

The **AI Job Search & Matching Agent** automates the job discovery process by analyzing a candidate’s resume, extracting relevant skills, searching for jobs via an external API, intelligently matching jobs based on those skills, and delivering the results directly via email.

This workflow is built entirely in **n8n** and combines document parsing, AI-powered skill extraction, job search APIs, intelligent matching, and automated communication.



https://github.com/user-attachments/assets/69cd0e30-542a-4d6f-9aed-6481b59fedb2





## 🧠 Workflow Architecture

```bash
Form Submission
   ↓
Extract Text from PDF
   ↓
AI Skill Extraction
   ↓
Job Search API
   ↓
Field Normalization
   ↓
Job Matching AI Agent
   ↓
Email Delivery
```

<img width="1846" height="818" alt="Screenshot 2026-02-19 105602" src="https://github.com/user-attachments/assets/2c43807c-c4be-4932-9bf4-db57fc34b8b5" />


---

## 🔧 Node-by-Node Breakdown

### 1️⃣ On Form Submission
- Trigger node that starts the workflow
- Accepts:
  - Resume file (PDF)
  - Optional job type preference (Job / Internship)

---

### 2️⃣ Extract Text from File
- Extracts raw text content from the uploaded resume
- Supports PDF documents

---

### 3️⃣ Extract Skills from Text (AI)
- Uses an AI model to analyze resume text
- Outputs a structured list of technical and professional skills
- Ensures extracted skills are relevant and normalized

---

### 4️⃣ Job Search API
- Fetches job listings from an external job search API
- Supports pagination and multiple result pages
- Returns raw job data including:
  - Job title
  - Company name
  - Job description
  - Application link

---

### 5️⃣ Edit Fields
- Normalizes and prepares API response fields
- Ensures consistent data structure for downstream processing

---

### 6️⃣ Code in JavaScript
- Performs light data transformation and cleanup
- Prepares skills and job data for optimal AI matching
- Optional but significantly improves matching accuracy and reliability

---

### 7️⃣ Matches Skills with Jobs (AI Agent)
- Core intelligence layer of the workflow
- Compares extracted skills against job descriptions
- Filters relevant jobs based on:
  - Skill overlap
  - Job type (Job / Internship)
- Outputs a detailed, readable list of matching jobs

---

### 8️⃣ Send a Message (Email)
- Sends the final list of matched jobs directly via email
- Email content includes:
  - Job title
  - Company name
  - Reason for match
  - Application link
- No additional formatting or processing required

---




