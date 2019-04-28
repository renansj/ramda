Ramda
=============

Uma biblioteca funcional prática para desenvolvedores JavaScript

[![Build Status](https://travis-ci.org/ramda/ramda.svg?branch=master)](https://travis-ci.org/ramda/ramda)
[![npm module](https://badge.fury.io/js/ramda.svg)](https://www.npmjs.org/package/ramda)
[![dependencies](https://david-dm.org/ramda/ramda.svg)](https://david-dm.org/ramda/ramda)
[![Gitter](https://badges.gitter.im/Join_Chat.svg)](https://gitter.im/ramda/ramda?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)



Por que Ramda?
----------

<img src="https://ramdajs.com/ramdaFilled_200x235.png" 
     width="170" height="190" align="right" hspace="12" />

Já existem várias bibliotecas funcionais excelentes, tipicamente, elas são supostamente feitas para ser um conjunto de ferramentas de general-purpose(propósitos gerais), adequadas para funcionarem em múltiplos paradigmas. Ramda tem um foco mais específico, nós queremos uma biblioteca projetada especificamente para o paradigma funcional, uma que deixa fácil criar pipelines funcionais, uma que nunca deixe os dados dos usuários mutáveis.

Qual a diferença?
-----------------

As características primárias que distinguem Ramda são:

* Ramda enfatiza um estilo funcional puro. A ausência de Imutabilidade e side-effect(efeitos colaterais) são o coração da filosofia do design. Isso pode ajudá-lo a fazer o seu trabalho com um código simples e elegante.

* As funções em Ramda são automaticamente curried(que é basicamente uma maneira de informar para a função os parâmetros de forma parcial, você pode injetar os parâmetros a medida que os mesmo ficarem disponíveis). Isso permite a você escrever novas funções a partir das antigas sem a necessidade de fornecer parâmetros finais.

* Os parâmetros para funções em Ramda são predispostos para fazê-los serem convenientes para o currying. Os dados a serem trabalhados geralmente são fornecidos por último. 

Os dois últimos pontos juntos deixam muito fácil criar funções como sequencias de funções mais simples, Cada um deles transforma os dados e passa ao próximo. Ramda é projetada para suportar esse estilo de código.


Introdução

-------------

* [Introducing Ramda](http://buzzdecafe.github.io/code/2014/05/16/introducing-ramda) por Buzz de Cafe
* [Why Ramda?](http://fr.umio.us/why-ramda/) por Scott Sauyet
* [Favoring Curry](http://fr.umio.us/favoring-curry/) por Scott Sauyet
* [Why Curry Helps](https://hughfdjackson.com/javascript/why-curry-helps/) por Hugh Jackson
* [Hey Underscore, You're Doing It Wrong!](https://www.youtube.com/watch?v=m3svKOdZijA&app=desktop) por Brian Lonsdorf
* [Thinking in Ramda](http://randycoulman.com/blog/categories/thinking-in-ramda) por Randy Coulman


Filosofia
----------
Usar Ramda deveria ser como usar Javascript.
É práticamente, Javascript funcional. Não iremos apresentar expressões lambdas em 
Strings, não estamos pegando emprestadas *consed lists*, não estamos portando Clojures.

Nossas estruturas de dados báscias são objetos Javascript puros, a nossas *colletions* são arrays.
Nós também mantemos outras features de Javascript, tais como funções como objetos com propriedades.

Programação funcional é boa parte sobre objetos imutáveis e funções livres de *side-effects*.
Enquanto Ramda não impõe isso, te permite tal estilo sem o menor atrito possível.

Nós buscamos uma implementação tanto quanto elegante e limpa, mas a peça chave é a API.
Nós sacrificamos uma grande parte da elegância da implementação por uma API um pouco mais limpa.

Por último mas não menos importante, Ramda tem grande empenho em performance. Uma implementação 
confiável e rápida supera qualquer noção de pureza funcional.

Instalação
------------

Para usar com node:

```bash
$ npm install ramda
```

Então no console:

```javascript
const R = require('ramda');
```

Para usar diretamente no *browser*:

```html
<script src="path/to/yourCopyOf/ramda.js"></script>
```

Ou a versão minificada: 

```html
<script src="path/to/yourCopyOf/ramda.min.js"></script>
```

or através do CDN ou cdnjs:

```html
<script src="//cdnjs.cloudflare.com/ajax/libs/ramda/0.25.0/ramda.min.js"></script>
```

Ou um dos links abaixo através de [jsDelivr](http://jsdelivr.com):

```html
<script src="//cdn.jsdelivr.net/npm/ramda@0.25.0/dist/ramda.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/ramda@0.25/dist/ramda.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/ramda@latest/dist/ramda.min.js"></script>
```

(Note que usando `latest` é levar em risco que a as mudanças da API ramda podem trazer *breaking changes*.)

Essas tags adicionam a variável `R` no scopo global do navegador.

Or você pode injetar ramda em praticamente qualquer website utilizando [the bookmarklet](https://github.com/ramda/ramda/blob/master/BOOKMARKLET.md).

**Notas para as versões > 0.25**
As versões de Ramda acima de 0.25 não tem *default export*.
Então ao invés de usar `import R from 'ramda';`, terá que usar `import * as R from 'ramda';`
Or melhor ainda, importe apenas as funções necessárias através de `import { functionName } from 'ramda';`

### Build

`npm run build` cria os diretórios `es`, `src` e atualiza __dist/ramda.js__ e __dist/ramda.min.js__

### Builds parciais

É possível *buildar* Ramda como um *subset* da funcionalidade para reduzir o seu tamanho. O sistema de build de Ramda tem suporte para *flags* de linha de comando.
Por exemplo, se você está usando `R.compose`, `R.reduce` e `R.filter` você pode criar *builds* parciais com:

    npm run --silent partial-build compose reduce filter > dist/ramda.custom.js

Para isso é necessário ter Node/io.js instalado e as dependências de Ramda (apenas use `npm install` antes de rodar sua build parcial)


Documentação
-------------
Por favor, revise: [API documentation](https://ramdajs.com/docs/).

Também disponível em nosso [Cookbook](https://github.com/ramda/ramda/wiki/Cookbook) de *built functions* de Ramda que você pode achar útil.

O nome
--------

Ok, então nos gostamos de carneiros. Isso é tudo. É um nome curto e que ainda não tinha sido utilizado.
Poderia facilmente ser `aweda`, mas nos seríamos forçados a dizer _eweda lamb!_, e ninguém quer isso.
Para pessoas que não falam nativamente inglês, *lambs* são filhotes de carneiros, *ewes* são carneiros fêmeas e *rams* carneiros.
Então talvez Ramda é uma lambda crescida... provavelmente não.

(Ficou um pouco estranho, já que em português os nomes são diferentes `carneiros` e `ovelhas`, por isso essa parte ficou com os nomes em inglês).

Rodando a suite de testes
----------------------

**Console:**

Para rodar a suite de testes a partir do console, você precisar ter o `mocha` instalado:

    npm install -g mocha

Então a partir da raíz do projeto você precisa apenas rodar

    mocha

Ou se você instalou as depedências pode ser através do:

    npm install

então você poderá rodar os testes (e ver os *output* detalhado) rodando:

    npm test

**Browser:**

Você pode usar 

**Browser:** [testem](https://github.com/airportyh/testem) para testar para diferentes *browsers* (ou mesmo de forma *headlessly*), com *livereloading* dos testes. instale testem (`npm install -g testem`) e rode `testem`. Abra o link fornecido no seu browser e você verá 
os resultados no seu terminal.

Se você tiver _PhantomJS_ instalado, você poderá rodar `testem -l phantomjs` para rodar os testes de forma completamente *headlessly*

Forma de uso
-----------------

Para as versões acima de `v0.25`, importar a biblioteca inteira ou pegar os *modules* diretamente da biblioteca:

```js
import * as R from 'ramda'

const {identity} = R
R.map(identity, [1, 2, 3])
```

A desestruturação dos imports do Ramda *não necessariamente impede a importação de toda a  biblioteca*. Você pode manualmente fazer um *cherry-pick* dos métodos como a seguir, irá apenas pegar as partes necessárias para `identity` funcionar:

```js
import identity from 'ramda/src/identity'

identity()
```

Fazer *cherry-pick* dos métodos é um pouco maçante, entretanto. A maioria dos *bundlers* como Webpack e Rollup oferecem *tree-shaking* como uma maneira de remover códigos não usados e diminuir o tamanho do bundle, mas a performance varia, discutido [Aqui](https://github.com/scabbiaza/ramda-webpack-tree-shaking-examples). 
Aqui está um sumário da configuração ideal de acordo com a tecnologia que você está usando:

1. Webpack + Babel - use [`babel-plugin-ramda`](https://github.com/megawac/babel-plugin-ramda) to automatically cherry pick methods. Discussion [here](http://www.andrewsouthpaw.com/2018/01/19/ramda-tree-shaking-not-supported-out-of-the-box/), example [here](https://github.com/AndrewSouthpaw/ramda-webpack-tree-shaking-examples/blob/master/07-webpack-babel-plugin-ramda/package.json)
1. Webpack only - use `UglifyJS` plugin for treeshaking along with the `ModuleConcatenationPlugin`. Discussion [here](https://github.com/ramda/ramda/issues/2355), with an example setup [here](https://github.com/scabbiaza/ramda-webpack-tree-shaking-examples/blob/master/06-webpack-scope-hoisted/webpack.config.js)
1. Rollup - does a fine job properly treeshaking, no special work needed; example [here](https://github.com/scabbiaza/ramda-webpack-tree-shaking-examples/blob/master/07-rollup-ramda-tree-shaking/rollup.config.js)


Typings
-----------------

- [TypeScript](https://github.com/types/npm-ramda/)
- [Flow](https://github.com/flowtype/flow-typed/tree/master/definitions/npm/ramda_v0.x.x)




Translations
-----------------

- [Chinese(中文)](http://ramda.cn/)
- [Ukrainian(Українська)](https://github.com/ivanzusko/ramda)
- [Portuguese(Português)](https://github.com/renansj/ramda)


Acknowledgements
-----------------

Thanks to [J. C. Phillipps](http://www.jcphillipps.com) for the Ramda logo.
Ramda logo artwork &copy; 2014 J. C. Phillipps. Licensed Creative Commons 
[CC BY-NC-SA 3.0](http://creativecommons.org/licenses/by-nc-sa/3.0/).
