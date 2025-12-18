# next-poi-travel-recommendation
A recommendation system for predicting the next Point of Interest (Next-POI) and generating k-sequential itineraries using Foursquare check-in data from NYC and Tokyo

# Travel Recommendation System: Next-POI & Itinerary Generation

This project implements a comprehensive travel recommendation system divided into two primary tasks: one-step-ahead prediction (Next-POI) and sequential travel planning (Itinerary Recommendation).

## Project Overview
The system is designed to provide personalized travel suggestions by analyzing historical user check-in patterns and integrating real-time data from external location service APIs.

### Task A: Next Point of Interest (Next-POI)
* **Goal:** Predict a user's next visit based on recent check-ins, time, and current location.
* **Datasets:** Foursquare NYC & Tokyo check-in datasets.
* **Preprocessing:** * DST-aware local time conversion for accurate hour/weekend features.
    * Median coordinate stabilization for robust venue attributes.
    * Session-based chronological data splitting to avoid leakage.
* **Models:** Comparison between a simple baseline ranker and an advanced sequence-aware model (FPMC/RNN-based).
* **Evaluation:** Evaluated using macro per-user ranking metrics including **Hit@K**, **MRR@10**, and **nDCG@10**.

### Task B: Itinerary Recommendation
* **Goal:** Recommend $k$ sequential stops for a personalized travel plan.
* **Data Sources:** Integration of **Google Places API** and **Yelp Fusion API**.
* **Features:** Multi-city support (Boston and Miami), intelligent caching, and content-based filtering balancing venue ratings with popularity.

## Technologies Used
* **Language:** Python
* **Data Science:** Pandas, NumPy, Scikit-Learn
* **Deep Learning:** PyTorch (for sequence modeling)
* **APIs:** Google Places, Yelp Fusion
* **Visualization:** Matplotlib, Seaborn

## Setup & Usage
1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/yourusername/travel-rec-system-next-poi.git](https://github.com/yourusername/travel-rec-system-next-poi.git)
    ```
2.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **API Keys:** Place your Google and Yelp API keys in a `.env` file or directly into the configuration script for Task B.
4.  **Run Task A:** Execute the Jupyter notebook `Task - A_next POI.ipynb` to view the EDA and model training.
