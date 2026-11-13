# Investigación: Especificación de Requerimientos de Software (SRS / ERS)

## 1. ¿Qué es un SRS/ERS y qué problemas evita?
Una **Especificación de Requerimientos de Software (SRS)** —o ERS en español— es un documento técnico que establece de forma formal, completa y estructurada qué debe hacer un sistema de software y bajo qué restricciones operará, sin entrar en detalles de diseño o implementación (IEEE, 1998). Actúa como un contrato entre los interesados (*stakeholders*) y el equipo de desarrollo.

**Problemas que evita:**
* **Corrupción del alcance (*Scope Creep*):** Impide que se agreguen funciones no acordadas a mitad del desarrollo sin evaluar su impacto.
* **Ambigüedad y retrabajo:** Evita malentendidos entre lo que el cliente pidió y lo que el programador interpretó, reduciendo costos de corrección en etapas tardías (Pressman & Maxim, 2021).
* **Falta de criterios de validación:** Permite que el equipo de pruebas (*QA*) verifique objetivamente si el producto final cumple con lo pactado.

## 2. Estructura según el estándar IEEE 830
El estándar **IEEE 830-1998** (actualizado posteriormente por la norma ISO/IEC/IEEE 29148) organiza el documento en tres grandes secciones principales:

1. **Introducción:** Define el **propósito** del documento y su audiencia; el **alcance** del producto (qué hará y qué no); las **definiciones, acrónimos y abreviaturas**; las **referencias** a otros documentos; y la **visión general** de cómo está organizado el resto del SRS.
2. **Descripción General:** Contextualiza el producto sin detallar requisitos técnicos aún. Incluye la **perspectiva del producto** (si es independiente o parte de un sistema mayor), las **funciones del producto** a alto nivel, las **características de los usuarios** (roles y nivel técnico), las **restricciones** (tecnológicas, legales o de hardware), y los **supuestos y dependencias**.
3. **Requerimientos Específicos:** Es el núcleo técnico del documento. Detalla los **requerimientos de interfaces externas** (usuario, hardware, software y comunicaciones), los **requerimientos funcionales** (entradas, procesamiento y salidas esperadas) y los **requerimientos no funcionales** (rendimiento, seguridad, disponibilidad, portabilidad y atributos de calidad).

## 3. Características de un buen requerimiento
Según IEEE (1998) y Sommerville (2011), todo requerimiento debe ser: **correcto, no ambiguo, completo, consistente, clasificado por importancia/estabilidad, verificable, modificable y trazable**.

* **Ejemplo Malo (ambiguo y no verificable):** *"El sistema debe ser rápido al buscar productos y tener una interfaz amigable."* (No define qué significa "rápido" ni cómo medir "amigable").
* **Ejemplo Bueno (no ambiguo y verificable):** *"El sistema deberá mostrar los resultados de búsqueda de productos en un tiempo máximo de 2 segundos para catálogos de hasta 10,000 registros bajo una conexión estándar de 10 Mbps."*

## 4. Plantillas, herramientas y elección para el equipo
* **Herramientas para redactar y versionar:** Markdown en repositorios Git (GitHub/GitLab) para control de versiones colaborativo, Notion/Confluence para documentación viva, y herramientas especializadas como Jira o ReqView para trazabilidad.
* **Plantillas existentes:** Plantilla clásica **IEEE 830**, plantilla **ISO/IEC/IEEE 29148**, y plantillas ágiles adaptadas a Markdown (como las de *Volere* o repositorios comunitarios tipo *brikerman/SRS-Template*).

**Plantilla elegida y justificación:**
Usaremos una **adaptación en Markdown del estándar IEEE 830** alojada directamente en `/docs/SRS.md` dentro de nuestro repositorio de GitHub. Se eligió porque su estructura de tres secciones cubre exactamente lo solicitado en la rúbrica, el formato Markdown permite revisar cambios mediante *Pull Requests* y *commits* claros, y facilita enlazar cada requerimiento directamente con los *Issues* de GitHub Projects.

---

## Referencias (APA 7)
* Institute of Electrical and Electronics Engineers. (1998). *IEEE Recommended Practice for Software Requirements Specifications* (IEEE Std 830-1998). IEEE Computer Society. https://doi.org/10.1109/IEEESTD.1998.88286
* Pressman, R. S., & Maxim, B. R. (2021). *Ingeniería del software: Un enfoque práctico* (9.ª ed.). McGraw-Hill Education.
* Sommerville, I. (2011). *Ingeniería de software* (9.ª ed.). Pearson Educación.

## Declaración de uso de IA Generativa
Se utilizó IA generativa como apoyo para sintetizar la estructura comparativa del estándar IEEE 830, estructurar el formato Markdown del documento y redactar ejemplos contrastados de requerimientos. Toda la información conceptual y las citas bibliográficas fueron verificadas contra los textos de Sommerville (2011), Pressman & Maxim (2021) y la documentación oficial del estándar IEEE 830-1998.
