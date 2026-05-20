# Simulación de Sistema Automatizado para Estampado por Serigrafía

## Descripción

Este proyecto consiste en la simulación de un proceso automatizado de estampado por serigrafía sobre bolsas plásticas, utilizando **TIA Portal** para la programación PLC y **Factory I/O** para la simulación del proceso.

El sistema representa una estación donde una banda transportadora posiciona bolsas frente a un mecanismo de estampado. Al detectar una bolsa, la banda se detiene, se acciona un cilindro vertical para posicionar el cabezal de impresión y luego un cilindro horizontal realiza el movimiento de estampado. Finalmente, los actuadores retornan y la banda continúa su recorrido hacia una zona representada como túnel de secado.

El proyecto fue desarrollado como una simulación conceptual orientada a una posible implementación física mediante PLC, sensores, actuadores neumáticos y elementos de control industrial.

---

## Objetivo

Simular la lógica de control de un proceso de estampado por serigrafía, considerando operación automática y manual, detección de bolsas, control secuencial de actuadores y conteo de unidades procesadas.

---

## Herramientas utilizadas

- **TIA Portal**: programación de la lógica PLC.
- **Factory I/O**: simulación del proceso industrial.
- **Excel**: documentación de variables de entrada/salida y memoria.
- **Diagramas técnicos**: representación estimada del proceso y arquitectura de control.

---

## Secuencia de funcionamiento

1. La banda transportadora desplaza las bolsas hacia la estación de estampado.
2. Un sensor de presencia detecta la bolsa en posición.
3. La banda transportadora se detiene.
4. Se acciona el cilindro vertical de simple efecto para posicionar el cabezal de impresión.
5. Se acciona el cilindro horizontal de simple efecto para realizar el movimiento de estampado.
6. El cilindro horizontal retorna a su posición inicial.
7. El cilindro vertical retorna a su posición inicial.
8. La banda transportadora vuelve a activarse.
9. La bolsa avanza hacia la zona de secado.
10. El ciclo se repite con la siguiente bolsa.

---

## Funcionalidades implementadas

- Modo automático de operación.
- Modo manual para pruebas o accionamiento individual.
- Arranque y parada del sistema.
- Detección de bolsa en posición de estampado.
- Parada de emergencia.
- Control secuencial de banda transportadora y cilindros neumáticos.
- Uso de finales de carrera para verificar posición extendida y retraída de cada cilindro.
- Conteo de bolsas procesadas.
- Reinicio del contador mediante pulsador.
- Representación visual de una zona de secado.

---

## Entradas y salidas principales

El detalle completo de las variables de entrada y salida se encuentra documentado en un archivo Excel incluido en el proyecto. De forma general, las señales principales consideradas son:

### Entradas principales

| Señal | Descripción |
|---|---|
| Pulsador de inicio | Activa el sistema |
| Pulsador de parada | Detiene el sistema |
| Selector manual/automático | Selecciona el modo de operación |
| Sensor de presencia | Detecta la bolsa en posición de estampado |
| Sensor de conteo | Registra bolsas procesadas |
| Reset de contador | Reinicia el conteo |
| Parada de emergencia | Detiene el proceso y no permite su reactivación |
| Final de carrera cilindro vertical retraído | Confirma posición inicial del cilindro vertical |
| Final de carrera cilindro vertical extendido | Confirma posición de trabajo del cilindro vertical |
| Final de carrera cilindro horizontal retraído | Confirma posición inicial del cilindro horizontal |
| Final de carrera cilindro horizontal extendido | Confirma posición de estampado del cilindro horizontal |

### Salidas principales

| Señal | Descripción |
|---|---|
| Motor de banda transportadora | Controla el avance de las bolsas |
| Activación de cilindro vertical | Posiciona el cabezal de impresión |
| Activación de cilindro horizontal | Ejecuta el movimiento de estampado |
| Indicadores de estado | Señalización visual del proceso, según configuración |

---

## Componentes representados

La lógica puede trasladarse a una implementación física mediante un PLC, sensores de presencia, finales de carrera, motorreductor para la banda transportadora, cilindros neumáticos de simple efecto y electroválvulas, siempre revisando las especificaciones técnicas pertinentes y las señales eléctricas con las que se energizan.
La simulación permite validar la secuencia de operación antes de una posible construcción del sistema real, reduciendo errores en la lógica de control y facilitando la definición de entradas, salidas y condiciones de funcionamiento.

| Elemento simulado | Posible equivalente físico |
|---|---|
| Banda transportadora | Faja transportadora con motorreductor |
| Sensor de presencia | Sensor fotoeléctrico |
| Cilindro vertical de simple efecto | Cilindro neumático para posicionamiento del cabezal |
| Cilindro horizontal de simple efecto | Cilindro neumático para accionamiento del rasero |
| Finales de carrera | Sensores magnéticos o mecánicos de posición |
| Controlador | PLC Siemens S7-1200 o equivalente |
| Actuación neumática | Electroválvulas, unidad FRL y compresor |
| Interfaz de operación | Pulsadores, selector manual/automático e indicadores |

---

## Evidencias del proyecto

Se adjunta:

- Archivo de programación PLC.
- Capturas de la simulación.
- Video demostrativo de la simulación.
- Excel con detalle de entradas y salidas.
- Diagrama funcional del proceso.
- Diagrama eléctrico estimado.

---

**Autor: Carlos Gabriel Baltodano Beltrán**
