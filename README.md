# Proyecto Segmentación de clientes para lanzamiento de campañas de marketing

**Fecha:** Septiembre de 2021  
**Elaborado por:** Diego Alejandro Zapata Marín  
**Programa:** Científico de Datos - Nivel Intermedio  
**Centro:** Universidad EAFIT en alianza con Microsoft y la empresa Idata  

**Machine Learning Aprendizaje NO Supervisado - Clustering**    
**Técnica de Segmentación:** K-Means  
**Otras Técnicas aplicadas:** Análisis de Componentes Principales PCA  
**Recursos:** Azure Databricks y Jupyter Notebook  
**DataSet Kaggle:**  __[Credit Card Dataset for Clustering](https://www.kaggle.com/arjunbhasin2013/ccdata)__  


## Contexto
Este proyecto corresponde a la construcción de un modelo de segmentación de clientes con el objetivo de crear campañas de marketing de acuerdo a sus necesidades específicas, que permita consolidar la marca, aumentar los ingresos y apalancar el crecimiento de las ventas.
Allí puedes encontrar lo siguiente:  
   * En la carpeta EDA se encuentra el código en Python del análisis descriptivo y exploratorio de los datos, incluyendo el análisis de correlación de todas las variables del dataset.  
   * En la carpeta PCA se encuentra el código en Python del análisis de componentes principales que permite reducir la dimensión del dataset y, de esta manera, determinar el número de componentes necesarios para que, en nuestro caso, la varianza explicada sea mínimo 80%.  
   * En la carpeta Segmentación K-Means encuentra el código en Python donde se desarrolla la construcción del modelo de aprendizaje NO supervisado K-Means tras la preparación de los datos. La elección del número óptimo K de clusters se realizó con base en el "método del codo".  
   * Código completo en Jupyter Notebook en Full-ProjectDS.  

## Problema
Las empresas trabajan incansablemente para aumentar la productividad. Para lograr esto se valen de tecnologías avanzadas que han ido aumentando significativamente. Machine Learning ha logrado que las empresas encuentren insights importantes a partir de los datos de sus clientes. La segmentación es un método de aprendizaje no supervisado que ha acaparado la atención y ha sido de uso constante en el marketing estratégico que puede ayudar a ofrecer productos específicos de acuerdo al segmento logrado, identificación de nuevos mercados, consolidación de marca, oportunidades en nuevos productos, entre otros.

## Pregunta de Investigación
¿ Cómo construir un modelo de Machine Learning No supervisado que permita segmentar los clientes de un Banco ofreciendo campañas de marketing de acuerdo a sus necesidades particulares?

## Objetivo General
Diseñar un modelo de segmentación que permita lanzar campañas de marketing dirigida a los clientes de un banco en la ciudad de New York.

## Objetivos Específicos	
* Encontrar, a partir de análisis descriptivo de datos, características similares de grupos de clientes que puedan ayudar a identificar sus necesidades particulares.
* Seleccionar el número óptimo de Clusters que permita una adecuada segmentación de mercado específico.
* Investigar y aplicar modelo de análisis de componentes principales PCA que permita establecer una varianza explicada de los datos de mínimo 80%.


## Implicaciones Éticas en modelos de Machine Learning
La Inteligencia Artificial y el Machine Learning ha tenido un auge durante los últimos años y se espera que en los próximos años, los líderes empresariales tengan dentro de su trabajo estas herramientas.  
Las decisiones que toman estos modelos de aprendizaje automático toman cada vez más relevancia y por esto es necesario que lo hagan de manera correcta. Es por esto, que es fundamental enseñarle a estos modelos no solo con información, sino también con principios, ética, responsabilidad, transparencia y que estos se comporten de manera responsable.


## Aspectos Legales y Comerciales
El modelo desarrollado es para el bien común y el beneficio de toda persona que ingrese al mundo de machine learning con esta técnica de aprendizaje no supervisado (Clustering).  
El modelo será de conocimiento accesible, gratuito y de uso público a cualquier usuario.  


## Plan y Fases del Proyecto
    
**Fase I** Contexto y definición del problema  
   * Pregunta de Investigación  
   * Revisión de Literatura, Estado del arte y Bibliografia  
   * Implicaciones Éticas  
   * Aspectos legales y comerciales  
 
**Fase II** Objetivos
   * Objetivo General  
   * Objetivos Específicos  
 
**Fase III** Obtención de los datos
   * Carga de Librerías
   * Carga de datos
   * Resumen de variables

**Fase IV** Preparación y Limpieza de Datos  
   * Datos faltantes NA  
   * Selección de columnas para el modelo de datos
   
**Fase V** Exploración y Análisis Descriptivo  
   * Estadísticos de cada variable  
   * Análisis exploratorio con histogramas  
   * Análisis de correlación    

**Fase VI** Modelado de Datos
   * Análisis de Componentes Principales  
   * Reducción de dimensiones con PCA  
   * Segmentación con K-Means  

**Fase VII** Conclusiones y Trabajo Futuro

