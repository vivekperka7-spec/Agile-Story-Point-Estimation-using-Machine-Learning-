# SprintIQ: Intelligent Agile Estimation System

## Introduction

SprintIQ is an advanced, machine learning-based estimation system designed to optimize Agile sprint planning processes. By leveraging Natural Language Processing (NLP) and historical project data, SprintIQ analyzes the semantic complexity of user stories to provide objective, data-driven story point estimates. This system eliminates the subjective bias inherent in traditional estimation methods and reduces the time engineering teams spend on sprint planning.

## Project Overview

Accurate estimation is critical for predictable delivery and effective resource allocation in modern software engineering. SprintIQ addresses the challenges of human estimation bias and inconsistency by introducing an objective, automated baseline.

The platform bridges the gap between human intuition and statistical reality. By training on a comprehensive dataset of completed user stories and their actual implementation complexities, SprintIQ learns to recognize patterns in requirements that correlate with higher or lower effort levels. This results in consistent, reproducible estimates grounded in empirical data.

## Key Features

*   **Artificial Intelligence-Powered Accuracy**: Utilizes a Regression model trained on historical agile data to understand technical requirement nuances.
*   **Mitigation of Planning Bias**: Provides a neutral, algorithmic second opinion to help teams converge on realistic estimates.
*   **Efficiency in Sprint Planning**: Delivers immediate estimates, allowing teams to focus on implementation details rather than numerical negotiation.
*   **Confidence Metrics**: Calculates a confidence score for each prediction to identify stories requiring deeper human review.
*   **Standard Agile Compliance**: Supports the standard Fibonacci sequence (1, 2, 3, 5, 8, 13) for story points.

## System Architecture

SprintIQ operates through a four-stage pipeline:

1.  **Data Input**: Accepts unstructured user stories via a web interface or RESTful API.
2.  **Preprocessing**: Performs tokenization, stop-word removal, and vectorization.
3.  **Model Inference**: Uses a Random Forest Regressor to calculate a raw continuous complexity score.
4.  **Prediction**: Maps the score to the Fibonacci scale and generates a confidence metric.

## Technology Stack

*   **Backend**: FastAPI (Python)
*   **Machine Learning**: Scikit-Learn
*   **Data Processing**: Pandas & NumPy
*   **Frontend**: Jinja2 Templates & Vanilla CSS
*   **Server**: Uvicorn

## Installation

### Prerequisites

*   Python 3.9 or higher
*   pip

### Setup

1.  **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

2.  **Train Model**
    ```bash
    python scripts/train_model.py
    ```

3.  **Start Application**
    ```bash
    uvicorn app.main:app --reload
    ```
    The application will be accessible at `http://127.0.0.1:8000`.

## Usage

### Web Interface
Navigate to the localized server URL, select the **Estimator** tab, and input a user story to receive a prediction.

### API Integration
**Endpoint**: `POST /predict`
**Content-Type**: `application/json`

**Request**:
```json
{
  "user_story": "As a user, I want to filter search results by price range so that I can find affordable items."
}
```

**Response**:
```json
{
  "predicted_story_points": 3,
  "confidence": "high"
}
```

## Credits and Copyright

**Lead Developer**: Vivek Perka

> "SprintIQ demonstrates the power of Machine Learning in modern software engineering, aiming to resolve real-world Agile challenges like estimation bias through data-driven insights."

**Copyright © 2026 Vivek Perka. All Rights Reserved.**

This project, including its source code and proprietary estimation algorithms, is the intellectual property of P.Vivek. Unauthorized reproduction, distribution, or commercial use of the core logic without explicit permission is strictly prohibited.
