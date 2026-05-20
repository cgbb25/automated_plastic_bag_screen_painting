# Simulación de Sistema Automatizado para Estampado por Serigrafía

## Descripción general

Este proyecto consiste en la simulación de un sistema automatizado para un proceso de estampado por serigrafía sobre bolsas plásticas, utilizando **TIA Portal** para la programación PLC y **Factory I/O** para la representación virtual del proceso.

El sistema simula una estación de trabajo donde una banda transportadora posiciona las bolsas frente a un mecanismo de impresión. Una vez detectada la bolsa, la banda se detiene, se posiciona el cabezal de impresión serigráfica y se acciona el mecanismo de estampado mediante actuadores neumáticos simulados.

El proyecto fue desarrollado como una prueba conceptual de automatización industrial, considerando tanto el modo automático como el modo manual de operación.

---

## Objetivo del proyecto

Diseñar y simular la lógica de control de un proceso automatizado de estampado por serigrafía, integrando sensores, actuadores, banda transportadora, conteo de unidades y modos de operación manual/automático.

---

## Herramientas utilizadas

- **TIA Portal**: programación de la lógica PLC.
- **Factory I/O**: simulación visual del proceso industrial.
- **Diagramas técnicos**: representación estimada del sistema eléctrico, señales de control y arquitectura del proceso.

---

## Descripción del proceso simulado

La secuencia principal del sistema es la siguiente:

1. La banda transportadora desplaza las bolsas plásticas hacia la estación de estampado.
2. Un sensor de presencia detecta la llegada de una bolsa a la posición de trabajo.
3. La banda transportadora se detiene.
4. Un cilindro neumático vertical posiciona el cabezal de impresión serigráfica sobre la bolsa.
5. Un cilindro neumático horizontal acciona el rasero o mecanismo de impresión.
6. El cilindro horizontal retorna a su posición inicial.
7. El cilindro vertical se retrae, retirando el cabezal de impresión.
8. La banda transportadora vuelve a activarse.
9. La bolsa avanza hacia una zona representada como túnel de secado.
10. El ciclo se repite al detectarse una nueva bolsa.

---

## Funcionalidades implementadas

- Control automático de la secuencia de estampado.
- Modo manual para accionamiento individual de los actuadores.
- Arranque y parada del sistema.
- Detección de bolsas mediante sensores de presencia.
- Detención automática de la banda en la posición de estampado.
- Control secuencial de cilindros neumáticos de doble efecto.
- Conteo de bolsas procesadas.
- Reinicio del contador mediante pulsador.
- Representación visual de una zona de secado dentro de la simulación.

---

## Componentes representados en la simulación

| Elemento simulado | Posible equivalente físico |
|---|---|
| Banda transportadora | Faja transportadora con motorreductor |
| Sensor de presencia | Sensor fotoeléctrico difuso o de barrera |
| Cilindro vertical | Cilindro neumático de doble efecto para posicionamiento del cabezal |
| Cilindro horizontal | Cilindro neumático de doble efecto para accionamiento del rasero |
| Cabezal de impresión | Cabezal de impresión serigráfica o conjunto porta-malla |
| Mecanismo de impresión | Rasero o escobilla serigráfica |
| Controlador | PLC Siemens S7-1200 o equivalente |
| Actuación neumática | Electroválvulas 5/2, unidad FRL y compresor |
| Interfaz de operación | Pulsadores, selector manual/automático y HMI básica |

---

## Mapeo general de entradas y salidas

| Tipo | Señal | Descripción |
|---|---|---|
| Entrada digital | I0.0 | Pulsador de inicio |
| Entrada digital | I0.1 | Pulsador de parada |
| Entrada digital | I0.2 | Sensor de presencia de bolsa en estación de estampado |
| Entrada digital | I0.3 | Sensor de conteo de bolsas |
| Entrada digital | I0.4 | Selector de modo manual/automático |
| Entrada digital | I0.5 | Reset de contador |
| Salida digital | Q0.0 | Motor de banda transportadora |
| Salida digital | Q0.1 | Extensión del cilindro vertical |
| Salida digital | Q0.2 | Retracción del cilindro vertical |
| Salida digital | Q0.3 | Extensión del cilindro horizontal |
| Salida digital | Q0.4 | Retracción del cilindro horizontal |

> Nota: El mapeo de señales puede adaptarse según el PLC, módulos de expansión, sensores y actuadores seleccionados para una implementación física.

---

## Modos de operación

### Modo automático

En modo automático, el sistema ejecuta la secuencia completa de estampado sin intervención del operador, desde la detección de la bolsa hasta el retorno de los actuadores y reinicio de la banda transportadora.

### Modo manual

En modo manual, el operador puede accionar individualmente los elementos principales del sistema, como la banda transportadora y los cilindros neumáticos. Este modo puede utilizarse para pruebas, mantenimiento o verificación de funcionamiento.

---

## Posible implementación física

Aunque el proyecto fue desarrollado en un entorno de simulación, la lógica de control puede trasladarse a una implementación física mediante componentes industriales reales.

Una posible arquitectura física incluiría:

- PLC Siemens S7-1200 o equivalente.
- Fuente de alimentación de 24 VDC.
- Sensores fotoeléctricos para detección y conteo de bolsas.
- Motorreductor para la banda transportadora.
- Cilindros neumáticos de doble efecto.
- Electroválvulas 5/2 para control de cilindros.
- Unidad de mantenimiento neumático FRL.
- Pulsadores de inicio, parada y reset.
- Selector de modo manual/automático.
- HMI básica para visualización de estado y conteo.

---

## Evidencias del proyecto

El repositorio incluye o puede incluir:

- Capturas de la simulación en Factory I/O.
- Capturas de la lógica programada en TIA Portal.
- Video demostrativo del funcionamiento.
- Archivo del programa PLC.
- Mapeo de entradas y salidas.
- Diagrama funcional del proceso.
- Diagrama eléctrico estimado.
- Propuesta básica de componentes reales.

---

## Resultados obtenidos

Se obtuvo una simulación funcional del proceso de estampado por serigrafía, permitiendo validar la lógica secuencial de operación, el control de actuadores, la detección de bolsas, el conteo de unidades y la alternancia entre modo automático y manual.

El proyecto demuestra una aproximación práctica al diseño de sistemas automatizados, desde la definición de la secuencia de proceso hasta la programación PLC y la simulación virtual de una posible solución industrial.

---

## Limitaciones y mejoras futuras

El proyecto representa una simulación conceptual y no una implementación física completa. Algunas mejoras futuras podrían incluir:

- Diseño detallado del circuito eléctrico de potencia y control.
- Desarrollo de un esquema neumático más completo.
- Integración de una HMI para visualización de estados, alarmas y conteo.
- Incorporación de condiciones de seguridad, como parada de emergencia y enclavamientos adicionales.
- Selección técnica más detallada de sensores, actuadores y componentes industriales.
- Implementación física a escala mediante PLC real, sensores y actuadores neumáticos.

---

## Autor

Proyecto desarrollado por: **Carlos Gabriel Baltodano Beltrán**

Área de interés: Automatización industrial, programación PLC, simulación de procesos y sistemas mecatrónicos.
