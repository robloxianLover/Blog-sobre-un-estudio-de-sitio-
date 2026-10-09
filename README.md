# Blog sobre un estudio de sitio
Este proyecto fue realizado por mi y mis compañeros de equipo Félix Espejo Alehtse María y Valdez Miranda Elias.
<br>
<br>

En este blog presenta el desarrollo de nuestro proyecto final, en el que realizamos un estudio de sitio de una red inalámbrica (WLAN) para analizar su rendimiento, identificar problemas de interferencia y evaluar la cobertura de la señal en diferentes áreas de una vivienda.

<br>

## Introducción

Las redes inalámbricas WLAN (*Wireless Local Area Network*) permiten conectar diferentes dispositivos sin necesidad de utilizar cables. Sin embargo, su rendimiento puede verse afectado por factores como la distancia entre los dispositivos y el punto de acceso, los obstáculos físicos, la saturación de los canales y las interferencias provocadas por otras redes o aparatos electrónicos.

Para estudiar estos factores, seleccionamos una red doméstica como sitio de análisis. Se evaluaron dos perfiles de red: `INFINITUM86AF`, correspondiente al módem, e `INFINITUM86AF_plus`, correspondiente al Access Point.

El estudio se dividió en dos partes principales: el análisis de las redes detectadas en distintos puntos de la vivienda y el mapeo de cobertura mediante mapas de calor.

<br>

## Herramientas usadas

Durante el desarrollo del proyecto utilizamos las siguientes herramientas:

* **Visual Paradigm Online:** elaboración del plano de la vivienda y ubicación de los puntos de medición.
* **InSSIDer:** análisis de las redes inalámbricas cercanas, intensidad de señal, canales, interferencias y características de seguridad.
* **NetSpot Premium:** recopilación de mediciones para generar el primer mapa de calor de cobertura.
* **WiFi Heatmap:** elaboración de un segundo mapa de calor para contrastar los resultados obtenidos.

Estas herramientas permitieron observar el comportamiento de la señal en diferentes zonas y relacionar las mediciones con la distribución física de la vivienda.

<br>

## Análisis de la red WLAN

Para el análisis inicial se seleccionaron tres puntos de medición. Cada uno presenta condiciones diferentes en cuanto a distancia, obstáculos e interferencias.

<img width="319" height="633" alt="image" src="https://github.com/user-attachments/assets/0a76f01a-2f1a-404e-9497-81e68ac84bcb" />

### Punto 1: Habitación cercana al Access Point

En el primer punto, ubicado en una habitación cercana al Access Point, se registraron los siguientes valores de intensidad de señal:

| Perfil de red        | Intensidad de señal |
| -------------------- | ------------------: |
| `INFINITUM86AF_plus` |             -55 dBm |
| `INFINITUM86AF`      |             -70 dBm |

El Access Point presentó una señal más fuerte que la del módem. Esto puede relacionarse con su ubicación y con el uso de la banda de 2.4 GHz, que generalmente ofrece mayor alcance y penetración a través de obstáculos que la banda de 5 GHz.

También se identificó que ambos perfiles utilizaban el canal 11, compartido con otras redes cercanas. Esta situación aumenta la posibilidad de interferencia y puede afectar el rendimiento de la conexión.

Se realizó una medición adicional con el microondas encendido. En este caso, la señal del módem disminuyó de -70 dBm a -75 dBm, mientras que la del Access Point no presentó una variación significativa.

**Resultado:** el Access Point fue la mejor opción de conexión para esta habitación, aunque la presencia de otras redes en los mismos canales representa un problema potencial.

### Punto 2: Sala de estar

El segundo punto se ubicó en la sala de estar, cerca de la entrada de la vivienda.

En esta zona se observó una señal del módem de aproximadamente -60 dBm en una de las mediciones, mientras que el otro perfil registró una señal más débil, de -73 dBm. También se detectó una red externa con una intensidad de -51 dBm.

El análisis mostró que la banda de 5 GHz podía ofrecer una buena alternativa para los dispositivos compatibles. Sin embargo, era necesario considerar la interferencia provocada por otras redes que utilizaban canales cercanos.

Por otra parte, la banda de 2.4 GHz ofrecía ventajas de alcance y penetración, aunque las mediciones realizadas no la mostraron como la mejor opción para esta zona.

**Resultado:** se recomendó priorizar la banda de 5 GHz, procurando utilizar una agrupación de canales que redujera la interferencia.

### Punto 3: Baño alejado de los dispositivos

El tercer punto se ubicó en un baño alejado tanto del módem como del Access Point.

Las mediciones registraron intensidades de señal aproximadas de:

| Perfil de red        | Intensidad de señal |
| -------------------- | ------------------: |
| `INFINITUM86AF`      |             -80 dBm |
| `INFINITUM86AF_plus` |             -87 dBm |

Estos valores reflejan una señal considerablemente más débil que la observada en los otros puntos. Además, el canal 11 presentaba un uso elevado por parte de las redes cercanas.

