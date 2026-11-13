# Especificación de Requerimientos de Software (SRS) - v1.0
**Proyecto:** Tap Tap Marisco  
**Equipo:** Matheo Jaramillo Cardenas - Victor Manuel Magaña Perez  
**Versión:** 1.0  
**Fecha:** Noviembre 2026  

---

## 1. Introducción

### 1.1 Propósito
El propósito de este documento es definir de manera formal, clara y verificable los requerimientos funcionales y no funcionales para el desarrollo de la primera versión jugable de un videojuego móvil 2D enfocado en la protección de ecosistemas marinos y la regulación pesquera. Este documento servirá como guía técnica para el equipo de desarrollo y como instrumento de evaluación para el docente.

### 1.2 Alcance
El sistema consiste en una aplicación de videojuego 2D para dispositivos móviles con sistema operativo Android. El jugador asumirá el rol de gestor ambiental marino, debiendo identificar y sancionar embarcaciones de pesca ilegal, delimitar Áreas Marinas Protegidas (AMP) mediante gestos táctiles y equilibrar la salud del ecosistema antes de que finalice el tiempo de cada nivel.

**Fuera del alcance de la v1.0:**
* Modo multijugador en línea o tablas de clasificación globales en la nube.
* Publicación comercial en Google Play Store o compras dentro de la aplicación (*in-app purchases*).
* Compatibilidad con sistemas operativos distintos a Android (como iOS o escritorio).

### 1.3 Glosario de términos
* **AMP (Área Marina Protegida):** Zona temporal delimitada por el jugador en el mapa mediante un gesto táctil donde se restringe la actividad pesquera para permitir la regeneración de especies.
* **Barco Ilegal:** Entidad móvil dentro del mapa, diferenciada visualmente (por ejemplo, resaltada en color rojo), que extrae recursos sin autorización y reduce el porcentaje de salud del ecosistema.
* **Máximo Rendimiento Sostenible (MRS):** Indicador objetivo del nivel, representado al alcanzar el 100% de la barra de salud del ecosistema marino.
* **APK / AAB:** Formatos de empaquetado de aplicaciones ejecutables e instalables en el sistema operativo Android (*Android Package* / *Android App Bundle*).

---

## 2. Descripción General

### 2.1 Usuarios del sistema
* **Jugador (Usuario Final):** Personas con conocimientos básicos de uso de dispositivos móviles táctiles (teléfonos inteligentes o tabletas). Interactúan con el sistema mediante toques simples (*tap*) y arrastres (*drag*) en pantalla sin requerir experiencia previa en simuladores complejos.

### 2.2 Restricciones
* **Plataforma destino:** El juego debe ejecutarse exclusivamente en dispositivos con sistema operativo Android.
* **Interfaz de entrada:** La interacción está restringida exclusivamente a controles táctiles en pantalla (sin soporte obligatorio para teclado físico o mandos externos).
* **Rendimiento gráfico:** El apartado visual debe limitarse a recursos 2D optimizados para garantizar compatibilidad con dispositivos Android de gama baja y media.

### 2.3 Supuestos y dependencias
* Se asume que el dispositivo móvil del usuario cuenta con pantalla táctil funcional y una versión de Android compatible con el paquete compilado (APK/AAB).
* El funcionamiento principal del juego no depende de una conexión permanente a Internet una vez instalada la aplicación.

---

## 3. Requerimientos Específicos

### 3.1 Requerimientos Funcionales

#### RF-01: Sanción y eliminación de barcos ilegales
* **Descripción:** El sistema deberá detectar cuando el usuario toque un barco clasificado como ilegal (identificado visualmente en color rojo), eliminarlo inmediatamente de la escena de juego e incrementar el marcador de puntos del jugador en una cantidad fija definida por el nivel.
* **Prioridad:** Alta
* **Criterio de aceptación:** Dado que existe al menos un barco ilegal activo desplazándose en el mapa, cuando el usuario presiona sobre su área de colisión táctil, entonces el barco desaparece de la pantalla en menos de 0.2 segundos y el puntaje visible aumenta.
* **Checklist de calidad:** [x] Correcto | [x] No ambiguo | [x] Completo | [x] Consistente | [x] Factible | [x] Verificable

#### RF-02: Trazado táctil de Áreas Marinas Protegidas (AMP)
* **Descripción:** El sistema deberá permitir al usuario mantener presionado y arrastrar el dedo sobre el mapa marítimo para dibujar y activar una zona delimitada como "Área Marina Protegida" de duración temporal.
* **Prioridad:** Alta
* **Criterio de aceptación:** Dado que una partida está en curso y el jugador dispone de capacidad para crear reservas, cuando mantiene presionada la pantalla y arrastra el dedo formando un área, entonces se renderiza visualmente la zona protegida durante un tiempo determinado antes de expirar.
* **Checklist de calidad:** [x] Correcto | [x] No ambiguo | [x] Completo | [x] Consistente | [x] Factible | [x] Verificable

