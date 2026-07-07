# Informações Gerais

O `Angular` é um framework web que siponibiliza um ambiente completo para desenvolvimento de aplicações robustas. Mantido pela equipe do Google. OBS.: `Programação Orientada a Objetos`.

## Guia de Instalação do Angular

Para instalar-se o Angular, é necessário ter instalado o Node em sua máquina.

```
npm install -g @angular/cli
```

> A flag `-g` simboliza que a instalação será global, ou seja, o cli será acessível de qualquer diretório.

### Verificar a versão instalada do Angular

```
ng --version
```

## Criação de um novo projeto

Para iniciar a criação de um novo projeto em Angular, no CLI, rode o comando:

```
ng new nome-do-meu-projeto
```

> Abrirá uma interface de cmd para seleção dos primeiros parâmetros do projeto.

- SSR - O HTML é criado dinamicamente no servidor a `cada requisição` do usuário, garantindo dados sempre atualizados.
- SSG - O HTML é pré-gerado uma única vez durante o `tempo de build` e servido como arquivos estáticos, resultando em carregamento mais rápido.

## Arquivos de configuração

- angular.json - Este arquivo guarda configurações do projeto Angular. Build, Serve, Testes unitários
- tsconfig.json - Configuração do Typescript, configuração global do Typescript
- tsconfig.app.json - Configurações referentes à aplicação
- tsconfig.spec.json - Configurações referentes aos testes unitários da aplicação