# Guía del Ecosistema de Habilidades HTML (Plannotator / Effective HTML)

Este documento detalla en qué te puede ayudar cada una de las 8 habilidades de la suite instalada en el proyecto (`big-pics-little-words`, `design-artifact`, `html`, `html-diagram`, `html-plan`, `html-prototype`, `html-wireframe`, `one-pager`), cómo se relacionan entre sí y cuándo utilizar cada una.

---

## 1. Visión General del Ecosistema

Estas habilidades provienen del conjunto **`plannotator/effective-html`**. Su propósito fundamental es permitir que un agente de IA genere **artefactos HTML autocontenidos (single-file)** de nivel profesional, interactivos, responsivos y con accesibilidad nativa, sin depender de librerías externas pesadas ni compiladores.

### Mapa de Especialización y Flujo

```
                       ┌─────────────────────────┐
                       │      Petición HTML      │
                       └────────────┬────────────┘
                                    │
                                    ▼
                       ┌─────────────────────────┐
                       │          html           │
                       │    (Router Principal)   │
                       └────────────┬────────────┘
                                    │
       ┌──────────────┬─────────────┼──────────────┬──────────────┐
       ▼              ▼             ▼              ▼              ▼
┌──────────────┐┌────────────┐┌────────────┐┌─────────────┐┌──────────────┐
│html-wireframe││html-proto- ││ html-plan  ││html-diagram ││  one-pager /  │
│(Baja fideli- ││type (Media/││(Planes de  ││(Arquitectura││big-pics-little│
│dad / flujo)  ││Alta fidel.)││trabajo/QA) ││ y procesos) ││(Pitch rápido)│
└──────┬───────┘└─────┬──────┘└────────────┘└─────────────┘└──────────────┘
       │              │
       └───────┬──────┘
               ▼
   ┌───────────────────────┐
   │    design-artifact    │
   │  (Dirección de arte,  │
   │   paleta, tipografía) │
   └───────────────────────┘
```

---

## 2. Detalle de Cada Habilidad

### 1. `html` (El Enrutador y Creador General)
- **¿Qué es?**: Es el punto de entrada principal y el único enrutador implícito de la colección. Si la petición es amplia o involucra un entregable HTML mixto (reportes, herramientas interactivas, calculadoras, páginas de aterrizaje, historias de datos), `html` toma el control.
- **En qué te ayuda**:
  - Centraliza la decisión de derivar la tarea a una habilidad especialista (`html-wireframe`, `html-prototype`, `html-diagram`, `html-plan`) cuando la necesidad es específica.
  - Genera páginas web completas y autónomas cuando el entregable no encaja en una sola categoría (ej. un reporte interactivo con gráficos, un cotizador de envíos con tabla de precios).
  - Asegura que todo archivo generado sea 100% autocontenido (CSS y JS embebidos, sin dependencias CDN que requieran internet).
- **Cuándo usarla**: Cuando pidas "crea una página HTML para..." o "diseña una landing/herramienta en HTML", sin haber definido aún si es solo un diagrama, un plano o un wireframe.

---

### 2. `design-artifact` (El Director Creativo)
- **¿Qué es?**: No crea archivos por sí solo; actúa como el **director de arte** que se compone con las demás habilidades. Define la paleta de color, pares tipográficos, espaciado, soporte para modo claro/oscuro (`prefers-color-scheme` y data-attributes) y tono visual (desde formal/sobrio hasta editorial expresivo).
- **En qué te ayuda**:
  - **Evita la "estética cliché de IA"**: Prohíbe degradados morados genéricos, tarjetas idénticas con bordes redondeados estándar, fuentes predecibles y emojis como viñetas.
  - Establece un sistema de diseño estricto antes de programar: 4 a 6 colores con roles claros, 2 tipografías bien emparejadas, reglas de flujo y espaciado con CSS Flex/Grid.
  - Garantiza soporte para temas claro y oscuro con variables CSS (`:root`), asegurando legibilidad y contraste en ambos.
  - Otorga una personalidad visual alineada al negocio real (por ejemplo, logística rápida, mensajería urbana o comercio electrónico).
