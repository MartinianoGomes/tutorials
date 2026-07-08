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
    }
];
```
`app.routes.ts`