# ReviewInsight

# **Customer Review Clustering and Summarization (Amazon Product Reviews)**

This project aims to collect, process, cluster, and summarize customer reviews of products on Amazon using various natural language processing (NLP) techniques and machine learning models. The goal is to gain insights into customer opinions and provide summarized feedback for each cluster of reviews.

## **Project Workflow**

### **1. Data Collection (Web Scraping)**
- **Tools Used**: Selenium WebDriver (Microsoft Edge)
- The project begins by scraping customer reviews for a specific product on Amazon.
- Reviews are gathered by simulating page scrolling to capture all available reviews.
- Extracted reviews are saved in a CSV file.

### **2. Data Preprocessing**
- **Tools Used**: Python (with regex)
- The reviews are cleaned by converting them to lowercase, removing punctuation, and trimming excess whitespace.
- Invalid reviews (e.g., containing only "Read more" or empty reviews) are discarded.

### **3. Embedding Generation**
- **Tools Used**: Sentence-BERT (all-MiniLM-L6-v2)
- Each review is converted into a numerical vector (embedding) that captures its semantic meaning.
- These embeddings are used as inputs for clustering algorithms.

### **4. Clustering**
- **Tools Used**: KMeans (Scikit-learn)
- The embeddings are clustered into predefined groups (5 clusters by default) using the KMeans algorithm.
- A new column with the cluster labels is added to the data, identifying which reviews belong to each cluster.

### **5. Data Visualization**
- **Tools Used**: PCA (Principal Component Analysis), Seaborn, Matplotlib
- The high-dimensional embeddings are reduced to 2D using PCA to visualize the clustering results.
- A scatter plot is generated to show the distribution of reviews across clusters.

### **6. Text Summarization**
- **Tools Used**: Meta-Llama 3.1-8B (LLM Model)
- A large language model (LLM) is used to generate concise summaries for each cluster of reviews.
- Each cluster’s reviews are combined into a single text, which is then summarized by the LLM.

### **7. Export Results**
- **Tools Used**: pandas
- The final output, including each cluster and its corresponding summary, is saved in a CSV file (`ket_qua_cum.csv`) for easy analysis and further processing.

## **Key Features**
- **Automated Review Scraping**: Collects reviews directly from Amazon for any product.
- **Text Preprocessing**: Cleans and standardizes review text to improve quality.
- **Clustering**: Uses unsupervised learning (KMeans) to group similar reviews together.
- **Summarization**: Uses a powerful LLM to summarize large volumes of customer feedback.
- **Visualization**: PCA and scatter plots help visualize how reviews are distributed across clusters.
- **Exportable Results**: The final summarized data is saved into a CSV file for easy analysis.

## **Technologies Used**
- Python
- Selenium WebDriver
- Sentence-BERT
- KMeans (Scikit-learn)
- PCA (Scikit-learn)
- Meta-Llama 3.1-8B (Hugging Face Model)
- Pandas
- Matplotlib
- Seaborn

## **Setup Instructions**

1. **Install Dependencies**:
   - Clone this repository and install required libraries using:
     ```bash
     pip install -r requirements.txt
     ```

2. **Run the Script**:
   - To start collecting reviews for a specific product, simply run the Python script.
   - Make sure to configure the product URL and other parameters in the script.

3. **Output**:
   - The cleaned reviews and cluster summaries will be saved as `ket_qua_cum.csv`.

4. **Link Colab**: https://colab.research.google.com/drive/14utSkhyJym8R6goo61S59cHDetg4OYft?usp=sharing

## **Usage Example**
To analyze reviews for a product, specify the Amazon product URL in the script, and the tool will automatically fetch, clean, cluster, summarize, and visualize the reviews.


## License

This project is licensed under the MIT License - see the LICENSE file for details.
---