- **Cuándo usarla**: En combinación con cualquier entrega visual HTML cuando quieras elevar la calidad estética, definir un tema de marca coherente o cuando el resultado no deba lucir como una plantilla genérica.

---

### 3. `html-wireframe` (Estructura y Jerarquía en Baja Fidelidad)
- **¿Qué es?**: Especialista en crear wireframes interactivos en blanco y negro / escala de grises. Se enfoca estrictamente en **qué va en pantalla**, la disposición de elementos, la navegación y la jerarquía de información, **antes** de gastar tiempo en colores, sombras o detalles de diseño.
- **En qué te ayuda**:
  - Validar ideas y flujos de usuario rápidamente sin distracciones estéticas.
  - Proponer y comparar **2 o 3 alternativas de layout** en el mismo archivo mediante un selector sencillo (ej. Menú lateral vs. Menú superior, o flujo por pasos vs. formulario único).
  - Validar textos reales y etiquetas en lugar de textos de relleno (*lorem ipsum*).
  - Probar responsive básico (cómo se reorganiza en móviles vs pantallas grandes).
- **Cuándo usarla**: Cuando estás comenzando una nueva pantalla, flujo de compra, cotizador o panel de control y aún no se ha decidido la estructura ni la colocación de los elementos clave.

---

### 4. `html-prototype` (Prototipos Interactivos y Mockups de Alta Fidelidad)
- **¿Qué es?**: Especialista en construir modelos interactivos realistas o mockups terminados de una decisión de producto. Funciona en dos modos:
  1. **Modo Mockup**: Visualmente pulido, responsive y estático (para evaluar tipografía, color y aspecto final).
  2. **Modo Prototipo**: Flujo funcional navegable que simula interacciones reales (formularios, validaciones, transiciones, diálogos modales).
- **En qué te ayuda**:
  - Testear flujos completos: simular el ingreso de datos, respuestas de validación, estados de carga (*loading*), estados de éxito y manejo de errores.
  - Asegurar accesibilidad real: navegación completa por teclado (`Tab`, `Enter`, `Escape`), foco visual claro y compatibilidad con lectores de pantalla.
  - Experimentar la experiencia del usuario final antes de pasar a la etapa de backend o producción.
- **Cuándo usarla**: Cuando la estructura ya está aprobada y necesitas probar cómo se sentirá la interacción real, cómo reacciona el diseño a diferentes datos o para realizar pruebas de usabilidad con clientes/equipo.

---

### 5. `html-plan` (Planes de Proyecto, Rollouts y Hojas de Ruta)
- **¿Qué es?**: Especialista en convertir notas, especificaciones o listas de tareas en un documento HTML claro, estructurado y fácil de auditar.
- **En qué te ayuda**:
  - Organizar fases de trabajo, dependencias entre tareas, responsables y puntos de decisión.
  - **Fidelidad al contenido original**: A diferencia de crear un panel ficticio con porcentajes inventados, esta habilidad preserva escrupulosamente los compromisos reales, riesgos y preguntas abiertas sin inventar métricas decorativas.
  - Crear checklists interactivos, matrices de decisión, tablas de equivalencias o cronogramas secuenciales legibles.
- **Cuándo usarla**: Para presentar planes de migración, cronogramas de lanzamiento de funciones, auditorías de código, planes de refactorización o roadmaps ejecutivos que deban compartirse con el equipo.

---

