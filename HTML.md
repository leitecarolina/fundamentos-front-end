# HTML

### Wiki

Sites para aprender e tirar duvidas:

- [w3schools](https://www.w3schools.com/html/default.asp)

##

### O QUE É HTML

HTML significa Hyper Text Markop Language.  é uma linguagem de marcação de texto padrão utilizada para criar e exibir páginas na Web, tornando o texto interativo e dinâmico, podendo transformar texto em links, tabelas, imagens, etc...

Os documentos HTML contém 2 elementos: Conteúdo e Marcadores.

A leitura deve ser feitas de cima para baixo e da esquerda para a direita. 

O HTML5 foi criado para substituir HTML4, XHTML e HTML DOM Nível 2. Os objetivos e motivações principais por trás da especificação HTML5 eram:

- Entrega de um rico conteúdo (gráficos, vídeos, etc.) sem a necessidade de *plugins* adicionais como o Flash.
- Fornecimento de um suporte semântico melhor para a página *web* por meio de marcadores de elementos estruturais.
- Fornecimento de um padrão de análise (***parse***) mais preciso de modo a simplificar o manuseio de erros, além de garantir um comportamento entre navegadores mais consistente e simplificar a compatibilidade com documentos escritos em outros padrões.
- Fornecimento de um melhor suporte entre plataformas, quer a pessoa utilize um PC, um *tablet* ou um *smartphone*.

##

### CHARACTER ENCODING - CODIFICADOR DE CARACTERES

Para que uma página HTML seja utilizada corretamente, o navegador  precisa saber qual conjunto de caracteres deve usar.

```html
<head>
   <meta charset="UTF-8">
</head>
```

##

### HTML SEMÂNTICO

HTML semântico é um estilo de código, onde a utilização de marcação HTML  é usada para reforçar a semântica ou o significado do conteúdo. Por exemplo, em textos em negrito não utilizamos a tag `b`  e nem a tag `i`  para textos em itálico. E sim, as tags `strong` e `em`. 

##

### MOBILE FIRST

Mobile First é um conceito aplicado em projetos web onde o foco inicial da arquitetura e desenvolvimento é direcionado aos dispositivos móveis e em seguida para os desktops.

Vantagens **mobile-first:**

- Grande parte dos acessos e vendas vem de dispositivos mobile
- O design é minimalista e simplificado
- Foco em conteúdo

Vantagens **desktop-first:**

- A interface pode ter diversas features mais ricas
- Maior capacidade de banda e processamento
- O produto é otimizado para desktop (ex: Google Docs)

##

### TAGS SEMANTICAS

Dentro do HTML exite alguns elementos semanticos que podem ser usados para definir diferentes partes de uma página web:

- `<article>` : especifica conteúdo independente e autocontido, deve fazer sentido por si só e deve ser possível distribuí-lo independentemente do resto do site (blog, forum, cards, etc)
- `<aside>` : define algum conteúdo além do conteúdo em que é colocado (como uma barra lateral)
- `<details>` : define detalhes adicionais que o usuário pode visualizar ou ocultar
- `<figcaption>` : define uma legenda para um elemento `<figure>`. O elemento `<figcaption>` pode ser colocado como o primeiro ou o último filho de um elemento `<figure>`
- `<figure>` : especifica conteúdo independente, como ilustrações, diagramas, fotos, listagens de código, etc
- `<footer>` : rodapé
- `<header>` : conteúdo introdutório ou um conjunto de links de navegação
- `<main>` : especifica o conteúdo principal do documento
- `<mark>` : define o texto marcado / destacado
- `<nav>` : define um conjunto de links de navegação
- `<section>` : define uma seção no documento
- `<summary>` : define um título visível para um elemento `<details>`
- `<time>` : define data/ tempo

##

### ESTRUTURAÇÃO DE UM DOCUMENTO HTML

```html
<!-- Estrutura de um documento HMTL pt-br -->
<!DOCTYPE html>
   <html lang="pt-br">
		<meta charset="utf-8">
     <head>
       <title>HTML Tutorial</title>
     </head>
     <body>
       <h1>This is a heading</h1>
       <p>This is a paragraph.</p>
    </body>
</html>
```

##

### DIFERENÇA ENTRE MARCADOR E ELEMENTOS

Os elementos se comunicam com o navegar para reproduzir texto. Quando um elemento está entre colchetes angulares `<>` , forma um marcador.

##

### MELHORES COLOCAÇÕES NAS PÁGINAS DE BUSCA

Para obter uma melhor colocação, é necessário incluir as seguintes definições no `head`:

```html
<meta name="keywords" content="keyword keyword keyword keyword">
<meta name="description" content="description of your site">
```

Ambas declarações podem conter até 1022 caracteres. Se uma palavra-chave for utilizada mais de 7 vezes, o marcador de palavras-chave será totalmente ignorado. Além disso, você também não pode incluir marcação (além de entidades) na descrição ou lista de palavras-chave.

##

### ANINHAMENTO

É quando um elemento esta dentro do outro elemento. Exemplo: o elemento `title` está dentro do elemento `head`, e o elemento `p` está dentro do elemento `body`

##


### MARCADORES -TAGS

Os marcadores HTML estão divididos em 3 elementos: marcador inicial, conteúdo e marcador final. Cada marcador tem propriedades distintas.  Sintaxe:

```html
<marcador>conteúdo</marcador>
```

Em alguns casos, os marcadores não possuem fechamento., como `img`, `br`, `hr`.

- Principais tags

    ### Títulos

    Existem seis tamanhos diferentes definidos de h1 (maior) a h6 (menor):

    ```html
    <h1>Heading 1</h1>
    <h2>Heading 2</h2>
    <h3>Heading 3</h3>
    <h4>Heading 4</h4>
    <h5>Heading 5</h5>
    <h6>Heading 6</h6>
    ```

   ##

    ### Elementos semânticos

    - `header`: cabeçalho do documento ou seção
    - `nav`: menu de navegação
    - `main`: conteúdo principal de um documento
    - `aside`: conteúdo localizado na parte lateral de uma página
    - `article`: conteúdo independente
    - `section`: seção do documento
    - `footer`: rodapé da página

    ##

    ### Div Vs Span

    - `div` é um block element (elemento em bloco)
    - `span` é um inline element (elemento e linha)

    ##

    ### Block elements VS Inline elements

    - **Elementos em bloco:** formam um bloco visível na página.  Eles aparecerão em uma nova linha logo após qualquer elemento que venha antes dele, e qualquer conteúdo depois de um elemento em bloco também aparecerá em uma nova linha. São elementos em bloco: `p`, `ol`, `ul`, `nav`, `footer`, etc.
    - **Elementos em linha:** são aqueles que estão contidos dentro de elementos em bloco, envolvem apenas pequenas partes do conteúdo do documento e não parágrafos inteiros ou agrupamentos de conteúdo. São elementos em linha: `a`, `strong`, `em`.
    - Exemplos

        ```html
        <!-- Cabeçalhos de títulos e legendas (elemento block) -->
        <h1>Heading 1</h1>
        <h2>Heading 2</h2>
        <h3>Heading 3</h3>
        <h4>Heading 4</h4>
        <h5>Heading 5</h5>
        <h6>Heading 6</h6>

        <!-- Link (elemento inline) -->
        <a href=”http://www.google.com”>Acesse o Google</a>

        <!-- Tabela (elemento block) -->
        <table>
           <thead>
             <tr>
              <th>Month</th>
              <th>Savings</th>
            </tr>
           </thead>
           <tbody>
             <tr>
               <td>January</td>
               <td>$100</td>
             </tr>
             <tr>
               <td>February</td>
               <td>$150</td>
             </tr>
            </tbody>
        </table>

        <!-- Lista ordenada (elemento block) -->
        <ol>
           <li>Item</li>
           <li>Item</li>
           <li>Item</li>
           <li>Item</li>
        </ol>

        <!-- Lista não ordenada (elemento block) -->
        <ul>
           <li>Item</li>
           <li>Item</li>
           <li>Item</li>
           <li>Item</li>
        </ul>

        <!-- Imagem (elemento inline) -->
        <img src=”image.jpg” alt=”imagem da igreja”>

        <!-- Linha divisória (elemento inline) -->
        <hr>

        <!-- Data (elemento inline) -->
        <input type=”date”>

        <!-- Realçar um texto (elemento inline) -->
        <p>Este texto está <mark>realçado</mark></p>
        ```

    ##

    ### Dados em forma de tabela

    A tag `table`  é utilizada para exibir dados em forma de tabela linha*coluna. Também controla o visual da página, como: cabeçalho, navegação, conteúdo, rodapé. 

    - `table`:  define uma tabela
    - `tr`: define uma linha em uma tabela
    - `th`: define uma célula de cabeçalho em uma tabela
    - `td`: define uma célula em uma tabela
    - `caption`: define uma legenda
    - `colgroup`: especifica um grupo de uma ou mais colunas em uma tabela para fins de formatação
    - `col`: utilizado com o marcador `colgroup` para especificar propriedades para cada coluna
    - `tbody`: usado para agrupar o conteúdo do corpo de uma tabela
    - `thead`: usado para agrupar o conteúdo do cabeçalho de uma tabela
    - `tfooter`: usado para agrupar o conteúdo do rodapé de uma tabela

    ```html
    <table>
       <tr>
         <td>50 pcs</td>
         <td>100</td>
         <td>500</td>
       </tr>
       <tr>
         <td>10 pcs</td>
         <td>5</td>
         <td>50</td>
       </tr>
    </table>
    ```
	
    ##

    ### Mapa de Imagem

    O mapa de imagem facilita o vínculo a várias páginas diferentes com o uso de uma única imagem. Representado pela tag `map`  :

    ```html
    <map name="planetmap">
      <area shape="rect" coords="0,0,82,126" href="sun.htm" alt="Sun">
      <area shape="circle" coords="90,58,3" href="mercur.htm" alt="Mercury">
      <area shape="circle" coords="124,58,8" href="venus.htm" alt="Venus">
    </map>
    ```

    ##

    ### Tag `iframe`

    A tag `iframe` é usada para exibir uma página dentro de outra página.

    ```html
    <iframe src="https://www.google.com"></iframe>
    ```

    ##

    ### Tag `meta`

    A tag meta descreve metadados dentro de um documento HTML. Esses metadados não aparecerão na página, mas serão analisados. Essa tag define a descrição da página, palavras-chave (keywords), autor do documento, ultima modificação, etc.

    ```html
    <head>
      <meta charset="UTF-8">
      <meta name="description" content="Free Web tutorials">
      <meta name="keywords" content="HTML,CSS,XML,JavaScript">
      <meta name="author" content="John Doe">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
    </head>
    ```

    ##

    ### Hyperlink (hipertexto)

    O HTML possui um marcador âncora para criar um hipertexto que vincula uma página a outra.

    ```html
    <a href="url">link text</a>
    ```

    Essas tags podem aparecem:

    - **Link não visitado:** sublinhado e com a cor azul.
    - **Link visitado:** sublinhado e com a cor púrpura.
    - **Link ativo:** sublinhado com a cor vermelha.

    ##

    ### Tipos de lista

    Existem diferentes tipos de listas:

    - **Lista ordenada:** exibe elementos em formato numerado. Tag: `ol`

    ```html
    <ol>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ol>
    ```

    - **Lista não ordenada:** exibe elementos em formato de ponto. Tag: `ul`

    ```html
    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
    </ul>
    ```

    - **Lista de definição:** exibe elementos como se fosse um dicionário. Os marcadores são: `dt`, `dl`, `dd`

    ```html
    <dl>
      <dt>Item</dt>
      <dd>Definition</dd>
      <dt>Item</dt>
      <dd>Definition</dd>
    </dl>
    ```

    ##

    ### Símbolo copyright

    Podemos inserir usando `&copy;` ou `&#169;`

    ##

    ### Destacar um texto

    A tag `mark` é uma forma rápida e fácil para destacar um texto na página:

    ```html
    <p>Do not forget to buy <mark>milk</mark> today.</p>
    ```

    Para destacar um texto no padrão HTML que seja suportado por todos os navegadores, utilize o estilo de cor de fundo dentro do marcador HTML.:

    ```html
    <p>Do not forget to buy <span style="background-color: yellow;">milk</span> today.</p>
    ```

- Compilado de tags e elementos

    [Untitled](https://www.notion.so/873b1899c43f464d9346ac9238a38efe)
    
##

### EMMET

Plugin para facilitar a construção/digitalização de HTML e CSS

- Estrutura HTML → `html:5`
- Uma tag dentro da outra → `header>h1`
- Uma classe → `header.nomedaclsse>h1`
- Atributos → `main.nomedaclassse>h1[style="text-align: center;"]{texto dentro da h1}`
    - Exemplo

        ```html
        <main class='container'>
        	<h1 style="text-align: center;">Título</h1>
        <main> 
        ```

- Listas: `ul>li*6`

*Documentação*

##

### BEM - BLOCK ELEMENT MODIFIER

BEM é uma metodologia, uma convenção, um padrão de nomenclatura que utilizamos para manter o nosso projeto simples e organizado. O principal objetivo dessa metodologia, além de manter os códigos simples na hora da escrita e (principalmente) da manutenção, é fazer com que qualquer desenvolvedor possa ter total autonomia para mexer em qualquer tipo de projeto — seja um projeto que você já conheça ou um projeto no qual você acabou de entrar. Essa metodologia é aplicada na nomenclatura das classes CSS dos nossos elementos HTML. A sigla BEM significa *Block Element Modifier*, esses 3 pilares são as bases dessa metodologia e também são as categorias nas quais vamos dividir nossos elementos:

`bloco__elemento—modificador`

- Exemplo

    ```html
    <ul class="list">
      <li class="list__item list__item--highlight">
        <h2 class="list__title">My publication</h2>
        <p class="list__author>Julio Lozovei</p>
        
        <p class="list__text">A publication using BEM.</p>
      </li>
    </ul>
    ```

##

### BOOTSRAP 4

Bootstrap é um framework web com código-fonte aberto para desenvolvimento de componentes de interface e front-end para sites e aplicações web usando HTML, CSS e JavaScript, baseado em modelos de design para a tipografia, melhorando a experiência do usuário em um site amigável e responsivo.

Passos:

1. Acessar o site do bootsrap
2. Copiar as tags style e scrip do [site](https://getbootstrap.com/docs/5.1/getting-started/introduction/)
3. Construir o documento colocando as classe do bootstrap e personalizando se necessário em um arquivo css separado

[**Documentação**](https://getbootstrap.com)
