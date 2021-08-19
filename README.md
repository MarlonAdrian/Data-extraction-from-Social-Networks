# Data-extraction-from-Social-Networks

**1. Twitter (Extracción y envío del mismo hacia CouchDB)**
   - Para realizar la extracción de datos de Twitter se debe tomar en cuenta que se debe poseer credenciales, de lo contrario será un poco más complicado realizar la actividad. Además, si se desea obtener datos de algún sitio en específico se lo hará mediante la página web: https://boundingbox.klokantech.com/ . En la parte inferior izquierda existe la opción del tipo de formato que retornará la ubicación, para esta ocasión se utilizó la de formato CSV, se copiará este archivo csv y se lo pegará en la línea 45 del código twitter.py (dentro de los corchetes). Por otra parte, si se desea extraer datos de algún tema en común se debe escribir dicho tema en la línea 45. **Tomar en cuenta que es mejor realizar uno de estos a la vez**.
Una vez hallado los tuits se los enviarán hacia la base de datos de CouchDB (línea 37 hasta 41)



**2. Facebook (Extracción y envío del mismo hacia MongoDB)**
   - Se importan las bibliotecas que se requerirán para realizar dicha petición, tomar en cuenta que si se tiene enlazada la cuenta de Facebook ya sea con gmail o el numero de celular, se enviará un mensaje de confirmación de este procedimiento a realizar.
En la línea 35 se especificará el numero de paginas que en que se buscará la información, para que no exista tanta información en las paginas se colocó el número 3. Este traerá como resultado la fecha, el texto, likes, comentaros, etc., de la publicación. **Todo esta extracción se la guardará en un archivo de formato json, dado que MongoDB admite formatos Json y CSV.**

**3. Web Scraping (Extracción de datos de una pagina web en particular y envío del mismo hacia MongoDB)**
   - Cuando se hace web Scraping se debe tene runa pagina web base de donde se extraerán los datos, la pagina de "El comercio" será en esta ocasión. Además de que la información extraída será almacenada en arrays, y después guardada en un formato Json. Finalmente se lo enviará a MongoDB.

**4. Tik Tok (Extracción de datos de cuentas oficiales mediante el símbolo del sistema)**
   - Con respecto a la obtención de datos de tik tok se utilizó la consola de windows en base a algunas librería que permiten tener acceso a los datos de esta red social. La cuenta en esta ocasión será la de **olympicteamisrael**. Una vez que se ingrese a la consola y en la carpeta en donde se desea guardar la info se deberá escribir las siguientes combinaciones:
   - *Nota: Si el usuario no desea presionar Enter podría escribir a su gusto los campos necesarios allí.*
     - *npm init* , este inicializa un proyecto, la cual tendrá un servidor, archivos de configuración e inicializa el entorno. 
       - package name: (tiktok) **nombre aleatorio***
       - version: (1.0.0)g **teclear *Enter***
       - description: **teclear *Enter***
       - entry point: (index.js) **teclear *Enter***
       - test command: **teclear *Enter***
       - git repository: **teclear *Enter***
       - keywords: **teclear *Enter***
       - author: **teclear *Enter***
     - *npm install calculator*, el npm es un administrador de paquetes; posee para Word, Excel, gif, mp3, etc.(tiene página oficial para descargarlos).
     - *npm install -g calculator*, el -g significa que se instalará en todo el entorno de programación.
     - *node-calc*
     - *npm i -g tiktok-scraper*    
     - Finalmente se escribe el nombre la cuenta oficial a buscar con el tipo de formato a guardarse, dado que se lo enviará a otra base de datos se lo pondra como csv: *tiktok-scraper user olympicteamisrael -t csv*


**5. Envío de los datos de Twitter a MongoDB (CouchDB hacia MongoDB)**
   - Dado que en el paso 1 los datos extraídos de Twitter fueron enviados a CouchDB, ahora se los enviará a MongoDb de la siguiente manera:
     - En el Script de Twitter se puso como nombre a la base de datos "name_data_base", pues esta base se la hallará así: ![Imagen1](https://user-images.githubusercontent.com/66731201/130008138-f16a87d2-c244-44d4-9e50-d689a7123540.png)
     - Se ingresará a dicha base de datos y se debe asegurar que el formato esté en el de tipo json, y en la parte superios derecha se dará clic en *{}Json*  
       - 
![Imagen2](https://user-images.githubusercontent.com/66731201/130008610-6d8175c3-cfaf-468f-be94-ecbcfa3e8bf4.png)
     - Se abrirá un nueva pestaña en el navegador con toda la información, entonces se debe dar un clic derecho y guardar el archivo.
     - Luego se debe dirigir a MongoDB y en *Create DataBase* se pondrá el nombre de la base de datos a crear y de la colección (en este caso será twitter e info_twitter).
     - En la siguiente captura de imagen se importará el archivo Json que se descargó en CouchDB ![3]
       - (https://user-images.githubusercontent.com/66731201/130009458-5bba3e2f-f5e4-4caa-87fa-1096bfc0867f.png) 
     - Finalmente se selecciona el archivo y se lo importa **Tomar en cuenta que el formato Json cumple una gramatica en específico**
       - ![4](https://user-images.githubusercontent.com/66731201/130010453-7290698e-c1ad-4db4-b7e0-a5e90583343d.png)
  
**6. Envío de los datos de Tik Tok a MongoDB (SQLite hacia MongoDB)**

**7. Enviar base de datos de MongoDB a MongoDB Atlas**


  
