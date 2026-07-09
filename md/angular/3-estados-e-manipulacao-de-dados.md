# Estados

No Angular, os `estados` representam as informações dinâmicas dentro de um componente, enquanto a `manipulação de dados` refere-se a como esses valores são exibidos, alterados e compartilhados.

## O que são Estados em um Componente

Sãp `atributos (propriedades) de uma classe` que armazenam dados que podem mudar ao longo do tempo, como títulos, valores de campos ou resultados.

- **Declaração**: São definidos dentro da classe do componente no TupeScript (Ex.: `meuBoleano: boolean = false`).
- **Atualização**: Para modificar um estado, criamos métodos na classe que alteram esses atributos sando a palavra-chave `this` (Ex.: `this.meuBoleano = true`).

# Manipulação e Exibição de Dados

A interação entre a lógica (TypeScript) e a interface (HTML) ocorre através de diferentes tipos de *binding - ligações, conectivos*:

- **Interpolação ( `{{ }}` )**: É a forma mais simples de `exibir dados` da classe diretamente no template HTML.
- **Property e Attribute Binding ( `[ ]` )**: Utilizado para passar valores da classe para atributos HTML.
    - Para atributos nativos (como `id` ou `src`), usa-se `[id]="valor"`.
    - Para atributos não nativos ou de acessibilidade (como `aria-label` ou `data-*`) usa-se o prefixo `attr.` (Ex.: `[attr.aria-label]="meuTitulo"`).
- **Event Binding ( `( )` )**: Usado para **reagir a eventos** do usuário, como cliques em botões.
    - A sintaxe utiliza parênteses em volta do evento: `(click)="minhaFuncao()"`.
    - É possível capturar o contexto do evento (como a posição do mouse ou dados de formulário) passando o parâmetro especial `$event` para a função.

# Comunicação de Dados entre Componentes

- `@Imput()` **(Pai para Filho)**: Permite que um componente receba dados externos. No componente filho, decora-se um atributo com `@Input()`; o componente pai, então, "injeta" o valor através de colchetes no HTML (Ex.: `[nome]="valor"`).
- `@Output()` e `EventEmitter` **(Filho para Pai)**: Usado quando o componente filho precisa enviar dados para o pai.
    - O filho cria um emissor de eventos **(`EventEmitter`)** e "emite" uma informação em um determinado momento (como um clique).
    - O pai escuta esse evento usando a sintaxe de parênteses, como se fosse um evento nativo do HTML.

```
<button (click)="submit($event)">Clique aqui</button>
```
`home.component.html`