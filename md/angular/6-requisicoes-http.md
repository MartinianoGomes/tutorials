# Requisições HTTP

**Requisições HTTP** permitem uma aplicação rodando no navegador se comunicar com um servidor externo para buscar dados (response) e exibi-los ao usuário.

## Service `HttpClient`

Diferente de outras bibliotecas como Axios ou a Fetch API nativa, o Angular utiliza um serviço próprio chamado `HttpClient` para gerenciar todas as chamadas assíncronas. Ele suporta os métodos padrão do protocolo, como `GET`, `POST`, `PUT`, `PATCH` e `DELETE`.

## Configuração (Padrão Standalone)

Para que as funcionalidades de HTTP fiquem disponíveis no projeto, é obrigatório configurar o provedor `provideHttpCLient` no arquivo de configuração global `app.config.ts`.

## Implementação

Recomenda-se fortemente nunca colocar a **lógica de requisição diretamente no componente**. Em vez disso, deve-se criar um **Service**dedicado para centralizar essas chamadas, o que torna o código mais modular, organizado e fácil de manter.

## Observables e Inscrição

As funções do `HttpClient` retornam um objeto chamado **Observable** (da biblioteca RxJS). Para que a requisição seja efetivamente disparada e os dados sejam recebidos, o desenvolvedor precisa se "inscrever" nesse Observable através do método `.subscrive()`.

- **Sucesso**: O primeiro parâmetro do `.subscrive()` é uma função executada quando a requisição retorna os dados corretamente.
- **Erro**: O sistema também permite tratar falhas, como servidores indisponíveis ou dados inválidos.

## Tipagem com Interfaces

Para garantir a segurança do código (TypeScript), é interessante criar **Interfaces** que representem exatamente a estrutura dos dados esperados da API (Ex.: um objeto com `id`, `title` e `body`). Ao tipar o retorno do método no Service, o componente passa a "saber" exatamente com quais dados está trabalhando, evitando erros de compilação.