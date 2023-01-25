# VueBurger

Este código é um componente **Vue.js** que cria um formulário para pedir um hambúrguer. O formulário inclui campos para o nome do usuário, tipo de pão, tipo de carne e ingredientes opcionais. Quando o formulário é enviado, os dados do formulário são enviados para um servidor como uma solicitação POST.

O componente tem várias propriedades de dados, incluindo pão, carne e dados opcionais, que são inicialmente definidos como nulos e serão preenchidos com dados do servidor quando o componente for montado.

O componente também possui vários métodos:

getIngredients(): Este método busca dados de um terminal de servidor em "http://localhost:3000/ingredientes" e atribui os dados aos pães, carnes e propriedades de dados opcionais do componente.
createBurger(e): Este método é chamado quando o formulário é enviado. Ele evita o comportamento padrão de envio de formulário e constrói um objeto com os dados do formulário. O objeto é então stringificado e enviado como o corpo de uma solicitação POST para um terminal de servidor em "http://localhost:3000/burgers" e a resposta é registrada no console. Por fim, os campos de entrada do formulário são limpos.
Este componente está usando a estrutura Vue.js, que usa uma sintaxe de modelo para definir o layout do componente e um bloco de script para definir o comportamento do componente. O modelo usa as diretivas do Vue, como v-model, v-for e @submit, para vincular propriedades de dados a elementos de formulário e ouvir o evento de envio do formulário.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
