# Guia de código CSS

Padrões para escrever CSS consistente, flexível e escalável.

## Tabela de conteúdos

- [Terminologia](#terminologia)
  - [Regra](#regra)
  - [Seletores](#seletores)
  - [Propriedades](#propriedades)
- [CSS](#css)
  - [Sintaxe](#sintaxe)
  - [Declarações únicas](#declarações-únicas)
  - [Notação abreviada](#notação-abreviada)
  - [Comentários](#comentários)
- [Nomenclatura](#nomenclatura)
  - [Nomes de classes](#nomes-de-classes)
  - [Metodologia BEM CSS](#metodologia-bem-css)

## Terminologia

### Regra

Uma "declaração de regra" sempre começa com um "seletor" (ou grupo de seletores) que define a quais elementos HTML ela se aplica. Após o seletor, temos um grupo de "propriedades" e seus respectivos valores.

**Exemplo:**

```css
.header {
  color: #414141;               
  background-color: #EEEEEE;   
}
```

### Seletores

Os seletores determinam quais elementos na árvore DOM serão estilizados pelas propriedades definidas.

**Exemplos:**

```css
.title { ... }

[aria-hidden] { ... }
```

### Propriedades

As propriedades são pares de chave-valor e definem o visual para cada "seletor". Uma regra pode conter uma ou mais propriedades.

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
- Ao agrupar seletores, mantenha-os em linhas individuais.
- Para maior legibilidade, inclua um espaço antes da chave de abertura dos blocos de declaração e em uma nova linha a chave de fechamento.
- Inclua um espaço depois `:` para cada declaração.
- Finalize todas as declarações com ponto e vírgula. A última declaração é opcional, mas seu código é mais suscetível a erros sem ele.
- Use todos os valores hexadecimais em minúsculo, por exemplo `#f1f1f1`.
- Use valores hexadecimais abreviados quando disponíveis, por exemplo, `#fff` em vez de `#ffffff`.
- Cite valores de atributo em seletores, por exemplo `input[type="text"]`.
- Evite especificar unidades para valores zero, por exemplo, `margin: 0;` em vez de `margin: 0px;`.
- Não use seletores `ID` para estilos.

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

### Declarações únicas

Nos casos em que um conjunto de regras inclui apenas uma declaração, considere remover quebras de linha para facilitar a leitura e editar mais rapidamente. Lembre-se que para qualquer regra definida com várias declarações deve ser dividida em linhas separadas.

**Exemplo:**

```css
/* Single declarations on one line */
.span1 { width: 60px; }
.span2 { width: 140px; }
.span3 { width: 220px; }

/* Multiple declarations, one per line */
.sprite {
  display: inline-block;
  width: 16px;
  height: 15px;
  background-image: url("../img/sprite.png");
}

.icon           { background-position: 0 0; }
.icon-home      { background-position: 0 -20px; }
.icon-account   { background-position: 0 -40px; }
```

### Notação abreviada

Limite o uso da declaração abreviada para instâncias em que você deve definir explicitamente todos os valores disponíveis. As propriedades de taquigrafia* frequentemente usadas em excesso incluem:

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

*Propriedades de taquigrafia são propriedades de CSS que lhe permitem definir simultaneamente os valores de várias outras propriedades de CSS.

### Comentários

Verifique se o seu código é descritivo, bem comentado e acessível por outras pessoas. Escreva frases completas para comentários maiores (descrevendo exatamente o componente) e frases sucintas para notas gerais.

```css
/* Bad example */
/* Modal header */
.modal-header { ... }

/* Good example */
/* Wrapping element for .modal-title and .modal-close */
.modal-header { ... }
```

## Nomenclatura

### Nomes de classes

- Mantenha as classes em minúsculas e use traços (não sublinhados ou camelCase), por exemplo, `.btn-danger`.
- Evite notações abreviadas e sem significado. `.btn` é útil para o botão, mas `.b` não significa nada.
- Mantenha as classes curtas e autoexplicativas.

```css
/* Bad example */
.t {
  ...
}

.red { ... }
.header { ... }

/* Good example */
.tweet { ... }
.important { ... }
.tweet-header { ... }
```

### Metodologia BEM CSS

A metodologia BEM (Block, Element, Modifier) é uma convenção de nomenclatura popular para classes em HTML e CSS. Desenvolvido pela equipe da Yandex, seu objetivo é ajudar os desenvolvedores a entenderem melhor o relacionamento entre o HTML e o CSS em um determinado projeto.

A convenção de nomenclatura segue o padrão abaixo:

```css
.block { ... }
.block__element { ... }
.block--modifier { ... }
```

**Exemplo:**

```css
/* Block */
.gallery { ... }

/* Element */
.gallery__title { ... }

.gallery__image { ... }

/* Modifier */
.gallery__image--large { ... }
```

- [Artigo sobre o BEM](https://css-tricks.com/bem-101/)
