# Paso 2: Diagrama de clases – App de pedidos de la cafetería

## Clases, atributos y métodos
| Clase | Atributos | Método |
|---|---|---|
| Alumno | `-nombre: String`, `-matricula: String` | `+hacerPedido(): Pedido` |
| Pedido | `-numero: int`, `-estado: String` | `+calcularTotal(): double` |
| Producto | `-nombre: String`, `-precio: double` | `+obtenerPrecio(): double` |

Visibilidad: `+` público, `-` privado.

## Diagrama
```mermaid
classDiagram
    class Alumno {
        -String nombre
        -String matricula
        +hacerPedido() Pedido
    }

    class Pedido {
        -int numero
        -String estado
        +calcularTotal() double
    }

    class Producto {
        -String nombre
        -double precio
        +obtenerPrecio() double
    }

    Alumno "1" --> "0..*" Pedido : hace
    Pedido "0..*" --> "1..*" Producto : contiene
```

## Multiplicidad
- Un **Alumno** hace **0 o muchos** Pedidos; cada Pedido pertenece a **un** Alumno.
- Un **Pedido** contiene **uno o muchos** Productos; un Producto puede aparecer en **0 o muchos** Pedidos.
