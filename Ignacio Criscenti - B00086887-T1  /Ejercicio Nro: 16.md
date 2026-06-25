# Ejercicio Nro: 16

## Enunciado
Objetivo:  
Utilizar el método Delphi para llegar a un consenso sobre la tecnología y la arquitectura más adecuadas para el desarrollo de una billetera virtual segura, escalable y confiable.  

Descripción:  
El método Delphi es una técnica de consulta estructurada que se utiliza para obtener opiniones expertas sobre un tema complejo. En este caso, el método Delphi se utilizará para recopilar información y opiniones de expertos en blockchain, seguridad, desarrollo de software y arquitectura de sistemas sobre la mejor tecnología y arquitectura para una billetera virtual.  

1- Definición del problema:  
  + Describir claramente los objetivos y requisitos de la billetera virtual, tal como se presentó en el enunciado anterior.  

  + Identificar los factores clave que se deben considerar al seleccionar la tecnología y la arquitectura, como la seguridad, la escalabilidad, la confiabilidad, la facilidad de uso y el costo.  

2- Selección del panel de expertos:  
  + Identificar y reclutar a un grupo de expertos con experiencia en las áreas relevantes, como blockchain, seguridad, desarrollo de software y arquitectura de sistemas.  

  + El panel de expertos debe estar compuesto por individuos con diferentes perspectivas y experiencias para garantizar la diversidad de opiniones.  

  + Es importante que los expertos sean independientes y no tengan conflictos de intereses.

3- Elaboración del cuestionario:
  + Diseñar un cuestionario que presente a los expertos una lista de opciones de tecnología y arquitectura para la billetera virtual.

  + El cuestionario debe incluir preguntas que permitan a los expertos evaluar cada opción en función de los factores clave identificados en el paso 1.

  + Las preguntas pueden ser de tipo Likert, abiertas o una combinación de ambas.

4- Aplicación del método Delphi:
  + Distribuir el cuestionario a los expertos de forma anónima.

  + Recopilar las respuestas de los expertos y analizarlas estadísticamente.

  + Sintetizar los resultados y presentarlos al panel de expertos.

  + Brindar a los expertos la oportunidad de revisar y comentar los resultados.

  + Realizar una segunda ronda de cuestionarios, incorporando los comentarios de la primera ronda.

  + Analizar nuevamente las respuestas y presentar los resultados finales al panel de expertos.

5- Selección de la tecnología y la arquitectura:
  + Con base en los resultados del método Delphi, seleccionar la tecnología y la arquitectura que mejor se adapten a los objetivos y requisitos de la billetera virtual.

  + Justificar la selección de la tecnología y la arquitectura elegidas, considerando los aportes del panel de expertos y los resultados del análisis estadístico.

6- Documentación y comunicación:
  + Documentar cuidadosamente el proceso de toma de decisiones, incluyendo los criterios utilizados, las opciones consideradas y la justificación de la selección final.

  + Comunicar la decisión tomada a las partes interesadas, incluyendo a los desarrolladores, inversores y usuarios potenciales.

## Resolución 

### 1)
El **objetivo principal** de este proyecto es diseñar una billetera virtual (o digital wallet) pensada para el uso cotidiano y masivo de los usuarios. Para que la aplicación sea viable, debe cumplir con ciertos requisitos fundamentales: en primer lugar, permitir el registro seguro de personas mediante una validación de identidad (KYC); en segundo lugar, ofrecer una gestión de cuentas clara, donde el usuario pueda ver su saldo en tiempo real y su historial de movimientos; y por último, garantizar una operatoria fluida para realizar transferencias inmediatas entre usuarios, pagos con código QR en comercios y recargas de servicios.

Para evaluar las tecnologías, primero debemos tener claros los criterios de éxito, una de ellas es la **seguridad** ya que ofrece resistencia a ataques, cifrado de claves privadas, auditorías de contratos inteligentes y cumplimiento de normativas; podemos mencionar a la **escalabilidad** porque es la capacidad para procesar un alto volumen de transacciones por segundo (TPS) a bajo costo y con baja latencia, previendo el crecimiento de usuarios. Otro de los conceptos es el de la **confiabilidad / disponibilidad**, por ejemplo la tolerancia a fallos, redundancia de nodos o servidores, y consistencia en el estado de los saldos (evitar doble gasto). Hay que mencionar la **facilidad de uso (UX/DevX)** que es una curva de aprendizaje para los desarrolladores (herramientas, documentación) y agilidad que permite en la interfaz final del usuario. Y finalmente, su **costo**, sean de infraestructura (servidores en la nube vs. nodos), costos de transacción (gas fees de la red blockchain elegida) y licencias.

