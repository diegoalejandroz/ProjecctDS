
# Análisis de Componentes Principales PCA

## Cargar librerías
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.preprocessing import StandardScaler, normalize
from sklearn.cluster import KMeans
```

## Cargar DataSet
```
creditcard_df = pd.read_csv("Marketing_data.csv")
creditcard_df.head()
```
## Sumar valores NA de cada variable
```
creditcard_df.isnull().sum()
```

## Reemplazar NA por el valor promedio de la columna
```
creditcard_df.loc[(creditcard_df['MINIMUM_PAYMENTS'].isnull() == True), 'MINIMUM_PAYMENTS'] = creditcard_df['MINIMUM_PAYMENTS'].mean()
creditcard_df.loc[(creditcard_df['CREDIT_LIMIT'].isnull() == True), 'CREDIT_LIMIT'] = creditcard_df['CREDIT_LIMIT'].mean()
```

## Dataset sin la columna Customer ID
```
creditcard_df.drop("CUST_ID", axis = 1, inplace=True)
```
## Escalado de los datos. 
Como es un algoritmo basado en distancias y hay variables con magnitudes muy diferentes, es necesario escalar
```
scaler = StandardScaler()
creditcard_df_scaled = scaler.fit_transform(creditcard_df)
```
# Análisis de Componentes Principales
```
pca = PCA().fit(creditcard_df_scaled)
```

# Gráfica de PCA
```
import matplotlib.pyplot as plt
plt.rcParams["figure.figsize"] = (12,6)

fig, ax = plt.subplots()
xi = np.arange(1, 18, step=1)
y = np.cumsum(pca.explained_variance_ratio_)

plt.ylim(0.0,1.1)
plt.plot(xi, y, marker='o', linestyle='--', color='b')

plt.xlabel('Number of Components')
plt.xticks(np.arange(0, 18, step=1)) #change from 0-based array index to 1-based human-readable label
plt.ylabel('Cumulative variance (%)')
plt.title('The number of components needed to explain variance')

plt.axhline(y=0.95, color='r', linestyle='-')
plt.text(0.5, 0.85, '95% cut-off threshold', color = 'red', fontsize=16)

ax.grid(axis='x')
plt.show()
```

# Reducir las dimensiones (variables) con PCA. 7 dimensiones que explican el 80% de la varianza del total de los datos
```
pca = PCA(n_components = 7)
principal_comp = pca.fit_transform(creditcard_df_scaled)
pca.explained_variance_ratio_.sum()
```

# DataFrame con las 7 componentes
```
pca_df = pd.DataFrame(data = principal_comp, columns=["pca1", "pca2", "pca3", "pca4", "pca5", "pca6", "pca7"])
```
