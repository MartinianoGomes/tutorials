# Fundamentos do Javascript

## Variáveis

Variáveis são usadas para armazenar valores na memória.

``` js
var cidade = "Rio de Janeiro";
let nome = "Martiniano";
const idade = 21;
```

As variáveis `var` e `let` podem ser alteradas durante o curso do programa. Já a `const` não pode ser alterada.

###

## Tipos de dados

Os tipos de dados em javascript são: `String`, `Number`, `Boolean`, `Undefined`, `Null`, `Symbol` e `Object`. Todos esses, exceto **Object**, são primitivos.

```js
// String
const nome = 'Martiniano';

// Number
const idade = 21;

// Boolean
const isTrue = true;

// Null
const variavelNula = null;

// Symbol
const id = Symbol("id");

// Object
const pessoa = {};
```

`Undefined` aparece quando uma variável não tem valor.

###

## Operadores

```js
let x;
x = 10; // x é igual a 10! Recebeu o valor.
x == 10; // x é igual a 10? Comparando o valor.
x === 10; // verifica estritamente se é igual no valor e no tipo da variável.
```

###

## Condicionais

```js
const n1 = 0

if (n1 === 0) {
    console.log(true);
} else {
    console.log(false);
}

if (!n1) console.log(false);
```