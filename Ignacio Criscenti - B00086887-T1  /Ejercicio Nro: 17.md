# Ejercicio Nro: 17

## Enunciado
Objetivo:  Desarrollar una aplicación web que permita a los usuarios gestionar sus finanzas personales de manera eficiente y segura. La aplicación debe cumplir con los siguientes requisitos funcionales:  

1- Gestión de cuentas bancarias:  
+ Permitir la creación y edición de cuentas bancarias.  

+ Visualizar el saldo actual y el historial de movimientos de cada cuenta.  

+ Realizar transferencias entre cuentas propias.  

+ Descargar el historial de movimientos en formato CSV o PDF.  

2- Gestión de ingresos y gastos:  
+ Permitir la creación y edición de ingresos y gastos.  

+ Categorizar los ingresos y gastos por tipo (salario, alquiler, alimentación, etc.).  

+ Visualizar gráficos y reportes sobre los ingresos y gastos por categoría y período de tiempo.  

+ Establecer presupuestos para diferentes categorías de gastos.  

3- Gestión de deudas:  
+ Permitir la creación y edición de deudas.  

+ Indicar el monto total de la deuda, la tasa de interés, el plazo de pago y el monto de las cuotas.  

+ Visualizar un calendario de pagos y realizar simulaciones de diferentes escenarios de pago.  

+ Generar informes sobre el progreso en el pago de las deudas.

**Resolver**  

Estimación del tamaño del proyecto:  
Utilizando el método COSMIC, se estima que el tamaño funcional total del proyecto es de X Puntos de Función COSMIC (PFC).  

Cálculo del costo por punto de función:  
El costo por punto de función (CPFC) se estima en Y USD.  

Cantidad de puntos de función que se pueden hacer en un mes:  
Se estima que un equipo de desarrollo de software de Z personas puede desarrollar W Puntos de Función COSMIC (PFC) por mes.  

Duración del proyecto:  
La duración del proyecto se estima en A meses.  

Costo del proyecto:  
El costo total del proyecto se estima en B USD.

**Instrucciones para el alumno:**

1. Identificar las interacciones funcionales: Analice los requisitos funcionales descritos anteriormente e identifique todas las interacciones entre los usuarios y la aplicación.
2. Clasificar las interacciones funcionales: Clasifique cada interacción funcional en una de las tres categorías de tamaño COSMIC: Pequeña (S), Mediana (M) o Grande (L).
3. Calcular el tamaño funcional: Asigne un valor de Puntos de Función COSMIC (PFC) a cada interacción funcional en función de su clasificación de tamaño y sume los valores de PFC de todas las interacciones para obtener el tamaño funcional total del proyecto en PFC.
4. Obtener el costo por punto de función: Investigue el costo promedio de desarrollo de software en su región y considere la complejidad del proyecto para estimar el costo por punto de función (CPFC).
5. Determinar la cantidad de PFC por mes: Estime la cantidad de Puntos de Función COSMIC (PFC) que un equipo de desarrollo de software de tamaño Z puede desarrollar por mes (W PFC/mes) en función de su experiencia y eficiencia.
6. Calcular la duración del proyecto: Divida el tamaño funcional total del proyecto (X PFC) por la cantidad de PFC que se pueden desarrollar por mes (W PFC/mes) para obtener la duración estimada del proyecto en meses (A meses).
7. Estimar el costo total: Multiplique el tamaño funcional total del proyecto (X PFC) por el costo por punto de función (Y USD/PFC) para obtener el costo total estimado del proyecto (B USD).
   
## Resolución
### 1 y 2) Identificación y Clasificación de Interacciones Funcionales

Analizando los requisitos funcionales del enunciado, desglosamos y clasificamos las interacciones entre el usuario y la aplicación utilizando el método COSMIC:

#### Bloque 1: Gestión de cuentas bancarias
* **Creación y edición de cuentas bancarias:** Interacción simple de carga y actualización de datos en el sistema. 
  * *Clasificación:* **Pequeña (S)** $\rightarrow$ **4 PFC**
* **Visualizar saldo actual e historial de movimientos:** Requiere consultar y recuperar datos financieros en tiempo real para mostrarlos en pantalla.
  * *Clasificación:* **Mediana (M)** $\rightarrow$ **6 PFC**
* **Realizar transferencias entre cuentas propias:** Interacción crítica que valida saldos, descuenta de una cuenta, impacta la otra y registra el movimiento de forma transaccional.
  * *Clasificación:* **Grande (L)** $\rightarrow$ **8 PFC**
* **Descargar historial de movimientos en CSV o PDF:** Toma los datos de la consulta, invoca un motor de renderizado o exportación y genera el archivo para el usuario.
  * *Clasificación:* **Mediana (M)** $\rightarrow$ **5 PFC**

