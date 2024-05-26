# Craigslist Category Enhancement Project

## Project Overview

This project aims to improve the categorization and search efficiency in the Health & Beauty section of Craigslist's New York market. The current system lacks the nuanced categorization seen in platforms like eBay, leading to a cluttered and inefficient user experience. Our goal is to implement enhanced categorization through the use of sophisticated data scraping and machine learning techniques to create a more organized and user-friendly interface.

## Methodology

### Phase 1: Data Collection

- **Tools Used**: Selenium and BeautifulSoup for web scraping.
- **Data Scraped**: Retrieved approximately [1,680 product URLs across 19 pages](Web_Scraping_Code_1.ipynb), capturing [detailed product information including descriptions, titles, and IDs](Web_Scraping_Code_2.ipynb).
- **Data Organization**: Compiled all extracted data into a CSV format for further processing.

### Phase 2: Data Labeling

- **Initial Plan**: Intended to use eBay as a model for labeling due to its efficient categorization.
- **Adjustment**: Due to scraping restrictions on eBay, we manually labeled the products.

### Phase 3: Model Training and Evaluation

- **Text Processing**: Tokenized the textual content of each product.
- **Model Development**:
  - [**Logistic Regression**](Categorization_Logistic_Regression.ipynb) :Achieved an accuracy of 0.58 using a TF-IDF vectorizer.
  - [**LSTM**](Categorization_LSTM.ipynb)
    - Accuracy: 0.595
    - Configuration: One-hot encoding, embedding layer, spatial dropout, LSTM layer, dense output layer with softmax activation.
    - Hyperparameters: GloVe dimensions (50, 100, 200, 300), LSTM layer sizes (100 to 200), epochs (1 to 6).
  - [**SVM**](Categorization_SVM.ipynb)
    - Best Accuracy: 0.6666
    - Configuration: TF-IDF vectorizer, multiple kernels tested (Polynomial, Sigmoid, RBF), with RBF providing the best results.

## Results

The SVM model showed the highest accuracy, effectively categorizing products within the Health & Beauty section. This improved the structure and accessibility of the category, addressing the previous challenges of high-dimensional data, small data size, and versatility in product types.

## Conclusion

- **Navigation Ease**: Our new category filters allow users to quickly find products of interest through a structured hierarchy, enhancing the browsing experience.
- **Search Efficiency**: The introduction of category filters narrows down search results, making the shopping process more efficient and user-friendly.
- **Enhanced Product Visibility**: Integrating product filters not only boosts overall product visibility but also aids customers in discovering new items, facilitating better deals.

## Future Work

Further refinement of models and expansion of categories will continue to improve the system's accuracy and user experience.
