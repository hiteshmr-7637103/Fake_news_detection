# Fake News Detection System

## Project Overview

This project presents a machine learning system for classifying news articles as either "Real" or "Fake". It leverages Natural Language Processing (NLP) techniques and a Logistic Regression model to analyze text and predict its authenticity. The final model is deployed as a simple, interactive web application using Gradio.

The primary goal is to provide a tool that can help identify misinformation, a growing concern in the digital age.

---

## Technical Workflow

The system follows a standard machine learning pipeline:

1.  **Data Collection and Preprocessing:** The core dataset is loaded and combined into a single structured DataFrame. Textual data is cleaned by converting it to lowercase, removing punctuation, and filtering out common English stopwords.
2.  **Feature Extraction:** Cleaned text is transformed into a numerical format suitable for machine learning using the Term Frequency-Inverse Document Frequency (TF-IDF) vectorization technique.
3.  **Model Training:** The dataset is split into training (80%) and testing (20%) sets. A Logistic Regression classifier is trained on the vectorized training data.
4.  **Evaluation:** The model's performance is assessed on the unseen test set using standard classification metrics, including accuracy, precision, recall, and F1-score.
5.  **Deployment:** The trained model and the complete data processing pipeline are encapsulated in a function and exposed through a Gradio web interface for real-time predictions.

---

## Dataset

This project utilizes the "Fake and Real News Dataset" available on Kaggle.

-   **Link:** [https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset](https://www.kaggle.com/datasets/clmentbisaillon/fake-and-real-news-dataset)

---

## Setup and Execution

### Prerequisites

-   Python 3.9+
-   pip (Python package installer)

### Installation

1.  Clone the repository to your local machine:
    `git clone <your-repository-url>`
2.  Navigate to the project's root directory:
    `cd <project-directory>`
3.  Install the required dependencies from the `requirements.txt` file:
    `pip install -r requirements.txt`

### Running the Application

1.  Execute the main script from the terminal:
    `Fake_news_detection.ipynb`
2.  A local URL will be generated (e.g., `http://127.0.0.1:7860`). Open this URL in your web browser to access the application.

---

## Model Performance

The trained Logistic Regression model achieved an accuracy of **98.70%** on the hold-out test set. The detailed classification report is as follows:

| Class         | Precision | Recall | F1-Score |
|---------------|-----------|--------|----------|
| Fake News (0) | 0.99      | 0.99   | 0.99     |
| Real News (1) | 0.98      | 0.99   | 0.99     |

---

## Limitations

-   **Temporal Dependency:** The model is trained on a dataset from circa 2018. Consequently, it may not accurately classify articles related to events that have transpired since that time.
-   **Pattern Recognition vs. Fact-Checking:** The system identifies linguistic patterns indicative of real or fake news based on its training data; it does not perform real-world fact-checking.
