# Guia de estilo CSS

Uma abordagem para escrever CSS gerenciável e escalável.

## Tópicos

## Terminologia

### Regra

Regra é o nome dado ao seletor (ou grupo de seletores) acompanhados de um grupo de propriedades com seus respectivos valores.

Exemplo:

```css
.titulo {
  font-size: 18px;
  line-height: 1.2;
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