### 6. `html-diagram` (Diagramas de Arquitectura, Flujo y Sistemas)
- **¿Qué es?**: Especialista en modelar visualmente relaciones, secuencias temporales, topologías de red/servicios, máquinas de estado y jerarquías usando HTML/CSS, SVG o Canvas embebido.
- **En qué te ayuda**:
  - Convertir explicaciones técnicas complejas en diagramas comprensibles de un vistazo.
  - Modelar:
    - **Topología**: microservicios, bases de datos, APIs y clientes.
    - **Secuencia**: llamadas asíncronas, webhooks, pasos de autenticación.
    - **Procesos y flujos**: estados de un pedido (ej. *Ingresado -> Retirado -> En depósito -> En camino -> Entregado*).
    - **Estados**: transiciones lógicas y condiciones de error.
  - Incorporar interactividad útil: filtros por componente, resaltado de rutas críticas, tooltips con detalles técnicos o modos de zoom.
- **Cuándo usarla**: Cuando explicar algo con texto sea demasiado engorroso y un diagrama gráfico interactivo resuelva dudas arquitectónicas o de procesos.

---

### 7. `one-pager` (Resumen Ejecutivo en Una Sola Página)
- **¿Qué es?**: Especialista en sintetizar una idea temprana o resumir el trabajo realizado en un único documento HTML concebido para leerse en **menos de 1 minuto**.
- **En qué te ayuda**:
  - Presentar propuestas de negocio, nuevas funciones o recapitulaciones de sprint a compañeros, clientes o directivos que no tienen tiempo para leer documentos largos.
  - Comunicar valor rápidamente bajo la regla: *"imágenes grandes y pocas palabras"*, sin eliminar detalles críticos pero eliminando jerga innecesaria.
  - Obtener retroalimentación temprana sobre una idea antes de dedicar horas a un diseño completo.
- **Cuándo usarla**: Al inicio de una iniciativa para validar interés o al final de una entrega para resumir el impacto logrado.

---

### 8. `big-pics-little-words` (Explicaciones Visuales y Conceptuales Directas)
- **¿Qué es?**: Habilidad enfocada en la explicación pedagógica y visual extrema: enseñar o comunicar conceptos mediante gráficos amplios, esquemas visuales destacados y texto mínimo de alto impacto.
- **En qué te ayuda**:
  - Explicar temas técnicos o de negocio a personas que se incorporan recién al proyecto o a perfiles no técnicos.
  - Reducir la fricción cognitiva descomponiendo problemas intrincados en diagramas visuales evidentes con explicaciones directas, breves y sin rodeos.
- **Cuándo usarla**: Cuando necesites que el agente te explique un tema complejo visualmente o cuando prepares material explicativo para usuarios finales o clientes.

---

## 3. Matriz de Decisión Rápida

| Si tu objetivo principal es... | La habilidad ideal es... | Habilidad de apoyo recomendada |
| :--- | :--- | :--- |
| **Probar la distribución de elementos y comparar layouts sin preocuparte por colores** | `html-wireframe` | `design-artifact` (para espaciado) |
| **Crear una pantalla realista con formularios interactivos, validaciones y feedback** | `html-prototype` | `design-artifact` (para marca y colores) |
| **Explicar una arquitectura de software, flujo de datos o ciclo de vida de un estado** | `html-diagram` | `big-pics-little-words` |
| **Documentar un plan de acción, roadmap técnico o pasos de migración** | `html-plan` | — |
| **Hacer un pitch rápido de 1 minuto de una idea para el equipo o clientes** | `one-pager` | `big-pics-little-words` |
| **Explicar un concepto difícil visualmente con poco texto** | `big-pics-little-words` | `html-diagram` |
| **Definir la identidad visual, tipografías, contraste y paleta de un entregable HTML** | `design-artifact` | Complementa a todas |
| **Construir una página general, reporte o calculadora autocontenida** | `html` | `design-artifact` |

---

## 4. Archivo Relacionado

Para consultar ejemplos de prompts prácticos listos para usar con cada una de estas habilidades en proyectos generales y en este repositorio, revisa:
- [`PROMPTS_HABILIDADES_HTML.md`](file:///D:/repositorios/0pruebas_envios/PROMPTS_HABILIDADES_HTML.md)
