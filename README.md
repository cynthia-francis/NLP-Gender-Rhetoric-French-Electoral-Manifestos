# Analysis of Gendered Rhetoric in French Electoral Manifestos (1973–1993)
### Author: Cynthia Francis

This project utilizes Natural Language Processing (NLP) and Unsupervised Machine Learning to investigate thematic and rhetorical divergences between male and female candidates in the *Archelec* archive. By applying **Non-Negative Matrix Factorization (NMF)**, the study quantifies how "challenger" voices navigate established institutional defaults.

## 📂 Project Structure

* **`data/`**: Raw electoral manifesto text files organized by election year (1973, 1978, 1981, 1988, 1993).
* **`metadata/`**: CSV and structured data containing candidate demographics (e.g., `titulaire-sexe`) and election details.
* **`script/`**: 
    * `cleaned_master_data.parquet`**: Finalized dataset used for modeling, optimized for performance.
    * `main.ipynb`: Primary analysis pipeline (Elbow Method, NMF modeling, and gender-based distribution heatmaps).
    * `text_preprocessing.ipynb`: Tokenization, stop-word removal, and TF-IDF vectorization.
    

## 🚀 Methodology

1. **Preprocessing**: Cleaned and tokenized over 20,000 documents, focusing on candidates with known gender metadata.
2. **Model Selection**: Determined the optimal number of topics ($k=15$) using the **Elbow Method** to minimize reconstruction error while maintaining semantic granularity.
3. **Topic Modeling**: Applied NMF to extract latent themes. This "parts-based" decomposition was chosen over LDA to better isolate specific political identities.
4. **Quantitative Analysis**: Calculated the mean prevalence of topics by gender to identify "Topic Ownership."

## 📊 Key Findings

* **The Identity Gap**: Female candidates exhibit a significantly higher reliance on "Gender & Labor Identity" and "Ecology" themes.
* **Institutional Default**: Male rhetoric is consistently anchored in "Institutional & Local Mandates," reflecting a status-quo positioning afforded by historical incumbency.
* **Robustness**: Sensitivity analysis at $k=10$ and comparisons with LDA confirmed that gendered rhetorical signals remain stable regardless of model hyper-parameters.
