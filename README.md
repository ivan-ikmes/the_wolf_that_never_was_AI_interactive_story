# El Lobo Que No Fue

**Audiovisual interactivo** basado en *Caperucita Roja* de Charles Perrault.
Productor: Iván Ochoa.

Cuatro decisiones, cinco finales. El cuento empieza por el final, con el lobo despierto en la cama de la abuela, y luego "rebobina" al bosque. Desde ahí, quien lo ve decide qué hacen Caperucita y el lobo.

## Cómo verlo

1. Copia la carpeta completa: `index.html` necesita la carpeta `media/` a su lado.
2. Abre `index.html` con doble clic en Chrome, Edge o Firefox.
3. No necesita internet ni instalar nada.

**Controles:** `A` / `B` para decidir · `Espacio` pausa · `F` pantalla completa · `M` mapa de finales.

## Estructura

```
Escena 1 (presente) → Escena 7 (origen) → D4 · Caperucita
    B → FINAL E — Los leñadores
    A → Escena 6 → D3 · El lobo
          B → FINAL D — El camino que no se tomó
          A → Escena 5 → Escena 4 → D2 · Caperucita
                B → FINAL C — La huida en la puerta
                A → Escena 3 → Escena 2 → D1 · El lobo
                      A → FINAL A — El final clásico
                      B → FINAL B — La duda
```

## Datos del usuario

El interactivo **no recoge, envía ni comparte ningún dato personal**. No tiene formularios, cuentas, analítica, cookies de terceros ni conexión a internet.

Lo único que guarda es **qué finales has descubierto** (por ejemplo `["A","C"]`), para mostrarlo en el mapa de finales. Se guarda en el `localStorage` de tu propio navegador, con la clave `lobo_finales`. Ese dato:

- no sale de tu equipo;
- no identifica a nadie;
- se borra al limpiar los datos de navegación. Si el navegador bloquea el almacenamiento, el interactivo funciona igual, solo que no recuerda los finales.

## Herramientas de IA usadas

| Etapa | Herramienta |
| --- | --- |
| Guion literario, guion técnico y storyboard | Redactados con ayuda de **ChatGPT** (OpenAI) y **Claude** (Anthropic) |
| Imágenes de cada plano | **Google Flow** |
| Animación de las imágenes a video | **Pruna P-Video-2** |
| Voces de los personajes | **ElevenLabs**: Text to Speech (modelos Multilingual v2 y v3) y Voice Design para Caperucita, la Abuela y el Narrador |
| Efectos de sonido, ambientes y música | **ElevenLabs** Sound Effects |
| Plan de audio, mezcla y reproductor interactivo | Creados con **Claude Code** (Anthropic) |

### Qué se hizo con Claude Code

- El plan de audio de los 70 clips, a partir del guion técnico (diálogos, efectos, música y volumen de cada plano).
- Los scripts que generan el audio con la API de ElevenLabs y lo mezclan con **FFmpeg**: normalización de volumen, ajuste de los diálogos a la duración de cada clip y ralentización de los clips donde el diálogo no cabía.
- El diseño de las voces en la web de ElevenLabs, manejando el navegador mientras el autor escuchaba y elegía las muestras.
- Este reproductor interactivo (`index.html`): decisiones con temporizador de 10 s, encadenado de clips sin cortes, mapa de finales y rótulos.

## Notas

- La voz de Caperucita es una voz adulta de tono juvenil, porque ElevenLabs no permite diseñar voces de menores.
- El audio se generó con el plan gratuito de ElevenLabs, que **no permite uso comercial** y pide atribución a ElevenLabs. Antes de publicar o comercializar la obra, hay que revisar las condiciones de cada herramienta.
- Algunos clips duran más que en el guion porque se ralentizaron para que cupiera el diálogo.
