# Documentación UML - Proyecto Integrador

## 1. Diagrama de Casos de Uso General

```mermaid
graph LR
    subgraph Sistema
        UC1([UC-01: Iniciar Sesión])
        UC2([UC-02: Consultar Catálogo])
        UC3([UC-03: Realizar Pedido])
    end

    Cliente((Cliente)) --> UC1
    Cliente --> UC2
    Cliente --> UC3
    Administrador((Administrador)) --> UC1


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
