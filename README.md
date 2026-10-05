# Optimizador Logístico de Cisternas de Agua SEDAPAL — Equipo 03

**Problema y quién lo sufre.** Las familias en zonas periféricas y entidades vulnerables (hospitales/colegios) en Lima pasan demasiados días sin abastecimiento durante los cortes masivos de agua debido a una distribución logística deficiente.
**Modo base.** Actualmente, SEDAPAL asigna los camiones cisterna mediante una regla de cola simple (FIFO): se envía el agua en el estricto orden en que ingresan las llamadas, ignorando la densidad poblacional y la urgencia.

**Técnicas comparadas.** 
Parte 1: Se implementó un **Agente Reflejo Simple** (que prioriza hospitales y luego zonas con más días sin agua) y un **Agente Basado en Utilidad** (que evalúa todas las peticiones con una ecuación que pondera vulnerabilidad, población, días de sequía y distancia logística). 


| Técnica | Métrica (cuál) | Tiempo | Corridas |
|---------|----------------|--------|----------|
| Base (FIFO) | % Críticas a tiempo (43%) / Personas (30,569) / Km (1075) | 1200 ms | 100 peticiones |
| Reflejo Simple | % Críticas a tiempo (57%) / Personas (31,051) / Km (1078) | 1400 ms | 100 peticiones |
| Utilidad | % Críticas a tiempo (96%) / Personas (37,721) / Km (1051) | 1650 ms | 100 peticiones |

**Cómo ejecutarlo.** 
Enlace público: `https://jefersonpaucarcaja.github.io/AI-2026-02-Equipo08-LoshDosh/index.html`
Para correrlo en local: Clonar el repositorio y abrir directamente el archivo `index.html` en cualquier navegador moderno (no requiere servidor local ni instalación de dependencias).

**Uso de IA.** 
Se empleó IA generativa (Gemini/Claude) como asistente para generar la estructura inicial del Game Loop (`requestAnimationFrame` en JavaScript), la compresión/minificación del CSS para optimizar la carga del archivo único, y la sintaxis de configuración de la librería Chart.js. 
*Qué modificamos:* Reescribimos la función de utilidad matemática `score()`, ajustamos los pesos logísticos, programamos la lógica de renderizado del Canvas para el mapa y calibramos las condiciones de "inanición" (starvation) de la cola de peticiones.

**Roles.** 
*   **Jeferson Paucarcaja:** Configuración del repositorio base, maquetación HTML/CSS (UI/UX) y programación de la clase lógica del Agente Base (FIFO).
*   **Gabriel Marengo:** Implementación del motor gráfico Canvas 2D, coordenadas de distribución de los puntos de acopio (Norte, Sur, Este, Oeste) y animaciones de rutas.
*   **Manuel Pérez:** Diseño de la función de utilidad matemática, programación del Agente Inteligente y vinculación de los Sliders de pesos dinámicos en la interfaz.
*   **Rodrigo Villanueva:** Integración del módulo de Benchmark automático masivo, despliegue de gráficas comparativas con Chart.js y redacción de documentación técnica.
