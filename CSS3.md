# CSS3

### O QUE É CSS

CSS significa Cascading Style Sheets, e descreve como os elementos HTML devem ser exibidos na tela, no papel ou em outra mídia
O CSS pode controlar o layout de várias páginas da web de uma só vez.

---

### ADICIONANDO CSS

- Externo

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <link rel="stylesheet" href="mystyle.css">
    </head>
    <body>

    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>

    </body>
    </html>
    ```

    ```css
    /*file name: mystyle.css*/

    body {
      background-color: lightblue;
    }

    h1 {
      color: navy;
      margin-left: 20px;
    }
    ```

- Interno

    ```html
    <!DOCTYPE html>
    <html>
    <head>
    <style>
    body {
      background-color: linen;
    }

    h1 {
      color: maroon;
      margin-left: 40px;
    }
    </style>
    </head>
    <body>

    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>

    </body>
    </html>
    ```

- Inline

    ```html
    <!DOCTYPE html>
    <html>
    <body>

    <h1 style="color:blue;text-align:center;">This is a heading</h1>
    <p style="color:red;">This is a paragraph.</p>

    </body>
    </html>
    ```

---

### SELETORES

Os seletores CSS são usados para "encontrar" (ou selecionar) os elementos HTML que você deseja estilizar. Podemos dividir os seletores CSS em cinco categorias:

- Seletores simples: selecione os elementos com base no nome, id, classe
- Seletores combinadores: selecione os elementos com base em uma relação específica entre eles
- Seletores de pseudoclasse: selecione os elementos com base em um determinado estado
- Seletores de pseudoelementos: selecione e estilize uma parte de um elemento
- Seletores de atributos: selecione os elementos com base em um atributo ou valor de atributo

- Exemplos

    Class Selector:  o seletor de classe seleciona elementos HTML com um atributo de classe específico.

    ```css
    .center {
      text-align: center;
      color: red;
    }

    p.center {
      text-align: center;
      color: red;
    }
    ```

    Universal Selector: afeta todo os elementos da pagina HTML.

    ```css
    * {
      text-align: center;
      color: blue;
    }
    ```

    Grouping Selector:  o seletor de agrupamento seleciona todos os elementos HTML com as mesmas definições de estilo.

    ```css
    h1 {
      text-align: center;
      color: red;
    }

    h2 {
      text-align: center;
      color: red;
    }

    p {
      text-align: center;
      color: red;
    }

    /*CORRETO*/
    h1, h2, p {
      text-align: center;
      color: red;
    }
    ```

---

### CORES

As cores são especificadas usando nomes de cores predefinidos ou valores RGB, HEX, HSL, RGBA, HSLA:

```html
<h1 style="background-color:rgb(255, 99, 71);">...</h1>
<h1 style="background-color:#ff6347;">...</h1>
<h1 style="background-color:hsl(9, 100%, 64%);">...</h1>

<!-- Opacidade -->
<h1 style="background-color:rgba(255, 99, 71, 0.5);">...</h1>
<h1 style="background-color:hsla(9, 100%, 64%, 0.5);">...</h1>
```

- [Color Names](https://www.w3schools.com/colors/colors_names.asp)

---

### CSS RESPONSIVO - MEDIA QUERY

Usar o `@media` no final de todo arquivo .css para definir as exceções em outros tamanhos de tela [screen and (excessão)] ou impressão [print and (excessão)]

```css
...

.chamada__texto {
	font-size: 1.25rem;
	line-height: normal;
	margin: 0 auto 2.5rem;
}

...

