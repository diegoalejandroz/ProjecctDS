# Segmentación de Clientes con K-Means

## Cargar librerías

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.preprocessing import StandardScaler, normalize
from sklearn.cluster import KMeans

## Cargar DataSet
creditcard_df = pd.read_csv("Marketing_data.csv")
creditcard_df.head()

# Sumar valores NA de cada variable
creditcard_df.isnull().sum()

# Reemplazar NA por el valor promedio de la columna
creditcard_df.loc[(creditcard_df['MINIMUM_PAYMENTS'].isnull() == True), 'MINIMUM_PAYMENTS'] = creditcard_df['MINIMUM_PAYMENTS'].mean()
creditcard_df.loc[(creditcard_df['CREDIT_LIMIT'].isnull() == True), 'CREDIT_LIMIT'] = creditcard_df['CREDIT_LIMIT'].mean()

# Dataset sin la columna Customer ID
creditcard_df.drop("CUST_ID", axis = 1, inplace=True)

# Escalado de los datos. 
# Como es un algoritmo basado en distancias y hay variables con magnitudes muy diferentes, es necesario escalar
scaler = StandardScaler()
creditcard_df_scaled = scaler.fit_transform(creditcard_df)

# 4 Clusters con la "técnica del codo"
wcss = []
for i in range(1, 15):
    kmeans = KMeans(n_clusters = i, init = "k-means++", max_iter = 300, n_init = 10, random_state = 0)
    kmeans.fit(pca_df)
    wcss.append(kmeans.inertia_)

plt.plot(range(1,15), wcss)
plt.title("Número óptimo de Clusters")
plt.xlabel("Número de Clusters")
plt.ylabel("WCSS(k)")
plt.show()

# Etiquetas de los clusters
kmeans = KMeans(4)
kmeans.fit(pca_df)
labels = kmeans.labels_

# Asignar cluster a cada observacion original
creditcard_df_cluster = pd.concat([creditcard_df, pd.DataFrame({'cluster': labels})], axis = 1)
creditcard_df_cluster.head(5)

# Histogramas para cada cluster 
for i in creditcard_df.columns:
    plt.figure(figsize=(35, 5))
    for j in range(4):
        plt.subplot(1, 4, j+1)
        cluster = creditcard_df_cluster[creditcard_df_cluster['cluster'] == j]
        cluster[i].hist(bins = k)
        plt.title('{}    \nCluster {}'.format(i, j))
    plt.show()
