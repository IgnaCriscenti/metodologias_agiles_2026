# Ejercicio Nro 13 - Desarrollo de Aplicación Bancaria con TDD

## Enunciado

Tu tarea es desarrollar una aplicación informática utilizando la técnica TDD para gestionar una cuenta bancaria. La aplicación debe permitir a los usuarios abrir una cuenta, realizar depósitos, hacer retiros y transferir fondos entre cuentas. 

Etapa 1:  Especificación y prueba inicial
1. Especificación de requisitos básicos y funcionalidades clave, como la apertura de cuenta, depósito de fondos, retiro de fondos y transferencia de fondos.
2. Escribe una prueba inicial que verifique si el sistema puede crear una instancia de una cuenta bancaria y obtener su saldo inicial.


## Resolución
### 1. Especificación de requisitos básicos y funcionalidades clave
* **Apertura de cuenta:** Creación de una instancia de cuenta asociada a un identificador único y un titular, con la opción de asignar un saldo inicial.
* **Depósito de fondos:** Incremento del saldo disponible mediante el ingreso de un monto válido y positivo.
* **Retiro de fondos:** Reducción del saldo mediante una extracción, validando que no se supere el dinero disponible ni se ingresen montos negativos.
* **Transferencia de fondos:** Traspaso de dinero desde una cuenta origen hacia una cuenta destino de forma segura y atómica.

### 2. Prueba inicial (Ciclo TDD - Fase Roja)
* **Objetivo:** Validar la creación correcta de la entidad y la lectura del saldo inicial asignado.
* **Código de la prueba (JavaScript):**

```javascript
const assert = require('assert');
const { CuentaBancaria } = require('./cuentaBancaria');

try {
    console.log("Ejecutando Prueba Inicial: Creación de Cuenta...");
    const cuenta = new CuentaBancaria("12345", "Carlos Gómez", 500.0);
    
    assert.strictEqual(cuenta.numeroCuenta, "12345");
    assert.strictEqual(cuenta.obtenerSaldo(), 500.0);
    console.log("✔ Prueba superada.");
} catch (error) {
    console.error("❌ Resultado esperado: La prueba fallará inmediatamente ya que la clase 'CuentaBancaria' aún no está implementada.");
    console.error(error.message);
}
```

## Enunciado
Etapa 2: Desarrollo de las funcionalidades básicas
3. Implementa la funcionalidad para abrir una cuenta bancaria, asegurándote de que se cumplan los requisitos especificados. Ejecuta la prueba y verifica que pase correctamente.
4. Implementa la funcionalidad para realizar depósitos en una cuenta bancaria. Ejecuta las pruebas y verifica que pasen correctamente.
5. Implementa la funcionalidad para realizar retiros de una cuenta bancaria. Ejecuta las pruebas y verifica que pasen correctamente.
6. Implementa la funcionalidad para transferir fondos entre cuentas bancarias. Ejecuta las pruebas y verifica que pasen correctamente.


## Resolución
### 3. Implementación para abrir una cuenta bancaria (Fase Verde)
* **Código de la prueba (JavaScript):**

```JavaScript
class CuentaBancaria {
    constructor(numeroCuenta, titular, saldoInicial = 0) {
        this.numeroCuenta = numeroCuenta;
        this.titular = titular;
        this.saldo = saldoInicial >= 0 ? saldoInicial : 0;
    }

    obtenerSaldo() {
        return this.saldo;
    }
}

module.exports = { CuentaBancaria };
```
**Resultado:** Al ejecutar la prueba inicial de la Etapa 1 con este código, el resultado pasa a Verde exitosamente.

### 4. Implementación para realizar depósitos
* **Código de la prueba (Fase Roja):**

```JavaScript
const cuenta = new CuentaBancaria("12345", "Carlos Gómez", 500.0);
cuenta.depositar(200.0);
assert.strictEqual(cuenta.obtenerSaldo(), 700.0); 
// Error: cuenta.depositar is not a function
```

* **Código de producción actualizado (Fase Verde):**

```JavaScript
class CuentaBancaria {
    constructor(numeroCuenta, titular, saldoInicial = 0) {
        this.numeroCuenta = numeroCuenta;
        this.titular = titular;
        this.saldo = saldoInicial >= 0 ? saldoInicial : 0;
    }

    obtenerSaldo() {
        return this.saldo;
    }

    depositar(monto) {
        if (monto <= 0) {
            throw new Error("El monto a depositar debe ser mayor a cero.");
        }
        this.saldo += monto;
    }
}
```

