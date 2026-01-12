# Breast Cancer Prediction System: Comprehensive Project Report

**Group IV Capstone Project**
*   **Vincent Nyakach** — Project Lead
*   **Esther Mutiria** — Web Developer
*   **Ryan Muchaba** — Data Scientist
*   **Vyone Vulimu** — Researcher
*   **Brian Mutiso** — Data Analyst

---

## 1. Problem Statement (Criteria 1)
**The Challenge:**
Breast cancer is one of the most common cancers worldwide. Early and accurate diagnosis is critical for effective treatment and survival. However, manual diagnosis from biopsy data can be:
*   **Time-consuming:** Pathologists require significant time to analyze samples.
*   **Subjective:** diagnosis can vary between different experts.
*   **Resource-intensive:** Requires specialized equipment and highly trained personnel, which may be scarce in resource-limited settings.

**The Solution:**
A machine learning-powered decision support system that can analyze patient biomarkers (from digitized Fine Needle Aspirate (FNA) of a breast mass) and predict whether a tumor is **Malignant** or **Benign**. This tool aims to assist clinicians by providing a rapid, objective second opinion, potentially speeding up diagnosis and reducing false negatives.

---

## 2. Project Proposal (Criteria 2)

### Project Goal
To develop a web-based application seamlessly integrated with a Machine Learning backend that provides real-time breast cancer malignancy predictions.

### SMART Objectives
1.  **Develop a ML Model**: Train and validate a classification model (e.g., Logistic Regression or Random Forest) using the Wisconsin Breast Cancer Dataset with an accuracy of at least 90%.
2.  **Build a REST API**: Create a Django backend to serve the model predictions via a secure API endpoint.
3.  **Create a User-Friendly Interface**: Develop a responsive frontend (HTML/CSS/JS) that allows medical staff to input data easily and view results clearly.
4.  **Integration**: Successfully connect the frontend and backend to allow for end-to-end data flow and prediction display within < 2 seconds.

### Scope
**In-Scope:**
*   Data preprocessing and model training.
*   Backend API development (Django).
*   Frontend User Interface (Landing page, Prediction form, Results display).
*   Basic user authentication (optional: for doctor login).

**Out-of-Scope:**
*   Integration with hospital Electronic Health Records (EHR) systems (for this MVP).
*   Image analysis (using numerical features derived from images, not raw images themselves).
*   Mobile app development (Web app is mobile-responsive).

### Expected Outcomes
*   A deployed or locally runnable web application.
*   A documented codebase and user guide.
*   A performance report showing the model's accuracy, precision, and recall.

---

## 3. Design and Planning (Criteria 3)

### System Architecture
The system follows a classic **Model-View-Template (MVT)** architecture (Django's variation of MVC), integrated with a Machine Learning pipeline.

```mermaid
graph TD
    User[Clinician/User] -->|HTTP Request| FE[Frontend (HTML/CSS/JS)]
    FE -->|API Call| BE[Backend (Django REST Framework)]
    
    subgraph Backend
    BE -->|Query| DB[(Database: SQLite/Postgres)]
    BE -->|Input Features| ML[ML Model (Scikit-Learn)]
    ML -->|Prediction| BE
    end
    
    DB -->|Patient Data| BE
```

### Components
1.  **Client-Side (Frontend):**
    *   **Technologies:** HTML5, CSS3, JavaScript.
    *   **Responsibility:** Rendering the UI, capturing user input (biomarkers), sending async requests to the API, and displaying results.
2.  **Server-Side (Backend):**
    *   **Technologies:** Python, Django.
    *   **Responsibility:** Handling HTTP requests, serving static files, managing database interactions, and invoking the ML inference engine.
3.  **Machine Learning Layer:**
    *   **Technologies:** Scikit-learn, Joblib.
    *   **Responsibility:** Loading the pre-trained model and generating predictions (Benign/Malignant) based on input vector.
4.  **Data Persistence:**
    *   **Technologies:** PostgreSQL (Production) / SQLite (Dev).
    *   **Responsibility:** Storing user profiles, doctor records, and patient prediction history.

### Project Timeline
| Phase | Duration | Key Activities | Status |
| :--- | :--- | :--- | :--- |
| **Research** | Week 1-2 | Problem definition, dataset selection, literature review. | [Completed] |
| **Design** | Week 3 | System architecture design, DB schema modeling, UI wireframing. | [Completed] |
| **ML Dev** | Week 4-5 | Data cleaning, EDA, Model training/tuning, Model serialization. | [In Progress] |
| **Backend**| Week 6 | Django setup, API creation, Model integration. | [In Progress] |
| **Frontend**| Week 7 | Building HTML templates, CSS styling, API integration logic. | [In Progress] |
| **Testing** | Week 8 | Unit testing, Integration testing, User Acceptance Testing. | [Pending] |
| **Finalization**| Week 9 | Documentation, Deployment, Presentation prep. | [Pending] |

---

## 4. Development & Code Structure (Criteria 4)
*   **Code Quality**: The codebase is organized into clear directories (`frontend` for UI, `backend` for logic).
*   **Separation of Concerns**: CSS styles are centralized in `style.css` rather than inline. JavaScript logic is separated from presentation where possible.
*   **Version Control**: Git is used for tracking changes (see `.git` directory).

---

## 5. Testing and Quality Assurance (Criteria 5)

### Strategy
We employ a multi-layered testing strategy:
1.  **Unit Testing (Backend & ML)**: Verifying logic of individual functions (e.g., Model Loading, Prediction Logic).
2.  **Integration Testing**: Verifying data flow between Frontend and Backend APIs.
3.  **Manual / User Acceptance Testing (UAT)**: Verifying the system from an end-user perspective.

### Manual Test Cases (UI)
| ID | Test Scenario | Steps | Expected Result |
| :--- | :--- | :--- | :--- |
| **TC01** | **Landing Page Load** | 1. Open `index.html`. | Page loads with Header and "Get Started" button. |
| **TC02** | **Form Validation**| 1. Leave fields empty & click "Predict". | HTML5 validation error appears. |
| **TC03** | **Successful Prediction** | 1. Fill fields with valid data & click "Predict". | Result ("Malignant" or "Benign") appears. |
| **TC04** | **Responsiveness** | 1. Resize browser to mobile view. | Layout adapts, menu stacks correctly. |

---

## 6. Finalization & Presentation (Criteria 6 & 7)

### Presentation Outline
1.  **Introduction (1 min)**: Hook, Problem (Slow diagnosis), Solution (AI Tool).
2.  **Methodology & Tech Stack (2 min)**: Data (Wisconsin Dataset), Model (Random Forest), Stack (Django/HTML).
3.  **Product Features (2 min)**: User-friendly form, Real-time prediction, Patient history.
4.  **Live Demo (3 min)**:
    *   **Scenario A:** Low-risk case -> "Benign" (Green).
    *   **Scenario B:** High-risk case -> "Malignant" (Red).
    *   Show Mobile Responsiveness.
5.  **Challenges & Learnings (1 min)**: Data imbalance, API integration.
6.  **Future Improvements (1 min)**: EHR integration, Image analysis (CNNs).
7.  **Q&A**

---
