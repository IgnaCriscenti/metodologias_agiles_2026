# Ejercicio Nro: 15

## Enunciado
Generar un plan de trabajo basado en SCRUM para resolver la siguiente tarea:

**Objetivo:** El objetivo de este ejercicio es que los alumnos universitarios practiquen la creación de historias de usuarios para un sistema informático de presupuesto de construcción de galpones, utilizando la metodología ágil.

**Descripción del ejercicio:**

1. Los alumnos deberán formar equipos de trabajo, de preferencia de 3 a 5 personas por equipo.
2. Cada equipo deberá seleccionar la temática de construcción de galpones para su sistema informático de presupuesto.
3. Los equipos deberán generar al menos tres historias de usuario para su sistema, basadas en la temática seleccionada. Cada historia de usuario debe incluir un título y una descripción que contenga los criterios de aceptación.
4. Las historias de usuario deben estar enfocadas en las funcionalidades y características del sistema informático, considerando aspectos como la creación de presupuestos detallados, seguimiento del presupuesto durante la construcción, inclusión de etapas, generación de informes, entre otros.
5. Los equipos deben asegurarse de que las historias de usuario sean claras, concisas y comprensibles, siguiendo las buenas prácticas de redacción de historias ágiles.
6. Al finalizar, cada equipo deberá presentar sus historias de usuario al resto de la clase, explicando el contexto de su sistema y los criterios de aceptación de cada historia.
7. Se fomenta el intercambio de ideas y la retroalimentación constructiva entre los equipos durante las presentaciones.

**Nota:** Los equipos pueden utilizar ejemplos y situaciones hipotéticas para desarrollar las historias de usuario, considerando las necesidades y requisitos típicos de un sistema de presupuesto de construcción de galpones. Además, se recomienda utilizar herramientas como tarjetas o post-its para escribir y visualizar las historias de usuario durante el ejercicio.

## Resolución
Para resolver el ejercicio lo podemos dividir en 5 etapas:
1. Requerimientos
2. Backlog
3. Refinamiento del backlog
4. Puntuarlo (velocidad)
5. Planificación (el desarrollo)

### Etapa 1: Requerimientos
Participantes: Cliente (dueño de la constructora de galpones) y el equipo de desarrollo/analista que levanta los requisitos.
Herramienta: Historias de Usuario (User Stories).

#### Historia de usuario 1: Creación de Presupuesto Detallado
**Como** contratista o encargado de ventas de la constructora,
**Quiero** ingresar las dimensiones del galpón (ancho, largo, alto) y seleccionar los materiales (tipo de chapa, perfiles, portones),
**Para** generar un presupuesto automatizado con el desglose detallado de costos para el cliente.

Criterios de Aceptación:

+ Escenario 1 (Cálculo exitoso): Dado que el usuario completa todos los campos de medidas con valores positivos y selecciona los materiales, cuando presiona "Calcular", el sistema debe mostrar en pantalla el costo de materiales, mano de obra estimada y el total general.

+ Escenario 2 (Validación de datos vacíos): Dado que el usuario deja un campo obligatorio en blanco, cuando intenta calcular, el sistema debe bloquear la acción y mostrar un mensaje de error indicando qué campo falta completar.

#### Historia de usuario 2: Seguimiento de Presupuesto por Etapas
**Como** director de obra o jefe de proyecto,
**Quiero** dividir el presupuesto en etapas cronológicas (ej: Cimentación, Estructura, Techado) y cargar los gastos reales a medida que avanza la construcción,
**Para** controlar en tiempo real si nos estamos desviando del presupuesto original planificado.

Criterios de Aceptación:

+ Escenario 1 (Asignación a etapas): Dado que existe un presupuesto aprobado, cuando el usuario ingresa a la sección de "Seguimiento", debe poder crear al menos 3 etapas distintas y asignar un monto estimado a cada una.

+ Escenario 2 (Alerta de desvío): Dado que el gasto real cargado en una etapa supera el monto presupuestado originalmente para esa misma etapa, el sistema debe resaltar el saldo en color rojo y emitir una alerta visual de "Presupuesto Excedido".

#### Historia de usuario 3: Generación de Informes de Costos
**Como** gerente o administrador de la constructora,
**Quiero** exportar un informe o reporte visual de los costos totales y desvíos de una obra,
**Para** analizar la rentabilidad del proyecto y presentárselo a la dirección.

Criterios de Aceptación:

+ Escenario 1 (Exportación a PDF): Dado que una obra está en curso o finalizada, cuando el usuario hace clic en "Generar Informe PDF", el sistema debe descargar un archivo limpio y legible con gráficos de barra que comparen el presupuesto estimado vs. el gasto real.

+ Escenario 2 (Filtro por estado): Dado que el usuario está en el panel de informes, debe poder filtrar la búsqueda de proyectos por "En proceso", "Finalizados" o "Iniciados" antes de exportar el reporte.


### Etapa 2: Backlog
Participantes: Cliente, Product Owner (PO) y el Analista.

Proceso: En esta fase, el PO y el Analista toman todos los requerimientos y las Historias de Usuario (HU) nacidas en la etapa anterior y las vuelcan en una lista única y centralizada llamada Product Backlog (Pila del Producto). El Cliente participa validando que no se haya quedado afuera ninguna necesidad del negocio. Esta lista se ordena de forma descendente, ubicando arriba de todo lo que es más crítico para empezar a trabajar.

Nuestro Product Backlog ordenado para el sistema de galpones:

+ HU01: Creación de Presupuesto Detallado (Prioridad Alta: Sin presupuesto no se puede iniciar el negocio).

+ HU02: Seguimiento de Presupuesto por Etapas (Prioridad Media: Es necesario para cuando la obra ya arrancó).