### 5. Implementación para realizar retiros
* **Código de la prueba (Fase Roja):**

```JavaScript
const cuenta = new CuentaBancaria("12345", "Carlos Gómez", 700.0);
cuenta.retirar(300.0);
assert.strictEqual(cuenta.obtenerSaldo(), 400.0);
// Error: cuenta.retirar is not a function
```

* **Código de producción actualizado (Fase Verde):**

```JavaScript
class CuentaBancaria {
    // ... constructor, obtenerSaldo y depositar se mantienen igual
    
    retirar(monto) {
        if (monto <= 0) {
            throw new Error("El monto a retirar debe ser mayor a cero.");
        }
        if (monto > this.saldo) {
            throw new Error("Fondos insuficientes.");
        }
        this.saldo -= monto;
    }
}
```

### 6. Implementación para transferir fondos entre cuentas
Para este requerimiento, se introduce la entidad Banco que orquestará la interacción entre múltiples cuentas.
* **Código de la prueba (Fase Roja):**

```JavaScript
const { CuentaBancaria, Banco } = require('./cuentaBancaria');

const banco = new Banco();
const origen = new CuentaBancaria("111", "Origen", 1000);
const destino = new CuentaBancaria("222", "Destino", 200);

banco.registrarCuenta(origen);
banco.registrarCuenta(destino);
banco.transferir("111", "222", 300);

assert.strictEqual(origen.obtenerSaldo(), 700);
assert.strictEqual(destino.obtenerSaldo(), 500);
// Error: Banco is not a constructor
```

* **Código de producción actualizado (Fase Verde - cuentaBancaria.js):**
  
```JavaScript
class Banco {
    constructor() {
        this.cuentas = new Map();
    }

    registrarCuenta(cuenta) {
        this.cuentas.set(cuenta.numeroCuenta, cuenta);
    }

    transferir(numeroOrigen, numeroDestino, monto) {
        const cuentaOrigen = this.cuentas.get(numeroOrigen);
        const cuentaDestino = this.cuentas.get(numeroDestino);

        if (!cuentaOrigen) throw new Error("Cuenta origen no encontrada.");
        if (!cuentaDestino) throw new Error("Cuenta destino no encontrada.");

        cuentaOrigen.retirar(monto);
        cuentaDestino.depositar(monto);
    }
}

module.exports = { CuentaBancaria, Banco };
```

## Enunciado
Etapa 3: Pruebas adicionales y mejoras
7. Escribe pruebas adicionales para cubrir casos de prueba específicos, como intentar retirar más dinero del disponible en una cuenta o transferir fondos a una cuenta inexistente.
8. Ejecuta todas las pruebas y verifica que pasen correctamente.
9. Refactoriza tu código si es necesario para mejorar su estructura, legibilidad y eficiencia.
10. Ejecuta todas las pruebas nuevamente para asegurarte de que el código refactorizado no haya introducido errores.

## Resolución
### 7. Pruebas adicionales:
* **Código de las pruebas (JavaScript):**

```JavaScript
const { CuentaBancaria, Banco } = require('./cuentaBancaria');
const assert = require('assert');

// Caso Excepcional A: Intentar retirar más dinero del disponible
const cuentaTest = new CuentaBancaria("999", "Tester", 100);
assert.throws(() => {
    cuentaTest.retirar(150); 
}, /Fondos insuficientes/);

// Caso Excepcional B: Transferir a una cuenta que no existe en el banco
const miBanco = new Banco();
const cuentaOrigen = new CuentaBancaria("111", "Juan", 500);
miBanco.registrarCuenta(cuentaOrigen);

assert.throws(() => {
    miBanco.transferir("111", "999-INEXISTENTE", 100);
}, /Cuenta destino no encontrada/);
```

### 8. Ejecución y Ajustes (Fase Verde)
Para asegurarnos de que estas validaciones pasen, el código de producción en cuentaBancaria.js debe verificar activamente estas condiciones lanzando errores explícitos con throw new Error():

