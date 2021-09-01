# TE2004
Diseño de sistemas embebidos avanzados

# Discriminación de agentes emisores de ruido urbano empleando redes de sensores y técnicas multiagente 

La exposición prolongada a niveles de ruido excesivo impactan en los niveles de vida en las grandes urbes. Los efectos negativos de la contaminación auditiva van desde afectación en la concentración hasta problemas del sueño. La organización mundial de la salud ha emitido estándares para la contaminación auditiva en zonas urbanas, las cuales,  desafortunadamente en muchas grandes ciudades, se han rebasado. Por ello, es importante detectar las fuentes que excedan el estándar internacional y sancionarlas. Además, es necesaria la actualización de la legislación sobre fuentes de ruido y rangos de emisión sonora, dadas las nuevas condiciones de parque vehicular activo. Por lo tanto, un escenario ideal para el diagnóstico de contaminación auditiva es la creación de una red de sensores que sea capaz de entregar datos confiables en largos periodos de trabajo a muy bajo costo, sin alterar el paisaje urbano. (Lee sobre la norma oficial mexicana NORMA 011 )
[Nom-011.pdf](https://github.com/etorresr/TE2004/files/7094484/Nom-011.pdf)

## Reto

A través de una red de sensores estratégicamente colocados en la periferia del Campus, empleando protocolos de comunicación del internet de las cosas (IoT), detectar emisión de ruido fuera de la norma para vehículos de carga pesada. Para tal efecto, cada sensor o agente, debe ser capaz de discriminar los elementos que generan el ruido, usando algún algoritmo descrito en la literatura o adaptado alguno para este fin a través de un sistema embebido dedicado al procesamiento de señales (DSP). Los datos recabados son entregados a una computadora central, capaz de dar seguimiento a la fuente de ruido fuera de la norma, siempre y cuando circule en la trayectoria de la red de sensores. Para el seguimiento de la fuente de ruido, se emplearan técnicas de cómputo en paralelo en la computadora que recibe la información de los agentes, con el propósito de obtener predicciones de ruta en el menor tiempo posible.

![reto](https://user-images.githubusercontent.com/49214324/131747641-2de5b952-c57c-4de0-a44d-960542ce8063.png)

## Entregables mínimos

Se cubren 4 entregables mínimos para considerar la evaluación del reto:

* Diseño de agente que discrimina las fuentes de ruido a través de un sistema electrónico que incluya un DSP en su arquitectura.
* Construye una red de agentes en la periferia del campus.
* Publica usando el protocolo MQTT, la información suficiente para dar seguimiento a las fuentes de ruido fuera de norma.
* Diseña y programa un algoritmo que permita dar seguimiento y predecir la ruta de una fuente de ruido fuera de norma usando técnicas de programación en paralelo.

## Etapas

Diseño de agente: Se diseña una arquitectura que sea capaz de medir los niveles de ruido en el ambiente. Este dispositivo (publisher) debe de ser capaz de publicar un mensaje de alerta a través del protocolo MQTT, una vez que los niveles de ruido superan los estándares definidos por la organización mundial de la salud (OMS) .

Discriminación de fuentes de ruido en el agente: Al agente diseñado en la etapa anterior se harán las siguientes modificaciones. Se emplean algoritmos que se encuentren en la literatura o se adapta alguno, para que se puedan discriminar las fuentes que generan el ruido en el entorno de trabajo del agente.  Se dará énfasis en la discriminación de vehículos de carga pesada y el agente debe de incluir un DSP para reducir el tiempo de respuesta del dispositivo.

Construcción de red de agentes: Con el agente diseñado en la etapa anterior se diseña e implementa la red de agentes en puntos estratégicos alrededor del Campus. Los datos a publicar se amplían, por lo que los tópicos a publicar se redefinen de la siguiente manera. a) fecha, b) hora, c) ubicación, d) ruido (dB), e) alerta de ruido fuera de norma, f) alerta de ruido por vehículo pesado. Como describe los tópicos a publicar, al hacer una medición de ruido (d), se envía la etiqueta que identifica la fecha (a), hora (b), y lugar de la medición (c). Además, se envía una alerta (cierto o falso) en caso de detectar una medición fuera de rango (e) y otra alerta (cierto o falso) por si la medición fuera de rango se debió a un vehículo de carga pesado (f) .

Procesamiento de la información: Por último, al tener la red de agentes trabajando, es necesario procesar la información de todos los agentes de forma simultánea. De esta manera, la fuente de ruido fuera de norma puede ser monitoreada a lo largo de la red de sensores establecida, en caso de seguir una ruta que cubran los agentes. Por lo tanto, se emplearán técnicas de cómputo en paralelo en la computadora que recibe la información de los agentes, para obtener predicciones de ruta en el menor tiempo posible.

*Tecnologico de Monterrey*

*Region Centro Sur*
