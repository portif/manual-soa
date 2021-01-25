---
jupytext:
  cell_metadata_filter: -all
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.12
    jupytext_version: 1.9.1
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Arquivos Markdown

Quer você escreva o conteúdo do seu livro em Jupyter Notebooks (`.ipynb`) ou em arquivos de markdown regulares (`.md`), você escreverá no mesmo tipo de markdown chamado **MyST Markdown**.

## O que é MyST?

MyST significa "texto estruturado marcadamente". Isto
é uma ligeira variação de um tipo de markdown chamado markdown "CommonMark", com pequenas extensões de sintaxe para permitir que você escreva **funções** e **diretivas** no ecossistema da Esfinge.

## O que são funções e diretivas?

Funções e diretivas são duas das ferramentas mais poderosas do Jupyter Book. Eles são funções semelhantes, mas escritas em uma linguagem de marcação. Ambos servem a um propósito semelhante, mas **funções são escritas em uma linha**, enquanto
**as diretivas abrangem muitas linhas**. Ambos aceitam diferentes tipos de entradas, e o que eles fazem com essas entradas depende da função ou diretiva específica que está sendo chamado.

### Usando uma diretiva

Na sua forma mais simples, você pode inserir uma diretiva no conteúdo do seu livro da seguinte forma:

````
```{nome-de-minha-diretiva}
Conteúdo de minha diretiva
```
````

Isso só funcionará se uma diretiva com o nome `mydirectivename` já existir (o que não acontece). Existem muitas diretivas predefinidas associadas a Livro de Jupyter. Por exemplo, para inserir uma caixa de nota em seu conteúdo, você pode use a seguinte diretiva:

````
```{note}
Aqui é uma nota
```
````

O resultado é:

```{note}
Aqui é uma nota
```

Em seu livro construído.

Para obter mais informações sobre como escrever diretivas, consulte o
[Documentação MyST](https://myst-parser.readthedocs.io/).

+++

### Usando uma função

As funções são muito semelhantes às diretivas, mas são menos complexas e escritas inteiramente em uma linha.Você pode inserir uma função no conteúdo do seu livro com esse padrão:

```
Algum conteúdo {rolename}`e aqui está o conteúdo da minha função!`
```

Novamente, os papéis só funcionarão se `rolename` for um nome de papel válido. Por exemplo, a função `doc` pode ser usada para se referir a outra página em seu livro. Você pode se referir diretamente a outra página por seu caminho relativo. Por exemplo, a sintaxe da função `` {doc}`intro` `` resultará em: {doc}` intro`.

Para obter mais informações sobre como escrever funções, consulte o
[Documentação MyST](https://myst-parser.readthedocs.io/).

### Adicionando uma citação

Você também pode citar referências que estão armazenadas em um arquivo `bibtex`. Por exemplo, a seguinte sintaxe: `` {cite}`holdgraf_evidence_2014` `` será renderizada assim: {cite}`holdgraf_evidence_2014`.

Além disso, você pode inserir uma bibliografia em sua página com esta sintaxe. A diretiva `{bibliography}` deve ser usada para que todas as funções `{cite}` sejam renderizadas corretamente. Por exemplo, se as referências para o seu livro estão armazenadas em `referencias.bib`, então a bibliografia é inserida com:

````
```{bibliography} referencias.bib
```
````

Resultando em uma bibliografia renderizada que se parece com:

```{bibliography} referencias.bib
```

### Executando código em seus arquivos markdown

Se você gostaria de incluir conteúdo computacional dentro desses arquivos markdown, você pode usar MyST Markdown para definir células que serão executadas quando seu livro é construído. O Jupyter Book usa *jupytext* para fazer isso.

Primeiro, adicione metadados Jupytext ao arquivo. Por exemplo, para adicionar metadados Jupytext para esta página de redução, execute este comando:

```
jupyter-book myst init markdown.md
```

Uma vez que um arquivo markdown contém metadados Jupytext, você pode adicionar o seguinte diretiva para executar o código em tempo de compilação:

````
```{code-cell}
print("Aqui está um código para executar")
```
````

Quando seu livro for construído, o conteúdo de qualquer bloco `{code-cell}` será executado com seu kernel Jupyter padrão, e suas saídas serão exibidas em linha com o resto do seu conteúdo.

```{code-cell}
print("Aqui está um código para executar")
```

Para obter mais informações sobre a execução de conteúdo computacional com o Jupyter Book, consulte [The MyST-NB documentation](https://myst-nb.readthedocs.io/).
