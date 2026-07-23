# Diretivas e Pipes

As [`Diretivas`](#diretivas) podem realizar diversas funções no sistema, **como aplicar estilos a um elemento, aplicar classes css a um elemento, etc**. Já os [`Pipes`](#pipes), são ferramentas para trabalhar com d**ados no templade do componente**.

A maioria das diretivas e pipes já vem importada junto com o `CommonModule`.

## Diretivas

As diretivas começam sempre com `ng`. Por exemplo: `ngAlgumaCoisa`, `ngStyle`, `ngClass`, etc.

Exemplo prático:

```
<h2 [ngStyle]="{ 'font-size': '12px', 'color': 'black' }">
    Testando diretiva de estilos / style
</h2>
```
`componente-generico.html`

## Pipes

Os Pipe Operators são recursos para trabalhar com dados. Aceitam um valor de entrada, processam e retornam um valor transformado.

<img src="assets/image.png" width="600px" alt="Ilustração sobre Pipes Operators" title="Pipes Operators">

- Pipes são definidos usando o símbolo pipe "|". Mas, é possível criar pipes personalizados.
- Podem ser encadeados com outros pipes.
- Podem receber argumentos usando o símbolo de dois pontos (:).

### Principais Pipes

- DatePipe: Formata um valor de data.
- UpperCasePipe: Transforma um texto em caixa alta.
- LouwerCasePipe: Transforma um texto em caixa baixa.
- CurrencyPipe: Transforma um número para uma string de moeda.
- DecimalPipe: Transforma um número numa string com um ponto decimal.
- PercentPipe: Tranforma um número para uma string percentual.

### Pipes Customizados

O Angular permite criar e customizar pipes para mais variações de tranformação e formas de trabalhar os dados.

Para criar um pipe, basta rodar o comando:

```
npx ng generate pipe <nomedopipe>
```

Exemplo prático:

```
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'stringInverter',
})
export class StringInverterPipe implements PipeTransform {
  nvalue: string | null = null;

  transform(value: any, ...args: unknown[]): unknown {
    this.nvalue = value.split('').reverse().join('');
    return this.nvalue;
  }
}
```
`string-inverter-pipe.ts`