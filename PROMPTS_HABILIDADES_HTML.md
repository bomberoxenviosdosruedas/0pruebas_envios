# Catálogo de Prompts para las Habilidades HTML

Este archivo contiene plantillas de prompts optimizadas y listas para usar con las 8 habilidades de la suite `plannotator/effective-html` instaladas en el entorno:
- `big-pics-little-words`
- `design-artifact`
- `html`
- `html-diagram`
- `html-plan`
- `html-prototype`
- `html-wireframe`
- `one-pager`

---

## 1. `html-wireframe`

### Cuándo usarla
Para explorar la disposición de elementos, la jerarquía visual y los flujos de navegación en baja fidelidad (escala de grises, sin distracciones de color ni sombras), comparando diferentes alternativas de layout.

### Prompt 1: Comparativa de 2 a 3 variantes de layout (Caso Envíos / Cotizador)
```markdown
Usa la habilidad html-wireframe para crear un wireframe en baja fidelidad de una pantalla para cotizar y solicitar envíos urbanos ("Envíos DosRuedas").

Requisitos:
- Incluye 2 o 3 variantes de diseño seleccionables mediante un switcher en la parte superior:
  * Variante A: Formulario paso a paso (Wizard guiado: origen/destino -> tipo de paquete -> método de pago).
  * Variante B: Formulario en una sola página con desglose de costos en vivo a la derecha.
  * Variante C: Enfoque mapa interactivo predominante con inputs flotantes.
- Utiliza escala de grises estricta, tipografía del sistema y contenedores limpios.
- Usa textos y datos reales (nombres de calles, rangos de peso en kg, tipos de servicio como Flex o Express), nada de lorem ipsum.
- Asegura que el archivo sea un único .html autocontenido y responsive para móvil y escritorio.
```

### Prompt 2: Panel de control de envíos (Dashboard B2B)
```markdown
Invoca html-wireframe para diseñar la estructura del panel de gestión de envíos para empresas y clientes con cuenta corriente.

Necesito definir la jerarquía de:
1. Resumen superior: pedidos activos, entregados hoy e incidencias.
2. Listado principal con filtros por estado (En depósito, En ruta, Entregado, Reprogramado).
3. Panel lateral de detalle del envío seleccionado (historial y comprobante de entrega).

Mantén el estilo en baja fidelidad, sin logos ni colores de marca. El objetivo es evaluar si el flujo de revisión rápida de pedidos es ágil.
```

---

## 2. `html-prototype`

### Cuándo usarla
Para crear maquetas pulidas estáticas (*Mockup*) o experiencias interactivas (*Prototype*) con formularios funcionales, validaciones, estados de carga, éxito y error.

### Prompt 1: Prototipo Interactivo de Tracking de Envío en Tiempo Real
```markdown
Usa la habilidad html-prototype en modo PROTOTIPO interactivo para crear una pantalla de rastreo de envíos para el cliente final.

Requisitos funcionales:
- Un campo de búsqueda para ingresar el número de seguimiento (ej. "DR-84920").
- Simula los estados del flujo:
  1. Estado inicial vacío (buscador y preguntas frecuentes).
  2. Estado de carga con indicador visual sutil al consultar.
  3. Estado de éxito: línea de tiempo del envío con estados cumplidos y pendientes, hora estimada de llegada y datos del repartidor.
  4. Estado de error: si se ingresa un código no válido, mostrar mensaje de error con sugerencia clara de solución.
- Debe soportar navegación completa por teclado (Tab, Enter, Escape).
- Archivo único .html autocontenido con CSS y JS embebidos, responsive para móviles.
```

### Prompt 2: Mockup de Alta Fidelidad para Landing Page de Servicios
```markdown
Usa la habilidad html-prototype en modo MOCKUP estático de alta fidelidad, complementado con design-artifact, para diseñar la sección de presentación del "Plan Emprendedores" de Envíos DosRuedas.

Detalles:
- Enfoque visual pulido, tipografía editorial moderna y paleta de colores coherente con logística y velocidad.
- Componentes: comparativa de planes (Lite vs Full vs Flex), calculadora rápida de ahorro mensual según volumen de paquetes, y sección de llamada a la acción con botón hacia WhatsApp/contacto.
- Incluye micro-interacciones en botones y tarjetas al pasar el cursor (hover) y soporte para modo oscuro automático.
```

---

## 3. `design-artifact`

### Cuándo usarla
Para definir la dirección artística, tokens de diseño (CSS variables), pares tipográficos, esquemas de color accesibles y asegurar que el resultado no parezca una plantilla genérica generada por IA.

