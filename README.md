# Melhorando seu workflow com Git Hooks

>Não Importa se você trabalha sozinho, em um time ou se só coda por hobbie. Escrever um código padronizado e limpo é sua obrigação!

<p align="center">
  <img src="./docs/clean-code.jpeg">
</p>

## TL;DR
O Git Husky é uma ferramenta que vai dar um boost no seu workflow, testar seu código, seu styleguide e ai sim, se estiver tudo certo, vai subir seu código para a produção.

<p align="center">
  <img style="text-align: center;" src="./docs/uau.gif">
</p>

Antes de explicar como a ferramenta funciona, vou falar sobre alguns pontos positivos e negativos sobre a padronização do seu código.

#### Pontos positivos:

* Um código com melhor legibilidade;

* Facilidade de manutenção;

* Código escalável;

* Menos bugs;

* Redução do tempo (e custo) do projeto;

* Um chefe feliz;

* E menos dor de cabeça.


#### Pontos negativos:

SE, numa sexta-feira, você não seguiu o padrão de código proposto pelo projeto, eis o ponto negativo:

* Sem HappyHour pra você :)

SENÃO não existem pontos negativos!

<p align="center">
  <img src="./docs/stronda.jpg">
  <p align="center">"Caralho, o maluco é brabo" - Stronda, Leo.</figcaption>
</p>

## Chega de enrolação e vamos ao código!

Irei exemplificar essa melhoria no seu workflow com o as seguintes ferramentas:

* [ESLint](https://eslint.org/)

>ESLint é um linter de código JavaScript, um projeto Open Source feito originalmente pelo Nicholas C. Zakas em 2013. A função do linter de código é analisar e detectar problemas no seu padrão de código e também verificar se o mesmo se encontra nos padrões de sua styleguide.

* [GitHusky](https://github.com/typicode/husky)

>O Git Husky nada mais é que um githook de forma facilitada. Um pouco mais recente, seu primeiro commit foi dia '23 Jun 2014' e foi criado por um usuário do github chamado Typicode.

## Parte 1 - definindo seu styleguide com ESLint

No diretório do seu projeto, inicie a instalação da ferramente ESLint com o commando:

```
  npm install eslint --save-dev
```

<p align="center">
  <img src="./docs/eslint-install.jpg">
</p>

Após a instalação, precisaremos definir o padrão do seu linter de código. Eu, particularmente, escolhi o styleguide do [AirBnB](https://github.com/airbnb/javascript). Iremos iniciar o padrão do seu styleguide com os seguintes passos:

```
  ./node_modules/.bin/eslint --init
```
<p align="center">
  <img src="./docs/eslint-init.jpg">
</p>

Com as setas, escolheremos então a opção 'Use a popular style guide' e apertaremos enter:

<p align="center">
  <img src="./docs/eslint-popular.jpg">
</p>

E 'setaremos' o estilo do AirBnB:

<p align="center">
  <img src="./docs/eslint-airbnb.jpg">
</p>

Nesse caso, não estarei usando o React, então eu respondo com 'N' a próxima etapa:

<p align="center">
  <img src="./docs/eslint-n.jpg">
</p>

E então será escolhido o formato do arquivo .eslintrc, que será gerado pelo linter. Eu sempre prefiro usar a extensão .json:

<p align="center">
  <img src="./docs/eslint-json.jpg">
</p>

Será instalado alguns plugins adicionais e pronto, seu linter está pronto para uso:

<p align="center">
  <img src="./docs/eslint-pronto.jpg">
</p>

## Parte 2 - Criando seu script npm de teste

A parte anterior foi unicamente ensinando como aplicar o ESlint no seu projeto, agora iremos fazer um NPM Script que verifique seu código! :)