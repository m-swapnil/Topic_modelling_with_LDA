# Topic Modeling with Latent Dirichlet Allocation (LDA)

This project demonstrates topic modeling using **Latent Dirichlet Allocation (LDA)** on a text dataset. It includes preprocessing, vectorization, topic extraction, and visualization. Multiple tools like `sklearn`, `gensim`, and `pyLDAvis` are utilized for an end-to-end analysis.

---

## Features

- Preprocesses text data by tokenizing and cleaning.
- Implements **TF-IDF** and **Bag-of-Words (BoW)** vectorization.
- Extracts topics using **LDA** with `sklearn` and `gensim`.
- Visualizes topic distribution using **pyLDAvis**.
- Generates word clouds for individual topics.
- Computes topic coherence for performance evaluation.

---

## Prerequisites

Ensure the following are installed:

- **Python 3.7 or above**
- Required libraries:
  ```bash
  pip install pandas numpy scikit-learn nltk gensim pyLDAvis wordcloud matplotlib tqdm
  ```

---

## File Structure

```plaintext
.
|-- undebate1.csv            # Input text dataset
|-- lda_topic_modeling.py    # Main script for topic modeling
|-- topic0.png, topic1.png   # Word clouds for each topic (generated output)
```

---

## Script Workflow

### 1. **Preprocessing**
- Reads the dataset (`undebate1.csv`) into a DataFrame.
- Splits text into paragraphs using delimiters like `.`, `?`, and `!`.
- Removes stopwords and performs tokenization.

### 2. **Vectorization**
- Applies **TF-IDF** and **BoW** to convert text into numerical vectors.
- Filters words based on frequency thresholds.

### 3. **LDA Topic Modeling**
- Uses `sklearn` and `gensim` to train LDA models on text data.
- Outputs the top words for each topic.
- Evaluates coherence scores for topic quality.

### 4. **Visualization**
- Generates word clouds for each topic.
- Visualizes topics and their distributions using **pyLDAvis**.

### 5. **Performance Tuning**
- Optimizes the number of topics by iterating over a range and plotting coherence scores.

---

## Configuration

1. **Dataset**
   - Replace `undebate1.csv` with your text dataset.
   - Ensure it has a column named `text` containing the textual data and `year` if analyzing trends over time.

2. **Adjust Parameters**
   - Modify the number of topics in the LDA model:
     ```python
     lda_para_model = LatentDirichletAllocation(n_components=10, random_state=42)
     ```
   - Adjust `min_df` and `max_df` for filtering uncommon and overly common words in vectorization:
     ```python
     CountVectorizer(stop_words=stopwords, min_df=5, max_df=0.7)
     ```

---

## Usage

### Topic Words
```
Topic 01:
  economy (25.00), trade (20.00), market (15.00)
Topic 02:
  education (30.00), school (20.00), teacher (10.00)
```

### Coherence Score
```
Optimal Number of Topics: 12
Coherence Score: 0.67
```

### Visualizations
- Word clouds (`topic0.png`, `topic1.png`, etc.).
- Interactive topic distribution via `pyLDAvis`.

---

## License

This project is licensed under the MIT License.
