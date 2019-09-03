# Guia de estilo CSS

Uma abordagem para escrever CSS gerenciável e escalável.

## Tópicos

## Terminologia

### Regra

Uma "regra" de CSS sempre começa com um "seletor" (ou grupo de seletores) que define a quais elementos HTML ele se aplica. Após o seletor, temos um bloco de declarações de "propriedades" e seus respectivos valores.

Exemplo:

```css
.header {
  color: #414141;               
  background-color: #EEEEEE;   
}
```

### Seletores

Os seletores determinam quais elementos na árvore de DOM serão estilizados pelas propriedades definidas.

Exemplos:

```css
.titulo {
  /* ... */
}

[aria-hidden] {
  /* ... */
}
```

### Propriedades

As propriedades são pares de chave-valor, onde uma regra pode conter uma ou mais declaração de propriedades.

Exemplo:

```css
/* algum-seletor */ {
  background: #f1f1f1;
  color: #e18728;
}
```
