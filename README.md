# Quiz_Practico_Tercer_Corte

📘 Quiz Práctico – Tercer Corte
Detección de Movimiento con OpenCV, Streamlit y MediaPipe

Este repositorio contiene el desarrollo del ejercicio práctico del tercer corte, donde se implementa un sistema de detección de movimiento y visualización en tiempo real usando Python, OpenCV, MediaPipe y Streamlit.

A continuación se describe todo el paso a paso real realizado durante el proceso, incluyendo instalación, configuración de entorno, pruebas de cámara y ejecución de la aplicación final.

🧩 1. Creación del repositorio y entorno de trabajo

Crear la carpeta principal del proyecto:

Quiz_Practico_Tercer_Corte/


Crear un entorno virtual:

python -m venv venv


Activar el entorno virtual:

En PowerShell:
.\venv\Scripts\activate



Confirmar que el entorno está activo (se debe ver (venv) en la terminal).

🛠️ 2. Instalación de dependencias

Dentro del entorno virtual se instalaron todas las librerías necesarias:

pip install opencv-python mediapipe streamlit streamlit-webrtc numpy

# 🎥 3. Prueba de funcionamiento de la cámara

Antes de implementar la app, se probó que la cámara funcionara correctamente con un script sencillo de OpenCV:
´´´bash
import cv2

cap = cv2.VideoCapture(0)
if not cap.isOpened():
    print("❌ No se pudo abrir la cámara.")
else:
    print("✅ Cámara abierta correctamente.")
    ret, frame = cap.read()
    if not ret:
        print("❌ No se pudo leer un frame.")
    else:
        print("Frame capturado correctamente.")

cap.release()


Esto permitió:

Verificar permisos

Validar drivers de video

Confirmar que OpenCV reconocía la cámara
´´´bash

🎛️ 4. Implementación del sistema de detección de movimiento

Se desarrolló un script que detecta movimiento usando:

Diferencias entre frames

Conversión a escala de grises

Suavizado con Gaussian Blur

Umbralización y contornos

Además, se integró con MediaPipe para mejorar el procesamiento según lo requerido por el profesor.

🌐 5. Implementación de la interfaz con Streamlit + WebRTC

Para visualizar la cámara en el navegador, se creó un archivo app.py usando Streamlit y streamlit-webrtc:

Visualización de video en tiempo real

Procesador de frames

Detección de movimiento por contornos

Comunicación WebRTC

Ejemplo de ejecución:

streamlit run app.py


O en caso de problemas con la ruta:

python -m streamlit run app.py

🧪 6. Prueba y validación del demo

Se verificó:

Que la cámara se inicializara correctamente

Que el procesador de stream detectara movimiento

Que en el navegador se dibujaran correctamente las cajas de movimiento

Que Streamlit no fallara al cargar WebRTC

Todo funcionando según el demo de referencia de MediaPipe.

📂 7. Estructura final del repositorio
Quiz_Practico_Tercer_Corte/
│── venv/
│── app.py
│── detector_movimiento.py
│── prueba_camara.py
│── requirements.txt
│── README.md

🎬 8. Rseultados


![Imagen de WhatsApp 2025-11-13 a las 16 29 17_41774549](https://github.com/user-attachments/assets/4bea1798-0657-4633-8b47-668cd1d87a58)
![Imagen de WhatsApp 2025-11-13 a las 16 30 18_b3136312](https://github.com/user-attachments/assets/16fe95d4-d218-4a19-9387-44811af81e01)
![Imagen de WhatsApp 2025-11-13 a las 16 30 28_18820de8](https://github.com/user-attachments/assets/ada9ea80-f175-4b52-b43a-5862b4b47c7c)



✅ 9. Conclusiones

Se configuró correctamente un entorno virtual.

Se comprobó el acceso a la cámara desde OpenCV.

Se implementó detección de movimiento en tiempo real.

Se integró Streamlit + WebRTC para visualización web.

El resultado final cumple con el demo solicitado por el docente.
