# 🍲 Ingredient Recommendation System  

## 📌 Project Overview  
This project develops a **personalized ingredient recommendation system** based on user preferences and recipe history from *food.com*.  

The system aims to:  
- Suggest **Top-N ingredients** tailored to users.  
- Provide **healthy substitutes** by incorporating nutrition-based scoring.  
- Enhance the **culinary experience** while promoting healthier choices.  

---

## 🔹 Approach  

### 1. Non-Personalized Recommendations  
- **Recency-based filtering**: Prioritize ingredients with recent positive reviews.  
- **Sentiment analysis** (TextBlob): Extract ingredients from reviews with positive polarity (>0) and ratings ≥ 4.  
- **Insight**: Identified the most appreciated and high-rated ingredients.  

### 2. Personalized Recommendations  
- **Weighted Rating Method**: Assigns higher weight to ingredients in simpler recipes where individual impact is greater.  
- **Collaborative Filtering (KNN-based)**: Optimized via GridSearch; strong recall and precision scores.  
- **Matrix Factorization (SVD)**: Best-performing model with high ranking metrics.  
- **Content-Based (TF-IDF)**: Uses ingredient descriptions to recommend similar items.  

---

## 🔹 Model Evaluation Metrics  
- **Top-N = 8** (average ingredients per recipe).  
- **Precision**: Accuracy of recommendations.  
- **Recall**: Coverage of relevant items.  
- **NDCG@8**: Considers ranking quality of recommended items.  

### Results Snapshot:  
- **Collaborative Filtering**: Precision ~0.95, Recall ~0.99, NDCG@8 ~0.85.  
- **SVD (Matrix Factorization)**: RMSE = 0.92, Precision ~0.95, Recall ~0.99.  
- **Content-Based TF-IDF**: Precision ~0.95, NDCG@8 ~0.85.  

---

## 🔹 Promoting Healthy Ingredients  
- **Health Score Formula**: Penalizes fat, sugar, sodium (scaled by 240), and saturated fat while rewarding protein.  
- **Final Recommendation Process**:  
  1. Generate Top-15 ingredients with SVD model.  
  2. Match with candidate recipes.  
  3. Combine **Recipe Matching Score** with **Health Score** (scale 1–2, higher = healthier).  

---

## 📌 Conclusion  
- Developed a **hybrid recommendation system** that integrates collaborative filtering, matrix factorization, and content-based methods.  
- Enhanced by **nutritional health scoring** to promote healthier food choices.  
- The final approach balances **personalization, accuracy, and health awareness** for recipe and ingredient recommendations.  
