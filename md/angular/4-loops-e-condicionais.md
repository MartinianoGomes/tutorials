# Loops e Condicionais

No Angular, `loops` e `condicionais` são ferramentas de controle de fluxo que permitem manipular o que é exibido no HTML com base na lógica do TypeScript. Também conhecido como `Flow Control`.

Obs.: Nas versões mais recentes do Framework, foi instroduzida uma nova sintaxe (chamada de *Control Flow*) que utiliza o símbolo `@` para tornar o código mais limpo e intuitivo.

## Condicionais

Os condicionais permitem mostrar ou esconder elementos da tela dependendo de uma condição booleana ou lógica.

- **Sintaxe Atual**: Utiliza-se o bloco `@if`. Se a condição for verdadeira, o conteúdo dentro das chaves é renderizado.
- **Complementos**: É possível adicionar os blocos `@else if` e `@else` para tratar casos onde a primeira condição não é atendida.

```
export class HomeComponent {
    name = "Julia"
    deveMostrarTitulo = true;
}
```
`home.component.ts`

### Nova sintaxe

```
@if(deveMostrarTitulo){
    <h1>Meu titulo</h1>
} @else if (name == "Julia") {
    <h1>Meu titulo para Julia</h1>
} @else {
    <h1>Não foi verdadeiro</h1>
}
```
`home.component.html`

### Antiga sintaxe

```
<h1 *ngIf="deveMostrarTitutlo">Meu titulo</h1>
<h1 *ngIf="!deveMostrarTitulo">Não deu certo</h1>
```
`home.component.html`

## Loops

Os loops são usados para repetir um elemento HTML várias vezes, geralmente para exibir uma lista de dados vinda de um array.

- **Sintaxe Atual**: Utiliza-se o bloco `@for`. A estrutura básica é `@for (item of listaItems; track item.id)`. Ele serve para indicar ao Angular como rastrear cada item da lista (geralmente através de um ID único). Isso é fundamental para que, caso a lista mude, o Angular saiba exatamente qual elemento atualizar na interface, garantindo **performance e renderização correta**.

```
export class HomeComponent {
    name = "Julia"
    deveMostrarTitulo = true;
    listItems = [
        {
            id: 0,
            nome: "Maçã"
        },
        {
            id: 1,
            nome: "Laranja"
        },
        {
            id: 2,
            nome: "Abacaxi"
        }
    ];
}
```
`home.component.ts`

### Nova sintaxe

```
@for (item of listItems; track item.id) {
    <p>{{item}}</p>
}
```
`home.component.html`

### Antiga sintaxe

```
<p *ngFor="let item of listItems">{{item}}</p>
```
`home.component.html`