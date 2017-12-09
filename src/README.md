# ITCSS
A ideia do ITCSS é você montar uma arquitetura que consiga mitigar esses pequenos problemas do CSS. Seu nome por extenso é Inverted Triangle CSS. Que envolve basicamente visualizar todo o CSS em camadas, que montadas formam um triângulo de cabeça para baixo. Essa organização hierárquica ajuda a organizar o CSS da forma mais efetiva, diminuindo conflitos e sobrescritas.

## 01 - Settings
Essas são as configurações básicas da sua arquitetura. Em geral, são as variáveis globais que vão definir cores, espaçamentos e outras configurações desejadas para o funcionamento do seu framework em si. Perceba que nada aqui será gerado como CSS final, sendo somente utilizado na criação.

## 02 - Tools
É o lugar onde você vai guardar seus mixins e funções necessárias para a construção de seus layouts. Pode ser qualquer coisa, desde mixins de font-face, até mixins de animações, etc. Repare que aqui, nada é gerado diretamente como CSS final também.

## 03 - Generic
Essa é a primeira camada que vai de fato aplicar CSS final e ela é destinada para as propriedades mais genéricas e com a menor especificidade possível. Em geral, é onde colocamos resets, box-sizing, etc.

## 04 - Base
Aqui ficarão as estilizações básicas, a última camada que veremos seletores em tags diretamente. Portanto aqui ficarão estilos para os headings h1-h6, blockquotes, a, buttons, etc. Mas lembre-se são estilizações BÁSICAS, nada de estilizar tudo aqui!

## 05 - Objects
Seguindo os princípios de OOCSS (CSS Orientado a Objetos), aqui é onde iremos ter nossos pequenos “objetos”, que nada mais são que pequenos pedaços da interface, em geral, padrões que se repetem por todo o site e que podem ter ou não uma camada visual por cima.

Aqui é onde fazemos os padrões de botões, listas, paineis, etc. Nesse momento, só é permitido também o uso de classes.

## 06 - Components
Aqui como o nome já diz, teremos nossos componentes já mais específicos. De acordo com o RSCSS, aqui que vamos jogar todos aqueles componentes/elementos criados. Enquanto nos objetos nós tentamos abstrair o máximo possível, para ter muitos objetos reutilizáveis e genéricos, aqui nós vamos ser específicos ao criar os componentes, mas respeitando as regras de especificidade e também não colocando positions ou outras propriedades que engessem muito o componente a ponto dele não ser reutilizável.

Normalmente, aqui ficarão listas específicas como de produtos, cards específicos como aqueles incluindo imagens, etc.

## 07 - Trumps _(Utils)_
Por final temos Trumps, que  também são chamados de Helpers ou Utils. Essa camada é a responsável pela maior especificidade de todas, tendo seus componentes até com !important. Mas não se engane e já comece a me xingar falando “ahhhh, ele usa important, que nojo.”, calma. A ideia dos trumps é que eles sejam usados para classes reativas, comumente aquelas que queremos que aconteça não importa o que aconteça, o clássico .hidden. Faz todo sentido que para esses casos, o !important seja utilizado.

É importante que você não confunda a existência dessa camada e saia colocando tudo aqui, essa camada somente deverá ser utilizada em casos que não vá afetar a estrutura da página.

**Links Úteis**
[https://willianjusten.com.br/organizando-seu-css-com-itcss/](https://willianjusten.com.br/organizando-seu-css-com-itcss/)
[http://hugobessa.com.br/ITCSS-uma-maneira-de-pensar-arquiteturas-css/](http://hugobessa.com.br/ITCSS-uma-maneira-de-pensar-arquiteturas-css/)

#  BEM
BEM - bloco de significado , elemento , modificador - é uma metodologia de nomeação de front-end pensada pelos caras no Yandex . É uma maneira inteligente de nomear suas classes CSS para dar-lhes mais transparência e significado para outros desenvolvedores. Eles são muito mais rigorosos e informativos, o que torna a convenção de nomeação BEM ideal para equipes de desenvolvedores em projetos maiores que podem durar um tempo.

O objetivo do BEM é dar muito mais transparência e clareza em sua marcação. O BEM diz aos desenvolvedores como as classes se relacionam, o que é particularmente útil em partes complexas ou profundas de DOM.

```
Bloco: a única raiz do componente.
Elemento: uma componente do bloco.
Modificador: uma variante ou extensão do bloco.
```


### Namespaces
A nomeação nos permite verificar exatamente qual o tipo de trabalho que uma classe pode ter, como e onde poderemos reutilizá-la (se for o caso), se podemos ou não modificá-la, e muito mais.

Os tipos de espaço de nomes mais comuns são:
```
c- para componentes,
o- para objetos,
u- para utilitários
is-/has- para estados
js- para javascript hooks
```

Com isso em mente, o HTML acima seria reescrito como este:
```
<div class="o-media  c-user  c-user--premium">
  <img src="" alt="" class="o-media__img  c-user__photo  c-avatar" />
  <p class="o-media__body  c-user__bio">...</p>
</div>
```
### Sufixos Responsivos.
Estes sufixos tomam o formato @breakpoint e nos dizem esta classe quando a este tamanho :

```
<div class="o-media@md  c-user  c-user--premium">
  <img src="" alt="" class="o-media__img@md  c-user__photo  c-avatar" />
  <p class="o-media__body@md  c-user__bio">...</p>
</div>
```

Então, aqui temos **o-media@md**, o que significa ser o objeto de mídia neste ponto de interrupção . Outros exemplos possíveis:

```
u-hidden@print - uma classe de utilitário para ocultar coisas quando em contexto de impressão.
u-1/4@lg - um utilitário para fazer algo um quarto de largura no ponto de interrupção grande.
o-layout@md - um objeto de layout no ponto de interrupção médio.
```

Esta @é uma maneira legível e lógica humana de denotar estados condicionais. Ele permite que os desenvolvedores aprendam sobre possíveis permutações ou aparências que a peça de UI em questão possa ter, apenas de relance.

**OBS** :  Você deve escapar do @símbolo em seu arquivo CSS, assim:

```
@media print {

  .u-hidden\@print {
    display: none;
  }

}
```
**Links Úteis**
[https://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/](https://csswizardry.com/2015/08/bemit-taking-the-bem-naming-convention-a-step-further/)
[http://getbem.com/introduction/](http://getbem.com/introduction/)

## Extras
[CSS Guidelines](https://cssguidelin.es/)
[Coding Style](https://github.com/LFeh/coding-style#css)