### 2)
Para armar nuestro panel, el objetivo fue buscar a profesionales independientes, con experiencia real y que representen distintos puntos de vista para evitar que la decisión final dependa de una sola opinión técnica.

Por eso, el equipo se pensó desde el principio integrando diferentes roles clave que se complementan entre sí. Convocamos a un **especialista en seguridad informática**, cuya función principal es analizar los riesgos del sistema, rastrear posibles fraudes o vulnerabilidades y blindar la protección de la información financiera de los usuarios. A la par, sumamos a un **arquitecto de software** para evaluar si nos conviene usar una estructura basada en microservicios o en la nube, poniendo la lupa sobre la escalabilidad, el rendimiento y qué tan fácil será mantener el sistema a largo plazo. La lógica interna de la billetera virtual, el procesamiento de las transacciones en tiempo real y el diseño de las APIs quedan bajo la mirada de un **desarrollador backend**. Por el lado de la interfaz, incorporamos a un **especialista en experiencia de usuario y desarrollo frontend**, encargado de medir la facilidad de uso de la aplicación y lograr que cualquier operación del día a día sea clara y ágil para la gente. Como el enunciado plantea el uso de nuevas tecnologías, un **especialista en blockchain** evalúa si realmente conviene meterse en ese terreno, sopesando las ventajas y desventajas de los contratos inteligentes en el manejo de saldos. Finalmente, para que todo esto tenga los pies sobre la tierra, sumamos a un **representante del área de negocio y producto**, quien nos ayuda a evaluar la viabilidad comercial, los costos de infraestructura, las licencias y las expectativas reales del mercado.

### 3)
Para la primera ronda del método Delphi, se diseñó un cuestionario mixto estructurado en cuatro secciones estratégicas. El objetivo es combinar preguntas cerradas (escala Likert de 1 al 5, donde 1 es "Muy bajo/Malo" y 5 es "Muy alto/Excelente") para el posterior análisis estadístico, junto con preguntas abiertas que permitan a los expertos justificar sus posturas y aportar matices técnicos.

**Sección 1: Contexto y Arquitectura General del Sistema**:

Esta sección busca definir el esqueleto evolutivo de la plataforma, evaluando cómo responderá la infraestructura ante el crecimiento de la demanda.

1.1. En una escala del 1 al 5, califique las siguientes opciones de arquitectura en función de su capacidad para asegurar la escalabilidad y la alta disponibilidad (tolerancia a fallos) de la billetera virtual:

+ Arquitectura de Microservicios (orientada a contenedores).

+ Arquitectura Serverless (Arquitectura basada en eventos / funciones en la nube).

+ Arquitectura Modular Monolítica.

1.2. [Pregunta Abierta]: Justifique brevemente su elección anterior. Si considera una combinación híbrida (por ejemplo, Backend en microservicios y pasarelas serverless), detalle los motivos.

**Sección 2: Definición del Stack Tecnológico (Backend, Base de Datos y Blockchain)**:

Orientado a determinar las herramientas de software que procesarán el negocio financiero y la consistencia de los saldos.

2.1. Evalúe del 1 al 5 las siguientes tecnologías para el desarrollo del Backend / API core, considerando la madurez del ecosistema, la seguridad nativa y la facilidad de conseguir talento en el mercado (DevX):

+ Java / Spring Boot

+ Node.js (TypeScript)

+ .NET Core

+ Go (Golang)

2.2. Pensando en la consistencia de los saldos, el historial de movimientos y la velocidad de lectura/escritura, ¿qué estrategia de Base de Datos considera más adecuada? (Seleccione una opción).

+ Relacional estricta (ej. PostgreSQL) para garantizar propiedades ACID completas.

+ No Relacional (ej. MongoDB) para flexibilidad de esquemas y rápida escalabilidad horizontal.

+ Enfoque políglota (Híbrido: Relacional para transacciones / No Relacional para logs e historial).

2.3. Con respecto a la tecnología Blockchain, ¿en qué medida considera que descentralizar los saldos mediante contratos inteligentes aporta valor real frente a una base de datos tradicional, considerando los costos de transacción (gas fees) y la latencia? (Escala 1: No aporta valor / añade complejidad innecesaria — 5: Es indispensable para la transparencia y seguridad).

2.4. [Pregunta Abierta]: Si su respuesta anterior fue mayor a 3, ¿qué red o infraestructura recomendaría (ej. Ethereum L2, Hyperledger Fabric, Stellar) y por qué?

**Sección 3: Seguridad, Cumplimiento Financiero y Criptografía**:

Bloque crítico para mitigar el riesgo operativo, el fraude y garantizar la protección del capital de los usuarios.

3.1. Califique de 1 a 5 la prioridad de implementación en la primera fase (MVP) de los siguientes mecanismos de seguridad:

+ Autenticación de Factores Múltiples (MFA) + Biometría (FaceID/Huella).

+ Tokenización de transacciones y datos sensibles de tarjetas.

+ Cifrado de datos en reposo y en tránsito (mTLS, AES-256).

+ Módulos de Seguridad de Hardware (HSM) en la nube para la gestión de claves privadas.

+ Sistemas de monitoreo en tiempo real basados en comportamiento para detección de anomalías/fraude.

**Sección 4: Viabilidad Financiera y Síntesis Final**:

Sección destinada a cruzar las decisiones técnicas con las restricciones presupuestarias y de negocio.

4.1. En una escala del 1 al 5 (donde 1 es muy económico y 5 es sumamente costoso), estimación del costo total de propiedad (TCO) incluyendo infraestructura cloud, licencias, mantenimiento y soporte especializado de la solución que usted visualiza como ideal.

4.2. [Pregunta Abierta]: A modo de síntesis, describa brevemente cuál sería para usted la combinación óptima de arquitectura, stack principal y estrategia de seguridad para lograr una billetera virtual exitosa en el mercado actual.


### 4)

La aplicación del método Delphi se estructuró en un proceso iterativo de dos rondas de consulta anónimas. Esto permite que los expertos reconsideren sus opiniones a la luz de las respuestas del grupo, evitando la influencia de sesgos de liderazgo o presiones sociales que suelen ocurrir en debates presenciales.A continuación, se detalla la ejecución cronológica de cada fase:

**Lanzamiento y Ronda 1:**

Su distribución fue anónima: El cuestionario diseñado en el punto 3 se digitalizó mediante una plataforma de formularios y se envió individualmente a los 6 miembros del panel de expertos elegidos en el punto 2 (especialista en seguridad, arquitecto, backend, frontend/UX, blockchain y negocio). El envío se realizó de forma enmascarada para asegurar que ningún experto conociera la identidad de los demás participantes.

Como procesamiento de datos estadísticos: Se obtuvo que una vez recolectadas las respuestas de la primera ronda, se procedió al análisis de los datos cuantitativos (preguntas Likert) e independientes. Para cada pregunta, se calcularon las siguientes métricas:

+ Mediana): Para identificar la tendencia central de la opinión del panel.
  
+ Rango Intercuartílico (IQR): Para medir el grado de dispersión o desacuerdo entre los expertos (un IQR bajo indica mayor nivel de acuerdo).

Como análisis cualitativo se agruparon y sintetizaron todos los argumentos de las preguntas abiertas. Por ejemplo, en el bloque de Blockchain, la mayoría coincidió en que una red pública como Ethereum añadiría latencia y costos excesivos de gas para pagos cotidianos, sugiriendo en su lugar soluciones híbridas o redes privadas de tipo permisionadas.

**Retroalimentación y Ronda 2**

Como elaboración del Informe de Retorno se preparó un documento de síntesis que se envió de regreso a cada experto. Este informe incluyó:

1. La respuesta inicial que ese experto en particular había dado.
2. Los resultados estadísticos globales del grupo (mediana y dispersión).
3. Un resumen anónimo con los argumentos cualitativos a favor y en contra de las opciones más polémicas.

Ejecución de la Segunda Ronda: Se solicitó a los expertos que revisaran el informe. Aquellos cuyas opiniones iniciales se encontraban en los extremos (fuera del rango intercuartílico) tuvieron la oportunidad de modificar su respuesta para acercarse al consenso del grupo tras leer los argumentos técnicos de sus colegas; y de mantener su postura original, estando obligados en este caso a justificar técnicamente por qué disentían con la mayoría.

**Cierre y Estabilización de Respuestas**

Tras recibir las respuestas de la Ronda 2, se repitió el análisis estadístico. Se observó una drástica reducción del rango intercuartílico (IQR), lo que demostró una convergencia de opiniones y un nivel de consenso óptimo (superior al 80% de concordancia en los criterios clave de arquitectura y seguridad). Con estos resultados consolidados y estabilizados, se dio por finalizada la consulta, quedando el terreno preparado para la toma de decisiones final.


### 5)
A partir de la convergencia de opiniones lograda en la última ronda del método Delphi, se consolidó la definición del stack tecnológico y el diseño arquitectónico de la billetera virtual. La selección final equilibra la rigurosidad financiera con la viabilidad técnica y económica del proyecto, justificándose de la siguiente manera:

**Arquitectura:** Monolito Modular (Evolutivo) Se seleccionó un enfoque modular sobre microservicios para la primera etapa del proyecto. El panel de expertos coincidió en que permite un desarrollo inicial más ágil, menor costo de infraestructura y un despliegue simplificado, manteniendo una estricta separación de componentes (Autenticación/KYC, Pagos, Transferencias, Notificaciones). Esta separación interna garantiza que, cuando el volumen de transacciones por segundo (TPS) lo requiera, los módulos críticos puedan migrarse de forma independiente hacia microservicios sin necesidad de reescribir el sistema desde cero.

**Backend:** Java con Spring Boot Fue la opción con mayor consenso debido a su madurez y presencia dominante en el sector fintech y bancario. Aporta tipado fuerte, excelente manejo de concurrencia y frameworks nativos de seguridad altamente probados (como Spring Security). Cumple con creces los requisitos de confiabilidad, control transaccional estricto y facilidad para integrar pasarelas de pago externas o el backend con el frontend.

**Base de Datos:** PostgreSQL (Enfoque Relacional) Para el almacenamiento del core financiero (saldos y movimientos) se optó por una base de datos relacional robusta. PostgreSQL garantiza el cumplimiento estricto de las propiedades ACID (Atomicidad, Consistencia, Aislamiento y Durabilidad), lo cual es innegociable para evitar errores críticos como el doble gasto o la inconsistencia de saldos en transferencias inmediatas.

**Postura sobre Blockchain:** Desestimado para la Fase 1 (MVP) Siguiendo el criterio unánime del panel de expertos (especialmente las áreas de negocio y desarrollo), se decidió no incluir tecnologías de registro distribuido (DLT/Blockchain) en el lanzamiento inicial. Introducir contratos inteligentes añadiría una latencia innecesaria en los pagos con código QR, elevaría los costos operativos (gas fees) y complejizaría la experiencia de usuario. Se archiva como una iniciativa de innovación futura en caso de que el modelo de negocio requiera interoperabilidad con criptoactivos o remesas internacionales descentralizadas.

### 6)
Para garantizar que las decisiones tomadas a través del método Delphi se ejecuten correctamente y aporten valor a largo plazo, se estableció una estrategia clara de registro y difusión hacia todos los actores involucrados:

**Documentación Técnica (El Registro)**

Registros de Decisión de Arquitectura (ADRs - Architecture Decision Records): Se creará un repositorio formal de ADRs dentro de la documentación del proyecto. Cada elección crítica realizada en el paso anterior (como el uso de PostgreSQL, la postergación de Blockchain o la estructura del monolito modular) se documentará en un archivo estandarizado que detalle: el contexto del problema, las alternativas evaluadas, la decisión final tomada bajo el consenso Delphi y las consecuencias técnicas (ventajas y limitaciones) de dicha elección. Esto evitará discusiones redundantes en el futuro y servirá de guía para los nuevos desarrolladores.

Diagramas de Arquitectura: Se modelarán las interacciones de los módulos y el flujo de datos mediante el estándar C4 Model (focalizado en Contexto y Contenedores), permitiendo que cualquier programador backend o especialista en seguridad entienda visualmente cómo se procesan las transacciones en tiempo real.

**Plan de Comunicación (Las Partes Interesadas)**

La decisión final se comunicará de manera diferenciada según el perfil del receptor, adaptando el nivel técnico para lograr el máximo impacto:

Al Equipo de Desarrollo (Backend, Frontend, QA y DevOps): Se realizarán sesiones de alineación técnica (Kick-off). Se les presentará el stack tecnológico (Java/Spring Boot y PostgreSQL) junto con las pautas de modularización. Al conocer los fundamentos de las decisiones, el equipo podrá enfocarse en construir APIs seguras y una interfaz limpia sin la incertidumbre de un cambio tecnológico a mitad de camino.

A los Inversores y Dirección de Negocio: Se presentará un informe ejecutivo de viabilidad enfocado en el retorno de inversión (ROI) y la mitigación de riesgos. Se destacará que la postergación de Blockchain y la elección de una arquitectura modular reducen drásticamente los costos iniciales de infraestructura y el tiempo de salida al mercado (Time-to-Market), asegurando un producto viable económico y eficiente.

A los Usuarios Potenciales (Mensaje de Producto): Aunque el usuario final no necesita conocer el código de la aplicación, la decisión técnica se traducirá en beneficios directos para su experiencia. El área de marketing y producto comunicará el lanzamiento de una plataforma diseñada bajo los más altos estándares de la industria bancaria, garantizando que sus transferencias e inicios de sesión serán inmediatos, estables y 100% seguros.
















