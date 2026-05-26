# Ejercicio Nro: 13

## Enunciado
1. ¿Qué es Extreme Programming (XP) y cuál es su objetivo principal dentro de las metodologías ágiles?
2. ¿Cuáles son los cinco valores principales de XP? Explicá brevemente cada uno.
3. ¿Por qué XP considera que las pruebas son un elemento fundamental del desarrollo de software?
4. ¿Qué es Test Driven Development (TDD) y cómo se relaciona con XP?
5. ¿En qué consiste la práctica de Pair Programming? Mencioná dos ventajas y una posible dificultad.
6. ¿Qué son las historias de usuario en XP y por qué se prefieren frente a una especificación extensa de requisitos?
7. ¿Qué significa Continuous Integration en XP y qué beneficios aporta al equipo de desarrollo?
8. ¿Cómo se aplica el concept de Weekly Cycle en un proyecto desarrollado con XP?
9. En XP se plantea que se fija el tiempo, el costo y la calidad, y se negocia el alcance. ¿Qué significa esta idea? Explicalo con un ejemplo.
10. Elegí tres prácticas de XP y explicá cómo podrían aplicarse en un proyecto real de desarrollo de software.

## Resolución

### 1. ¿Qué es Extreme Programming (XP) y cuál es su objetivo principal dentro de las metodologías ágiles?
Extreme Programming (XP) es una metodología ágil de desarrollo de software diseñada específicamente para proyectos que enfrentan requisitos vagos, cambiantes o de alto riesgo. Se centra fuertemente en la adaptabilidad, la excelencia técnica y las relaciones humanas dentro del equipo de desarrollo. El objetivo principal es maximizar la calidad del software y responder de manera eficiente a las necesidades cambiantes del cliente, minimizando el costo del cambio tecnológico a lo largo del ciclo de vida del proyecto. Para lograrlo, lleva las prácticas de ingeniería tradicionales a niveles "extremos" (por ejemplo, si las revisiones de código son buenas, se hace revisión de código constante mediante la programación en parejas).


### 2. ¿Cuáles son los cinco valores principales de XP? Explicá brevemente cada uno.
Los cinco valores fundamentales que rigen el comportamiento y las decisiones en un proyecto XP son:
1. **Comunicación:** El éxito de un proyecto depende de una comunicación fluida y directa. XP prioriza las conversaciones cara a cara, el uso de historias de usuario físicas y el diseño de espacios abiertos para evitar malentendidos entre desarrolladores y el cliente.
2. **Simplicidad:** Consiste en diseñar y programar la solución más simple que funcione hoy, en lugar de intentar predecir necesidades futuras abstractas. "Hacer lo que es necesario, nada más" reduce la carga de mantenimiento y acelera la entrega.
3. **Retroalimentación (Feedback):** El equipo busca opiniones e información sobre el estado del proyecto de forma constante. Se obtiene a través de pruebas automatizadas (en segundos), integración continua (en minutos), ciclos semanales con el cliente (en días) y lanzamientos de versiones (en meses).
4. **Respeto:** Cada miembro del equipo respeta la contribución y el rol de los demás. Los programadores respetan la opinión del cliente, el cliente respeta las estimaciones de los programadores, y todos valoran la calidad del código y el bienestar del equipo.
5. **Coraje (Valor):** Es la valentía para tomar decisiones difíciles en favor del proyecto. Significa tener el coraje de decir la verdad sobre los plazos, descartar código obsoleto o mal estructurado (refactorización) y enfrentar los problemas a medida que surgen en lugar de postergarlos.


### 3. ¿Por qué XP considera que las pruebas son un elemento fundamental del desarrollo de software?
En XP, las pruebas son el impulso el desarrollo del día a día y se consideran fundamentales por algunas razones tales como la red de seguridad contra regresiones: Permitir cambios frecuentes en el código (refactorización) requiere la absoluta certeza de que las funcionalidades existentes no se han roto. Las pruebas automatizadas brindan esta confianza en cuestión de segundos. También podemos mencionar a la documentación viva: Un caso de prueba bien escrito sirve como la especificación técnica más precisa sobre cómo debe comportarse un componente de software, superando a cualquier manual estático. Y principalmente, las pruebas nos dan como resultado una reducción del costo de corrección: Detectar un bug inmediatamente después de escribir el código es infinitamente más barato y rápido que descubrirlo semanas después en producción o en una fase tardía de testing manual.


### 4. ¿Qué es Test Driven Development (TDD) y cómo se relaciona con XP?
Test Driven Development (TDD) es una técnica de ingeniería de software donde el programador escribe las pruebas automatizadas antes de escribir el código de producción propiamente dicho. Sigue un ciclo estricto y repetitivo conocido como Red-Green-Refactor:
1. Red: Escribir una prueba automatizada para una nueva funcionalidad que falle (ya que la funcionalidad aún no existe).
2. Green: Escribir la cantidad mínima de código de producción necesaria para que la prueba pase.
3. Refactor (Refactorizar): Limpiar y optimizar el código escrito, eliminando duplicaciones y mejorando el diseño, asegurándose de que la prueba siga pasando.

TDD es una de las prácticas técnicas centrales e indispensables de Extreme Programming. Encarna a la perfección los valores de Simplicidad y Retroalimentación, asegurando que el diseño de software sea limpio y altamente testeable desde su concepción.


### 5. ¿En qué consiste la práctica de Pair Programming? Mencioná dos ventajas y una posible dificultad.
La práctica de Pair Programming consiste en que dos desarrolladores trabajen juntos en una sola computadora para resolver una misma tarea de programación. Se dividen en dos roles dinámicos que se intercambian frecuentemente:
* El Conductor (Driver): Tiene el control del teclado y el mouse, enfocándose en los detalles táctiles de la escritura del código actual.
* El Observador/Navegador (Navigator): Revisa el código en tiempo real mientras se escribe, piensa estratégicamente a largo plazo (diseño, posibles bugs, casos borde) y planifica los siguientes pasos.

**Ventajas:**
1. Mayor calidad del código y menos errores: Dos pares de ojos reducen drásticamente la introducción de bugs y evitan malas prácticas de diseño en el momento exacto en que ocurren.
2. Transferencia de conocimiento inmediata: Promueve la difusión orgánica de habilidades técnicas, del dominio del negocio y de buenas prácticas entre los miembros del equipo, eliminando los "silos de información".

Posible dificultad: trabajar de manera tan colaborativa e intensa requiere un alto nivel de concentración y habilidades blandas. Si no hay buena química, si hay choques de ego, o si las sesiones se extienden demasiado sin descansos, puede generar agotamiento mental y tensiones en el equipo.


### 6. ¿Qué son las historias de usuario en XP y por qué se prefieren frente a una especificación extensa de requisitos?
Las Historias de Usuario son descripciones breves, simples y redactadas en el lenguaje cotidiano del cliente sobre una funcionalidad que aporta valor de negocio. Tradicionalmente se escribían en tarjetas de papel físicas (notas adhesivas o fichas de cartulina) bajo una estructura general: *"Como [tipo de usuario], quiero [realizar una acción] para [obtener un beneficio]"*.

Se prefieren frente a una especificación extensa  porque:
* Fomentan la conversación en lugar de la burocracia: XP sostiene que los requisitos no se "capturan" en un papel estático, sino que se negocian. La historia de usuario es un "recordatorio para una conversación" futura entre el cliente y los desarrolladores.
* Flexibilidad ante el cambio: Un documento de requisitos de 200 páginas se vuelve obsoleto rápidamente y es costoso de modificar. Las tarjetas de historias de usuario se pueden priorizar, descartar, dividir o reescribir fácilmente a medida que el negocio evoluciona.
* Comprensibles para todos: Al evitar la jerga técnica, actúan como un puente de entendimiento común entre el equipo técnico y los stakeholders comerciales.


### 7. ¿Qué significa Continuous Integration en XP y qué beneficios aporta al equipo de desarrollo?
Continuous Integration es una práctica mediante la cual los desarrolladores integran el código nuevo que van produciendo con la rama principal (main/trunk) de forma muy frecuente, idealmente varias veces al día. Cada integración es verificada automáticamente por una herramienta que compila el código y ejecuta toda la suite de pruebas unitarias para detectar fallos de inmediato.

Aporta grandes beneficios al equipo de desarrollo, pobele evita los problemas masivos de fusionar ramas de código que estuvieron separadas durante semanas o meses, donde resolver conflictos de código puede tomar días. Otro beneficio puede ser que si un desarrollador sube un código que rompe otra parte del sistema, el sistema de CI avisa en minutos, permitiendo solucionar el problema cuando el contexto aún está fresco en la mente. Asegura que el repositorio principal esté en un estado de salud constante y estable, lo que incrementa la predictibilidad y la confianza del equipo.


### 8. ¿Cómo se aplica el concept de Weekly Cycle en un proyecto desarrollado con XP?
El Weekly Cycle es el marco que estructura el ritmo de trabajo a corto plazo en XP. Se aplica al inicio de cada semana mediante una reunión conjunta entre el cliente y el equipo de desarrollo, siguiendo estos pasos:

1. Revisión del progreso anterior: El cliente evalúa las historias de usuario terminadas la semana anterior para verificar que funcionan según lo esperado.
2. Selección de historias: El cliente elige las historias de usuario que desea ver implementadas durante la semana actual, basándose en el valor de negocio que aportan y en el "presupuesto" de velocidad estimado del equipo.
3. Desglose en tareas: Los desarrolladores desglosan las historias seleccionadas en tareas técnicas individuales más pequeñas (de unas pocas horas cada una) y se las autoasignan de forma voluntaria.
4. Desarrollo enfocado: Durante el resto de la semana, el equipo se dedica exclusivamente a programar, probar e integrar estas tareas, buscando entregar un software funcional al término de los 5 días.


### 9. En XP se plantea que se fija el tiempo, el costo y la calidad, y se negocia el alcance. ¿Qué significa esta idea? Explicalo con un ejemplo.
En la gestión de proyectos tradicional (Cascada), se suele fijar el *alcance* (todo lo que se prometió hacer) y se intenta estimar el *tiempo* y el *costo*, lo cual suele llevar a retrasos o a sacrificar la *calidad* mediante recortes de pruebas al final del proyecto. XP invierte este paradigma basándose en las cuatro variables de un proyecto (Tiempo, Costo, Calidad y Alcance). Por un lado, el Tiempo y Costo se fijan haciendo que el tamaño del equipo y la fecha de entrega de los ciclos o lanzamientos son constantes bien conocidos. La Calidad tampoco es negociable: reducir la calidad (no testear, escribir código sucio) ralentiza el desarrollo a mediano plazo, por lo que XP la mantiene fija en un estándar de excelencia técnica. Por lo tanto, el Alcance es negociable, es la variable de ajuste: Si el tiempo apremia, lo único que se reduce o se posterga es la cantidad de características o funcionalidades que se entregarán en esa iteración.

Ejemplo: Supongamos que un equipo está desarrollando una aplicación de comercio electrónico para una tienda que debe lanzarse obligatoriamente antes de la temporada navideña (Tiempo fijo), con un equipo de 4 programadores ya contratados (Costo fijo) y garantizando que no haya errores en los pagos (Calidad fija). A dos semanas del lanzamiento, se dan cuenta de que no llegarán a desarrollar el módulo de "cupones de descuento complejos" y el sistema de "recomendaciones personalizadas por Inteligencia Artificial". En XP, se reúne al cliente y se negocia el alcance: se decide postergar el sistema de recomendaciones por IA para una fase posterior, y para los cupones se implementa una solución simplificada de código fijo. De esta forma, el producto se lanza a tiempo, dentro del presupuesto y funcionando de forma excelente y segura en sus características principales (carrito y pasarela de pago).


### 10. Elegí tres prácticas de XP y explicá cómo podrían aplicarse en un proyecto real de desarrollo de software.
Para un proyecto real de desarrollo de una Aplicación Móvil de Gestión de Turnos Médicos, podríamos aplicar las siguientes tres prácticas de XP:

1. **Sitio con el Cliente (On-Site Customer):**
   * *Aplicación:* Incluir dentro de la oficina del equipo de desarrollo a un representante real de la clínica o un administrador de salud que conozca a fondo el negocio.
   * *Ejemplo práctico:* Cuando los desarrolladores están diseñando la pantalla de cancelación de turnos y surge la duda de si un paciente puede cancelar con menos de 2 horas de anticipación, no envían un correo formal esperando días por una respuesta. Simplemente llaman o consultan al cliente en ese instante, quien aclara que "sí se puede, pero debe disparar una alerta al médico". La duda se resuelve en 2 minutos.

2. **Refactorización (Refactoring):**
   * *Aplicación:* Mejorar la estructura interna del código de forma continua sin alterar su comportamiento externo, para mantener la base de código limpia y adaptable.
   * *Ejemplo práctico:* Al inicio, la lógica para calcular la disponibilidad horaria de los médicos se programó rápidamente dentro de la misma pantalla (vista) para validar que funcionaba. En la siguiente iteración, al notar que el código quedó largo y confuso, la pareja de desarrolladores aplica refactorización: extrae esa lógica a una clase independiente y especializada llamada `ValidadorHorarios`, ordenando el código y dejándolo listo para ser reutilizado en el módulo de notificaciones, asegurando que todas las pruebas automatizadas sigan pasando en verde.

3. **Ritmo Sostenible (Sustainable Pace / 40-Hour Week):**
   * *Aplicación:* Establecer una cultura donde no se permiten las horas extra sistemáticas ni las jornadas maratónicas, protegiendo la salud física y mental de los trabajadores.
   * *Ejemplo práctico:* Faltando pocos días para el cierre del ciclo semanal, la gerencia nota que hay una acumulación de tareas pendientes. En lugar de exigirle al equipo trabajar hasta la medianoche, se aplica el principio de XP: se comunica con el cliente, reajusta el alcance quitando una tarea no esencial, y el equipo se retira a su horario habitual. Al día siguiente, regresan enfocados y con la mente clara para escribir código libre de errores.
