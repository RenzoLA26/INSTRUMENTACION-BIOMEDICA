# INSTRUMENTACION-BIOMEDICA
Cuidando a ADULTOS MAYORES de SOBREESFUERZO CARDIOVASCULAR EN rehabilitación POST-ANGIOPLASTÍA

## Placa PCB:


## Modelado 3D:



## Interfaz:
### Adquisición de señales fisiológicas con HealthyPi 5
La adquisición de señales fisiológicas mediante HealthyPi 5 utilizando OpenView 2. Se visualizan las señales de ECG, onda pletismográfica (PPG), frecuencia cardíaca y la saturación de oxígeno (SpO₂).
<img width="552" height="150" alt="WhatsApp Image 2026-07-17 at 12 48 43 PM" src="https://github.com/user-attachments/assets/a16dba20-b8a7-45e8-bfbc-4660bd92bd6b" />
Fig. 1 
Adquisición de señales de ECG, frecuencia cardíaca, SpO2 y onda pletismográfica
Durante la adquisición se obtuvieron simultáneamente las siguientes variables fisiológicas: 
Variable
Valor observado
Frecuencia cardíaca
98 bpm
Saturación de oxígeno
98 %

Las señales fisiológicas fueron adquiridas empleando la plataforma HealthyPi 5 y visualizadas mediante el software OpenView 2.
Las condiciones del registro fueron las siguientes:
Posición del voluntario: sentado y en reposo.
Sensor ECG: electrodos conectados en derivación II.
Sensor PPG: finger clip colocado en el dedo índice.
Duración del registro: aproximadamente 6 segundos, correspondiente a la ventana de visualización del software.
Condición durante la adquisición: reposo, evitando movimientos voluntarios para reducir artefactos.

Fig. Posición de la colocación de los electrodos en el cuerpo, conectados en derivación II
Las señales adquiridas permiten la visualización simultánea del ECG, la onda pletismográfica y los parámetros fisiológicos derivados.
Respecto a la calidad de las señales, se observa que:
La señal de ECG presenta variaciones atribuibles al ruido eléctrico y pequeños artefactos por movimiento, aunque mantiene suficiente calidad para la estimación de la frecuencia cardíaca.
La onda pletismográfica (PPG) muestra una morfología periódica claramente identificable, con mínimos artefactos y buena estabilidad durante el registro.
La saturación de oxígeno (98 %) corresponde a un valor fisiológicamente esperado para un voluntario sano.
La frecuencia cardíaca reportada (98 bpm) fue calculada automáticamente por el sistema a partir de la señal ECG.

Estado de la interfaz de usuario

Se desarrolló una aplicación móvil utilizando Android Studio, cuya comunicación con la plataforma HealthyPi 5 se realizará mediante la tecnología Bluetooth Low Energy (BLE). Esta interfaz permitirá la visualización en tiempo real de las variables fisiológicas adquiridas por el dispositivo, así como la interacción del usuario con las diferentes funcionalidades del sistema:


Fig. Escaneo de HealthyPi cercanos mediante Bluetooth Low Energy (BLE) en la app


Fig. Interfaz principal de monitoreo 
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


