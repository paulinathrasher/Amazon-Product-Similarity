# Amazon Product Similarity Analysis

## Overview
This project uses transformer-based sentence embeddings to compare Amazon products based on customer reviews. By representing each product as an aggregated embedding of its reviews, we can determine product similarity using cosine similarity and Euclidean distance. This type of analysis is valuable for recommendation systems, product grouping, and customer segmentation.

The project explores three different aggregation methods (simple average, rating-weighted, helpfulness-weighted) and compares how each affects similarity results. Visualizations such as t-SNE plots are used to illustrate product clustering.

---

## Dataset
- **Source**: [Amazon Reviews 2023 Dataset](https://huggingface.co/datasets/amazon/amazon-reviews-2023)  
- **Filtered Sample**:
  - Category: Handmade Products  
  - 10 products selected (minimum 20 reviews each)  
  - Metadata merged with review text  
- **Key Features**:
  - Review text
  - Ratings (1–5)
  - Helpfulness votes
  - Product titles & parent_asin (grouping identifier)

---

## Methods

### **1. Review Embeddings**
- Embeddings generated using Hugging Face’s `"all-MiniLM-L6-v2"` model (384-dimensional).
- Aggregation methods:
  1. **Simple Average** – all reviews weighted equally  
  2. **Rating-Weighted Average** – reviews weighted by star rating  
  3. **Helpfulness-Weighted Average** – reviews weighted by helpfulness votes

### **2. Product Similarity**
- **Cosine Similarity** – measures similarity based on the angle between product vectors (captures semantic tone)
- **Euclidean Distance** – measures straight-line distance in embedding space (sensitive to magnitude)

### **3. Visualizations**
- **t-SNE (2D)** – visualizes how product embeddings cluster together based on aggregated review embeddings.

---

## Results

### **Key Findings**
- Rating-weighted aggregation emphasized highly rated products, clustering together similar items with positive reviews (e.g., personalized jewelry products).
- Helpfulness-weighted aggregation highlighted detailed reviews, sometimes producing unique groupings based on nuanced customer experiences.
- Cosine similarity was better at grouping products with similar **tone**, while Euclidean distance sometimes paired unrelated products due to shared keywords (e.g., “unique”, “gift”) despite different functions.

### **Example Similar Products**
Example using **cosine similarity** with rating-weighted embeddings:

