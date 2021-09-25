# Segmentación de Clientes con K-Means

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


## Estadísticos de cada variable
```
round(creditcard_df.describe(),2)
```

### Vamos a investigar quien ha hecho una compra de mas de $30761!
```
creditcard_df[creditcard_df["ONEOFF_PURCHASES"] > 30761]
```

## Análisis de Correlación
```
correlations = creditcard_df.corr()
f, ax = plt.subplots(figsize = (15,15))
sns.heatmap(correlations, annot = True)
```

## Histograma de todas las variables (numericas) con Linea roja (mediana), linea cyan (media)  
k como numero de bins óptimo  

```
k = int(np.ceil(1+np.log2(8950)))
numeric_features = ['BALANCE', 'BALANCE_FREQUENCY', 'PURCHASES', 'ONEOFF_PURCHASES',
       'INSTALLMENTS_PURCHASES', 'CASH_ADVANCE', 'PURCHASES_FREQUENCY',
       'ONEOFF_PURCHASES_FREQUENCY', 'PURCHASES_INSTALLMENTS_FREQUENCY',
       'CASH_ADVANCE_FREQUENCY', 'CASH_ADVANCE_TRX', 'PURCHASES_TRX',
       'CREDIT_LIMIT', 'PAYMENTS', 'MINIMUM_PAYMENTS', 'PRC_FULL_PAYMENT',
       'TENURE']

for col in numeric_features:
    fig = plt.figure(figsize = (9, 5))
    ax = fig.gca()
    feature = creditcard_df[col]
    feature.hist(bins = k, ax = ax)
    ax.axvline(feature.mean(), color = "cyan", linestyle = "dashed") 
    ax.axvline(feature.median(), color = "red", linestyle = "dashed")
    ax.set_title(col)
plt.show();
```

## Histograma - Boxplot de variable BALANCE
```
label = creditcard_df['BALANCE']
fig, ax = plt.subplots(2, 1, figsize = (9, 10))

ax[0].hist(label, bins = k)
ax[0].set_ylabel("Frecuencia")

ax[0].axvline(label.mean(), color = "red", linestyle = "dashed")
ax[0].axvline(label.median(), color = "cyan", linestyle = "dashed")

ax[1].boxplot(label, vert = False)
ax[1].set_xlabel("BALANCE")

fig.suptitle("BALANCE");
```
