Chapter 11: Principal Component Analysis (PCA)
Overview of PCA
Principal Component Analysis (PCA) is a dimensionality reduction technique used to reduce the number of variables in a dataset while preserving as much variability as possible. It transforms the original variables into a new set of uncorrelated variables called principal components.

Performing PCA
Example: Performing PCA
Let's use a hypothetical dataset to demonstrate PCA using Python's scikit-learn library.

python
Copy code
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler

# Creating a sample dataset
np.random.seed(0)
data = np.random.randn(100, 5)
df = pd.DataFrame(data, columns=['Feature1', 'Feature2', 'Feature3', 'Feature4', 'Feature5'])

# Standardizing the data
scaler = StandardScaler()
scaled_data = scaler.fit_transform(df)

# Performing PCA
pca = PCA(n_components=2)
principal_components = pca.fit_transform(scaled_data)

# Creating a DataFrame with the principal components
df_pca = pd.DataFrame(data=principal_components, columns=['Principal Component 1', 'Principal Component 2'])

# Visualizing the principal components
plt.scatter(df_pca['Principal Component 1'], df_pca['Principal Component 2'])
plt.xlabel('Principal Component 1')
plt.ylabel('Principal Component 2')
plt.title('PCA Result')
plt.show()
Interpreting PCA Results
Explained Variance
The explained variance indicates how much information (variance) can be attributed to each of the principal components.

python
Copy code
# Explained variance
explained_variance = pca.explained_variance_ratio_
print(f'Explained variance by component: {explained_variance}')

# Plotting explained variance
plt.bar(range(1, len(explained_variance) + 1), explained_variance)
plt.xlabel('Principal Component')
plt.ylabel('Explained Variance Ratio')
plt.title('Explained Variance by Principal Components')
plt.show()
Cumulative Explained Variance
The cumulative explained variance shows the total variance explained by the first n principal components.

python
Copy code
# Cumulative explained variance
cumulative_explained_variance = np.cumsum(explained_variance)
print(f'Cumulative explained variance: {cumulative_explained_variance}')

# Plotting cumulative explained variance
plt.plot(range(1, len(cumulative_explained_variance) + 1), cumulative_explained_variance)
plt.xlabel('Number of Principal Components')
plt.ylabel('Cumulative Explained Variance')
plt.title('Cumulative Explained Variance by Principal Components')
plt.show()
Principal Component Loadings
The loadings are the weights by which each standardized original variable should be multiplied to get the principal component score.

python
Copy code
# Principal component loadings
loadings = pca.components_
loadings_df = pd.DataFrame(loadings, columns=df.columns, index=['Principal Component 1', 'Principal Component 2'])
print(loadings_df)

# Visualizing loadings
plt.matshow(loadings, cmap='viridis')
plt.colorbar()
plt.xticks(range(len(df.columns)), df.columns, rotation=90)
plt.yticks(range(len(loadings_df.index)), loadings_df.index)
plt.title('Principal Component Loadings')
plt.show()
Example: Complete Workflow
Here is a complete example that demonstrates performing PCA and interpreting the results.

python
Copy code
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler

# Creating a sample dataset
np.random.seed(0)
data = np.random.randn(100, 5)
df = pd.DataFrame(data, columns=['Feature1', 'Feature2', 'Feature3', 'Feature4', 'Feature5'])

# Standardizing the data
scaler = StandardScaler()
scaled_data = scaler.fit_transform(df)

# Performing PCA
pca = PCA(n_components=2)
principal_components = pca.fit_transform(scaled_data)

# Creating a DataFrame with the principal components
df_pca = pd.DataFrame(data=principal_components, columns=['Principal Component 1', 'Principal Component 2'])

# Visualizing the principal components
plt.scatter(df_pca['Principal Component 1'], df_pca['Principal Component 2'])
plt.xlabel('Principal Component 1')
plt.ylabel('Principal Component 2')
plt.title('PCA Result')
plt.show()

# Explained variance
explained_variance = pca.explained_variance_ratio_
print(f'Explained variance by component: {explained_variance}')

# Plotting explained variance
plt.bar(range(1, len(explained_variance) + 1), explained_variance)
plt.xlabel('Principal Component')
plt.ylabel('Explained Variance Ratio')
plt.title('Explained Variance by Principal Components')
plt.show()

# Cumulative explained variance
cumulative_explained_variance = np.cumsum(explained_variance)
print(f'Cumulative explained variance: {cumulative_explained_variance}')

# Plotting cumulative explained variance
plt.plot(range(1, len(cumulative_explained_variance) + 1), cumulative_explained_variance)
plt.xlabel('Number of Principal Components')
plt.ylabel('Cumulative Explained Variance')
plt.title('Cumulative Explained Variance by Principal Components')
plt.show()

# Principal component loadings
loadings = pca.components_
loadings_df = pd.DataFrame(loadings, columns=df.columns, index=['Principal Component 1', 'Principal Component 2'])
print(loadings_df)

# Visualizing loadings
plt.matshow(loadings, cmap='viridis')
plt.colorbar()
plt.xticks(range(len(df.columns)), df.columns, rotation=90)
plt.yticks(range(len(loadings_df.index)), loadings_df.index)
plt.title('Principal Component Loadings')
plt.show()
In this chapter, we covered the basics of Principal Component Analysis (PCA), including performing PCA and interpreting the results. We provided examples to demonstrate how to perform PCA using Python's scikit-learn library and how to interpret the explained variance, cumulative explained variance, and principal component loadings.
