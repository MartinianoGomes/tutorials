# Routes

O conceito de `rotas` permite que você crie diferentes "páginas" e navegações dentro de uma Single Page Application (SPA).

<details>
  <summary>Como funciona uma SPA com Angular?</summary>
  
  Numa aplicação SPA com o Angular, o navegador carrega `apenas um arquivo HTML principal` e o Angular utiliza as rotas para criar "páginas virtuais" através do JavaScript, **trocando os componentes na tela sem a necessidade de recarregar a página inteira**.
</details>

## Mapeamento de Rotas

As rotas são configuradas no arquivo app.routes.ts. Nele, é definido um array de objetos onde cada item mapeia um caminho na URL para um componente. Por exemplo:

```
export const routes: Routes = [
    {
        path: "", // Raíz do domínio
        component: HomeComponent
    },
    {
        path: "home",
        component: HomeComponent
    }
];
```
`app.routes.ts`

## O Marcador `<router-outlet>`

Para que as rotas funcionem visualmente, utiliza-se a tag `<router-outlet>` no template do componente principal (normalmente o `app.component.html`). Essa tag funciona como um **espaço reservado** ou "output": é exatamente nesse local que o Angular irá injetar e mostrar o componente associado à rota que o usuário acessou no momento.

## Configuração e Provedores

Para que o sistema de roteamento seja ativado na aplicação, o Angular utiliza um módulo ou provedor específico. No arquivo de configuração global (`app.config.ts`), deve-se injetar o `providerRouter`, passando para ele as rotas que foram definidas no arquivo de mapeamento.