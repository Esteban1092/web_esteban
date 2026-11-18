# DESIGN.md — Webs Esteban González (gusto registrado)

Reglas de gusto de Esteban, sacadas de sus correcciones. Un agente nuevo
que toque esta web debe respetarlas sin que se las repitan.

## Reglas (cada una viene de algo que Esteban dijo o corrigió)

| Regla | Origen |
| --- | --- |
| Solo Scott, sin Ramona, en la web y en los videos | "tiene q tener solo a scott haciendo gestos sin ramona" |
| La playera negra con logo WEBS va fija todo el video; solo cambian las expresiones | "la playera solo q este fija oor q expresa las emociones" |
| Decir solo "web", nunca "Webs Esteban" en la narración | "q no diga webs esteban solo q diga web" |
| Videos ~30 s, solo voz, sin canciones | "Pero no pongas las canciones mejor solo la voz" |
| Sin faltas de ortografía en textos en pantalla | "pero q no tenga ninguna falta de ortografía" |
| Precios exactos, nunca inventados por el generador | El generador inventó $19/$49/$99/mes y hubo que quitarlos |
| Sin reseñas, clientes ni rating inventados | La web no tiene clientes todavía; no inventar confianza |
| Sin dirección exacta de calle, solo "Chalco, Estado de México" | Decisión de privacidad de Esteban |
| Las webs son negocio aparte de HYPE DROP MX, sin su marca | Decisión 2026-11-15 |
| Scott Pilgrim de verdad: que se parezca a Scott, no un genérico | "los videos no se parecen a scott piligrim" |

## Motion (Emil Kowalski, aplicado 2026-11-18)

- Tokens: `--ease-out: cubic-bezier(0.23,1,0.32,1)`, `--ease-in-out: cubic-bezier(0.77,0,0.175,1)`.
- UI < 300ms. Solo transform/opacity (+ clip-path en reveals).
- Botones: `:active scale(0.97)`, 160ms. Entradas desde scale(0.95)+opacity.
- Hover gateado con `@media (hover:hover) and (pointer:fine)`.
- `prefers-reduced-motion`: se quita el movimiento, no el cambio de estado.

## Vocabulario (animation-vocabulary)

- **Pop in** — la cara de Scott entra con scale + fade.
- **Crossfade** — cambio de cara de Scott y del texto del bubble.
- **Stagger** — entrada del hero y de las tarjetas, con delays no uniformes.
- **Clip-path reveal** — las secciones se revelan con `inset(0 0 100% 0) → inset(0 0 0 0)`.
- **Rubber-banding** — resistencia al arrastrar a Scott pasado el límite.

## Coreografía del hero (choreograph)

| Elemento | Rol | Inicio | Duración | Movimiento | Relación |
| --- | --- | --- | --- | --- | --- |
| Eyebrow | Decoración | 0ms | 500ms | fade + 8px rise | Junto al título |
| WEBS (h1) | Lead | 60ms | 500ms | fade + 8px rise | Solapa al eyebrow |
| Subtítulo | Support | 130ms | 500ms | fade + 8px rise | Solapa al título |
| Lead | Support | 200ms | 500ms | fade + 8px rise | Solapa al subtítulo |
| CTAs | Support | 270ms | 500ms | fade + 6px rise | Solapa al lead |
| Trust | Support | 340ms | 500ms | fade + 6px rise | Solapa a los CTAs |
| Hero-art (Scott) | Decoración | 120ms | 500ms | solo fade | Junto al título |

No se mueve: fondo, marquee (ya tiene su propio loop), precios (dato funcional).