@media screen and (min-width: 768px) {
	.chamada__texto {
			max-width: 600px;
	}

/*até a largura de 768 faça a largura máx da classe
chamad__texto igual a 600px*/
```

🔗 [Definição de tamanhos](https://css-tricks.com/snippets/css/media-queries-for-standard-devices/) 

### CLASS VS. ID

Class:  utilizada para elementos que repetem muitas vezes

Id: utilizado quando o elemento é único na página;

```html
<ul id=”lista_de_compras”>
<li class=”item”>Arroz</li>
<li class=”item”>Feijão</li>
<li class=”item”>Macarrão</li>
<li class=”item”>Carne</li>
</ul>
```

---

### COMENTÁRIOS

```css
/* This is a single-line comment */

/* This is
a multi-line
comment */
```

---

### GUIA DE UNIDADES

- Valores Absolutos

    Essas são as mais comuns que vemos no dia a dia. São medidas que não estão referenciadas a qualquer outra unidade, ou seja, não dependem de um valor de referência. São unidades de medidas definidas pela física, como o píxel, centímetro, metro, etc...

    - Pixel
    - Points
    - Inches
    - Centímetro e Mílimetro
    - Paica

    1 in = 2,54cm = 25,4mm = 72pt = 6pc

- Valore Relativos

    Essas medidas são calculadas tendo como base uma outra unidade de medida definida, como por exemplo **em** e o **rem**. O uso delas é mais apropriado para que possamos fazer ajustes em diferentes dispositivos garantindo um layout consistente e fluido em diversas mídias.

    Devido ao fato de que essas medidas são calculadas pelo browser baseando-se em outra unidade, elas tendem a ser bastante flexíveis. Ou seja, podemos ter resultados diferentes de acordo com o ambiente.

    - em: Essa unidade muda para os elementos filhos de acordo com o tamanho da fonte (font-size) do elemento pai

    ```html
    <style>
        #div{
            font-size: 16px;
        }

        #filho{
            font-size: 2em;
        }
    </style>

    <div id="pai">
        div pai
        <div id="filho">
            div filho
        </div>
    </div>

    <!--
    Nesse nosso caso, para a div mais interna (id=filho), 
    1em será igual a 16px, seguindo a lógica, 2em será igual 
    a 32px e assim por diante. Podemos colocar valores como 
    1.5 também! Nesse nosso caso, 1.5em será igual a 24px.
    -->
    ```

    - rem:  o REM vem como sucessor do EM e ambos compartilham a mesma lógica de funcionamento (font-size), porém a forma de implementação é diferente. Enquanto o em está diretamente relacionado ao tamanho da fonte do elemento pai, o rem está relacionado com o tamanho da fonte do elemento root (raiz), no caso, a tag.

        Exemplificando, sabemos que a tag html é a tag raiz de todo documento html. Dito isso, se definirmos que o font-size desse elemento será de 18px, então 1rem = 18px, 2rem = 36px e assim por diante... Normalmente os browsers especificam o tamanho default da fonte do elemento root (raiz) sendo 16px, então guarde isso no coração!

    ```html
    10px = 0.625rem
    12px = 0.75rem
    14px = 0.875rem
    16px = 1rem
    18px = 1.125rem
    ```

    - porcentagem
    - ex: essa unidade não se relaciona com o tamanho da fonte (font-size), mas com qual fonte está sendo utilizada naquele momento (font-family), mais especificamente ao tamanho do caractere x dessa fonte em questão (x-height).
    - ch (character unit): é definida na documentação como sendo a "medida avançada" da largura do caractere zero ("0").
    - vw (viewport width): Viewport nada mais é que a área visível de uma página web para o seu usuário, essa viewport pode variar de acordo com o dispositivo, sendo menor em celulares e maior em desktops. Essa unidade se relaciona diretamente com a largura da viewport, onde 1vw representa 1% do tamanho da largura dessa área visível. A diferença entre vw e a % é bem semelhante a diferença entre em e rem, onde a % é relativa ao contexto local do elemento e o vw é relativo ao tamanho total da largura da viewport do usuário.
    - vh (viewport height): Essa unidade funciona da mesma forma que o vw, porém dessa vez, a referência será a altura e não a largura.
    - Vmin (viewport minimun): utilizará como base a menor dimensão da viewport (altura x largura). Imagine que estamos trabalhando com uma viewport de 1600px de altura e 900px de largura. Nesse caso, 1vmin terá o valor de 9px (1% da menor dimensão!), caso tenhamos 100vmin, esse será igual a 900px!
    - Vmax (viewport maximum): terá como valor de referência a maior dimensão da viewport. Ou seja, utilizando o mesmo exemplo, se tivermos 1600px de altura e 900px de largura, 1vmax será equivalente a 16px!

---

### CSS VARIAVEIS

É possível adicionar variáveis no CSS seguindo a estrutura: 

```css
:root {
--branco: #FFF;
}