#### RF-03: Evaluación de condición de victoria por Máximo Rendimiento Sostenible
* **Descripción:** El sistema deberá monitorear el estado del ecosistema y declarar la victoria del nivel en el instante en que la barra de "Máximo Rendimiento Sostenible" alcance el 100%, siempre y cuando el temporizador del nivel sea mayor a cero segundos.
* **Prioridad:** Alta
* **Criterio de aceptación:** Dado que el temporizador del nivel aún cuenta con tiempo restante (> 0 s), cuando el indicador del ecosistema llega al 100%, entonces el juego detiene la partida y despliega la pantalla de nivel completado.
* **Checklist de calidad:** [x] Correcto | [x] No ambiguo | [x] Completo | [x] Consistente | [x] Factible | [x] Verificable

#### RF-04: Generación y desplazamiento de embarcaciones en el mapa
* **Descripción:** El sistema deberá generar periódicamente embarcaciones legales e ilegales en los bordes del escenario marítimo, desplazándolas a través del mapa según rutas predefinidas durante el transcurso del nivel.
* **Prioridad:** Media
* **Criterio de aceptación:** Dado que un nivel ha iniciado, cuando transcurren los intervalos de aparición configurados, entonces aparecen barcos en pantalla con su identificador visual correspondiente (legal o ilegal) moviéndose de forma continua por el área de juego.
* **Checklist de calidad:** [x] Correcto | [x] No ambiguo | [x] Completo | [x] Consistente | [x] Factible | [x] Verificable

#### RF-05: Actualización dinámica de la barra de salud del ecosistema
* **Descripción:** El sistema deberá incrementar el porcentaje de la barra de ecosistema cuando existan Áreas Marinas Protegidas activas y decrementarlo proporcionalmente por cada barco ilegal que permanezca operando sin ser sancionado.
* **Prioridad:** Media
* **Criterio de aceptación:** Dado que la partida está activa, cuando un barco ilegal permanece en el mapa sin ser eliminado, entonces el porcentaje de la barra de ecosistema disminuye visiblemente cada segundo; y cuando se activa una AMP, dicho porcentaje aumenta progresivamente.
* **Checklist de calidad:** [x] Correcto | [x] No ambiguo | [x] Completo | [x] Consistente | [x] Factible | [x] Verificable

---

### 3.2 Requerimientos No Funcionales

#### RNF-01: Compilación y empaquetado para Android
* **Descripción:** El proyecto deberá poder compilarse sin errores en formatos instalables APK o AAB compatibles con el sistema operativo Android.
* **Prioridad:** Alta
* **Criterio de aceptación:** El archivo APK generado se instala correctamente en un dispositivo físico o emulador Android y ejecuta el menú principal y el primer nivel sin cierres inesperados (*crashes*).
* **Checklist de calidad:** [x] Correcto | [x] No ambiguo | [x] Completo | [x] Consistente | [x] Factible | [x] Verificable

#### RNF-02: Adaptabilidad visual multipantalla (Responsive UI)
* **Descripción:** La interfaz de usuario (HUD, barras de progreso, temporizador y botones) deberá escalar y reubicarse dinámicamente para adaptarse a distintas relaciones de aspecto y resoluciones de teléfonos y tabletas Android.
* **Prioridad:** Media
* **Criterio de aceptación:** Al ejecutar el juego en al menos dos resoluciones distintas (por ejemplo, relación de aspecto 16:9 y 20:9), todos los elementos de la interfaz permanecen visibles, legibles y sin recortes ni superposiciones.
* **Checklist de calidad:** [x] Correcto | [x] No ambiguo | [x] Completo | [x] Consistente | [x] Factible | [x] Verificable

#### RNF-03: Optimización de recursos gráficos 2D y consumo energético
* **Descripción:** El juego deberá utilizar sprites e interfaces 2D ligeros, manteniendo una tasa estable de al menos 30 cuadros por segundo (FPS) para prevenir el sobrecalentamiento del dispositivo y el consumo excesivo de batería en sesiones continuas.
* **Prioridad:** Media
* **Criterio de aceptación:** Durante una prueba de ejecución continua de 15 minutos en un dispositivo Android de gama media, la aplicación mantiene un rendimiento fluido (>= 30 FPS) y un uso de memoria RAM dentro de los límites estándar del motor gráfico.
* **Checklist de calidad:** [x] Correcto | [x] No ambiguo | [x] Completo | [x] Consistente | [x] Factible | [x] Verificable
