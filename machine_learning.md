## PCA
```
from sklearn.decomposition import PCA
pca = PCA(n_components=2)
pca_features = pca.fit_transform(features)
pca.explained_variance_ratio_
```
## T-SNE
```
from sklearn.manifold import TSNE
tsne = TSNE(n_components=2, init='pca', random_state=0)
tsne_features = tsne.fit_transform(features)
```
