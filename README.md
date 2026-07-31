# Entrega Final - IA Automation

## Descripción

Ecosistema de automatización IA autónomo para la atención de consultas de una tienda de indumentaria.

El sistema recibe correos de clientes, registra la información en Airtable, clasifica la consulta con OpenAI, genera una respuesta sugerida, solicita aprobación humana y responde dentro del mismo hilo de Gmail.

## Objetivo

Automatizar la gestión de consultas comerciales sin perder control humano, trazabilidad ni seguridad.

## Arquitectura

El proyecto está compuesto por dos escenarios en Make:

### Escenario principal

1. Gmail detecta un correo nuevo.
2. Airtable crea o actualiza el cliente.
3. Airtable busca el registro del cliente.
4. OpenAI clasifica la consulta y genera una respuesta sugerida.
5. Airtable guarda la consulta.
6. Gmail notifica al revisor.
7. Si OpenAI falla, se registra el error y se ejecutan reintentos.

### Escenario HITL

1. Airtable detecta una consulta aprobada.
2. Gmail responde dentro del hilo original.
3. Airtable actualiza el estado a `Respondido`.

## Tecnologías utilizadas

- Make
- Airtable
- OpenAI GPT-4.1 mini
- Gmail
- GitHub
- Human-in-the-Loop

## Funcionalidades implementadas

- Registro de clientes
- Clasificación por categoría
- Asignación de prioridad
- Generación de respuesta sugerida
- Aprobación humana
- Respuesta automática por Gmail
- Manejo de errores
- Reintentos automáticos
- Dashboard público
- Trazabilidad de consultas

## Estructura del repositorio

- `01-Documentacion`: documentos del proyecto
- `02-Blueprint-make`: escenarios exportados desde Make
- `03-Capturas-evidencias`: pruebas de funcionamiento
- `04-Enlaces`: enlaces públicos del sistema

## Enlaces públicos

### Base de Airtable en modo lectura

https://airtable.com/applYl4pSi0updjZY/shrrt2XMKCP9v2n6U

### Dashboard público de consultas

https://airtable.com/applYl4pSi0updjZY/shrzTtjrsGLbQDLsF
### Dashboard público de errores

https://airtable.com/applYl4pSi0updjZY/shr8O86ilPUK6968W
### Video demostrativo

[PEGAR AQUÍ EL ENLACE DEL VIDEO]

## Pruebas realizadas

Se realizaron cinco casos de prueba:

1. Consulta mayorista
2. Consulta urgente de ventas
3. Consulta de stock
4. Cambio o devolución
5. Consulta de envío

También se probó un camino infeliz relacionado con una categoría inexistente en Airtable. El error fue corregido y la ejecución posterior finalizó correctamente.

## Seguridad y resiliencia

- Conexiones OAuth
- Claves API protegidas
- Minimización de datos
- Aprobación humana antes del envío
- Registro de errores
- Reintentos automáticos
- Acceso público en modo lectura

## Autora

Celeste Pereyra