La distancia, los obstáculos físicos y las interferencias contribuyen a la degradación de la conexión en esta zona.

**Resultado:** el baño se identificó como un área de cobertura deficiente, en la que la conexión podía resultar prácticamente inutilizable para algunas actividades.

<br>

## Análisis de seguridad

Durante la revisión de los perfiles de red también se identificaron diferencias en sus configuraciones de seguridad.

* **Módem (`INFINITUM86AF`):** utilizaba WPA2, el estándar de seguridad más alto que el documento identifica como compatible con el dispositivo.
* **Access Point (`INFINITUM86AF_plus`):** utilizaba WPA, una configuración vulnerable a diferentes ataques.

A partir de estos resultados, se identificó la necesidad de revisar la configuración del Access Point y comprobar si admite WPA2, con el objetivo de mejorar la seguridad de la red.

También se observó que las interferencias causadas por redes externas no podían eliminarse directamente, por lo que las modificaciones de canales solamente permitirían mitigar parte del problema.

<br>

## Mapeo de cobertura WLAN

Después del análisis puntual, realizamos un mapeo de cobertura para observar cómo se distribuía la señal en toda el área estudiada.

Para ello, utilizamos un plano elaborado en Visual Paradigm Online y recopilamos mediciones con NetSpot Premium. Posteriormente, realizamos un segundo mapeo con WiFi Heatmap para contrastar los resultados.

<img width="419" height="786" alt="image" src="https://github.com/user-attachments/assets/4252aaf3-8fff-4d7f-8abd-83533a803783" />

Los mapas de calor permitieron identificar tres condiciones principales:

* **Zonas cercanas al módem y al Access Point:** presentaron una intensidad de señal aproximada de -45 a -50 dBm, correspondiente a las áreas con mejor cobertura.
* **Zonas cercanas a los puntos 1 y 2:** registraron valores aproximados de -50 a -65 dBm, que permiten una conectividad funcional, aunque su rendimiento puede variar.
* **Zonas alejadas, como el punto 3:** presentaron valores de -80 dBm o inferiores, lo que evidencia una cobertura deficiente.

Los dos mapeos mostraron resultados similares, consistentes con las mediciones realizadas inicialmente mediante InSSIDer.

También se identificaron variaciones de señal en distancias cortas, relacionadas con la presencia de paredes, muebles y otros obstáculos que afectan la propagación de las ondas inalámbricas.

<br>

## Resultados generales

A partir de las mediciones realizadas, se identificaron los siguientes hallazgos:

1. La intensidad de señal cambia considerablemente según la ubicación dentro de la vivienda.
2. El uso compartido de canales por varias redes aumenta la posibilidad de interferencias.
3. La banda de 2.4 GHz puede ofrecer ventajas de alcance, mientras que la banda de 5 GHz puede ser una alternativa conveniente en zonas donde su señal sea favorable.
4. El microondas produjo una disminución de la señal del módem en el punto donde se realizó la prueba.
5. El punto 3 presentó las condiciones más desfavorables de cobertura.
6. El Access Point utilizaba una configuración de seguridad que podía mejorarse.
7. Los dos mapas de calor respaldaron las observaciones obtenidas durante el análisis inicial.

<br>

## Recomendaciones de mejora

Con base en los resultados del estudio, se proponen las siguientes medidas:

* **Revisar la selección de canales:** elegir canales con menor interferencia, considerando las redes cercanas y las condiciones observadas en cada zona.
* **Evaluar la selección automática de canales:** utilizarla cuando el equipo permita una configuración efectiva que reduzca la interferencia.
* **Mejorar la seguridad del Access Point:** cambiar de WPA a WPA2 si el dispositivo lo permite.
* **Evaluar la cobertura del punto 3:** considerar la ubicación de los dispositivos, la potencia de transmisión permitida y la posible instalación de un Access Point o repetidor adicional.
* **Priorizar las zonas de mayor uso:** determinar si es necesario mejorar la cobertura en el baño o si la conexión actual resulta suficiente para las actividades que se realizan ahí.
* **Realizar nuevas mediciones:** comprobar si los cambios implementados producen mejoras reales en la intensidad y estabilidad de la señal.

Estas recomendaciones deben evaluarse de acuerdo con las características de los equipos y las condiciones físicas del sitio.

<br>

## Conclusión

La realización de este estudio de sitio nos permitió comprender mejor los factores que influyen en el rendimiento de una red WLAN dentro de un entorno doméstico.

Mediante el análisis con InSSIDer y la elaboración de mapas de calor con NetSpot Premium y WiFi Heatmap, identificamos zonas con buena cobertura, áreas con señal reducida y posibles problemas relacionados con la interferencia entre canales.

Los resultados muestran que no basta con contar con un módem o un Access Point: también es importante considerar su ubicación, la configuración de los canales, los obstáculos físicos y la seguridad de la red.

Finalmente, este proyecto nos permitió aplicar herramientas de análisis de redes inalámbricas en un caso práctico y formular recomendaciones orientadas a mejorar la cobertura, la estabilidad y la seguridad de la conexión.