### Prompt 1: Creación de Sistema de Diseño y Tokens para un Artefacto
```markdown
Aplica los principios de la habilidad design-artifact para crear la dirección de arte de las páginas de servicios de nuestro repositorio.

Requisitos de diseño:
1. Paleta de colores: Define exactamente entre 4 y 6 tokens en variables CSS (:root), incluyendo color primario de acento, fondos neutros intencionales (evita grises muertos sin matiz) y colores semánticos (éxito, advertencia, error).
2. Temas: Configura compatibilidad nativa tanto para prefers-color-scheme como para atributo data-theme="dark" / data-theme="light", asegurando que el modo oscuro tenga un contraste perfecto y no sea una simple inversión mecánica.
3. Tipografía: Empareja dos familias tipográficas (una con personalidad para títulos y otra de lectura óptima para el cuerpo) con text-wrap: balance en encabezados y números tabulares (tabular-nums).
4. Evita el cliché de IA: Nada de fondos crema con acentos terracota ni degradados morados/azules genéricos.
```

### Prompt 2: Auditoría y Refactor Estético de un HTML Existente
```markdown
Revisa el archivo `inicio.html` bajo las reglas de la habilidad design-artifact. 
Genera una versión mejorada en un nuevo archivo HTML que:
- Corrija la jerarquía visual y el ritmo vertical (usa flex/grid con gap uniforme en lugar de márgenes dispersos).
- Eleve el tono visual de la página al nivel de una empresa de logística moderna y confiable.
- Integre micro-interacciones con propósito que respeten prefers-reduced-motion.
- Mantenga el archivo 100% autocontenido y listo para abrir en el navegador.
```

---

## 4. `html-diagram`

### Cuándo usarla
Para explicar arquitecturas de software, secuencias temporales, máquinas de estado, topologías de infraestructura o procesos de negocio complejos en un modelo visual interactivo.

### Prompt 1: Ciclo de Vida del Paquete / Máquina de Estados Logística
```markdown
Usa la habilidad html-diagram para modelar el ciclo de vida completo de un paquete en el servicio de logística y distribución urbana.

Debe incluir:
- Los estados posibles: Recibido en depósito -> Clasificado por zona -> Asignado a repartidor -> En tránsito -> Primer intento fallido -> Reintento / Custodia -> Entregado con éxito / Devuelto al remitente.
- Transiciones con condiciones claras (ej. "Reintento permitido: máx 2 veces", "Motivo de no entrega: domicilio cerrado").
- Interactividad: al hacer clic o pasar el cursor sobre un estado, resaltar la ruta previa y los siguientes pasos posibles, mostrando un panel lateral con los datos técnicos (disparadores de eventos y webhooks generados).
- Generado en un único archivo HTML interactivo con SVG/Canvas embebido.
```

### Prompt 2: Arquitectura del Sistema de Notificaciones y Webhooks
```markdown
Invoca html-diagram para crear un diagrama de secuencia y topología técnica que ilustre la integración de pedidos con tiendas online (WooCommerce / Tiendanube / MercadoLibre):
1. Evento de compra en la tienda del cliente.
2. Webhook recibido por nuestra API.
3. Validación de coordenadas y asignación de tarifa.
4. Notificación al despachante y generación de etiqueta térmica.
5. Mensajería automática por WhatsApp al comprador final.

Incluye controles de visualización (filtro por actores y vista paso a paso interactiva).
```

---

## 5. `html-plan`

### Cuándo usarla
Para transformar especificaciones, roadmaps, planes de refactorización o lanzamientos en documentos interactivos legibles, manteniendo la trazabilidad estricta de compromisos y riesgos sin inventar métricas ficticias.

### Prompt 1: Plan de Migración y Rediseño Web
```markdown
Usa la habilidad html-plan para estructurar el plan de migración y modernización de las páginas HTML del proyecto (`inicio.html`, `contacto.html`, páginas de servicios).

El documento HTML generado debe presentar:
1. Fases de ejecución (Fase 1: Auditoría de accesibilidad y SEO; Fase 2: Unificación de sistema de diseño y componentes; Fase 3: Pruebas responsive y lanzamiento).
2. Matriz de dependencias y riesgos críticos (ej. impacto en formularios de contacto y enlaces existentes).
3. Checklists de criterios de aceptación verificables para cada archivo.
4. Sección dedicada a preguntas abiertas y decisiones de diseño pendientes de aprobación.

Asegúrate de que la navegación sea accesible mediante teclado y el documento sea sobrio y profesional.
```

### Prompt 2: Plan de Implementación de Integración con Mercado Envíos Flex
```markdown
Invoca html-plan para documentar el plan de trabajo para la integración técnica y operativa del servicio de Envíos Flex.

Organiza la información en:
- Requisitos técnicos previos (credenciales, webhooks, rango horario de corte).
- Secuencia de tareas ordenada por sprint/semana con responsables y entregables.
- Protocolo de pruebas de contingencia y tiempos de respuesta.
- Formato tabla interactiva con filtros por estado (Pendiente, En curso, Bloqueado, Completado).
```

---

## 6. `one-pager`

### Cuándo usarla
Para crear una sola página HTML con foco en "imágenes grandes y pocas palabras" que comunique una propuesta o resuma el trabajo realizado para ser leída y entendida en menos de 60 segundos por compañeros o clientes.

