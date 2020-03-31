## PCA
```
from sklearn.decomposition import PCA
pca = PCA(n_components=2)
pca_features = pca.fit_transform(features)
pca.explained_variance_ratio_
```
