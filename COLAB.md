# Como probar en Google Colab

1. Abre [Google Colab](https://colab.research.google.com).
2. **File > Upload notebook** y sube `creador_acertijos_ig.ipynb`.
3. **Runtime > Change runtime type > Hardware accelerator > GPU** (T4 recomendado).
4. Ejecuta las celdas en orden de arriba a abajo:
   - Celda 1: instalacion (unos minutos).
   - Celdas 2-5: config y funciones.
   - Celda 6: carga el modelo de voz (espera a que termine).
   - Celda 7: define el pipeline.
   - Celda 8: crea la interfaz.
   - Celda 9: lanza la app; haz clic en el enlace que aparezca.
5. En la interfaz escribe el texto del acertijo y opcionalmente la descripcion del video. Pulsa **Submit**.
6. La primera generacion puede tardar mas (descarga del modelo de video). Las siguientes seran mas rapidas.
7. Descarga el MP4 desde el reproductor de la interfaz.

## Si algo falla

- **Out of memory:** Cierra otras pestañas de Colab, reinicia el runtime y vuelve a ejecutar. Usa solo el modelo 1.3B (ya esta configurado).
- **TextClip / ImageMagick:** Si los subtitulos no aparecen, el video se generara igual con voz; solo faltaran los textos en pantalla. En Colab a veces hace falta `apt-get install imagemagick`.
- **Modelos:** La primera vez se descargan desde Hugging Face; asegura tener conexion estable.
