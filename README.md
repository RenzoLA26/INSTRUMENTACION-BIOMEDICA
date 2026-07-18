# INSTRUMENTACION-BIOMEDICA
Cuidando a ADULTOS MAYORES de SOBREESFUERZO CARDIOVASCULAR EN rehabilitación POST-ANGIOPLASTÍA

## Placa PCB:
La placa de circuito impreso desarrollada tiene como finalidad integrar todos los módulos electrónicos externos requeridos para complementar las funciones del sistema de monitoreo cardiovascular basado en HealthyPi 5.
A diferencia del HealthyPi 5, que incorpora el acondicionamiento y adquisición de las señales biomédicas, la PCB diseñada concentra los elementos relacionados con la alimentación, almacenamiento de datos, interfaz de usuario y generación de alertas.

Por esta razón, la PCB puede clasificarse como una combinación de:
    - Placa de alimentación y distribución de energía, ya que incorpora el módulo cargador TP4056, el convertidor DC-DC XL6009 y la distribución de la         alimentación hacia todos los módulos electrónicos.
    - Placa de expansión, debido a que integra el ESP32 Mini, el módulo MicroSD, el amplificador MAX98357A y el interruptor de selección de modo.
    - Placa de integración física, al proporcionar los conectores necesarios para la batería, el parlante y los diferentes periféricos del sistema.

Es importante destacar que la PCB no replica el front-end analógico del HealthyPi 5, respetando la arquitectura definida en las prácticas anteriores. El acondicionamiento y adquisición de las señales biomédicas continúan siendo responsabilidad del HealthyPi 5, mientras que la PCB actúa como un módulo auxiliar encargado de ampliar las capacidades del sistema mediante almacenamiento local, comunicación, control y generación de alertas. Esta estrategia reduce la complejidad del diseño, disminuye el número de componentes y favorece la confiabilidad del prototipo, además de facilitar futuras actualizaciones del sistema sin modificar la etapa de adquisición biomédica.

<img width="493" height="432" alt="Captura de pantalla 2026-07-17 193611" src="https://github.com/user-attachments/assets/7c3badd9-ab7e-4b59-b7b2-751ed4fbe187" />

           Fig 1. Fabricación de la placa PCB JLCPCB
           
<img width="291" height="216" alt="Captura de pantalla 2026-07-17 193916" src="https://github.com/user-attachments/assets/72be4859-7d2f-4a26-b779-66a81e5be8fc" />
<img width="291" height="216" alt="Captura de pantalla 2026-07-17 193922" src="https://github.com/user-attachments/assets/286d0c08-c8ee-4f0b-933d-603d9e7347cf" />

           Fig 2 y 3. Vista superior e inferior de la placa PCB 


## Modelado 3D:
Se trabajó en onshape debido a la facildiad de sus herramientas y de colcoar tanto partes como ensamblajes dentro de una misma carpeta:
https://cad.onshape.com/documents/6da69b8a9d5808f3a0344195/w/9f1509aac2bd9f4551558aa5/e/5c245e15afb65efe04834944   
  - Se tomaron las medidas de los componnetes electrónicos para el debido modelado en 3D para que entre en forma de encaje sin tornillos.
  - Los componenetes electrónicos fueron importados y en su mayoría diseñados para el ensamblaje
  - Como futuras mejoras se cambiará los cases por uno mas ergómico.

<img width="632" height="302" alt="Captura de pantalla 2026-07-17 194257" src="https://github.com/user-attachments/assets/5ddac8e7-132c-4243-a283-3a99e2297d68" />

      Fig 4. Vista isométrica y lateral del case de los componentes electrónicos

<img width="397" height="432" alt="WhatsApp Image 2026-07-17 at 1 09 48 PM" src="https://github.com/user-attachments/assets/62706b81-956a-4a33-8265-5695936990d8" />

      Fig 5. Ensamblaje del case del healthypi5

<img width="421" height="382" alt="WhatsApp Image 2026-07-17 at 1 10 27 PM" src="https://github.com/user-attachments/assets/2427799f-73db-49d3-9f04-901bdf9c9d75" />

     Fig 6. Ensamblaje del case de los componentes electrónicos
## Interfaz:
### Adquisición de señales fisiológicas con HealthyPi 5
La adquisición de señales fisiológicas mediante HealthyPi 5 utilizando OpenView 2. Se visualizan las señales de ECG, onda pletismográfica (PPG), frecuencia cardíaca y la saturación de oxígeno (SpO₂).

<img width="452" height="150" alt="WhatsApp Image 2026-07-17 at 12 48 43 PM" src="https://github.com/user-attachments/assets/e79a5c65-4c9e-4b86-a831-9404ec56ee02" />

    Fig 7. Adquisición de señales de ECG, frecuencia cardíaca, SpO2 y onda pletismográfica

Durante la adquisición se obtuvieron simultáneamente las siguientes variables fisiológicas: 
Variable
Valor observado
Frecuencia cardíaca
98 bpm
Saturación de oxígeno
98 %

<img width="350" height="180" alt="WhatsApp Image 2026-07-17 at 1 06 06 PM" src="https://github.com/user-attachments/assets/66f97a54-d06d-449a-bf7b-a5608d530811" />
    Fig 8. Valores de Frecuencia cardiaca y SpO2