.botao {
	border: 1px solid var(--branco)
}
```

 Assim todas as variáveis podem ser trocadas de uma vez, facilitando a manutenção.

---

### CSS FLEXBOX

O Flexbox tem como meta ser um modo mais eficiente para criar layouts, alinhar e distribuir espaços entre itens em um container, mesmo quando as dimensões destes itens são desconhecidas e/ou dinâmicas (daí o termo "flex").  A ferramenta Flexbox (de Flexible Box) foi criada para tornar essas tarefas mais simples e funcionais: os filhos de um elemento com Flexbox podem se posicionar em qualquer direção e pode ter dimensões flexíveis para se adaptar. O Flexbox é um módulo completo e não uma única propriedade; algumas delas devem ser declaradas no container (pai), enquanto outras devem ser declaradas nos elementos-filhos (flex itens). Se o layout "padrão" é baseado nas direções block e inline, o layout Flex é baseado em direções "flex flow".

🔗 [Froggy](https://flexboxfroggy.com/#pt-br)

🔗 [Yoksel](https://yoksel.github.io/flex-cheatsheet/)

🔗 [Guia do FlexBox Alura](https://www.alura.com.br/artigos/css-guia-do-flexbox)

🔗 [CSS Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

![CSS3%201c9f104080b443e4bb2f2c00f60334ca/Untitled.png](CSS3%201c9f104080b443e4bb2f2c00f60334ca/Untitled.png)

- Eixo principal: o eixo principal de um *flex container* é o eixo primário e ao longo dele são inseridos os *flex items*. **Cuidado**: O eixo principal não é necessariamente horizontal; vai depender da propriedade `flex-direction` .
- *main-start | main-end*: os *flex items* são inseridos dentro do container começando pelo lado *start*, indo em direção ao lado *end*.
- Tamanho principal: A largura ou altura de um *flex item*, dependendo da direção do container, é o tamanho principal do ítem. A propriedade de tamanho principal de um *flex item* pode ser tanto `width` quanto `height`, dependendo de qual delas estiver na direção principal.
- Eixo transversal: O eixo perpendicular ao eixo principal é chamado de eixo transversal. Sua direção depende da direção do eixo principal.
- *cross-start | cross-end*: Linhas flex são preenchidas com ítens e adicionadas ao container, começando pelo lado *cross start* do *flex container* em direção ao lado *cross end*.
- *cross size*: A largura ou altura de um *flex item*, dependendo do que estiver na dimensão transversal, é o *cross size* do íten. A propriedade *cross size* pode ser tanto a largura quanto a altura do ítem, o que estiver na transversal.

---

### PROPIEDADES CONTAINER

- Display: coloca todos os elementos filhos em flex
    - exemplos

        ![CSS3%201c9f104080b443e4bb2f2c00f60334ca/Untitled%201.png](CSS3%201c9f104080b443e4bb2f2c00f60334ca/Untitled%201.png)

        ```css
        .container {
        	display: flex; /* or inline-flex*/
        ```

- Flex-direction: estabelece a direção do flex
    - exemplos

        ![CSS3%201c9f104080b443e4bb2f2c00f60334ca/Untitled%202.png](CSS3%201c9f104080b443e4bb2f2c00f60334ca/Untitled%202.png)

        - `row` (padrão): esquerda para a direita em `ltr` (left to right), direita para a esquerda em `rtl` (right to left)
        - `row-reverse`: direita para a esquerda em `ltr`, esquerda para a direita em `rtl`
        - `column`: mesmo que `row`, mas de cima para baixo
        - `column-reverse`: mesmo que `row-reverse` mas de baixo para cima

- Flex-wrap: faz a quebra de linha
    - exemplos

        ![CSS3%201c9f104080b443e4bb2f2c00f60334ca/Untitled%203.png](CSS3%201c9f104080b443e4bb2f2c00f60334ca/Untitled%203.png)

        - `nowrap` (padrão): todos os *flex items* ficarão em uma só linha
        - `wrap`: os *flex items* vão quebrar em múltiplas linhas, de cima para baixo
        - `wrap-reverse`: os *flex items* vão quebrar em múltiplas linhas de baixo para cima

- Flex-flow: propriedade shorthand que inclui flex-direction e flex-wrap
    - exemplos

        ```css
        .flex-container {
            flex-flow: row nowrap | row wrap | column nowrap | column wrap;
          }
        ```

- Justify-content: define o alinhamento dos itens ao longo do eixo principal, distribuindo o espaço livre do container
    - exemplos

        ![https://css-tricks.com/wp-content/uploads/2018/10/justify-content.svg](https://css-tricks.com/wp-content/uploads/2018/10/justify-content.svg)

        - `flex-start` (padrão): os ítens são alinhados junto à borda de início (start) de acordo com qual for a `flex-direction` do container.
        - `flex-end`: os ítens são alinhados junto à borda final (end) de acordo com qual for a `flex-direction` do container.
        - `start`: os ítens são alinhados junto à borda de início da direção do `writing-mode` (modo de escrita).
        - `end`: os ítens são alinhados junto à borda final da direção do `writing-mode` (modo de escrita).
        - `left`: os ítens são alinhados junto à borda esquerda do container, a não ser que isso não faça sentido com o `flex-direction` que estiver sendo utilizado. Nesse caso, se comporta como `start`.
        - `right`: os ítens são alinhados junto à borda direita do container, a não ser que isso não faça sentido com o `flex-direction` que estiver sendo utilizado. Nesse caso, se comporta como `start`.
        - `center`: os ítens são centralizados na linha.
        - `space-between`: os ítens são distribuídos de forma igual ao longo da linha; o primeiro ítem junto à borda inicial da linha, o último junto à borda final da linha.
        - `space-around`: os ítens são distribuídos na linha com o mesmo espaçamento entre eles. Note que, visualmente, o espaço pode não ser igual, uma vez que todos os ítens tem a mesma quantidade de espaço dos dois lados: o primeiro item vai ter somente uma unidade de espaço junto à borda do container, mas duas unidades de espaço entre ele e o próximo ítem, pois o próximo ítem também tem seu próprio espaçamento que está sendo aplicado.
        - `space-evenly`: os ítens são distribuídos de forma que o espaçamento entre quaisquer dois itens da linha (incluindo entre os ítens e as bordas) seja igual.

- Align-items: define como os flex items são posicionados de acordo com o eixo transversal
    - exemplos

        ![https://css-tricks.com/wp-content/uploads/2018/10/align-items.svg](https://css-tricks.com/wp-content/uploads/2018/10/align-items.svg)

        - `stretch` (padrão): estica os ítens para preencher o container, respeitando o `min-width`/`max-width`).
        - `flex-start`/ `start` / `self-start`: ítens são posicionados no início do eixo transversal. A diferença entre eles é sutil e diz respeito às regras de `flex-direction` ou `writing-mode`.
        - `center`: ítens são centralizados no eixo transversal.
        - `baseline`: ítens são alinhados de acordo com suas baselines

- Align-content: organiza as linhas dentro do container quando tem espaço extra no eixo transversal
    - exemplos

        ![https://css-tricks.com/wp-content/uploads/2018/10/align-content.svg](https://css-tricks.com/wp-content/uploads/2018/10/align-content.svg)

        - `flex-start` / `start`: ítens alinhados com o início do container. O valor (com maior suporte dos navegadores) flex-start se guia pela flex-direction, enquanto start se guia pela direção do writing-mode.
        - `flex-end` / `end`: ítens alinhados com o final do container. O valor (com maior suporte dos navegadores) flex-end se guia pela flex-direction, enquanto end se guia pela direção do writing-mode.
        - `center`: ítens centralizados no container.
        - `space-between`: ítens distribuídos igualmente; a primeira linha junto ao início do container e a última linha junto ao final do container.
        - `space-around`: ítens distribuídos igualmente com o mesmo espaçamento entre cada linha.
        - `space-evenly`: ítens distribuídos igualmente com o mesmo espaçamento entre eles.
        - `stretch` (padrão): ítens em cada linha esticam para ocupar o espaço remanescente entre elas.

### PROPIEDADES FLEX ITEMS

- Order: determina a ordem que os elementos vão aparecer
    - exemplos

        ![https://css-tricks.com/wp-content/uploads/2018/10/order.svg](https://css-tricks.com/wp-content/uploads/2018/10/order.svg)

        ```css
        .flex-item {
            order: <número>; /* o valor padrão é 0 */
          }
        ```

- Flex-grow: habilidade que um flex item tem de crescer. O valor dessa propriedade é um valor numérico sem indicação de unidade, que serve para cálculo de proporção. Este valor dita a quantidade de espaço disponível no container que será ocupado pelo item. Se todos os ítens tiverem flex-grow definido em 1, o espaço remanescente no container será distribuído de forma igual entre todos. Se um dos ítens tem o valor de 2, vai ocupar o dobro de espaço no container com relação aos outros
    - exemplos

        ![https://css-tricks.com/wp-content/uploads/2018/10/flex-grow.svg](https://css-tricks.com/wp-content/uploads/2018/10/flex-grow.svg)

        ```css
        .flex-item {
            flex-grow: <numero>; /* o valor default(padrão) é 0 */
          }
        ```

- Flex-shrink: habilidade de um flex item encolher
    - exemplos

        ```css
        .flex-item {
            flex-shrink: <número>; /* o valor padrão é 0 */
          }
        ```

- Flex-basis: define o tamanho padrão para um elemento antes que o espaço remanescente do container seja distribuído
    - exemplos

        ```css
        .flex-item {
            flex-basis: flex-basis:  | auto; /* o valor padrão é auto */
          }
        ```

- Flex: shorthand para `flex-grow`, `flex-shrink` e `flex-basis`, combinadas
    - exemplos

        ```css
        .item {
            flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
          }
        ```

- Align-self: permite que o alinhamento padrão definido por `align-items` seja sobrescrito
    - exemplos

        ![https://css-tricks.com/wp-content/uploads/2018/10/align-self.svg](https://css-tricks.com/wp-content/uploads/2018/10/align-self.svg)

        ```css
        .item {
            align-self: auto | flex-start | flex-end | center | baseline | stretch;
          }
        ```

---

### CSS GRID

dsfsdfsdf

Grid tem final exclusivo

Precisa estar definido no elemento pai:

```css
.pai {
	display: grid;
	grid-template-areas: 
		"cabecalho"
		"conteudo"
		"rodape";
	grid-template-columns: auto;
	grid-template-rows: 50px 100vh auto;
}
```

---

### SASS E COMPASS

Sass é um dos principais pré-processadores CSS, que facilita a manutenção das paginas web

Passos:

1. Pegar o arquivo CSS e transformar em .SCSS (manualmente)
2. Abrir o prompt e localizar o arquivo
3. Compilar o arquivo:
    1. usando:  `sass nomedoaquivo.scss:nomedoarquivo.css`
    2. ou assistindo: `sass —watch nomedoaquivo.scss:nomedoarquivo.css` (faz atualização automatica)

### VARIÁVEIS

Para declarar uma variável usa $:

```scss
$cor-padrao: #000000;

/* header */
h1 {
	color: $cor-padrao;
}
```

---

### COMENTÁRIOS

- /*   */  - aparece no arquivo .css
- //  - não aparece no arquivo .css

---

### ANINHAMENTO

Colocar os filhos dentro do pai no arquivo scss (o neme da classe muda automático):

```scss
.menu-principal {
  position: absolute;
  right: 0;
  top: -.5em;
  font-size: 1.2em;
  font-weight: lighter;

  ul {
    padding-left: 0;
  }

  li {
    display: inline-block;
    width: 5em;
  }
}

//mudando a tag automatica de um :hover
a {
    color: white;
    text-decoration: none;

    &:hover {
      text-decoration: underline;
    }
```

### MIXIN

Salva partes do código repetidas:

```scss
@mixin borda-arredondada {
  -webkit-border-radius: $raio;
  border-radius: $raio;
}

/* header */
@include borda-arredondada;
```

Quando a variável tiver mais de um valor usar () na função:

```scss
@mixin borda-arredondada($raio: 0.3em /*valor padrao*/) {
  -webkit-border-radius: $raio;
  border-radius: $raio;
}

/* header */
@include borda-arredondada(50px);

/* footer */
@include borda-arredondada;
```

---

### IMPORT

Podemos dividir o arquivo scss em vários arquivos, e deixar o principal apenas para importar os outros arquivos, usando o `@import`  :

```scss
@import 'variaveis';
@import 'mixin';
@import 'geral';
@import 'header';

//não pracisa usar extenção
```

---

### PLACEHOLDER

Usar o placeholder para juntar as classe:

```scss
//declarando
%image-replacement {
  text-indent: -9999px;
  overflow: hidden;
  background-repeat: no-repeat;
}

//estilizando
.plataformas li {
    @extend %image-replacement;;
  }
```