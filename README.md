# Project 4: Automated Error Handling & Logging Framework

## Project Overview
This project implements a **robust, reusable error handling and logging framework** in Azure Data Factory. It automatically captures detailed error information and logs it centrally whenever any activity or pipeline fails.

## Key Features
- Centralized error logging pipeline (`pl_error_handler`)
- Dynamic capture of Pipeline Name, Activity Name, Error Message, Error Code & Timestamp
- Try-Catch pattern using **If Condition + Execute Pipeline**
- Retry logic for transient failures
- Logs stored in Azure Data Lake Storage Gen2 (`errorlogs/` folder)
- Fully reusable across all pipelines

## Architecture
- Main Pipeline → On Failure → Calls Error Handler Pipeline
- Error Handler → Captures error details using expressions → Writes to ADLS

## Technologies Used
- Azure Data Factory (If Condition, Execute Pipeline, Expressions)
- Azure Data Lake Storage Gen2
- Parameterized & Modular Design

## Screenshots
 - Error Handler Pipeline
  <img width="489" height="304" alt="image" src="https://github.com/user-attachments/assets/4b70829e-176b-4746-ab61-b9492ccf7046" />

  <img width="499" height="286" alt="image" src="https://github.com/user-attachments/assets/94a5a388-17c6-4119-b36a-a4ed9572a0a6" />


  <img width="487" height="269" alt="image" src="https://github.com/user-attachments/assets/de21abb5-5b2e-42bf-bc40-089a7299bf93" />




## How to Use
1. Import `pl_error_handler` pipeline
2. In any main pipeline, connect the failure path to Execute Pipeline activity
3. Pass required parameters (Pipeline Name, Activity Name, etc.)

## Learnings
- Production-grade error handling patterns
- Dynamic logging and observability in ADF
- Building reusable framework components

---
**Made by Rajendra K**  
Aspiring Azure Data Engineer | Open to UK & Europe Opportunities