Las señales fisiológicas fueron adquiridas empleando la plataforma HealthyPi 5 y visualizadas mediante el software OpenView 2.
Las condiciones del registro fueron las siguientes:
Posición del voluntario: sentado y en reposo.
Sensor ECG: electrodos conectados en derivación II.
Sensor PPG: finger clip colocado en el dedo índice.
Duración del registro: aproximadamente 6 segundos, correspondiente a la ventana de visualización del software.
Condición durante la adquisición: reposo, evitando movimientos voluntarios para reducir artefactos.
<img width="297" height="282" alt="WhatsApp Image 2026-07-17 at 12 51 56 PM" src="https://github.com/user-attachments/assets/7bbda2c1-d579-4aad-a6f6-197ead1d247a" />

     Fig 9. Posición de la colocación de los electrodos en el cuerpo, conectados en derivación II

Las señales adquiridas permiten la visualización simultánea del ECG, la onda pletismográfica y los parámetros fisiológicos derivados.
Respecto a la calidad de las señales, se observa que:
La señal de ECG presenta variaciones atribuibles al ruido eléctrico y pequeños artefactos por movimiento, aunque mantiene suficiente calidad para la estimación de la frecuencia cardíaca.
La onda pletismográfica (PPG) muestra una morfología periódica claramente identificable, con mínimos artefactos y buena estabilidad durante el registro.
La saturación de oxígeno (98 %) corresponde a un valor fisiológicamente esperado para un voluntario sano.
La frecuencia cardíaca reportada (98 bpm) fue calculada automáticamente por el sistema a partir de la señal ECG.

Estado de la interfaz de usuario

Se desarrolló una aplicación móvil utilizando Android Studio, cuya comunicación con la plataforma HealthyPi 5 se realizará mediante la tecnología Bluetooth Low Energy (BLE). Esta interfaz permitirá la visualización en tiempo real de las variables fisiológicas adquiridas por el dispositivo, así como la interacción del usuario con las diferentes funcionalidades del sistema:

<img width="345" height="292" alt="WhatsApp Image 2026-07-17 at 12 56 24 PM" src="https://github.com/user-attachments/assets/f702adcb-0654-49f3-8558-8adc8175bffb" />

       Fig 10. Escaneo de HealthyPi cercanos mediante Bluetooth Low Energy (BLE) en la app

<img width="337" height="490" alt="WhatsApp Image 2026-07-17 at 12 57 38 PM" src="https://github.com/user-attachments/assets/29e8481d-46cd-42c3-a536-a778bffa1331" />

      Fig 11. Interfaz principal de monitoreo 

Las figuras mostradas muestran el estado actual de desarrollo de la aplicación móvil.
En la primera imagen se presenta la pantalla de escaneo de dispositivos, donde la aplicación realiza la búsqueda y detección del módulo HealthyPi 5 disponible para establecer la conexión mediante BLE.
En la segunda imagen se observa la interfaz principal de monitoreo del usuario. En ella se visualizan las principales variables fisiológicas adquiridas por el sistema, como la frecuencia cardíaca (FC) y la saturación de oxígeno (SpO₂), siendo esta última una medición opcional dentro del proyecto. Asimismo, la interfaz muestra el nivel de riesgo del paciente, clasificado en cuatro estados: Normal, Precaución, Alerta y Emergencia, de acuerdo con los umbrales personalizados establecidos para cada usuario. Adicionalmente, se incorpora la estimación de la actividad física mediante el Equivalente Metabólico (MET), el cual constituye uno de los parámetros empleados para evaluar el nivel de esfuerzo realizado por el paciente. La aplicación también permite seleccionar manualmente el modo de funcionamiento entre actividad común y modo ejercicio, adaptando la evaluación de los umbrales a cada contexto.
Actualmente, la aplicación móvil se encuentra en fase de desarrollo y aún no incorpora la visualización en tiempo real de las señales fisiológicas provenientes del HealthyPi 5. No obstante, la correcta adquisición de la señal de PPG (onda pletismográfica) y del valor de SpO₂ fue verificada previamente mediante el software OpenView 2, tal como se presentó en la sección correspondiente a la adquisición de señales fisiológicas. 

Aunque, hasta la fecha, se han implementado los siguientes componentes de la aplicación:
- Configuración e integración de Firebase.
- Implementación del modelo de datos.
- Desarrollo del servicio de comunicación BLE.
- Implementación del repositorio para Firebase.
- Desarrollo de la pantalla de monitoreo (MonitorScreen).
- Implementación del ViewModel, encargado de gestionar la comunicación entre la interfaz de usuario, el servicio BLE y Firebase.
- Desarrollo de la pantalla de escaneo BLE, destinada a la detección y conexión con el dispositivo HealthyPi 5.
  
Por otro lado, las funcionalidades continúan en desarrollo para completar la implementación del sistema:
- Sistema de notificaciones automáticas
- Nivel Alerta: envío de notificación a un familiar.
- Nivel Emergencia: envío de notificación al personal de salud.
- Implementación de la señal sonora en los diferentes modos de actividad (Actividad común o ejercicio).
- Implementación de la navegación entre pantallas.
- Configuración de los umbrales personalizados para cada paciente.
- Visualización de la señal ECG en tiempo real.
- Validación y pruebas funcionales en dispositivos móviles Android.


