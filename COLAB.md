# Como probar en Google Colab

1. Abre [Google Colab](https://colab.research.google.com).
2. **File > Upload notebook** (o **Open notebook > GitHub** con el repo `acertijo`) y abre `creador_acertijos_ig.ipynb`.
3. **Runtime > Change runtime type > Hardware accelerator > GPU** (T4 recomendado).
4. Ejecuta las celdas en orden de arriba a abajo:
   - Celda 0 (opcional): clonar/actualizar repo desde GitHub.
   - Celda 1: instalacion (unos minutos).
   - Celdas 2-5: config, voz, video y composicion.
   - Celda 6: inicializacion (no precarga modelos).
   - Celda 7: pipeline completo.
   - Celda 8: interfaz Gradio.
   - **Celda 8b: pre-descarga de modelos** (recomendado). Ejecutala una vez para dejar TTS y Wan en cache; asi la primera generacion no se bloquea por la descarga.
   - Celda 9: lanza la app; haz clic en el enlace que aparezca.
5. En la interfaz escribe el texto del acertijo y opcionalmente la descripcion del video. Pulsa **Generar**.
6. Si ejecutaste la Celda 8b, la primera generacion sera mas rapida (modelos ya en cache). Si no, la primera vez descargara voz y video.
7. Descarga el MP4 desde el reproductor de la interfaz.

## Si algo falla

- **Out of memory:** Cierra otras pestañas de Colab, reinicia el runtime y vuelve a ejecutar. Usa solo el modelo 1.3B (ya esta configurado).
- **TextClip / ImageMagick:** Si los subtitulos no aparecen, el video se generara igual con voz; solo faltaran los textos en pantalla. En Colab a veces hace falta `apt-get install imagemagick`.
- **Modelos:** La primera vez se descargan desde Hugging Face; asegura tener conexion estable.
