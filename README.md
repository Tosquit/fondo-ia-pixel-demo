# Fondo IA · Oficina Pixel

Demo funcional del fondo de inversiones con IA y estética pixel-art, integrada en el panel de Hermes (:9119, plugin `oficina`) y desplegable en GitHub Pages.

## Qué muestra

- **HUD superior**: cuota de LLM, gasto mensual, posiciones abiertas, P&L del día y estado del motor.
- **Oficina pixel-art**: 9 salas de trading (risk, señales, dirección, auditoría, ejecución, estrategias, seguridad, guardián y documentación) con sprites 10×14 píxeles generados en SVG.
- **Chart de portfolio**: renderizado pixel-native con `<rect>` `shape-rendering="crispEdges"`, sin librerías externas.
- **Terminal lateral**: ficha del agente seleccionado, posiciones simuladas y log de operaciones.
- **Hexcore · Argos**: motor de decisión con anillos giratorios y el búho de Argos.

## Stack

Vanilla HTML/CSS/JS autocontenido, sin build.

- Tipografía: `VT323` + `Press Start 2P` (Google Fonts).
- Sprites y búho generados por JS a píxel en SVG.
- Datos simulados de portfolio y posiciones.
- Paleta y componentes basados en la maqueta `oficina-zaun` (Fallout Shelter × Arcane).

## Decisiones de estilo (ADR-0001)

- Desarrollo propio desde cero; ningún repo del reel se adopta como base.
- No se usan librerías de charts externas; el chart es pixel-native.
- `--down: #ff4d4d` para pérdidas (promovido de literal a variable).
- `prefers-reduced-motion` desactiva animaciones.
- `.btn.warn` para acciones que mueven dinero.
- Sprites generados propios; ningún asset externo sin licencia verificada.

## Cómo probar

```bash
python -m http.server 8124 --directory .
# Abre http://localhost:8124/index.html
```

## Despliegue

### GitHub Pages

Activado automáticamente desde la rama `main` en la carpeta raíz.
URL: `https://tosquit.github.io/fondo-ia-pixel-demo/`

### Panel Hermes :9119

El fichero `index.html` se sirve también desde el plugin `oficina`:

```
http://localhost:9119/dashboard-plugins/oficina/dist/fondo-ia-demo.html
```

## Estructura

```
.
├── index.html      # Demo completa autocontenida
├── README.md       # Este fichero
├── LICENSE         # MIT
└── CREDITS.md      # Atribuciones
```

## Licencia

MIT — ver [LICENSE](LICENSE).
