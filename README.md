# Modelo de esteira CI/CD 

Este modelo usa as Github Actions para montar uma pipeline e integrar com a nuvem [Vercel](https://vercel.com/docs). Integração essa detalhada através de um [tutorial](https://vercel.com/guides/how-can-i-use-github-actions-with-vercel).

# Projeto

Projeto básico utilizando o framework Next em sua última versão.

## Instalação

Para instalar o projeto basta executar o comando:

```
npm install
```

## Execução local

Pare executar localmente o projeto basta rodar o comando listado anteriormente e logo após o seguinte comando:

```
npm run dev
```

## Qualidade

É possível verificar os padrões de qualidade do código através do ESLint, executando o seguinte comando:

```
npm run lint
```

Além disso, a execução dos testes unitários são através do comando:

```
npm run test
```

# Esteira

Dividida em dois ambientes, desenvolvimento (preview) e produção (production), cada ambiente está vinculado às mudanças de uma branch, develop e main respectivamente.

Desta forma, quando a branch develop sofre alteração, ativa a [pipeline preview](https://github.com/Rezende123/react-deployment-poc/actions/workflows/preview.yaml), que está  conectada a um projeto do Vercel responsável por realizar o deploy da aplicação no seguinte domínio: https://react-deployment-poc-development.vercel.app .

Do mesmo modo, quando a branch main sofre alteração, ativa a [pipeline production](https://github.com/Rezende123/react-deployment-poc/actions/workflows/production.yaml), que vai realizar o deploy da aplicação no seguinte domínio: https://react-deployment-poc.vercel.app

Em resumo:

- Produção: https://react-deployment-poc.vercel.app
- Desenvolvimento: https://react-deployment-poc-development.vercel.app