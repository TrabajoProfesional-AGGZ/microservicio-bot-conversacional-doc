---
layout: default
title: Justificación tecnológica
nav_order: 3
---

# 🛠️ Justificación tecnológica

En esta sección documentamos las decisiones técnicas tomadas para la construcción del microservicio de BotIn, asegurando que cada herramienta elegida aporte valor real al desarrollo y mantenimiento del producto.

## Lenguajes y frameworks

Para dotar a BotIn de agilidad y capacidad de respuesta inmediata, la selección tecnológica priorizó la ligereza y la integración asíncrona:

* **Python:** Elegido como lenguaje base por su excelente soporte para la manipulación de cadenas, procesamiento de lenguaje y la disponibilidad de librerías maduras para bots.
* **FastAPI:** Seleccionado como el framework web encargado de exponer los webhooks y puntos de integración con el resto del sistema de SocioUnido con un rendimiento óptimo.
* **Telegram Bot API (python-telegram-bot):** Utilizado como la interfaz de comunicación principal, permitiendo gestionar de forma robusta los comandos, estados de conversación y la interacción multimedia con los usuarios.
* **SQLite / SQLAlchemy:** Utilizado para la persistencia local de estados de chat y configuraciones específicas del asistente conversacional de manera ligera.
* **Pytest y Pytest-Asyncio:** Adoptado para garantizar mediante pruebas unitarias y asíncronas que los flujos de conversación y los manejadores (*handlers*) respondan correctamente ante cualquier escenario.
* **Docker y Docker Compose:** La contenerización es indispensable en nuestra arquitectura. Nos permite aislar el bot y garantizar la paridad exacta entre entornos (desarrollo, *staging* y producción).

## Integración y despliegue continuo (CI/CD)

La implementación de pipelines de CI/CD es fundamental en el microservicio para garantizar entregas ágiles y seguras. Nos permite automatizar la ejecución de pruebas y el despliegue a los distintos entornos, reduciendo el error humano y acelerando el *time-to-market*.

## Pruebas unitarias y Code Coverage

Para asegurar la robustez y estabilidad del código, mantenemos un estándar estricto de calidad:

* Se han implementado pruebas unitarias para validar la lógica de los comandos y la correcta comunicación con los servicios del club.
* Mantenemos un **estricto nivel de Code Coverage** (cobertura de código) validado automáticamente en cada Pull Request mediante nuestro pipeline.

## Documentación integral

Utilizamos **JustTheDocs** para mantener esta documentación viva, versionada junto con el código y fácilmente accesible para cualquier miembro del equipo. Esto centraliza el conocimiento y reduce los cuellos de botella en la comunicación.
