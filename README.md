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

El sistema de medición de peso se realizó con el fin de realizar una medida continua, de forma que se mostrara la información en una pantalla OLED, este proceso se llevó a cabo por medio de una galga extensiométrica de capacidad de 5Kg, configurada en un puente de Wheatstone, la cual convierte la deformación mecánica causada por el peso en una señal eléctrica diferencial, dicha señal es sumamente pequeña (mircovoltios), por lo que se emplea un módulo HX711 que integra un amplificador de instrumentación de alta ganancia y un convertidor analógico-digital (ADC) de 24 bits, permitiendo una lectura precisa y estable; dicha lectura es digitalizada y posteriormente enviada a la ESP32 donde a su vez envía la infrmación mostrada a una pantalla OLED del peso en gramos en tiempo real. En cuanto a la alimentación del sistema anterior, se realizó por medio de la fuente de 3.3V de la ESP32. Finalmente, con el objetivo de garantizar una medicion correcta, se colocó una plataforma de acrílico sobre las galgas que permitían el posisionamiento uniforme del peso.

<img width="1204" height="1600" alt="image" src="https://github.com/user-attachments/assets/bd6c4d67-f4f9-4672-a8d9-04709ed973b4" />

_(Fig 3. Visualización montaje circuito análogo.)_

Como información relevante, las galgas fueron sujetas a un procedimiento de calibración, donde se tara sin peso, es decir, se retira todo el peso de la plataforma de las galgas, permitiendo la estabilización y que ese sea el valor de referncia de 0g, posteriormente se ejecuta la función "balanza.tare(30)", que promedia 30 lecturas para establecer el punto de referencia de 0g. Posteriormente se coloca una masa de 1Kg sobre la plataforma, y se promedia 50 lecturas utilizando "balanza.get_value()", con lo anterior se calcula la escala del objeto a medir y proporciona la información. Después de lo anterior se puede realizar la lectura y filtrado del peso en tiempo real de modo:

    if (balanza.is_ready()) {
        peso = balanza.get_units(10);  // Promedia 10 lecturas
        if (peso < 0) peso = 0;        // Evita valores negativos
    }

En donde "balanza.is_ready()" verifica que el HX711 haya completado una conversión y esté listo para enviar datos, y "balanza.get_units(10)" promedia internamente 10 lecturas consecutivas, este promediado reduce el ruido de la señal y mejora la estabilidad de la medición; en caso de que se llegen a medir valores negativos, siplemente lo asumirá como cero. Por último el peso calculado se envía a la pantalla OLED.

<img width="1204" height="1600" alt="image" src="https://github.com/user-attachments/assets/927c18be-9cc1-42c7-b297-316c1908f5a6" />

_(Fig 4. Procedimiento de ajuste galgas extensiométricas.)_


### b) Sistema control de temperatura

Como se mencionó en el marco teórico, es necesaro mantener un control de temperatura entre 36°C y 37.5°C, por dicha razón se estableción un controlador proporcional para regular la temperatura. La forma en que se llevo a acabo eso fue por medio de un sensor DHT11, que mide la temperatura del aire e un rango de 0-50°C; una bombilla de incubación, que genera calor por efecto Joule cuando se activa, elevando la temperatura del aire interior, dicha bombilla es conectada a un rele de 5V que actua como un interruptor controlado por el ESP32, que permite encender o apagar la bombilla conectada a la red eléctrica (110/220V AC) sin riesgos para el microcontrolador, pues el bombilla funciona con conexión a un tomacorriente. 

<img width="1204" height="1600" alt="image" src="https://github.com/user-attachments/assets/f471453b-f9cf-4a17-988f-dde6ded493ff" />

_(Fig 5. Ensamble control de temperatura.)_

