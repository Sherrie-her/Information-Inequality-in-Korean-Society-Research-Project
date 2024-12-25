# Information-Inequality-in-Korean-Society-Research-Project
From Data Crawling of Naver Q&amp;A to Topic Modelling
<img width="721" alt="Screenshot 2024-12-25 at 8 41 53 PM" src="https://github.com/user-attachments/assets/d3fc6414-8e94-4249-9819-f0b108cff918" />

## Project Overview 
This repository contains research work analyzing information inequality across regions in South Korea using Naver Knowledge-iN Q&A platform data. The project employs topic modeling and SDI (Social Deprivation Index) analysis to understand regional information disparities.

## Repository Structure
```
.
├── .ipynb_checkpoints/           # Jupyter notebook checkpoints
├── data/
│   ├── Questions_new.csv        # Recent Q&A questions dataset
│   ├── Questions_old.csv        # Historical Q&A questions
│   ├── Answers_new.csv         # Recent Q&A answers
│   ├── Answers_old.csv         # Historical Q&A answers 
│   ├── SDI.csv                 # Social Deprivation Index data
│   ├── information_table.csv   # Processed information metrics
│   ├── joined_table.csv        # Combined analysis tables
│   ├── naver_kin_regions_df_l2.csv  # Regional classification
│   └── stopwords.csv           # Korean stopwords for text processing
├── notebooks/
│   ├── URP_11_06.ipynb        # Initial analysis
│   ├── URP_Dec13 (1).ipynb    # Topic modeling implementation
│   ├── URP_Dec5_(2).ipynb     # SDI analysis
│   └── URP_assignment.ipynb    # Final analysis and visualization
└── src/
    ├── Crawling_naver.py      # Naver Knowledge-iN crawler
    └── main.py                # Main execution script
```

## Data Collection Methodology
The `Crawling_naver.py` script implements:
- Web crawling of Naver Knowledge-iN platform using BeautifulSoup4
- Regional classification based on question content
- Data structured with columns:
  - Questions: Document ID, Title, Content, Region, Timestamp
  - Answers: Answer ID, Content, Timestamp

## Analysis Components

### 1. Topic Modeling
Implemented three different approaches:
- **LDA (Latent Dirichlet Allocation)**
  - Used for initial topic discovery
  - Evaluated using Silhouette Score
  - Identifies key terms and topic distributions
- **NMF (Non-negative Matrix Factorization)**
  - Applied for document-term matrix analysis
  - Focuses on identifying regional patterns
- **KoBERT**
  - Utilized for Korean language processing
  - Embedded text data into 768-dimensional vectors
  - Implemented K-means clustering with elbow method

### 2. SDI (Social Deprivation Index) Analysis
- Analyzed regional information disparities using SDI metrics
- Classified regions into three groups:
  - Low SDI: Districts like Seocho-gu, Gangnam-gu
  - Medium SDI: Districts like Dongdaemun-gu, Guro-gu
  - High SDI: Districts like Namyangju, Bucheon
- Correlation analysis between SDI and information patterns

## Topic Categories Identified
1. Treatment, Healthcare, and Education
2. Academic and School Information
3. Public Services and Real Estate
4. Legal Information
5. Transportation and Location Services
6. Community and Life Information

## Requirements
```python
# Core dependencies
pandas
numpy
beautifulsoup4
requests

# NLP & Topic Modeling
konlpy
transformers
torch
gensim

# Visualization
matplotlib
seaborn
plotly

# Deep Learning
pytorch
transformers
```

## Usage
1. Data Collection:
```python
python src/Crawling_naver.py
```

2. Topic Analysis:
```python
jupyter notebook notebooks/URP_Dec13\ \(1\).ipynb
```

## Research Team
- Research Assistant: Team Hayaman Handa
  - Student IDs: 202031445, 202031057, 201931114
- Advisor: Professor Yang Seung Won , Professor Oh Sang Hee
  - Louisiana State University School of Library and Information Science
  - Head, Department of Data Science, School of Library and Information Science, Sungkyunkwan University

## Citations
Lee, Myeong, et al. "The Effects of Socioeconomic Deprivation on Public Library Book Circulation: A Community-Level Study." Journal of the Korean Society for Library and Information Science, vol. 55, no. 4, Nov. 2021, pp. 219-243.

## License
This project is part of the 2024-2 URP research initiative. Please contact the research team for usage permissions.(chaelee29@g.skku.edu)
