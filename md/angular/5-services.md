# Services

No Angular, os **Services** são a forma de **compartilhar lógica** entre diferentes componentes da aplicação. Enquanto os componentes focam na exibição de dados e na interface, os Services lidam com tarefas que precisam ser reutilizadas ou que envolvem processamento de dados.

## Aplicabilidade

O principal motivo é evitar a **duplicação de código**. Se você tem uma lógica (como uma chamada para um backend ou a formatação de um formulário) que precisa ser usada tanto no `HomeComponent` quanto no `AppComponent`, em vez de escrever o mesmo código duas vezes, você cria um Service centralizado que ambos podem acessar.

## Estrutura e Criação

Um Service é basicamente uma classe TypeScript. Para criá-lo de forma padronizada, utiliza-se a CLI com o comando `ng generate service nome-do-service` (ou de forma abreviada: `ng g s nome-do-service`).

Sua estrutura principal inclui:

- **Decorador `@Injectable`**: Assim como os componentes usam o `@Component`, os Services usam o `@Injectable` para indicar ao Angular que essa classe pode ser "injetada" em outros lugares.
- **Metadado `providedIn: 'root'`**: Por padrão, os Services são configurados com `providedIn: 'root'`, o que significa que o Angular cria uma única instância do service que fica **acessível por toda a aplicação**.

## Utilização do Componente (Injeção)

Para que um componente consiga usar as funções de um Service, ele precisa **injetar** esse Service. Nas versões atuais do Angular, isso é feito de forma simples:

- Importa-se a função `inject` do `@angular/core`.
- Dentro da classe do componente, cria-se um atributo (geralmente privado) para receber a instância do service;

```
private meuService = inject(NomeDoService);
```
`meu-service.service.ts`

- A partir daí, você pode chamar os métodos do service dentro das funções do componte.

```
this.meuService.enviarDados();
```
`home.component.html`