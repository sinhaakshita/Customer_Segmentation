# Customer Segmentation with K-Means

This project explores customer marketing data and groups customers into similar segments using **K-Means clustering**. It includes data cleaning, exploratory analysis, feature preparation, cluster selection using the elbow method, and a two-dimensional visualization of the final segments.

## Project overview

The notebook answers a simple business question: **which customers share similar characteristics and purchasing behavior?**

It uses demographic, household, purchasing, campaign, and offer-response variables to identify five customer segments. These segments can support more targeted marketing campaigns and customer analysis.

## Workflow

1. Load the customer dataset (`new.csv`)
2. Inspect data types, descriptive statistics, missing values, and unique values
3. Remove rows with missing values
4. Extract day, month, and year from `Dt_Customer`
5. Remove non-useful or constant columns
6. Explore categorical columns such as `Education` and `Marital_Status`
7. Compare categorical groups by their marketing-offer response
8. Encode categorical values with `LabelEncoder`
9. Inspect highly correlated features
10. Standardize features and create a t-SNE projection for visualization
11. Use the elbow method to select the number of clusters
12. Fit a five-cluster K-Means model and visualize the resulting segments

## Visualizations

The notebook produces:

- Count plots for categorical customer attributes
- Offer-response comparisons by customer category
- A correlation heatmap
- A two-dimensional t-SNE customer map
- An elbow curve for choosing a cluster count
- A color-coded scatter plot of the final customer segments

## Tech stack

- Python
- Pandas and NumPy for data processing
- Matplotlib and Seaborn for visualization
- Scikit-learn for preprocessing, t-SNE, and K-Means clustering
- Jupyter Notebook

## Getting started

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd <your-repository-folder>
```

### 2. Install dependencies

```bash
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
```

### 3. Add the dataset

Place the dataset file in the same folder as the notebook and name it:

```text
new.csv
```

### 4. Run the notebook

```bash
jupyter notebook Customer_Segmentation.ipynb
```

Run the cells from top to bottom.

## Repository structure

```text
├── Customer_Segmentation.ipynb   # Analysis, visualizations, and clustering model
├── new.csv                       # Customer marketing dataset (add locally)
└── README.md                     # Project documentation
```

## Notes

- The dataset contains a small number of missing `Income` values; the notebook removes incomplete records before analysis.
- `Education` and `Marital_Status` are converted to numeric values before clustering.
- The elbow curve is used to select **five clusters** for the final K-Means model.
- Cluster numbers (`0` through `4`) are labels only. To turn them into business personas, compare the average values of key features within each segment.

## Possible improvements

- Fit K-Means on the standardized feature matrix rather than the unscaled data.
- Profile each cluster with average income, spending, household composition, and response rate.
- Add meaningful business names to segments after profiling them.
- Save the trained model and cluster assignments for reuse.
- Add a `requirements.txt` file for reproducible setup.