+ HU03: Generación de Informes de Costos (Prioridad Baja/Complementaria: Es la herramienta de cierre y análisis gerencial).

### Etapa 3: Refinamiento del backlog
Participantes: Product Owner (PO), Analista y el Equipo de Desarrollo (Dev).

Proceso: Antes de pasar a votar o planificar el código, este grupo se reúne para "limpiar" y detallar el Backlog. El Equipo Dev lee las historias de usuario redactadas en la Etapa 1 para asegurarse de que entienden la lógica y que técnicamente son viables. Si algo está ambiguo, el Analista y el PO lo aclaran o lo vuelven a redactar.

Acciones de refinamiento en nuestro ejercicio:

+ Se revisa la HU01 y el equipo de desarrollo pregunta qué tipos de materiales base deben estar precargados (se acuerda incluir chapas, perfiles y portones).

+ Se analiza la HU02 y se aclara que la alerta visual en rojo debe aparecer inmediatamente cuando el gasto real supere el estimado de la etapa en pantalla, sin necesidad de recargar la página.

+ Se confirma que todas las historias cumplen con el criterio de estar "Listas para estimar" (Definition of Ready).


### Etapa 4: Puntuarlo (velocidad / complejidad)
Participantes: Product Owner (PO), Analista y el Equipo de Desarrollo (Dev). 

Proceso: El equipo evalúa el esfuerzo y la complejidad de cada Historia de Usuario del Backlog. Para esto se suele usar una escala para asignar "Puntos de Historia". Esto ayuda a medir la velocidad que el equipo puede sostener. Para realizar esta votación en equipo de forma objetiva y sin sesgos, se utilizará la dinámica de Poker Planning.

Puntuación de nuestras Historias de Usuario (HU):

+ HU01 (Creación de Presupuesto): **5 Puntos.** Complejidad media. Requiere armar un formulario, validar los datos y hacer fórmulas de cálculo automatizadas.

+ HU02 (Seguimiento por Etapas): **8 Puntos.** Complejidad alta. Implica cruzar datos dinámicos, segmentar por etapas y programar la lógica de alertas en tiempo real (cambiar a color rojo al pasarse del presupuesto).

+ HU03 (Generación de Informes): **3 Puntos.** Complejidad baja. Es el diseño de un reporte visual y la exportación de los datos existentes a un archivo PDF.

+ Velocidad total estimada del proyecto: **16 puntos de historia.**


### Etapa 5: Planificación (El Desarrollo y el Sprint)
Participantes: Scrum Master (SM) y el Equipo de Desarrollo (Dev).

Proceso: Se da inicio al Sprint, estimamos en un ciclo corto de 1 o 2 semanas. El equipo se compromete a cumplir el objetivo del Sprint, que es entregar el sistema de presupuestos funcional con las 3 historias aprobadas.

Para lograrlo, cada Historia de Usuario se divide en tareas técnicas más chicas y a cada tarea se le asigna su propia velocidad/estimación de tiempo:

Desglose del Sprint Backlog (Tareas):
+ Para HU01 (Presupuestos):

  + Tarea 1.1: Diseñar la interfaz del formulario de medidas (Ancho, Alto, Largo) y selección de materiales. (Velocidad: 4 hs)

  + Tarea 1.2: Programar la base de datos con los precios de chapas, perfiles y portones. (Velocidad: 6 hs)

  + Tarea 1.3: Desarrollar el motor de cálculo matemático del costo total. (Velocidad: 5 hs)

+ Para HU02 (Seguimiento):

  + Tarea 2.1: Crear la vista para dividir la obra en etapas (Cimentación, Estructura, Techado). (Velocidad: 6 hs)

  + Tarea 2.2: Programar la lógica de comparación (Presupuestado vs. Real) y la alerta visual en rojo. (Velocidad: 8 hs)

+ Para HU03 (Informes):

  + Tarea 3.1: Configurar la librería para exportar la pantalla a formato PDF. (Velocidad: 4 hs)

Ceremonias / Eventos durante este Sprint:
**Daily Meeting**:
Se realiza al iniciar cada jornada de trabajo, es una reunión diaria de 15 minutos. Cada desarrollador responde brevemente frente al tablero:

+ ¿Qué hice ayer? (Ej: "Terminé el diseño del formulario de presupuestos").

+ ¿Qué voy a hacer hoy? (Ej: "Voy a empezar a programar la base de datos de los materiales").

+ ¿Tengo algún bloqueo/impedimento? (Ej: "No me queda claro el precio por metro de los perfiles, necesito ayuda del analista").

**Review (Revisión)**:
Antes de presentarlo formalmente, el equipo Dev analiza internamente que todo funcione. Luego, se realiza la demo ante el Product Owner (el profesor y la clase) para mostrar el grado de avance e incremento de software terminado (las historias de usuario funcionando correctamente y cumpliendo sus criterios de aceptación).

**Retrospective (Retrospectiva)**:
Al finalizar el Sprint, el Scrum Master reúne al equipo para analizar cómo funcionó la metodología y cómo se sintieron. Se arma la siguiente tabla de mejora continua:
| Lo que se hizo BIEN (Se mantiene) | Lo que se hizo MAL (Se transforma en Requerimiento) |
| :--- | :--- |
| • Excelente comunicación interna por Discord.<br><br>• El diseño visual de las tarjetas/post-its ayudó a entender las tareas.<br><br>• Se cumplieron los tiempos de desarrollo de la HU01. | • **Fallo:** Faltaron definir mejor los tipos de portones en los materiales de construcción, lo que retrasó la HU02.<br><br>• **Fallo:** La exportación a PDF se rompe si el nombre del galpón es muy largo. |

