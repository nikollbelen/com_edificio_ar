# WebAR Loma de Jesús

Experiencia de realidad aumentada web para visualizar contenido promocional de **Loma de Jesús** al apuntar la cámara del dispositivo hacia un póster físico. El proyecto combina detección de imagen, modelo 3D, video y controles táctiles directamente desde el navegador.

## Funcionalidades

- Pantalla inicial con llamada a la acción para iniciar AR.
- Solicitud de cámara activada por interacción del usuario.
- Detección de imagen objetivo usando `targets.mind`.
- HUD superior con estado de búsqueda o detección del póster.
- Guía visual de escaneo para orientar al usuario.
- Carga de modelo 3D `.glb` sobre el marcador detectado.
- Reproducción de video promocional `video.mp4` dentro de la escena AR.
- Pausa automática del video cuando se pierde el target.
- Reanudación automática del video cuando el target vuelve a detectarse.
- Etiqueta visual de contenido promocional.
- Iluminación ambiente y direccional para el modelo.
- Controles táctiles y mouse para ajustar la escena.
- Escalado del modelo: grande / pequeño.
- Rotación izquierda / derecha.
- Movimiento horizontal y vertical.
- Ajuste de profundidad hacia adelante / atrás.
- Acciones continuas mientras se mantiene presionado el botón.
- Botón para resetear posición, escala y rotación.
- Interfaz mobile-first para uso desde celular.

## Tecnologías

| Tecnología | Rol |
|---|---|
| HTML | Estructura de la experiencia |
| CSS | Interfaz, HUD, splash, loader y controles |
| JavaScript | Lógica de AR, eventos y manipulación del modelo |
| A-Frame | Escena 3D declarativa en navegador |
| MindAR | Tracking de imagen para WebAR |
| WebGL | Renderizado 3D |
| GLB | Formato del modelo 3D |
| MP4 | Video promocional |

## Requisitos

- Navegador moderno con soporte WebGL y acceso a cámara.
- Dispositivo con cámara, preferiblemente móvil.
- Conexión HTTPS para usar cámara en producción.
- Un servidor local o remoto para servir los archivos. Abrir el HTML directo como `file://` puede bloquear cámara o assets en algunos navegadores.
- Póster o imagen objetivo asociada a `targets.mind`.

## Ejecutar después de clonar

1. Clona el repositorio:

```bash
git clone <URL_DEL_REPOSITORIO>
cd com_edificio_ar
```

2. Sirve la carpeta con un servidor estático. Por ejemplo, con Node.js:

```bash
npx serve .
```

También puedes usar cualquier servidor estático equivalente, como la extensión Live Server de VS Code.

3. Abre la URL local que indique el servidor, por ejemplo:

```text
http://localhost:3000
```

4. En un celular, abre la URL desde el navegador y concede permiso de cámara.

5. Apunta la cámara al póster entrenado en `targets.mind`.

## Archivos principales

| Archivo | Descripción |
|---|---|
| `index.html` | Experiencia completa: interfaz, escena AR y lógica JavaScript |
| `targets.mind` | Target compilado para detección de imagen |
| `avatar.glb` | Modelo 3D mostrado sobre el póster |
| `video.mp4` | Video promocional reproducido en la escena |
| `poster.jpg` | Imagen/poster de referencia |

## Personalización

- Cambia `avatar.glb` para reemplazar el modelo 3D.
- Cambia `video.mp4` para actualizar el video promocional.
- Regenera `targets.mind` si se usa otro póster o imagen objetivo.
- Ajusta posición, escala o rotación inicial del modelo en el componente `<a-gltf-model>`.
- Ajusta el tamaño y ubicación del video en el componente `<a-video>`.
