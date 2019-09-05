# Guia de código CSS

Padrões para escrever CSS consistente, flexível e escalável.

## Tabela de conteúdos

- [Terminologia](#terminologia)
  - [Regra](#regra)
  - [Seletores](#seletores)
  - [Propriedades](#propriedades)
- [CSS](#css)
  - [Sintaxe](#sintaxe)
  - [Notação abreviada](#notação-abreviada)
  - [Comentários](comentarios)
- [BEM](#bem)

## Terminologia

### Regra

Uma "regra" de CSS sempre começa com um "seletor" (ou grupo de seletores) que define a quais elementos HTML ele se aplica. Após o seletor, temos um bloco de declarações de "propriedades" e seus respectivos valores.

**Exemplo:**

```css
.header {
  color: #414141;               
  background-color: #EEEEEE;   
}
```

### Seletores

Os seletores determinam quais elementos na árvore de DOM serão estilizados pelas propriedades definidas.

**Exemplos:**

```css
.title {
  /* ... */
}

[aria-hidden] {
  /* ... */
}
```

### Propriedades

As propriedades são pares de chave-valor, onde uma regra pode conter uma ou mais declaração de propriedades.

**Exemplo:**

```css
/* some selector */ {
  background: #f1f1f1;
  color: #e18728;
}
```

## CSS

### Sintaxe

- Use 2 espaços para indentação.
- Ao agrupar seletores, mantenha os seletores individuais em uma única linha.
- Inclua um espaço antes da chave de abertura dos blocos de declaração para legibilidade.
- Coloque chaves de fechamento de blocos de declaração em uma nova linha.
- Inclua um espaço depois `:` para cada declaração.
- Finalize todas as declarações com ponto e vírgula. A última declaração é opcional, mas seu código é mais suscetível a erros sem ele.
- Use todos os valores hexadecimais em minúsculo, por exemplo `#f1f1f1`.
- Use valores hexadecimais abreviados quando disponíveis, por exemplo, `#fff` em vez de `#ffffff`.
- Cite valores de atributo em seletores, por exemplo `input[type="text"]`.
- Evite especificar unidades para valores zero, por exemplo, `margin: 0;` em vez de `margin: 0px;`.
- Use dashes `(-)` no lugar de camelCasing em nomes de classes.
- Não use seletores `ID`.

**Exemplo:**

```css
/* Bad CSS */
.selector, .selector-secondary, .selector[type=text] {
  padding:15px;
  margin:0px 0px 15px;
  background-color:rgba(0, 0, 0, 0.5);
  box-shadow:0px 1px 2px #CCC,inset 0 1px 0 #FFFFFF
}

/* Good CSS */
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin-bottom: 15px;
  background-color: rgba(0,0,0,.5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```

### Notação abreviada

Limite o uso da declaração abreviada para instâncias em que você deve definir explicitamente todos os valores disponíveis. As propriedades de taquigrafia frequentemente usadas em excesso incluem:

- `padding`
- `margin`
- `font`
- `background`
- `border`
- `border-radius`

```css
/* Bad example */
.element {
  margin: 0 0 10px;
  background: #000;
  background: url("image.jpg");
  border-radius: 3px 3px 0 0;
}

/* Good example */
.element {
  margin-bottom: 10px;
  background-color: #000;
  background-image: url("image.jpg");
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
}
```

### Comentários

- Deixe um comentário sempre que o trecho não seja óbvio apenas a partir do código
- Prefira comentários em uma única linha

```css
/* Bad example */
/* Modal header */
.modal-header {
  ...
}

/* Good example */
/* Wrapping element for .modal-title and .modal-close */
.modal-header {
  ...
}
```

## BEM

A metodologia Block, Element, Modifier (comumente referida como BEM ) é uma convenção de nomenclatura popular para classes em HTML e CSS. Desenvolvido pela equipe da Yandex, seu objetivo é ajudar os desenvolvedores a entender melhor o relacionamento entre o HTML e o CSS em um determinado projeto.

A convenção de nomenclatura segue o padrão abaixo:

```css
.block {
  ...
}

.block__element {
  ...
}

.block--modifier {
  ...
}
```

**Exemplo:**

```css
.gallery {
  ...
}

.gallery__title {
  ...
}

.gallery__image {
  ...
}

.gallery__image--large {
  ...
}
```

- [Artigo sobre o BEM](https://css-tricks.com/bem-101/)
