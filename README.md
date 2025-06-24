
# 🛍️ Shopper Spectrum: Customer Segmentation & Product Recommendation App

**Shopper Spectrum** is a powerful Streamlit web application designed to analyze e-commerce customer behavior through **RFM (Recency, Frequency, Monetary)** segmentation and provide **item-based product recommendations** using collaborative filtering.

---

## 🔧 Features

### 🎯 1. Customer Segmentation Module
- Input: `Recency`, `Frequency`, and `Monetary` values
- Output: Predicted **customer segment** using a pre-trained **KMeans clustering model**
- Segments include:
  - **High-Value** – recent, frequent, and high spenders
  - **Regular** – steady purchasers with moderate frequency and spend
  - **Occasional** – low frequency, low spend, older recency
  - **At-Risk** – haven't purchased recently

### 🎯 2. Product Recommendation Module
- Input: Product name
- Output: Top 5 **similar products** based on **item-based collaborative filtering**
- Similarity computed using **cosine similarity** on a `CustomerID–StockCode` purchase matrix

---

## 📁 Project Structure

```
📦 Shopper_Spectrum_Project/
├── shopper_spectrum_app.py        # ✅ Streamlit application
├── kmeans_model.pkl               # ✅ Trained KMeans model
├── scaler.pkl                     # ✅ Scaler used for RFM features
├── similarity_matrix.pkl          # ✅ Item-item cosine similarity matrix
├── product_map.pkl                # ✅ Mapping of StockCode ↔ Description
├── README.md                      # 📄 Project documentation (you’re here!)
└── requirements.txt               # 📦 List of dependencies
```

---

## 🚀 How to Run

### ✅ Step 1: Install Requirements
```bash
streamlit
pandas
numpy
scikit-learn
matplotlib
seaborn
plotly
```

### ✅ Step 2: Run the Streamlit App
```bash
streamlit run shopper_spectrum_app.py
```

---

## 📦 Required Files

Make sure the following files are present in the working directory:

- `kmeans_model.pkl`
- `scaler.pkl`
- `similarity_matrix.pkl`
- `product_map.pkl`

---

## 📌 Dependencies

Your `requirements.txt` should include:

```
streamlit
pandas
numpy
scikit-learn
```

Add `matplotlib`, `seaborn`, or `plotly` if used elsewhere in the pipeline.

---

## 📊 Data Preprocessing Summary

- Removed rows with missing `CustomerID`
- Excluded canceled invoices (InvoiceNo starting with 'C')
- Removed negative/zero `Quantity` and `UnitPrice`
- Dropped duplicates
- Converted `InvoiceDate` to datetime format
- Constructed `RFM` table from cleaned data

---

## 🤖 Model Details

- **Segmentation**: KMeans clustering on normalized RFM values
- **Recommendation**: Item-based collaborative filtering using cosine similarity

---

## ✅ Future Enhancements

- Deploy on Streamlit Cloud
- Add user authentication
- Enable search suggestions for product input
- Visualize RFM segment distribution

---

## 🧠 Credits

Developed by **Yugeshwar** as part of the **Shopper Spectrum** project on customer segmentation and product recommendation in e-commerce.

