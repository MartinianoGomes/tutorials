# Components

Os `Components` são a unidade básica de contrução de aplicações no Angular, funcionando como **blocos reutilizáveis que encapsulam a lógica, a estrutura e a estilização de partes específicas da interface do usuário, como botões, formulários ou menus**.


## Criando um Componente

Para criar um componente novo, rode:

```
ng generate component components/home
```

> `components/home` é o nome do componente e também a localização do componente.

## Estrutura dos Componentes

- home/home.component.css - Arquivo que contém todas as estilizações CSS do compoente.
- home/home.component.html - Arquivo que contém a construção em HTML do componente, ou seja, as tags html desse componente.
- home/home.component.spec - Arquivo de testes unitários para garantir o funcionamento da lógica. Verifica se está renderizando ou se o componente não está quebrado.
- home/home.component.ts - Arquivo que representa o componente e o faz visível para a aplicação Angular. Esse arquivo contém a lógica, dinamicidade, dados (estados) e comportamentos do componente. Dentro desse arquivo contém um `decorator` que indica um componente e como ele será selecionado ou quais os arquivos de estilização ou o arquivo html dele.

### Decorator

Esse decorador `@Component`, que fica acima da classe, faz com que o Angular reconheça uma classe TypeScript como um componente.

```
@Component({
    selector: 'app-home',
    standalone: true,
    imports: [],
    templateUrl: './home.component.html',
    styleUrl: './home.component.css'
})
```
`home.component.ts`

### Descrição dos Metadados

- `selector`: "tag" personalizada (ex.: `<app-home></app-home>`) que invoca esse componente dentro de outros arquivos html.
- `templateUrl` e `styleUrls`: Mapeiam os arquivos de estrutura e estilo que pertecem àquele componente.
- `standalone`: Indica que o componente é independente e não precisa estar contido em um módulo tradicional, permitindo que ele gerencie seus próprios imports e de outras ferramentas e componentes.

## Utilização de um Componente

Para que o componente esteja visível para a aplicação, é necessário importá-lo no campo `imports` do arquivo app/app.component.ts, como destacado a seguir:

```
@Component({
    ...
    imports: [RouterOutlet, HomeComponent],
    ...
})
```
`app.component.ts`

Após isso, é possível ir no arquivo app.component.html e chamar o componente. Nesse caso, esse componente geralmente é uma página que chama outros componentes e assim por diante.