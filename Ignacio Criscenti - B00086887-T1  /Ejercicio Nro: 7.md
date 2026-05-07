# Ejercicio Nro: 7

## Enunciado
Dar un ejemplo de cada uno de los cuellos de botellas analizados anteriormente en el paper de Brooks.

## Resolución
Brooks plantea en su ensayo que la complejidad es la esencia del software. Para entender los cuellos de botella, podemos observar el caso de una plataforma de gran escala como Mercado Libre:

- Dificultad Accidental: Se refiere a los problemas que surgen de la implementación técnica. Un ejemplo concreto sería el tiempo que pierden los desarrolladores de la empresa si tienen que configurar manualmente cada servidor para que soporte el lenguaje de programación que usan. Antiguamente, este era un gran cuello de botella, pero hoy se ha reducido muchísimo gracias al uso de Cloud Computing (AWS) y herramientas de automatización. Es decir, la "traba" de la infraestructura es accidental porque no tiene que ver con el negocio de vender productos, sino con las herramientas.

- Dificultad Esencial: Es el verdadero cuello de botella y no se puede eliminar con tecnología. En el caso de Mercado Libre, la dificultad esencial es la lógica del negocio: cómo coordinar en milisegundos el stock de un vendedor en un punto del país, con el pago de un comprador en otro, calculando el costo de envío y las regulaciones fiscales de cada región. Esa complejidad conceptual es inherente al problema. Aunque usen la inteligencia artificial más avanzada, la dificultad de diseñar esa estructura lógica seguirá existiendo porque es la esencia de lo que el software debe hacer.