Ahora bien, una vez los datos adquiridos por el sensor son enviados a la tarjeta ESP32, las procesa de tal forma de mandar el valor de la temperatura en °C visible en la pantalla OLED, adicionalmente posee un sistema mediante LED's rojo (temperatura superior a la ideal), verde (temperatura ideal) y azul (temperatura inferior a la ideal), que es capás de indicar intuitivamente la temperatura presente en la incubadora por medio de los umbrales establecidos. 

    void actualizarLEDs(float temp) {
        if (temp < 36.6) {
            digitalWrite(LED_FRIO,  HIGH);  // LED azul: temperatura baja
            digitalWrite(LED_OK,    LOW);
            digitalWrite(LED_CALOR, LOW);
        } else if (temp <= 37.4) {
            digitalWrite(LED_FRIO,  LOW);
            digitalWrite(LED_OK,    HIGH);  // LED verde: rango óptimo
            digitalWrite(LED_CALOR, LOW);
        } else {
            digitalWrite(LED_FRIO,  LOW);
            digitalWrite(LED_OK,    LOW);
            digitalWrite(LED_CALOR, HIGH);  // LED rojo: sobrecalentamiento
        }
    }

En cuanto a la ESP32 ejecuta un controlador PI (proporcional integral) con un punto de equilibrio de 36.5°C, la decisión de encendido/apagado del bombillo se basa en la comparación de la salida PI con un umbral de 1.0, implementando un control de OFF/ON con histéresis, es decir, la bombilla por medio de los umbrales se encendía o apagaba según fuera necesario a partir de los datos recopilados por el sensor, de forma que tiene un control ajustado a lo requerido; es este procesos lo que nos permite ajustar a su vez los umbrales del sensor, en nuestro caso si la temperatura estaba entre los 36–37.5°C, se activaba el LED verde; en el momento que la temperatura superaba el umbral por un exceso de temperatura se prendía el LED rojo y se apagaba la bobilla (OFF), de mismo modo, en caso de que la temperatura disminuyera, se prendía el LED azul y se prendía la bombilla (ON). Cabe resaltar que con tal de mantener una temperatura estable y homogenea en la totalidad de la incubadora, se desidío mantener un ventilador axial de 5V encendido en todo momento para distribuir el calor generado por la bombilla, tal como se observa en la figura 5.

<img width="1204" height="1600" alt="image" src="https://github.com/user-attachments/assets/c24c0ce3-a76d-49cd-93fb-92f21ee9b0c5" />

_(Fig 6. Indicadores LED's de temperatura.)_

### c) Estructura prototipo incubadora

Respecto a la estructura de la incubadora, fue construida a partir de un armazón de aluminio, y se desidió escoger goma espuma como material para las paredes de la incubadora, pues aunque no es un material resistente, es económico y permite mantener una temperatura interna cálida una vez se activa el mecanismo de calefacción (bombilla), adicionalemte al tener un color claro permite que la luz no sea absorvida por las paredes, sino que rebote de vuelta hacia el interior de la ncubadora, adicionalmente posee un acrílico en la parte frontal de la estructura que permite la visualización del neonato desde el exterior sin necesidad de abrir la incubadora. Respecto a la ubicación de los componentes, las galgas fueron ubicadas en el centro de la incubadora, donde se situa al neonato, la bombilla se encuentra a su lado, y directamente incrustrado en la pared se encuentra el ventilador y el sensor térmico (fig 5.).

Los circuitos se optó por ubicarlos en el exterior de la incubadora, donde guarda especial importancia los LED's y pantalla OLED que muestran los valores de interés (peso y temperatura), sin contar que se limita el riesgo de que el neonato pueda presentar a causa de los circuitos presentados.

<img width="1600" height="632" alt="image" src="https://github.com/user-attachments/assets/ad4004c0-4018-43d8-83a7-49cd1daa3e60" />

_(Fig 7. Estructura exterior incubadora a escala.)_


## IV. ANÁLISIS DE RESULTADOS



## V. CONCLUSIONES



## VI. BIBLIOGRAFÍA

[1] A. Rosero, "Diseño y construcción de una incubadora neonatal a escala", Colombia, UMNG facultad de ingeniería biomédica, sep. 2025.

[2] A. Gonzalez, "¿Cómo funcionan las incubadoras neonatales?", Medium (Ingeniería, Salud y Educación), Mar. 2024.

[3] J. War, "Manual Técnico Incubadora RWT", Olidef, Dec. 2019.





