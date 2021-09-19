# Proyecto Segmentación de clientes para lanzamiento de campañas de marketing

**Fecha:** Septiembre de 2021  
**Elaborado por:** Diego Alejandro Zapata Marín  
**Programa:** Científico de Datos - Nivel Intermedio  
**Centro:** Universidad EAFIT en alianza con Microsoft y la empresa Idata  

**Técnica de Machine Learning:** Aprendizaje NO Supervisado - Clustering  
**Técnica de Segmentación:** K-Means  
**Otras Técnicas aplicadas:** Análisis de Componentes Principales PCA  
**Recurso de Azure:** Azure Databricks  
**DataSet Kaggle:**  __[Credit Card Dataset for Clustering](https://www.kaggle.com/arjunbhasin2013/ccdata)__  


## Contexto
Este proyecto corresponde a la construcción de un modelo de segmentación de clientes con el objetivo de crear campañas de marketing de acuerdo a sus necesidades específicas, que permita consolidar la marca, aumentas los ingresos y apalancar el crecimiento de las ventas.
Pueden encontras lo siguiente:  
1. En la carpeta EDA se puede encontrar en análisis descriptivo y exploratorio de los datos, incluyendo el análisis de correlación de todas las variables del dataset.
2. En la carpeta PCA se encuentra el análisis de componentes principales que permite reducir la dimensión del dataset determinar el número de componentes necesarios para que, en nuestro caso, la varianza explicada sea mínimo 80%.
3. En la carpeta Segmentación K-Means se desarrolla la construcción del modelo de aprendizaje NO supervisado K-Means tras la preparación de los datos. La elección del número óptimo K de clusters se hará con base en el "método del codo"

## Problema
Las empresas trabajan incansablemente para aumentar la productividad. Para lograr esto se valen de tecnologías avanzadas que han ido aumentando significativamente. Machine Learning ha logrado que las empresas encuentren insights importantes a partir de los datos de sus clientes. La segmentación es un método de aprendizaje no supervisado que ha acaparado la atención y ha sido de uso constante en el marketing estratégico que puede ayudar a ofrecer productos específicos de acuerdo al segmento logrado, identificación de nuevos mercados, consolidación de marca, oportunidades en nuevos productos, entre otros.

## Pregunta de Investigación
¿ Cómo construir un modelo de Machine Learning No supervisado que permita segmentar los clientes de un Banco ofreciendo campañas de marketing de acuerdo a sus necesidades particulares?

## Objetivo General
Diseñar un modelo de segmentación que permita lanzar campañas de marketing dirigida a los clientes de un banco en la ciudad de New York.

## Objetivos Específicos	
* Encontrar, a partir de análisis descriptivo de datos, características similares de grupos de clientes que puedan ayudar a identificar sus necesidades particulares.
* Seleccionar el número óptimo de Clusters que permita una adecuada segmentación de mercado específico.
* Investigar y aplicar modelo de análisis de componentes principales PCA que permita establecer una varianza explicada de los datos de mínimo 90%.

## Plan y Actividades del Proyecto
1. Definición del Problema
2. Obtención de los datos
3. Limpieza de datos
4. Exploración de los datos y análisis descriptivo
5. Modelado de datos
6. Resultados y Conclusiones
