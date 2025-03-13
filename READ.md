# Fake Review Detection

## Authors

- **Hải Dương**, **Xuân Tùng**
- **Supervisor:** Associate Professor **Phan Duy Hưng** - FPT University

## Project Overview

With the increasing reliance on online reviews, fake reviews have become a significant challenge for e-commerce platforms like Shopee and Lazada. However, there is currently no well-established method for detecting fake reviews in Vietnamese e-commerce platforms. This project aims to address this gap by utilizing advanced natural language processing (NLP) techniques to generate and detect fake reviews.

## Research Approach

We propose a two-step methodology for detecting fake reviews:

1. **Generating Fake Reviews**

   - We use **GPT-2** to generate synthetic fake reviews based on real customer feedback from Shopee.

2. **Detecting Fake Reviews**

   - We employ a **BERT-based Vietnamese model** (pre-trained on Vietnamese text) to classify and detect fake reviews with high accuracy.

## Dataset

The dataset used in this research contains authentic product reviews collected from Shopee.

- **Source:** [Shopee Review Dataset](https://www.kaggle.com/datasets/thinhtran2045/shopee-data)

## Folder Structure

### Folder: `fake_comment_detection`

- **models/**: Contains the fine-tuned GPT-2 model for generating fake comments.
- **shopee_data/**:
  - `new_shopee_1.csv`: Filtered data used for training the comment generation model
  - `Generated_Sentences_1.csv`: Dataset containing both machine-generated and real comments
- **Jupyter Notebooks (Pipeline):**
  - `shopee.ipynb` → `create_fine_tuned_gpt2.ipynb` → `create_data_generation.ipynb` → `final_model.ipynb` → `main.ipynb`

## References

- [Fake Reviews Repository](https://github.com/joolsa/FakeReviews.git)

## Future Work

- Expanding the dataset with reviews from additional platforms (e.g., Lazada, Tiki).
- Fine-tuning the BERT-based model for better performance.
- Developing an interactive tool for automated fake review detection.

## Contact

For any inquiries, please reach out to the authors.