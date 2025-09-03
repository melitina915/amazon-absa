# amazon-absa 

[25-Spring] Dacos Project

### 📌 Overview

This project analyzes Amazon review data using Aspect-Based Sentiment Analysis (ABSA) methodology.
Unlike conventional rating systems that cluster around 4.0 ± 0.5, this approach captures fine-grained insights on what customers truly value (e.g., price, quality, delivery).

Our final goal is to design a new scoring system that:
- Reflects aspect-level importance for each product category
- Incorporates sentiment polarity (positive / neutral / negative)
- Adjusts scores based on product price tier & discount factor

---

### 🗂 Dataset
- Source: [Amazon Sales Dataset (Kaggle)](https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset)
- Fields used:
	- product_id
	- review_title, review_content
	- rating, rating_count
	- discount_percentage
	- large_category, mid_category, small_category

---

### 🔎 Methodology

**1. Aspect Extraction (ATE)**
- LDA topic modeling
- RoBERTa-base ABSA (gauneg/roberta-base-absa-ate-sentiment)
- Manual refinement for common aspects

**2. Sentiment Classification**
- Two-step (ACD + Sentiment) and End-to-End LLM prompt-based approaches tested
-	Final method: GPT-3.5-turbo (prompt-based ABSA)

**3. Scoring System**
-	Step 1: Compute aspect weight per category
-	Step 2: Aggregate weighted sentiment scores per product
-	Step 3: Apply high-price adjustment factor

---

### 📊 Results
-	Distribution: Final scores follow a near-normal distribution, unlike skewed original ratings
-	Comparison: Products with identical ratings can be differentiated by ABSA-based scores

---

### 💡 Implications
-	ABSA provides a more reliable indicator than raw ratings
-	Helps identify category-specific drivers of satisfaction
-	Potential application in recommendation systems & product benchmarking

---

### 👥 Contributors
	- Dacos Team 2 (Spring 2025)
| Name            | Role                          | GitHub                    |
|-----------------|-------------------------------|---------------------------|
| SeoWon Lee      | Project Lead                  | [@seo-won-lee](https://github.com/seo-won-lee) |
| SeBin Jeong     |                               |                            |
| CheEun Yoon     |                                |                            |
| HyeLim Je       |                                |                             |
  
