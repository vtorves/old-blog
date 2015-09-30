---
published: true
author: Vinicius Torves
layout: post
title: "Debugando a Aplicação com Pry"
date: 2014-07-04 16:30
comments: true
categories:
  - Vinicius Torves
  - ruby
  - rails
  - debug
  - pry
  - gem
---
Uma das perguntas mais comuns é:
 "O que devo saber para começar com rails?"
 Rails é um framework escrito com Ruby e possui uma sintaxe bastante amigável,
  e com ela fazemos [MÁGICAS](http://hemobile.com.br/magica/)
. =)

<!--more-->

Para trabalharmos com ele e sermos bastante produtivos, buscamos explorar o
 melhor dele,  e com essa evolução surgiram varias [gems](http://en.wikipedia.org/wiki/RubyGems) que nos auxiliam
 diariamente a escrever [melhor o código](https://github.com/bbatsov/rubocop), nos [mostra erros](https://github.com/charliesome/better_errors),
  pontos sem coberturas de [testes](https://github.com/colszowka/simplecov), [debugar](http://pryrepl.org) e permitir que o cliente tenha mais
   segurança e qualidade.

Mas como podemos debugar rapidamente?
Vou falar aqui um pouco sobre uma gem bastante utilizada pela comunidade para debug código ruby: o PRY, você pode substituir o irb padrão, por ele e ser mais feliz, com seus diversos recursos.

## Primeiros passos, vamos explorar o brackpoint:
Após [instalado](https://github.com/pry/pry#use-pry-as-your-rails-console) no seu
rails insira o texto: **'binding.pry' ** onde você desejar dentro do seu código para poder parar a execução do código e start o servidor.

No exemplo abaixo eu coloquei no método index do controller, repare na linha 4, este símbolo** '=>' ** indica onde você está.

Tornando-o muito útil caso você tenha mais de um **binding.pry** inserido no código.

![Imagem 1](/images/posts/2014-07-04/binding-pry.png "Imagem - Binding.pry")

A navegação pelo pry é similar ao terminal que já usamos, sendo bem legal e intuitivo, permitindo o uso de TAB para auto-complete, cd para entrar (literalmente) no objeto e poder explorá-lo mais. Para obter uma lista mais detalhada dos comandos, ** digite 'help'  < enter >**


![Imagem 2](/images/posts/2014-07-04/help-pry.png "help - ls")

Para ver uma lista de métodos e variáveis acessíveis naquele momento basta ** digitar 'ls'< enter >**


![Imagem 3](/images/posts/2014-07-04/ls-pry.png "Imagem - ls")

Verificar em que método estamos no momento :** show-method  < enter >**

![Imagem 4](/images/posts/2014-07-04/show-method-pry.png "Imagem - show-method")

E para verificar o conteúdo de @situations ? digitando **@situations < enter >**

![Imagem 5](/images/posts/2014-07-04/situation-pry.png "Imagem - @situation")

Pronto, está listando como esperamos =)

Podemos também verificar os parâmetros apenas, digitando **params < enter >**
Ótimo para vermos os dados de GET e POST.

![Imagem 6](/images/posts/2014-07-04/params-pry.png "Imagem - params")

Estando tudo certo, podemos então remover o binding.pry  usando o editor (SIM! É POSSIVEL!)
**edit SituationsController#index  < enter >**

![Imagem 7](/images/posts/2014-07-04/edit-text-pry.png "Imagem - edit")

Após editado e salvo, você pode encerrar o ciclo usando **exit < enter >** para sair e ele pulará para o
 próximo **'binding.pry'** ou seguir seu fluxo esperado.

Este foi um dos diversos exemplos possíveis, você pode usar ele também com o RSPEC e  explorar diversos outros recursos e plugins disponíveis, turbinando seu pry para por exemplo: procurar documentação ruby e até compartilhar código no GIST.

 Leia mais aqui: https://github.com/pry/pry e torne seu ambiente mais produtivo.

Até a próxima!