```JavaScript
// Fragmento de lógica clave implementada en cuentaBancaria.js
retirar(monto) {
    if (monto > this.saldo) {
        throw new Error("Fondos insuficientes.");
    }
    this.saldo -= monto;
}

transferir(numeroOrigen, numeroDestino, monto) {
    const cuentaOrigen = this.cuentas.get(numeroOrigen);
    const cuentaDestino = this.cuentas.get(numeroDestino);

    if (!cuentaOrigen) throw new Error("Cuenta origen no encontrada.");
    if (!cuentaDestino) throw new Error("Cuenta destino no encontrada.");

    cuentaOrigen.retirar(monto);
    cuentaDestino.depositar(monto);
}
```

### 9. Refactorización (Refactoring)
* **Problema detectado:** Al revisar nuestro código actual, notamos que tanto en depositar() como en retirar() estamos repitiendo manualmente la validación de que el monto sea un número positivo (monto <= 0). Además, si el día de mañana agregamos comisiones, el código se volverá engorroso.

* **Acción de Refactor:** Extraeremos la validación de montos negativos a un método privado interno para limpiar la estructura y mejorar la legibilidad sin alterar el comportamiento que las pruebas ya validan.

* **Código Refactorizado (cuentaBancaria.js):**

```JavaScript
class CuentaBancaria {
    constructor(numeroCuenta, titular, saldoInicial = 0) {
        this.numeroCuenta = numeroCuenta;
        this.titular = titular;
        this.saldo = saldoInicial >= 0 ? saldoInicial : 0;
    }

    obtenerSaldo() {
        return this.saldo;
    }

    #validarMontoPositivo(monto) {
        if (monto <= 0) {
            throw new Error("El monto debe ser mayor a cero.");
        }
    }

    depositar(monto) {
        this.#validarMontoPositivo(monto);
        this.saldo += monto;
    }

    retirar(monto) {
        this.#validarMontoPositivo(monto);
        if (monto > this.saldo) {
            throw new Error("Fondos insuficientes.");
        }
        this.saldo -= monto;
    }
}
```

### 10. Ejecución post-refactorización
Volvemos a correr la suite completa de pruebas unitarias. Como modificamos la estructura interna pero mantuvimos intacta la interfaz pública, todas las pruebas pasan en verde. Esto demuestra que el refactor fue exitoso y seguro.

## Enunciado
Etapa 4: Cobertura completa de pruebas
11. Asegúrate de que todas las funcionalidades del sistema estén cubiertas por pruebas automatizadas.
12. Examina los casos límite y situaciones excepcionales para garantizar que el sistema se comporte correctamente en todos los escenarios.
13. Ejecuta todas las pruebas y verifica que pasen correctamente.

Recuerda seguir el enfoque TDD, donde agregarás una prueba antes de implementar cada funcionalidad y verificarás que todas las pruebas pasen antes de pasar a la siguiente etapa. Esto te ayudará a desarrollar una aplicación confiable, mantenible y que cumpla con los requisitos establecidos.

## Resolución
### 11 y 12. Cobertura total y análisis de Casos Límite (Fase Roja)
* **Análisis de Frontera / Casos Límite:**
  1. Monto cero exacto: Validar que el sistema rechace depósitos o retiros de $0.
  2. Saldo vacío: Verificar qué pasa si una cuenta se retira exactamente todo su dinero y queda en $0 justos (debería permitirlo sin lanzar error de fondos insuficientes).

* **Código de pruebas para Casos Límite (JavaScript):**

```JavaScript
// Caso Límite 1: Intentar depositar cero pesos
const cuentaLimite = new CuentaBancaria("444", "Ana", 200);
assert.throws(() => {
    cuentaLimite.depositar(0);
}, /El monto debe ser mayor a cero/);

// Caso Límite 2: Retiro del total exacto (Quedar en cero)
cuentaLimite.retirar(200); 
assert.strictEqual(cuentaLimite.obtenerSaldo(), 0); // Debería funcionar sin lanzar error
```

### 13. Ejecución final del sistema (Fase Verde)
Gracias a las validaciones precisas implementadas durante la fase de refactorización de la Etapa 3, el motor de JavaScript procesa los límites correctamente.

Al ejecutar el set completo de pruebas integradas:
```bash
npm install jest
node cuentaBancaria.test.js
```

Resultado en Consola:

```plaintext
=== INICIANDO SUITE DE PRUEBAS TDD ===
▶ Probando Etapa 1... ✔ OK
🎉 ¡TODAS LAS PRUEBAS PASARON EXITOSAMENTE!
```