#### Bloque 2: Gestión de ingresos y gastos
* **Creación y edición de ingresos y gastos:** Formularios de carga de transacciones cotidianas.
  * *Clasificación:* **Pequeña (S)** $\rightarrow$ **4 PFC**
* **Categorizar ingresos y gastos:** Interacción para asociar transacciones a etiquetas o tipos predefinidos.
  * *Clasificación:* **Pequeña (S)** $\rightarrow$ **3 PFC**
* **Visualizar gráficos y reportes por categoría y tiempo:** Interacción compleja que requiere lógica de agregación de datos y procesamiento en el backend para alimentar la interfaz gráfica.
  * *Clasificación:* **Grande (L)** $\rightarrow$ **8 PFC**
* **Establecer presupuestos por categorías:** Permite definir un límite, leer los gastos acumulados de esa categoría y comparar si se excede el tope.
  * *Clasificación:* **Mediana (M)** $\rightarrow$ **6 PFC**

#### Bloque 3: Gestión de deudas
* **Creación y edición de deudas:** Registro inicial de los datos de la deudora.
  * *Clasificación:* **Pequeña (S)** $\rightarrow$ **4 PFC**
* **Cálculo e indicación de monto total, tasas y cuotas:** Lógica que procesa variables financieras para mostrar el desglose de amortización al usuario.
  * *Clasificación:* **Mediana (M)** $\rightarrow$ **6 PFC**
* **Calendario de pagos y simulador de escenarios:** Interacción muy compleja que procesa fórmulas financieras dinámicas (ej. variaciones de tasas o adelantos de cuotas) y las proyecta temporalmente.
  * *Clasificación:* **Grande (L)** $\rightarrow$ **10 PFC**
* **Generar informes sobre el progreso del pago:** Reporte analítico que mide el estado actual frente al total de la deuda.
  * *Clasificación:* **Mediana (M)** $\rightarrow$ **6 PFC**

---

### 3) Cálculo del Tamaño Funcional Total (X)

Sumamos los puntos asignados a cada una de las interacciones identificadas:

$$X = 4 + 6 + 8 + 5 + 4 + 3 + 8 + 6 + 4 + 6 + 10 + 6$$
$$\mathbf{X = 70 \text{ Puntos de Función COSMIC (PFC)}}$$

---

### 4) Obtención del costo por punto de función (Y)

Considerando la complejidad del sistema financiero (manejo estricto de saldos, simuladores y seguridad) y tomando como referencia los costos promedio de desarrollo de software en la región para una fábrica de software o equipo profesional:
* Se estima un Costo por Punto de Función (**CPFC**) de **150 USD**. 
* **Justificación:** Este valor cubre las horas de ingeniería, aseguramiento de la calidad (QA) y gestión de proyecto ajustadas a la complejidad media-alta del software.

$$\mathbf{Y = 150 \text{ USD/PFC}}$$

---

### 5) Determinar la cantidad de PFC por mes (Z y W)

Definimos la capacidad del equipo de desarrollo de software:
* **Tamaño del equipo (Z):** Se propone un equipo ágil y compacto de **3 personas** (1 Desarrollador Backend, 1 Desarrollador Frontend y 1 QA/Product Owner híbrido).
* **Velocidad de entrega (W):** Basado en métricas de eficiencia promedio en la industria para proyectos *Green Field* (desde cero), un equipo con experiencia intermedia puede entregar de forma segura **20 PFC por mes**.

$$\mathbf{Z = 3 \text{ personas}}$$
$$\mathbf{W = 20 \text{ PFC/mes}}$$

---

### 6) Calcular la duración del proyecto (A)

Dividimos el tamaño total del proyecto por la velocidad de entrega mensual:

$$A = \frac{X}{W} = \frac{70 \text{ PFC}}{20 \text{ PFC/mes}} = 3.5 \text{ meses}$$

Para absorber imprevistos de pruebas o despliegue, redondeamos el cronograma comercial a **4 meses**.

$$\mathbf{A = 4 \text{ meses}}$$

---

### 7) Estimar el costo total (B)

Multiplicamos el tamaño funcional total por el costo unitario por punto de función:

$$B = X \times Y = 70 \text{ PFC} \times 150 \text{ USD/PFC}$$
$$\mathbf{B = 10.500 \text{ USD}}$$

---

### Item 'Resolver'

### Estimación del tamaño del proyecto:
Utilizando el método COSMIC, se estima que el tamaño funcional total del proyecto es de **70 Puntos de Función COSMIC (PFC)**.

### Cálculo del costo por punto de función:
El costo por punto de función (CPFC) se estima en **150 USD**.

### Cantidad de puntos de función que se pueden hacer en un mes:
Se estima que un equipo de desarrollo de software de **3 personas** puede desarrollar **20 Puntos de Función COSMIC (PFC)** por mes.

### Duración del proyecto:
La duración del proyecto se estima en **4 meses**.

### Costo del proyecto:
El costo total del proyecto se estima en **10.500 USD**.
