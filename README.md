# Resultados con método semi automático por coincidencia de tesauros
> Tesis: Diálogo sema onomasiológico. Teoría, método y resultados para el *Diccionario de la Reforma Protestante*

## Explicación

Este método semi automático compara una pregunta natural con un tesauro. Se recomienda abrir el archivo desde :link: [Google Colab](https://colab.research.google.com/github/AlefoElfo/thesis_semiautomatic_thesaurus_matching_method/blob/main/assets/Tesis_M%C3%A9todo_semiautom%C3%A1tico_por_coincidencia_de_tesauros.ipynb) o, si se prefiere, desde este mismo :link: [repositorio GitHub](https://github.com/AlefoElfo/thesis_semiautomatic_thesaurus_matching_method/blob/main/assets/Tesis_M%C3%A9todo_semiautom%C3%A1tico_por_coincidencia_de_tesauros.ipynb)

El tesauro es elaborado manualmente desde una definición del diccionario. Fue un primer ejercicio hacia la elaboración del método siguiente, :link: [Método automático por coincidencia de vectores](https://github.com/AlefoElfo/thesis_automatic_vector_matching_method), que es más eficiente, deja de lado los tesauros y abarca todo el corpus del diccionario.

La ventaja de este mótodo semi automático es que puede clasificar los resultados de búsqueda de acuerdo con el tipo de fuente. Así, las fuentes terciarias se pueden considerar comentarios que aportan valor a la definición principal y que, muchas veces, tales fuentes se aproximen más al lenguaje con el que las personas hacen una búsqueda de información. Las redes sociales, por ejemplo, pueden despertar la curiosidad de las personas o ser la primera fuente de consulta. Tal información podría ser un puente entre terminologías populares  y entre las fuentes primarias y secundarias.

Las secciones principales son:
- Tesauro
- Pregunta
- Resultados de coincidencias

El Tesauro fue hecho previamente en un archivo JSON, el cual es importando, se le extraen las palabras almacenadas en los valores (`llave: valor`) y, por medio de la librería `spaCy`, se almacenan en una lista las palabras que no están vacías de significado (`stop words`) y como tipo raíz o lema (`lemma`).

De la pregunta que hace el usuario se crea una lista de palabras que no son vacías de significado y también formato lema.

Luego se comparan las dos listas, del tesauro (`statenLista`) y de la pregunta (`preguntaLista`) para terminar contando el número de lemas coincidentes.

## Resultado
Sólo se realizaron dos pruebas con las palabras "statenvertaling" y con "Biblia del Oso"

### Statenvertaling
1. 
Archivo JSON ingresado como DICT
Con 9 atributos:

||
|---|
|Nombre|
|Sinónimos|
|Hiperónimos|
|Cohipónimos|
|Hipónimos|
|Polisemia|
|Antonimia|
|Meronimia|
|Definición|

2. 
Archivo DICT se ha limpiado

3. 
Archivo DICT leído con PLN. 72 campos de búsqueda
...
['traducción', 'bíblico', 'país', 'bajo']

4. 
Coincidencias:
{'bajo', 'traducción', 'país'}

### Biblia del Oso
1. 
Archivo JSON ingresado como DICT
Con 9 atributos:

||
|---|
|Nombre|
|Sinónimos|
|Hiperónimos|
|Cohipónimos|
|Hipónimos|
|Polisemia|
|Antonimia|
|Meronimia|
|Definición|

2. 
Archivo DICT se ha limpiado

3. 
Archivo DICT leído con PLN. 72 campos de búsqueda
...
['traducción', 'biblia', 'español']

4. 
Coincidencias:
{'español', 'traducción', 'biblia'}

## Conclusiones
Es poco eficiente generar tesauros para cada entrada del diccionario, más cuando son muchas o hay que estarlas actualizando.

[Mattingly](http://spacy.pythonhumanities.com/01_03_word_vectors.html), acerca de un método diferente por coincidencia de sinónimos, dice:
> This, as we can see, has some potential to work, but again it is not entirely reliable and to work with such a list would be computationally expensive. For both of these reasons, word vectors are prefered. The reason? Because they are formed by the computer on corpora for a specific task. Further, they are numerical in nature (not a dictionary of words), meaning the computer can process them more quickly.

Como se dijo al principio:

Este modelo fue un primer ejercicio hacia la elaboración del método siguiente, :link: [Método automático por coincidencia de vectores](https://github.com/AlefoElfo/thesis_automatic_vector_matching_method), que es más eficiente, deja de lado los tesauros y abarca todo el corpus del diccionario.

