# Guia de código CSS

Padrões para escrever CSS consistente, flexível e escalável.

## Tabela de conteúdos

- [Terminologia](#terminologia)
  - [Regra](#regra)
  - [Seletores](#seletores)
  - [Propriedades](#propriedades)
- [CSS](#css)
  - [Formato](#formato)
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

### Formato

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
.btn {
  border-radius: 50%;
  border: 2px solid white;
}

.btn:disabled,
.btn.btn-disabled {
  /* ... */
}
```

### Comentários

- Deixe um comentário sempre que o trecho não seja óbvio apenas a partir do código
- Prefira comentários em uma única linha

## BEM

A metodologia Block, Element, Modifier (comumente referida como BEM ) é uma convenção de nomenclatura popular para classes em HTML e CSS. Desenvolvido pela equipe da Yandex, seu objetivo é ajudar os desenvolvedores a entender melhor o relacionamento entre o HTML e o CSS em um determinado projeto.

A convenção de nomenclatura segue o padrão abaixo:

```css
.block {

}
.block__element {

}
.block--modifier {

}
```

**Exemplo:**

```html
<div class="gallery">
  <h1 class="gallery__title">Gallery</h1>
  <img class="gallery__image gallery__image--large" />
  <img class="gallery__image" />
  <img class="gallery__image" />
</div>
```

- [Artigo sobre o BEM](https://css-tricks.com/bem-101/)
