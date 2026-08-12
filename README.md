# Asteroids

Clon del clásico arcade **Asteroids** implementado en canvas HTML5 puro, sin dependencias ni bundler.

## Descripción

Nave espacial en un campo de asteroides con envolvimiento de bordes (el espacio es toroidal). Destruye asteroides para sumar puntos: los grandes se parten en medianos, los medianos en pequeños. Incluye power-ups especiales y tipos de asteroides únicos como la estrella fugaz.

## Tecnologías

- **HTML5 Canvas** — renderizado 2D
- **JavaScript (ES6+)** — lógica del juego en un solo archivo `game.js`
- Sin frameworks, sin bundler, sin dependencias

## Cómo correr

Abre `index.html` directamente en el navegador (doble clic), o usa un servidor local:

```bash
npx serve .
```

Luego visita `http://localhost:3000`.

## Controles

| Tecla     | Acción     |
| --------- | ---------- |
| `←` `→`   | Rotar nave |
| `↑`       | Propulsar  |
| `Espacio` | Disparar   |
| `Q`       | Cambiar skin de la nave |

## Puntuación

| Asteroide    | Puntos |
| ----------- | ------ |
| Grande      | 20     |
| Mediano     | 50     |
| Pequeño     | 100    |
| Estrella fugaz | 200   |

## Características

- 3 vidas con invencibilidad temporal al reaparecer (parpadeo)
- Asteroides se parten en fragmentos más pequeños al ser destruidos
- Partículas de explosión al destruir asteroides
- Power-ups: al destruir un asteroide hay 50 % de probabilidad de que caiga uno (a partes iguales entre los tres)
  - Velocidad (rayo): 2× de velocidad durante 5 s
  - Escudo (aro): protege la nave durante 8 s; cualquier asteroide o estrella fugaz que toque el escudo se destruye
  - Triple shot (tres puntos): cada disparo produce una ráfaga de 3 balas secuenciales durante 5 s
- Estrella fugaz: un asteroide especial que cruza la pantalla a gran velocidad con una estela brillante. Desaparece después de 7 segundos si no la destruyes. Otorga 200 puntos.
- Sistema de skins: personaliza el color de tu nave. Pulsa `Q` para cambiar de skin. Tu selección se guarda automáticamente.
  - La skin **Morada** duplica el tamaño de la nave y duplica los puntos que obtienes por cada asteroide y estrella fugaz destruidos.
