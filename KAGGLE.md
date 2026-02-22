# Ejecutar el Creador de Acertijos en Kaggle

El notebook `creador_acertijos_ig.ipynb` detecta si corre en Kaggle y adapta rutas, instalacion y lanzamiento de la interfaz.

## Pasos en Kaggle

1. **Crear un notebook**
   - Entra en [kaggle.com](https://www.kaggle.com) y en **Code** elige **New Notebook**.

2. **Subir el proyecto**
   - Opcion A: Sube solo el notebook (**File > Add input > Upload** y sube `creador_acertijos_ig.ipynb`). Luego copia o pega el contenido de las celdas si hace falta, o abre el notebook subido.
   - Opcion B: Crea un Dataset en Kaggle con el repo (por ejemplo clonando desde GitHub) y en **Add input** anade ese dataset; el notebook podra leer desde `/kaggle/input/nombre-dataset/`.

3. **Configurar el entorno**
   - En el panel derecho: **Settings**.
   - **Accelerator:** elige **GPU** (P100 o T4).
   - **Internet:** **On** (necesario para descargar modelos y dependencias).

4. **Ejecutar celdas**
   - Ejecuta las celdas en orden de arriba a abajo.
   - La **Celda 0** en Kaggle no clona el repo (solo imprime un mensaje).
   - La **Celda 1** instala dependencias por pip (en Kaggle no se usa `apt-get`; ImageMagick puede no estar; los subtitulos se queman con ffmpeg si esta disponible).
   - La **Celda 2** detecta Kaggle y usa `OUTPUT_DIR = /kaggle/working/salida_acertijos`.

5. **Interfaz Gradio**
   - En la **Celda 9** se lanza la app con `server_name='0.0.0.0'`, `server_port=7860`.
   - En algunos entornos de Kaggle puedes usar **Add-ons > Web app** para exponer el puerto 7860 y obtener una URL publica.
   - Si no hay Web app, la interfaz corre dentro del notebook; revisa si aparece un enlace en la salida de la celda o usa la vista previa embebida si Gradio lo muestra.

6. **Videos generados**
   - Se guardan en `/kaggle/working/salida_acertijos/`.
   - Puedes descargarlos desde el panel **Output** o desde el reproductor de la interfaz.

## Diferencias Colab vs Kaggle

| Aspecto        | Colab                    | Kaggle                          |
|----------------|---------------------------|----------------------------------|
| Salida         | `/content/salida_acertijos` | `/kaggle/working/salida_acertijos` |
| Celda 0        | Clona/actualiza repo      | Se omite (solo mensaje)          |
| Celda 1        | apt-get + pip             | Solo pip                         |
| Launch Gradio  | `share=True`              | `0.0.0.0:7860` (Web app si hay)  |

## Si algo falla

- **Sin GPU:** En Settings > Accelerator elige GPU y reinicia el notebook.
- **Sin Internet:** Activa **Internet > On** en Settings.
- **Subtitulos:** Si ffmpeg no quema los subtitulos, el video se genera igual con voz; solo faltaran los textos en pantalla.
- **Tiempo:** La primera ejecucion descarga modelos (voz y video); puede tardar 8-15 min. Las siguientes suelen ser 6-11 min.
