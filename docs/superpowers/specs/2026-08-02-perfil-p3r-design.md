# Perfil GitHub estilo Persona 3 Reload

Fecha: 2026-08-02 · Repo: `Johannuel/Johannuel`

## Objetivo

Rediseñar el perfil GitHub (banner + README) con la estética de Persona 3 Reload:
elegancia, azul marino profundo, agua/burbujas, luna, tarot, blackletter "Memento Mori".
Aprobado por el usuario el 2026-08-02 con animación CSS incluida.

## Identidad visual

- Paleta: `#05070D` (negro azulado), `#0B2A5B` (azul marino), `#1269CC` (azul eléctrico),
  `#51EEFC` (cian burbuja), `#6D9AC7` (azul grisáceo), `#F2F7FF` (blanco),
  `#C9A24B` (dorado tarot, sutil).
- Tipografías (Google Fonts, vía `@import` embebido en los SVGs):
  - UnifrakturMaguntia — blackletter para "MEMENTO MORI" y "RELOAD" (logo P3R).
  - Rajdhani (300/500/700) — sans geométrica condensada para UI.
- Motivos: agua/caustics, burbujas ascendentes, luna llena con glow, sello SEES circular
  con texto curvo, tarjeta de tarot volteándose (THE FOOL 0), fecha 04.04.2009,
  marco fino con esquinas doradas.

## Banner `profile-banner.svg` (1500×500)

Composición de izquierda a derecha:
1. Luna llena con halo radial + "Memento Mori" (gótico) y "RELOAD" (sans espaciada).
2. Centro: "MF CODER" (Rajdhani 700, ~120px, skew −6°, gradiente cian→blanco, glow) +
   bandas de agua (shimmer) pasando por encima; tagline `[ RUST · LINUX · DEVOPS ]`.
3. Sello circular "PHANTOM OF CODE" rotando lento (textPath + triángulos + núcleo dorado).
4. Tarjeta THE FOOL 0 volteándose periódicamente (flip scaleX + alternancia de caras).
5. Fecha `04.04.2009`, marco, caustics ondulados animados, burbujas subiendo con
   delays distintos, sparkles.

Animaciones (todas seguras para el render de GitHub: opacity/translate/rotate/scaleX):
rise (burbujas), float (caustics), pulse (luna), spin (sello), shimmer (bandas de agua),
flip (tarjeta), twinkle (sparkles).

## README

- Banner como primera imagen.
- Divisores SVG de onda de agua entre secciones.
- Cards de proyectos estilo tarjeta P3R (SVG auto-contenido).
- Stack con iconos simpleicons en azul eléctrico `#1269CC`/`#51EEFC`.
- Se conserva `ratatui-spin-dark.gif`.

## Técnica

SVGs auto-contenidos referenciados como `![alt](./archivo.svg)`; GitHub los sirve vía
camo con `@import` de fuentes funcionando. Sin dependencias externas ni servicios.

## Verificación

- XML válido (ET.parse).
- Preview con `rsvg-convert` a `Pictures/banner-preview.png`.
- `git push` tras aprobación.
