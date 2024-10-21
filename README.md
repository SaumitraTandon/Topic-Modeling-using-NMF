# Topic Modeling Using Non-Negative Matrix Factorization (NMF)

This repository contains a Jupyter Notebook that demonstrates how to perform **Topic Modeling** using **Non-Negative Matrix Factorization (NMF)** on a text dataset. The dataset used here is a collection of news articles labeled by topic from the BBC.

## Dataset

The dataset `bbc_text_cls.csv` contains BBC news articles with the following columns:
- `text`: The full text of the news article.
- `labels`: The category or label of the news article (e.g., 'business', 'tech', 'sport', etc.).

### Dataset Example:

| Text                                                | Labels  |
| --------------------------------------------------- | ------- |
| Ad sales boost Time Warner profit...                | business|
| Dollar gains on Greenspan speech...                 | business|
| Yukos unit buyer faces loan claim...                | business|
| High fuel prices hit BA's profits...                | business|
| Pernod takeover talk lifts Domecq...                | business|

## Project Structure

The notebook walks through the following steps:
1. **Text Preprocessing**: 
    - Tokenization
    - Removal of stopwords (customized for the dataset)
    - Vectorization using **TF-IDF (Term Frequency-Inverse Document Frequency)**

2. **Topic Modeling using NMF**:
    - After preprocessing, the TF-IDF matrix is decomposed into topics using **Non-Negative Matrix Factorization (NMF)**.
    - Each topic is associated with a set of top keywords, and the model attempts to group articles into these topics.

3. **Visualization**:
    - The notebook visualizes the discovered topics and their top keywords.
    - Displays how the articles are distributed among different topics.

## Installation

To run this project, you'll need to install the following dependencies:

```bash
pip install pandas numpy matplotlib nltk scikit-learn
```

Additionally, download the NLTK stopwords package (if not already installed):

```python
import nltk
nltk.download('stopwords')
```

## Usage

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/topic-modeling-nmf.git
   cd topic-modeling-nmf
   ```

2. **Open the Jupyter Notebook**:
   Launch Jupyter and open the notebook:

   ```bash
   jupyter notebook Topic_Modelling_using_NMF.ipynb
   ```

3. **Run the Notebook**:
   Follow the step-by-step instructions in the notebook to preprocess the data, train the NMF model, and visualize the topics.

## Customization

- **Adjusting the Number of Topics**: 
  You can change the number of topics in the NMF model by modifying the `n_components` parameter in the following line:
  ```python
  nmf_model = NMF(n_components=6, random_state=42)
  ```

- **Stopwords**: 
  The stopwords list has been expanded beyond the default NLTK English stopwords to remove common non-informative words like 'said', 'would', etc. You can modify this list in the notebook according to your dataset.

## Example Output

The notebook generates an output like the following, showing the topics and their corresponding top words:

```plaintext
Topic 1:
   money, bank, stock, shares, profit

Topic 2:
   match, team, game, win, cup

Topic 3:
   computer, technology, software, internet, device
```

You can also visualize the articles mapped to topics and their corresponding keywords.

## Contributing

Feel free to contribute by:
- Improving the preprocessing pipeline
- Testing with other datasets or vectorization techniques
- Improving the visualizations

1. Fork the repository
2. Create a new feature branch (`git checkout -b feature-branch`)
3. Commit your changes (`git commit -m 'Add feature'`)
4. Push to the branch (`git push origin feature-branch`)
5. Open a Pull Request
