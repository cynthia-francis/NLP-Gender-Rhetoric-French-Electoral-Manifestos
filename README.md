# Analysis of Gendered Rhetoric in French Electoral Manifestos (1973–1993)

### Author: Cynthia Francis

This project utilizes Natural Language Processing (NLP) and Unsupervised Machine Learning to investigate thematic and rhetorical divergences between male and female candidates in the *Archelec* archive. By applying **Non-Negative Matrix Factorization (NMF)**, the study quantifies how "challenger" voices navigate established institutional defaults.

## 📂 Project Structure

* **`CF_Report.pdf`**: The final research report.
* **`electoral_data.zip`**: Zipped archive of raw electoral manifestos. **Note:** Must be unzipped in the root directory to create the `/data` folder for script compatibility.
* **`metadata/`**: Candidate demographics and election-specific metadata.
* **`script/`**: 
    * `cleaned_master_data.parquet`: Processed dataset (Git LFS).
    * `main.ipynb`: NMF modeling, Elbow Method, and gender distribution heatmaps.
    * `text_preprocessing.ipynb`: Data cleaning and TF-IDF vectorization using relative pathing (`Path.cwd().parent`).

## 🚀 Methodology

1. **Preprocessing**: Cleaned and tokenized ~20,000 documents using `spaCy`'s French model.
2. **Model Selection**: Used the **Elbow Method** to fix $k=15$ topics, balancing model parsimony with semantic granularity.
3. **Topic Modeling**: Applied NMF to isolate "parts-based" political identities, providing better resolution than traditional LDA.
4. **Quantitative Analysis**: Analyzed mean topic prevalence by gender to identify "Topic Ownership" and the "Identity Gap."

## 📊 Key Findings

* **The Identity Gap**: Female candidates rely significantly more on "Gender & Labor Identity" rhetoric—a 5-fold increase over male counterparts—reflecting a "challenger" strategy.
* **Institutional Default**: Male rhetoric is consistently anchored in "Institutional & Local Development," aligning with established incumbency norms.

## ⚙️ Setup & Reproduction
To reproduce the analysis:
1. Ensure Git LFS is installed and pull the large files.
2. Unzip `electoral_data.zip` into the root directory. This will create the `/data` folder required by the scripts.
3. Run `text_preprocessing.ipynb` to generate the TF-IDF matrix (optional, as the parquet is provided).
4. Run `main.ipynb` to generate the NMF models and heatmaps.