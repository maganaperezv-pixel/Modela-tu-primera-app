# Paso 3: Diagrama de secuencia – Escenario "Hacer un pedido"

## Líneas de vida
Alumno, App y Cafetería.

## Diagrama
```mermaid
sequenceDiagram
    actor Alumno
    participant App
    participant Cafeteria as Cafetería

    Alumno->>App: 1. Selecciona productos del menú
    Alumno->>App: 2. Confirma el pedido
    App->>App: 3. Calcula el total
    App-->>Alumno: 4. Muestra resumen y total (retorno)
    Alumno->>App: 5. Paga el pedido
    App->>Cafeteria: 6. Envía el pedido
    Cafeteria-->>App: 7. Confirma recepción del pedido (retorno)
    App-->>Alumno: 8. Muestra número de pedido y estado "En preparación" (retorno)
```

## Mensajes
- **Mensajes de llamada:** 1, 2, 3, 5 y 6.
- **Mensajes de retorno (línea punteada):** 4, 7 y 8.
