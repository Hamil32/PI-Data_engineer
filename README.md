# PI-Data_engineer
PROYECTO INDIVIDUAL N°1 - INGENIERO DE DATOS
Desarrollado por Hamil Flores Balverdi para el bootcamp de Henry
Problemática:
Simulación de un equipo de datos empresarial donde el área de análisis de datos le solicita al de Ingeniería de datos que, utilizando un grupo de conjuntos de datos proporcionados, realice las transformaciones requeridas y posteriormente ponga a disposición los datos mediante la elaboración y ejecución de una API
Rol del desarrollador:
ingeniero de datos
Proceso de "ETL" (Extraer, transformar, cargar) en VisualStudioCode - Python:
EXTRACCIÓN DE DATOS

Importacion de la libreria pandas para el manejo de dataframes
Ingesta de datos (Archivos .csv provistos por el cliente) en respectivos dataframes (Disney, Amazon, Hulu y Netflix)
Análisis exploratorio de los distintos conjuntos de datos para conocer sus características principales
TRANSFORMACIONES

Identificación de generación del campo
Reemplazo valores nulos del campo Calificación por "g"
Conversión de date_added al formato adecuado (AAAA-mm-dd)
Conversión de campos de texto a minúscula utilizando el método "applymap"
Separación de columna "duración" en dos ("duración_int" y "duración_tipo")
En nueva columna "duration_type" unificar temporada y temporadas en "temporada"
Unificar 4 plataformas a través de la función “concat” en un dataframe único "general_df" facilitando el código de las consultas a desarrollar
Cambio tipo de dato "duration_int" a entero
Exportar CSV final (general_df) con todas las transformaciones
Nota: La extracción de datos así como las respectivas transformaciones pueden verse desarrolladas en el archivo ETL.ipynb
Desarrollo de las consultas solicitadas:
CONSULTAS A REALIZAR

Cantidad de veces que aparece una palabra clave en el título de peliculas/series, por plataforma
Cantidad de películas por plataforma con un puntaje mayor a XX en determinado año
La segunda película con mayor partitura para una plataforma determinada, según el orden alfabético de los títulos.
Película que más apareció según año, plataforma y tipo de duración
Cantidad de series y películas por rating
Se desarrolla el código de las funciones que responde a las consultas solicitadas por el cliente

Nota: El desarrollo de las consultas se encuentra alojado en el archivo desarrollo_funciones.ipynb
Proceso de puesta a disposición de los datos utilizando FastAPI (framework que permite construir APIs con Python) y Deta para realizar el deployment:
Generación de archivo main.py (donde desarrollar el script) y otro requirements.txt (donde alojar los requisitos para la API)
Importacion de las librerias a utilizar
Declaración de la creación de la API
Declaración de la ruta de acceso para la base de datos (general_df)
Creación de un índice de directorio con mensaje de bienvenida a la interfaz
Desarrollo de las consultas con formato:
@app.get("/tipo_de_consulta/")
def tipo_de_consulta(variable1:tipo_de_dato, variable"n":...):
  desarrollo_de_la_funcion
Creación de una cuenta en detalle
Instalacion del Deta CLI en consola de forma local mediante el comando "iwr https://get.deta.dev/cli.ps1 -useb | iex"
Comprobacion de la instalacion correcta con "deta --help"
Inicie sesión en detalle a través de la consola mediante el comando "deta login"
Ubicado en el camino de la carpeta donde se encuentra la API desarrollada se procede a la creacion de un micro mediante el comando "deta new"
Una vez creado el micro, se realizan las pruebas correspondientes a las consultas con el endpoint URL provisto por deta.
Instrucciones para la utilizacion de la herramienta:
Ingrese al siguiente URL: https://qlprmb.deta.dev

Segun lo consulta que quiera solicitar, debera agregarle a continuación del URL la consulta y variables con el siguiente formato :

Consulta 1: .../ get_word_count/?plataforma=netflix&keyword=love
Consulta 2: ... /get_score_count/?plataform=netflix&score=85&year=2010
Consulta 3: ... /obtener_segundo_puntaje/?plataforma=amazon
Consulta 4: ... /get_longest/?plataforma=netflix&duracion=min&anio=2016
Consulta 5: ... /get_rating_count/?rate=18%2B
Las variables pueden ser reemplazadas en el formato de consulta por el elemento deseado:

Plataforma : netflix, disney, hulu, amazon
Keyword : puede ser reemplazado por cualquier termino deseado (la busqueda se realiza en el "titulo" de peliculas)
Score : puntaje determinado de película/serie
Año : año de estreno de la película/serie
Duracion : tipo de duracion en min o temporada
Rate : rate de determinada pelicula usando g (general), 7+ , 13+ , 16+ , 18+ ( Nota: el simbola "+" debe ser reemplazado por "%2B" - Ejemplo: 18+ = 18%2B )
Ejemplos de busquedas:
Consulta 1: https://qlprmb.deta.dev/get_word_count/?plataforma=netflix&keyword=love
Consulta 2: https://qlprmb.deta.dev/get_score_count/?plataform=netflix&score=85&year=2010
Consulta 3: https://qlprmb.deta.dev/get_second_score/?plataforma=amazon
Consulta 4: https://qlprmb.deta.dev/get_longest/?plataforma=netflix&duracion=min&anio=2016
Consulta 5: https://qlprmb.deta.dev/get_rating_count/?rate=18%2B
Nota: Para conocer más detalles técnicos acerca de las funciones y sus respectivos parámetros puede ingresar a https://qlprmb.deta.dev/docs
Link a video explicativo confeccionado para equipo de data analytics
Tecnologías utilizadas:
código de estudio visual
Python
Nube de datos
FastApi
uvicornio
biblioteca de pandas
