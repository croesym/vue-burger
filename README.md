# VueBurger

<h1> Home Page </h1>
Este código é um componente **Vue.js** que cria um formulário para pedir um hambúrguer. O formulário inclui campos para o nome do usuário, tipo de pão, tipo de carne e ingredientes opcionais. Quando o formulário é enviado, os dados do formulário são enviados para um servidor como uma solicitação POST.

O componente tem várias propriedades de dados, incluindo pão, carne e dados opcionais, que são inicialmente definidos como nulos e serão preenchidos com dados do servidor quando o componente for montado.

![Vueburger](https://user-images.githubusercontent.com/87200550/214623352-f83ab583-3c62-4335-bf6c-944c7b5439e1.png)

O componente também possui vários métodos:

**getIngredients()**: Este método busca dados de um terminal de servidor em "http://localhost:3000/ingredientes" e atribui os dados aos pães, carnes e propriedades de dados opcionais do componente.
<br>

**createBurger(e)**: Este método é chamado quando o formulário é enviado. Ele evita o comportamento padrão de envio de formulário e constrói um objeto com os dados do formulário. O objeto é então stringificado e enviado como o corpo de uma solicitação POST para um terminal de servidor em "http://localhost:3000/burgers" e a resposta é registrada no console. Por fim, os campos de entrada do formulário são limpos.
<br>

Este componente está usando a estrutura Vue.js, que usa uma sintaxe de modelo para definir o layout do componente e um bloco de script para definir o comportamento do componente. O modelo usa as diretivas do Vue, como v-model, v-for e @submit, para vincular propriedades de dados a elementos de formulário e ouvir o evento de envio do formulário.

<br>
<h1> Pedidos </h1>
Este é um código de componente Vue.js que define uma tabela para exibir e gerenciar pedidos de hambúrgueres. O componente tem um template HTML que define a aparência da tabela e um script que define sua funcionalidade.

![vueDashboard](https://user-images.githubusercontent.com/87200550/215557734-1e8c4672-56d5-44bc-80b7-3993caaee1b3.png)

O script define a seguinte lógica:

O componente tem uma propriedade de data chamada "burgers", que armazena os dados dos pedidos.

O componente tem vários métodos que realizam ações na tabela, como exibir, atualizar e excluir pedidos. Esses métodos fazem solicitações HTTP para uma API com as informações dos pedidos.

O componente importa outro componente chamado OrderMessage para exibir mensagens de sucesso ou erro para o usuário.

O componente é montado chamando o método getOrders(), que busca os dados dos pedidos da API e atualiza a propriedade "burgers".

A tabela exibe informações dos pedidos, como número do pedido, nome do cliente, pão, carne e opcionais. Há também uma caixa de seleção para atualizar o status do pedido e um botão para cancelar o pedido.




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
npm run backend
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```
