# Deployment del Modelo de Predicción de Sentimiento - Empresa Olist

![](https://rosanarosas.com/wp-content/uploads/2019/07/analisis-sentimientos-RRSS.png)

El presente endpoint, es exclusivo para las personas que posean las credenciales de acceso obtenidas a través de Google Cloud. EL Endpoint en primer lugar solicitará al usuario que arrastre o a través del Browser señale el corespondiente archivo JSON de autorizaciones. EL Endpoint desarrolla dos puntos o etapas claramente marcadas :

## Sentimiento Archivo Externo

*   Recepción de credenciales y autentificación del usuario con Google Clouds.
*   De estar el usuario correctamente autorizado, el endpoint solicitará el o los modelos a Google Cloud
*   Se solicitará al usuario el ingreso mediante arrastre o por browse, del archivo csv de comentarios.
*   Se emitirán las predicciones acerca del Sentimiento según el ejecutable del modelo o modelos escogidos.

### Archivo de Comentarios :

El archivo de comentarios deberá estar en formato CSV y el dataset deberá contener una sola columna , conteniendo los comentarios. Se recomienda efectuar requests que no excedan los 5000 registros. Los comentarios pueden estar en cualquier idioma, el Endpoint maneja traductor universal y trasladará todo comentario en cualquier idioma registrado por Google hacia el idioma portugués.

### Outputs :
El Endpoint emitirá dos gráficos de distribución : un diagrama de pie, un gráfico de barras y un wordcloud de terminos negativos, todos con los resultados de sentimiento calculado. Asimismo el Endpoint generará un archivo csv con los comentarios procesados y su resultado correspondiente en cálculo de sentimiento, el archivo mencionado podrá ser bajado a solicitud del usuario.

## Sentimiento Redes Sociales
Recepción de credenciales y autentificación del usuario con Google Clouds.
De estar el usuario correctamente autorizado, el endpoint solicitará el o los modelos a Google Cloud
Se solicitará al usuario decida por consultar la red social twitter y/o las busquedas de Google.
Se emitirán las predicciones acerca del Sentimiento según el ejecutable del modelo o modelos escogidos.

### Red Social Twitter :
El acceso a la red social Twitter, será en tiempo real, la búsqueda puede traer muchos registros, por razones de procesamiento se restringen los requests a 1000 Tweets. El proceso de conexión a la red de twitter es interno, por lo que el usuario solo deberá escoger la opción. El proceso interno entre otras cosas trasladará todo comentario en cualquier idioma registrado por Google hacia el idioma portugués.

### Google :
Se tiene acceso también a las búsquedas de Google, con la diferencia, que las tablas de Google serán actualizadas cada 6 meses o a pedido del usuario. Las tablas actuales se encuentran almacenadas en un bucket de Google Cloud. Son más de 10,000 registros, por tanto por razones de procesamiento también se restringen los requests a 1000 registros. El proceso de conexión a Google Cloud es interno, por lo que el usuario solo deberá escoger la opción. El proceso interno entre otras cosas trasladará todo comentario en cualquier idioma registrado por Google hacia el idioma portugués.