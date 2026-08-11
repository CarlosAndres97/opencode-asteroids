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
- Power-up de velocidad (rayo): 12.5 % de probabilidad de drop al destruir un asteroide — al recogerlo, la nave obtiene 2× de velocidad durante 5 s
- Power-up de escudo (aro): 12.5 % de probabilidad de drop al destruir un asteroide — al recogerlo, la nave queda protegida durante 8 s; cualquier asteroide o estrella fugaz que toque el escudo se destruye
- Estrella fugaz: un asteroide especial que cruza la pantalla a gran velocidad con una estela brillante. Desaparece después de 7 segundos si no la destruyes. Otorga 200 puntos.
