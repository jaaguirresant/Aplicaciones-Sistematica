# Aplicaciones-Sistematica

# Sistematica-Filogenetica

# MÓDULO INFERENCIA FILOGENÉTICA


## Objetivos

1. Aprender las bases metodológicas de los principales métodos de inferencia filogenética a partir de matrices de caracteres homólogos y evaluar críticamente los supuestos, virtudes y desventajas de estos métodos.

2. Conocer los principios estadísticos para medición de la confianza de las hipótesis filogenéticas.  

3. Adquirir destrezas computacionales para llevar a cabo análisis de inferencia filogenética a partir de matrices de caracteres empíricas.

## Competencias

1. Habilidad de inferir e interpretar críticamente hipótesis de relaciones filogenéticas en cualquier grupo de organismos generadas bajo distintas metodologías a partir de matrices de caracteres.

2. Capacidad para interpretar fundamentos de la biología evolutiva en un árbol filogenético generado a partir de matrices de caracteres empíricas.

3. Entendimiento de la importancia de la inferencia filogenética para abordar problemas biológicos en un contexto evolutivo.

## Estructura general del módulo

### Preparación

Este módulo ha sido diseñado para estudiantes del curso de posgrado "Sistemática Filogenética y Nomenclatura Botánica/Zoológica" del programa de Maestría en Ciencias-Biología de la Universidad Nacional de Colombia. Los estudiantes inscritos en este curso ya debieron haber tomado cinco semanas de temas introductorios sobre evolución y sistemática filogenética para poder seguir con los contenidos de este módulo. Este módulo fue diseñado para ser tomado de manera remota dada la emergencia generada por el virus COVID-19. 

#### Los requerimientos y materiales básicos para llevar a cabo este módulo son los siguientes:

A. Computador o laptop con los siguientes programas instalados: 
- Editor de texto (recomendados notepad++ para Windows y Atom para Mac).
- [Mesquite](https://www.mesquiteproject.org/). Útil para construir y/o visualizar matrices de caracteres.
- R y R Studio (bajar los paquetes: Ape, Claddis, Phangorn, Phytools).
- [TNT](http://www.lillo.org.ar/phylogeny/tnt/). GUI solo para Windows. Para análisis de Máxima Parsimonia.
- [jmodelTest](https://github.com/ddarriba/jmodeltest2). Para selección de modelos evolutivos de secuencias de nucleótidos.
- [RAxML-GUI](https://antonellilab.github.io/raxmlGUI/). Para análisis de Máxima Verosimilitud.
- [MrBayes](http://nbisweden.github.io/MrBayes/download.html). Para análisis de Inferencia Bayesiana.
- [ASTRAL](https://github.com/smirarab/ASTRAL/blob/master/README.md). Para inferencia de árboles de especies a partir de árboles de genes.
- [FigTree](https://github.com/rambaut/figtree/releases). Para visualización y edición de árboles filogenéticos.
- [Tracer](https://github.com/beast-dev/tracer/releases/tag/v1.7.1). Para visualizar resultados de MCMC.

**Nota:** Es posible que usemos otros programas, pero les avisaré con tiempo. Todos los programas de inferencia filogenética vienen acompañados con sus respectivos tutoriales. Se sugiere seguirlos en su tiempo libre; no se limiten únicamente a los ejercicios de la clase.  

B. Abrir una cuenta en el portal [CIPRES](http://www.phylo.org/).

C. Disponibilidad técnica (conexión a internet) para las sesiones virtuales. Si tiene problemas para conectarse, ponerse en contacto directamente conmigo con suficiente anticipación (jaaguirresa@unal.edu.co).

### Dinámica de las clases

Para facilitar el trabajo autónomo de los estudiantes desde sus casas y minimizar la presencialidad en las sesiones virtuales, este módulo está principalmente enfocado en talleres y lecturas en casa. Las sesiones virtuales estarán limitadas a clases cortas sobre conceptos fundamentales de los métodos, explicación de las tareas, resolución de dudas y presentación de resultados. Todas las presentaciones con diapositivas, artículos y talleres serán subidos a esta plataforma en su debido momento. Se recomienda enfáticamente replicar los ejercicios practicados en clase con los datos de sus proyecto de semestre.

## Contenido

### Semana 1

**[Clase 1](/clase_1/Taller_matrices.md). Repaso y corto taller de manejo de matrices y datos en R.** se hará un breve repaso de los recursos informáticos para construcción de matrices con editor de texto, el programa Mesquite y R. Descargar la presentación [aquí](/clase_1/Clase_1.pdf). Para esta parte se deben descargar las siguientes matrices para este ejercicio: [ADN.tnt](/clase_1/ADN.tnt), [morfologia.tnt](/clase_1/morfologia.tnt),[morfologia.nex](/clase_1/morfologia.nex), [ADN.nex](/clase_1/ADN.nex), [ADN.phy](/clase_1/ADN.phy). 

**[IR AL TALLER](/clase_1/Taller_matrices.md)**

#

**[Clase 2](/clase_2/Taller_2.md). Métodos de distancia y argumentación Hennigiana.** Esta clase hace una breve mención a los métodos que dieron origen a los métodos modernos de inferencia filogenética. Descargar diapositivas [aquí](/clase_2/Clase_2.pdf). Para la parte práctica hacer el taller de ejercicios manuales con datos morfológicos para inferir árboles filogenéticos usando UPGMA y argumentación Hennigiana. 

**[IR AL TALLER 2](/clase_2/Taller_2.md)**

<p align="center">
  <img src="https://github.com/jaaguirresant/Sistematica-Filogenetica/blob/master/clase_2/Hennig_book.jpg" width="130" height="200" />
</p>


**_NOTA:_** Para esta y las próximas dos clases se requiere leer los siguientes artículos:

- Métodos de distancia: [Van de Peer 2009](/clase_2/distancia.pdf)

- Argumentación Hennigiana y Máxima Parsimonia: [Wiley & Lieberman 2011 - Capítulo 6](/clase_2/MP_Wiley_Lieberman.pdf)

#

**[Clase 3](/Clase_3/Taller_MP1.md). Criterio de optimalidad y Máxima Parsimonia.** En esta clase se define el concepto de "criterio de optimalidad" para la inferencia filogenética y se presenta el primer método que incorpora este criterio: la Máxima Parsimonia (Descargar diapositivas [aquí](/Clase_3/Clase_3.pdf)). Esta clase se complementa con un taller básico de inferencia manual de hipótesis filogenéticas usando este método. 

**[IR AL TALLER 3](/Clase_3/Taller_MP1.md)**

<p align="center">
  <img src="https://github.com/jaaguirresant/Sistematica-Filogenetica/blob/master/Clase_3/Strict.png" width="250" height="200" />
</p>

**NOTA:** Para la próxima clase leer los siguientes artículos: 

- [Wiens 2011](/Clase_3/Wiens_2011.pdf)

- [González 1999](/Clase_3/Gonzalez_1999_Aristolochia.pdf)

#

### Semana 2

**[Clase 4](/clase_4/Taller_MP2.md). Ramificaciones de la Máxima Parsimonia y medidas de confianza.** En esta clase se explican algunas ramificaciones de la Máxima Parsimonia y se explican los métodos principales para medir la confianza en las hipótesis filogenéticas ([Descargar diapositivas aquí](/clase_4/clase_4.pdf)). Esta clase termina con un taller manual de ejercicios y una práctica computacional de inferencia filogenética con Máxima Parsimonia usando el programa TNT y el paquete Phangorn de R. 

<p align="center">
  <img src="https://github.com/jaaguirresant/Sistematica-Filogenetica/blob/master/clase_4/Gastrotheca2.jpg" width="250" height="300" />
</p>

**[IR AL TALLER 4](/clase_4/Taller_MP2.md)**

**Nota 1:** Para la clase del miércoles, traer una corta presentación (5-10 minutos) donde explican las matrices que usarán en sus proyectos y las matrices en formato Nexus.

**Nota 2:** Para la clase del jueves leer:

1. Modelos evolutivos: [Strimmer & Haeseler 2009](/clase_4/Modelos.pdf).

2. Filogenética paramétrica: [Wiley & Lieberman 2011 - Capítulo 7](/clase_4/Parametric_Phylogenetics.pdf).

3. Atracción de ramas largas: [Philippe et al. 2005](/clase_4/LBA_2005.pdf). 

#

**[Clase 5](/clase_5/Taller_Lectura_Gonzalez_1999.md). Discusión de artículo y presentación de matrices del proyecto.**  Esta clase se destina a discutir el artículo de [González 1999](/clase_3/Gonzalez_1999_Aristolochia.pdf) y a presentar las matrices de los proyectos individuales (PowerPoint de máximo 10 minutos por persona). Para la discusión del artículo es necesario leer y responder las preguntas del siguiente enlace: 

[Taller artículo González (1999)](/clase_5/Taller_Lectura_Gonzalez_1999.md)

#

**[Clase 6](/clase_5/Taller_arboles.md). Taller de manejo de árboles filogenéticos e introducción a la inferencia filogenética usando modelos evolutivos.**  Esta clase se destina a realizar un taller sobre la visualización y manipulación de archivos de árboles filogenéticos ([Descargar taller aquí](/clase_5/Taller_arboles.md)) y a una breve discusión guiada sobre los problemas asociados a la inferencia filogenética usando Máxima Parsimonia y un introducción a los métodos de inferencia filogenética usando modelos de evolución. Para esto último es necesario tener fresca la lectura de los siguientes artículos:

- [Strimmer & Haeseler 2009](/clase_4/Modelos.pdf).

- [Philippe et al. 2005](/clase_4/LBA_2005.pdf). 

Como complemento de las lecturas, responder las preguntas del siguiente cuestionario y subir las respuestas al DRIVE:

[Cuestionario LBA y modelos evoltivos](/clase_6/Taller_Lectura_Modelos.md)

#

### Semana 3

**Clase 7. Modelos evolutivos.** Esta clase se destinan a entender los conceptos básicos del uso de modelos evolutivos explícitos para la inferencia filogenética usando la máxima verosimilitud como criterio de opimalidad ([Descargar diapositivas aquí](/clase_7/clase_7.pdf)).

<p align="center">
  <img src="https://github.com/jaaguirresant/Sistematica-Filogenetica/blob/master/clase_7/Imagen_c7.jpg" width="250" height="270" />
</p>

**NOTA:** Recuerden que para esta  y las próximas dos clases deben haber leído el siguiente capítulo:

- Filogenética paramétrica: [Wiley & Lieberman 2011 - Capítulo 7](/clase_4/Parametric_Phylogenetics.pdf).

#

**[Clase 8](/clase_7/Taller_ML_1.md). Máxima verosimilitud.** Esta clase se divide en dos partes:

1. Charla sobre los fundamentos de la máxima verosimilitud como criterio de opimalidad ([Descargar diapositivas aquí](/clase_7/clase_7.pdf)). 

   - **Tarea.** Realizar los ejercicios del siguiente taller: [TALLER MV](/clase_7/Taller_ML_1.md)

2. Taller de inferencia filogenética usando la Máxima Verosimilitud en R: [ir al Script de R aquí](/clase_8/ML.R). Para este taller usaremos la matriz de ADN de primates del siguiente enlace: [ADN.nex](/clase_1/ADN.nex). 

   - **NOTA:** Se recomienda que los estudiantes realicen el ejercicio previo a la clase y se preparen para explicarlo. Casi todo el ejercicio fue tomado y modificado del siguiente artículo: [Schliep (2019)](/clase_8/Phangorn.pdf).

   - **Tarea.** Responder las preguntas del Script. 

#

**Clase 9. Inferencia Bayesiana.** El objetivo de esta clase es el de aprender como implementar la estadística bayesiana en el contexto de la inferencia filogenética. Para esto, presentaré una corta clase de conceptos fundamentales (bajar diapositivas [aquí](/clase_9/clase_9.pdf) y haremos un ejercicio práctico de inferencia filogenética con el programa [MrBayes](http://nbisweden.github.io/MrBayes/download.html).

<p align="center">
  <img src="https://anabelforte.com/wp-content/uploads/2020/04/Thomas_Bayes.gif" width="250" height="270" />
</p>

Para la práctica usaremos la matriz [primates.nex](/clase_9/primates.nex) y seguiremos el siguiente tutorial: http://mrbayes.sourceforge.net/mb3.2_manual.pdf

**Nota:** Las siguientes lecturas son excelentes complementos para la clase: [Hueselnbeck & Roquist (2004)](/clase_9/Bayesiano_1.pdf) y [Huelsenbeck et al (2002)](/clase_9/Bayesiano_2.pdf)

**Tarea:** Leer para la próxima clase el siguiente artículo: [Sanderson & Schauffer (2002)](/clase_9/Lectura.pdf).

#

### Semana 3

**Clase 10. Evaluación crítica de hipótesis filogenéticas** En esta clase estudiaremos de forma crítica algunos aspectos metodológicos y biológicos generales que deben tenerse en cuenta en los análisis de inferencia filogenética. Para esto haremos una corta clase donde mencionaremos estos aspectos y algunas ayudas metodológicas para sobrellevarlos ([bajar diaposistivas acá](/clase_10/Clase_10.pdf)). La clase se complementa con un taller sobre los temas aprendidos ([Ir al Taller](/clase_10/Taller_clase_10.md)).

<p align="center">
  <img src="https://www.researchgate.net/publication/330808851/figure/fig1/AS:721682977275905@1549074038961/Effect-of-introgression-and-incomplete-lineage-sorting-ILS-in-molecular.png" width="350" height="250" />
</p>

[Fuente de la imagen](https://www.researchgate.net/publication/330808851/figure/fig1/AS:721682977275905@1549074038961/Effect-of-introgression-and-incomplete-lineage-sorting-ILS-in-molecular.png)

#

**Clase 11. Sistemática Filogenética en la práctica** Para esta clase presentaremos dos estudios empíricos de sistemática filogenética realizados por investigadores colombianos. Esta actividad tiene dos propósitos: (1) que los estudiantes se empapen de la investigación en filogenética que hacen los investigadores colombianos, y (2) analizar de una manera crítica las estrategias metodológicas, preguntas de investigación y conclusiones de este tipo de investigaciones. Como preparación para esta actividad, los estudiantes deberán leer los siguientes artículos:

- [Clark, J. L., Clavijo, L., & Muchhala, N. (2015). Convergence of anti-bee pollination mechanisms in the Neotropical plant genus Drymonia (Gesneriaceae). Evolutionary Ecology, 29(3), 355-377.](/clase_11/Clavijo.pdf)

- [Aguirre-Santoro, J., Michelangeli, F. A., & Stevenson, D. W. (2016). Molecular Phylogenetics of the Ronnbergia Alliance (Bromeliaceae, Bromelioideae) and insights into their morphological evolution. Molecular phylogenetics and evolution, 100, 1-20.](/clase_11/Aguirre.pdf)

Para esta clase es necesario que los estudiantes preparen por lo menos tres preguntas sobre los tres principales componentes del estudio: la pregunta de investigación, los métodos y las conclusiones. En el caso de los métodos, pueden hacer preguntas detalladas sobre los muestreos de taxones y caracteres, método de inferencia escogido, modelos evolutivos, medidas de soporte y supuestos biológicos de los sistemas de estudio. 

#

**Clase 12. Presentación de proyectos finales** 

Tiempo para cada presentación: 30 minutos (incluyendo tiempo para preguntas).

