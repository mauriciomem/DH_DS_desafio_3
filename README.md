 ## DH - DESAFIO 3

 ### Alcance de trabajo y caracteristicas generales

 ### Rx de tórax en pacientes COVID-19
https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7269964/

Las radiografías de tórax son la modalidad de imagen más utilizada para casos de Covid-19 sospechosos y confirmados.
Los hallazgos en las imágenes pueden variar según la etapa de la enfermedad (días desde los primeros síntomas) y según la gravedad de la misma. Ejemplo:

![](https://github.com/DHDSDesafios/DH_DS_desafio_3/raw/master/data/severidad_covid19.jpg)

La sensibilidad del método varía según los hallazgos y según la técnica: en promedio 69%, y la especificidad es baja, promedio 40%<sup>[1]</sup>.

TÉCNICA:
 * paciente en bipedestación 
 * apoya el pecho al centro de chasis con las muñecas colocadas en las caderas y los hombros hacia delante.
 *  El rayo debe dirigirse horizontalmente al centro del chasis o hacia la altura de la sexta vértebra dorsal con distancia tubo-película de 1,80 y no debe ser menor a 1,5 m.
 *  en inspiración completa.

![](https://github.com/DHDSDesafios/DH_DS_desafio_3/raw/master/data/radiografia_tecnica.png)

 #### Hallazgos de RX de tórax en pacientes con COVID-19

Lo más frecuente que podemos encontrar son infiltrados en los campos pulmonares con distintos grados (desde vidrio esmerilado hasta consolidación del parénquima pulmonar),que suelen estar en zonas periféricas del pulmón<sup>[2]</sup>.

Ejemplo de grados:

![](https://github.com/DHDSDesafios/DH_DS_desafio_3/raw/master/data/foto_grados_covid19.jpg)

En este último cuadro podemos ver que pacientes con COVID + pueden tener RX normales<sup>[3]</sup>.

![](https://github.com/DHDSDesafios/DH_DS_desafio_3/raw/master/data/table2.jpg)
![](https://github.com/DHDSDesafios/DH_DS_desafio_3/raw/master/data/table3.png)

La tomografía de tórax tiene mayor sensibilidad y especificidad, de cualquier modo es difícil poder diferenciar. 
Excepto por una mayor prevalencia de distribución periférica, la afectación de los lóbulos superior y medio, la neumonía viral COVID-19 y no COVID presentaron hallazgos de TC de tórax superpuestos<sup>[4][5]</sup>.

**COMPARACIÓN CON OTRAS NEUMONÍAS VÍRICAS**

Recientemente se ha publicado un estudio comparativo entre la neumonía por COVID y otras neumonías víricas. Las características más discriminatorias para la neumonía por COVID-19 incluyeron:
 * Distribución periférica (80% vs. 57%, p <0.001)
 * Opacidad de vidrio deslustrado (91% vs. 68%, p <0.001)
 * Engrosamiento vascular (58% frente a 22%, p <0,001).
Pese a este estudio la opinión más extendida es que la neumonía por COVID-19 y otras neumonías víricas pueden ser indistinguibles, de aquí nace la dificultad diagnóstica.

 ### Datasets

 Fuente de repositorio de imagenes:

* [Covid-19 Image Dataset](https://www.kaggle.com/pranavraikokte/covid19-image-dataset). Usability: 8.8
  * Dataset para deteccion de casos de Covid o Neumonia a traves de imagenes de radiografias de torax.
  * Las imagenes fueron liberadas por la Universidad de Montreal.


* [COVID19 High quality images](https://www.kaggle.com/theroyakash/covid19). Usability: 5.0
  * Dataset para deteccion de casos de Covid o Neumonia a traves de imagenes de radiografias de torax.
  * Fuente no oficial. Imagenes extraidas desde sitios publicos mediante Web Scrapping.

Ambos datasets se encuentran dispuestos en una estructura de directorios que comienza con la separacion de carpetas de training y testing. Luego a partir de estas carpetas se crean nuevas carpetas que identifican los casos de Covid, Neumonia y casos sin afecciones.

Para poder distribuir de forma uniforme el set de datos utilizados para testing y training, unificamos ambos repositorios en la siguiente estructura de directorios:

```
$ tree -d .

.
├── photos1
│   ├── Covid
│   ├── Normal
│   └── Viral Pneumonia
├── photos2
│   ├── Covid
│   ├── Normal
│   └── Viral Pneumonia
└── photos3
    ├── Covid
    ├── Normal
    └── Viral Pneumonia
```

Con el armado del dataset delegaremos luego en los metodos `train_test_split()` y `StratifiedKFold()` de la bilbioteca scikit-learn la distribucion del set de datos para training y testing.

 ### Referencias

 [1][COVID-19 in the radiology department: What radiographers need to know](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7269964/). Published online on Jun 4, 2020
 
 [2][Frequency and Distribution of Chest Radiographic Findings in Patients Positive for COVID-19](https://pubs.rsna.org/doi/10.1148/radiol.2020201160). Published online on Mar 27, 2020
 
 [3][A Characteristic Chest Radiographic Pattern in the Setting of COVID-19 Pandemic](https://pubs.rsna.org/doi/10.1148/ryct.2020200280). Published online on Sep 3, 2020
 
 [4][Performance of radiologists in differentiating COVID-19 from viral pneumonia on chest CT](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7233414/). Published online on Mar 10, 2020
 
 [5][Comparison of the computed tomography findings in COVID-19 and other viral pneumonia in immunocompetent adults: a systematic review and meta-analysis](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7320914/). Published online on Jun 27, 2020
 
  ### Integrantes

 * [Natalia Soria](https://github.com/natsoria)
 * [Fernando Torres](https://github.com/fetorres0)
 * [Mauricio Mitolo](https://github.com/mauriciomem)