### Prompt 1: Pitch Ejecutivo de Nueva Funcionalidad
```markdown
Usa la habilidad one-pager para crear un documento HTML de una sola pantalla que presente al equipo la propuesta: "Retiros en el día con franja horaria pactada para ecommerce".

Reglas clave:
- Formato concebido para leerse en menos de 1 minuto.
- Enfoque visual: gráficos claros, cifras de impacto grandes y texto sumamente conciso sin jerga técnica.
- Estructura:
  1. El problema actual (clientes ausentes en entregas diurnas).
  2. La solución propuesta (franjas de 3 horas seleccionables por el comprador).
  3. El impacto proyectado (reducción del 40% en segundas visitas).
  4. La llamada a la decisión (qué necesitamos para arrancar).
```

### Prompt 2: Resumen de Resultados de Campaña / Métricas Logísticas
```markdown
Crea un one-pager en HTML resumiendo el balance operativo del último mes para los clientes corporativos.
- Destaca visualmente 3 métricas clave: Tasa de efectividad de entrega (98.4%), Tiempo promedio de entrega Express (110 min), e Índice de satisfacción del cliente (4.9/5).
- Agrega un gráfico visual simplificado del volumen por zonas geográficas.
- Incluye un bloque de agradecimiento y próximos pasos para el siguiente mes.
```

---

## 7. `big-pics-little-words`

### Cuándo usarla
Cuando necesites explicar un tema intrincado o proceso conceptual de forma visual y pedagógica, con gráficos destacados y explicaciones breves aptas para cualquier persona.

### Prompt 1: Explicación Visual del Servicio de Fulfillment y Depósito
```markdown
Aplica la habilidad big-pics-little-words para generar un archivo HTML interactivo que explique a dueños de tiendas online cómo funciona el servicio de Depósito y Fulfillment de Envíos DosRuedas:

- Muestra visualmente las 4 etapas con ilustraciones/iconos claros y textos ultra breves:
  1. Recepción: Dejas tu mercadería en nuestro depósito central.
  2. Almacenaje & Inventario: Tu stock se registra en tiempo real en nuestra plataforma.
  3. Preparación (Picking & Packing): Se vende en tu tienda y nosotros empaquetamos el pedido.
  4. Entrega: Sale en moto o utilitario y llega el mismo día al cliente.
- Sin tecnicismos ni texto redundante. Cada etapa debe entenderse con solo mirar la imagen y leer una oración.
```

### Prompt 2: Explicación de Cómo se Calcula la Tarifa por Zonas
```markdown
Usa big-pics-little-words para ilustrar cómo se calculan las zonas tarifarias de mensajería (CABA / Zona Norte / Zona Oeste / Zona Sur).
- Representa un mapa conceptual esquemático con radios concéntricos visuales.
- Incluye etiquetas claras y concisas con tiempos estimados y requisitos de embalaje.
- Redacción simple, directa y orientada a nuevos clientes.
```

---

## 8. `html` (Router e Integrador Completo)

### Cuándo usarla
Cuando la solicitud requiera una herramienta autónoma completa, un cotizador funcional, un informe con gráficos o una landing page que combine varias necesidades sin encasillarse en una sola especialidad.

### Prompt 1: Calculadora y Cotizador de Envíos Autocontenido
```markdown
Usa la habilidad html (y apóyate en design-artifact) para crear una herramienta interactiva completa y autocontenida: "Cotizador Rápido de Envíos".

Características requeridas:
1. Formulario interactivo:
   - Selección de origen y destino (Zonas de cobertura predefinidas).
   - Tipo de paquete (Documento / Paquete hasta 2kg / Bulto hasta 10kg).
   - Velocidad de entrega (Express en 2 horas / En el día / Programado 24hs).
2. Cálculo de tarifa dinámico con desglose transparente (precio base, recargo por distancia y seguro opcional).
3. Botón para "Solicitar este envío" que pre-cargue un mensaje formateado listo para enviar por WhatsApp.
4. Código 100% autocontenido en un archivo HTML con estilos y lógica JavaScript sin librerías externas.
```

---

## Buenas Prácticas al Escribir tus Propios Prompts

1. **Especifica siempre la audiencia y el objetivo**: Indica claramente si el archivo es para uso interno del equipo técnico, para un cliente final o para un directivo.
2. **Declara el nivel de fidelidad deseado**: Si estás en una fase preliminar, pide explícitamente `html-wireframe`; si buscas evaluar acabados y sensaciones de marca, solicita `html-prototype` con `design-artifact`.
3. **Pide estados completos**: En formularios y componentes interactivos, recuerda solicitar el estado vacío (*empty state*), estado de carga (*loading*), estado exitoso y de error.
4. **Exige archivos autocontenidos**: Recuerda al agente que el código CSS y JS debe quedar dentro del mismo archivo `.html`, asegurando que puedas enviarlo o abrirlo directamente con doble clic en cualquier navegador.
