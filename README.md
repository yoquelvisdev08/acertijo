# Creador de Clips Virales - Acertijos para IG

Proyecto para generar videos cortos de acertijos para Instagram (Reels) con voz, video generado por IA y subtitulos. Todo en un solo notebook de Google Colab.

## Que incluye

- **Voz:** Qwen3-TTS (espanol, voces predefinidas).
- **Video:** Wan 2.1 T2V 1.3B (text-to-video, optimizado para Colab).
- **Subtitulos:** Generados a partir del guion y el audio.
- **Composicion:** MoviePy (video + audio + subtitulos quemados, formato 9:16).
- **Interfaz:** Gradio en el propio Colab.

## Conectar con Colab sin borrar el proyecto (recomendado)

Para que los cambios que hagas en tu PC se vean en Colab sin tener que borrar ni volver a crear el proyecto:

1. **Repo:** https://github.com/yoquelvisdev08/acertijo
2. **En tu PC:** para subir cambios: `git add .`, `git commit -m "..."`, `git push`.
3. **En Colab:** Menu **File > Open notebook** > pestaña **GitHub** > pega `https://github.com/yoquelvisdev08/acertijo` o busca "acertijo", y abre **creador_acertijos_ig.ipynb**.
4. **Cuando cambies algo en tu PC:** haz `git push`. En Colab vuelve a abrir el notebook desde GitHub y tendras la version nueva. No hace falta borrar nada.

Dentro del notebook hay una **Celda 0 (opcional)** para clonar o actualizar el repo desde Colab con `git pull` si prefieres ese flujo.

## Como usar en Colab

1. Abre el notebook en Colab (subiendolo o abriendo desde GitHub como arriba).
2. En Colab: **Runtime > Change runtime type > GPU** (T4 o superior).
3. Ejecuta las celdas en orden:
   - Primera celda: instalacion de dependencias (tardara unos minutos).
   - Siguientes celdas: imports, configuracion, funciones y modelo.
   - Ultima: lanzar la interfaz Gradio.
4. En el cuadro de texto escribe el tema del acertijo (o el texto completo del acertijo) y pulsa **Generar video**.
5. Descarga el MP4 desde el reproductor o el enlace que aparezca.

## Requisitos

- Cuenta de Google (Colab).
- Runtime con GPU (gratis T4 o Colab Pro para mas VRAM).
- Para Wan 2.1 T2V 1.3B se recomienda al menos 10 GB VRAM.

## Estructura del proyecto

```
creador de clips virales/
  README.md
  requirements_colab.txt
  creador_acertijos_ig.ipynb
```

## Referencias

- [Wan 2.1](https://github.com/Wan-Video/Wan2.1) / [Diffusers Wan](https://huggingface.co/docs/diffusers/main/en/api/pipelines/wan)
- [Qwen3-TTS](https://github.com/QwenLM/Qwen3-TTS)
- [Wan2GP](https://github.com/deepbeepmeep/Wan2GP) (inspiracion para uso eficiente en GPU limitada)
