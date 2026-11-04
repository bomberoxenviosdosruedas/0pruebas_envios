# Envíos DosRuedas — Project Constitution

## 1. Project Overview & Context
- **Business**: Mensajería urbana y logística e-commerce de última milla en Mar del Plata.
- **Key Differentiator**: Flota propia, cero tercerización, base física en Friuli 1972.
- **Stack**: HTML5 semántico, CSS3 moderno con variables CSS (:root), JavaScript nativo / GSAP.

## 2. Token-Saving Guidelines (Strict)
1. **Targeted Reading**: Always use `read_file` with `StartLine`/`EndLine` ranges. Never read full files if only a section is needed.
2. **Lean Responses**: Provide concise, github-style markdown answers and clickable file links. Do not dump entire HTML files into the chat.
3. **On-Demand Reference**: Detailed design specs live in `SISTEMA_DISENO_Y_DEFINICION_SITIO.md`. Read it only when designing new components.
4. **Progressive Disclosure**: Domain-specific rules live in `.agents/rules/` and are loaded via globs or model decision, never permanently in memory.

## 3. Brand & Palette Snapshot
- Primary Blue: `#0950F6` (hover `#073BC2`, surface `#E6EEFE`)
- High-Vis Yellow: `#FFEC01` (hover `#FFF12E`, contrast text `#0950F6` or `#071536`)
- Typography: Display: `Anton SC` / `Anton` | Subheading: `Bebas Neue` | Body: `Outfit` | Mono: `Geist Mono`
- Contrast Rule: Text on yellow background MUST be blue (`#0950F6`) or dark ink (`#071536`). Never white.

## 4. Work Directory Standards
- Production Proposals: `propuestas/pruebas/home/`
- Static Assets: `propuestas/public/` (`logo.webp`, `card_mapa.webp`, `persona_icono.webp`)
