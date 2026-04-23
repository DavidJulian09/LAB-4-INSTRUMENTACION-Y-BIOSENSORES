# LAB 4: DISEÑO Y CONSTRUCCIÓN DE UNA INCUBADORA NEONATAL A ESCALA

## I. INTRODUCCIÓN

Las incubadoras neonatales son dispositivos médicos cuyo papel es generar un ambiente y condiciones que asemejen lo más posible al vientre materno, tales como la temperatura, humedad y nivel de oxígeno; esto con la finalidad de asegurar el bienestar y el desarrollo óptimo del neonato. Lo anterior cobra especial relevancia en neonatos prematuros, quienes poseen una especial sensibilidad a los cambios de temperatura, y cuyo incremento o decrecimiento pueden ser factores de vida o muerte, por lo que las incubadoras deben poseer sistemas extremadamente refinados de calefacción e inframiento, así mismo como los sensores y procesamiento de señales para que el control de temperatura sea exácto.

De lo anterior proviene el por qué de la presente práctica, pues la importancia de contar con los sistemas o dispositivos biomédicos para mantener un control estrictos de la temperatura, nos permtirá familiarizarnos con conceptos y herramientas de sistemas análogos requeridos, así como de apropiarnos de los sistemas digitales necesarios para la automatización del control de temperatura que se busca. Lo anterior se especifica en los objetivos presentados a continuación [1]:

### Objetivo general:

Desarrollar un sistema de medición continua del índice pletismográfico quirúrgico (SPI) en condiciones ambulatorias.

### Objetivos específicos:

• Identificar las partes principales que componen una incubadora neonatal.

• Desarrollar un sistema que emule el modo de operación de una incubadora neonatal.

• Evaluar cómo impacta el control de variables como temperatura, humedad y flujo de aire en la salud del neonato.

## II. MARCO TEÓRICO

### a) Principales componentes de una incubadora neonatal

#### • Sistema estructural:
La estructura de una incubadora neonatal está conformada por una cubierta transparente que permite la visibilidad del neonato, así como el aislamennto térmico cuyo material es de acrílico o policarbonato, esta estructura está sujeta por una base y soportes que proveen estabilidad y soporte a los equipos de monitoreo; adicionalmente posee orificios de acceso, que son orificios sellados con guantes que permiten la manipulación del neonato sin abrir la incubadora, esto para mantener las condiciones internas sin cambios.

#### • Sistema de control térmico:
El modo en que las incubadoras poseen el control de la temperatura es por medio de una resistencia, la cual genera calor por efecto Joule para elevar la temperatura del aire interior, lo anterior trabaja en equipo con un ventilador (blower), que distribuye el aire caliente de manera uniforme dentro de la cabina mediante convección forzada, evitando puntos calientes o fríos. En cuanto al sensor de temperatura posee un termistor o un RTD, que mide continuamente la temperatura interna y envía la señal al sistema de control, en cuanto a dicho sistema puede ser uno "PID" o un "on-off" que activan o desactivan al calentador según se requiera (36–37.5°C). Finalmente, poseen un sistema de enfriamiento, que permite reducir la temperatura interna cuando la ambiental supera los valores deseados por medio de un sistema de ventilación.

#### • Sistema de humidificación:
Para mantener una humedad ideal se posee un depósito de agua que almacena agua destilada, que por medio de un calefactor, calienta el agua para generar vapor y aumentar la humedad relativa (entre 50–70% idealmente); este sistema a su vez trabaja en conjunto con un sensor de humedad llamado higrómetro y un sistema de control que mantienen los valores de humedad en rangos óptimos. Mantener la humedad es especialmente importante para prevenir la perdida de agua a través de la piel del neonato.

#### • Sistema de suministro de gases:
Para las incubadoras se requiere la entrada de oxígeno medicinal y mezcladores de gases que permita ajustar la concentración de oxígeno entre 21–100%, adicionalmente, por medio de un oxímetro se mide la concentración de O2 dentro; por último cabe mencionar que la incubadora posee un sistema de salida de gases, es decir una ventilación, que evita la acumulación de CO2 exhalado por el neonato. [2]

<img width="1181" height="685" alt="image" src="https://github.com/user-attachments/assets/d097eb0d-573f-4954-973e-4b3a63ea3573" />

_(Fig 1. Esquema sistemas temperatura, humedad, gases  de incubadora neonatal.) [2]_

#### • Sistema de monitoreo de signos vitales:
Este sistema monitorea la temperatura corporal del neonato, no solo la del entorno sino directamente sobre su dermis; tambíen posee sensores de SpO2 y de frecuencia cardiaca, que monitorean su saturación de oxígeno y su itmo cardiaco, por lo general mediante pulsoxímetros; finalmente posee sensores de peso, que proporciona la información de la ganancia o pérdida ponderal del peso, esto último es especialmente importante pues la perdida de peso por mínimo que sea puede representarun riesgo potencial al recién nacido.

#### • Sistema eléctrico y de control:
La incubadora cuenta con una fuente de alimentación, que convierte a corriente de la red (110/220 V AC) a voltajes DC seguros para la electrónica (5 V, 12 V), sin contar de que cuenta con una batería de resplado que garantiza el funcionamiento continuo durante cortes de energía eléctrica; a su vez posee microcontroladores que procesan las señales de los sensores, ejecutan el algoritmo de control y actualiza las pantallas y alarmas, todo lo annterior permitiendo al personal médico ajustar los parámetros de temperatura, humedad u otros según sea requerido. Cabe resaltar que las incubadoras poseen sistemas de fusibles y protecciones que evitan daños por sobrecorriente o cortocircuitos, así como detectores de fallo de sensores, en donde el sistema cambia a un modo seguro y activa una alarma, dicha alarma también esta diseñada para activarse en el momento que se detecte un cambio no deseado en los parámetros medidos. [3]

<img width="577" height="282" alt="image" src="https://github.com/user-attachments/assets/a286cee6-12e5-4209-b55e-b148c5f663ad" />

_(Fig 2. Estructura y partes de incubadora neonatal.) [3]_

## III. METODOLOGÍA EXPERIMENTAL

### a) Sistema medición de peso:



### b) Sistema control de temperatura



### c) Estructura prototipo incubadora



## IV. ANÁLISIS DE RESULTADOS



## V. CONCLUSIONES



## VI. BIBLIOGRAFÍA

[1] A. Rosero, "Diseño y construcción de una incubadora neonatal a escala", Colombia, UMNG facultad de ingeniería biomédica, sep. 2025.

[2] A. Gonzalez, "¿Cómo funcionan las incubadoras neonatales?", Medium (Ingeniería, Salud y Educación), Mar. 2024.

[3] J. War, "Manual Técnico Incubadora RWT", Olidef, Dec. 2019.





