# Documentación UML - Módulo del Proyecto

## Diagrama de Clases

```mermaid
classDiagram
    class Usuario {
        +string nombre
        +string correo
        +login()
    }

    class Producto {
        +string nombre
        +float precio
    }

    class Pedido {
        +int id
        +float total
    }

    Usuario "1" -- "*" Pedido : realiza
    Pedido "*" -- "*" Producto : contiene

classDiagram
    class Usuario {
        +string nombre
        +string correo
        +login()
    }

    class Producto {
        +string nombre
        +float precio
    }

    class Pedido {
        +int id
        +float total
    }

    Usuario "1" -- "*" Pedido : realiza
    Pedido "*" -- "*" Producto : contiene
