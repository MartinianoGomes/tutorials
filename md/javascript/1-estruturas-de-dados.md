# Estruturas de Dados do Javascript

## Funções

Uma função é um bloco de instruções que pode ser executado e reutilizado. Uma função pode rececber dados e retorna outro valor.

- Ao `criar` uma função, você pode definir `parâmetros`.
- Ao `executar` uma função, você pode passar `argumentos`.

```js
// lado é um parâmetro
function areaQuadrado(lado) {
    const area = lado * lado;
    return area;
}

// 5 é um argumento
areaQuadrado(5);
```