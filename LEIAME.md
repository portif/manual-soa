# manual-soa

Manual de Sistemas Operacionais Abertos

## Uso

### Construindo o livro

Se você gostaria de desenvolver e construir o livro manual-soa, você deve:

- Clonar este repositório e execute
- Executar `pip install -r requirements.txt` (é recomendável que você faça isso em um ambiente virtual)
- (Recomendado) Remova o diretório `manual-soa_build` existente
- Execute `jupyter-book build manual-soa/`

Uma versão HTML totalmente renderizada do livro será construída em `manual-soa/_buil/dhtml`.

### Hospedando o livro

A versão html do livro está hospedada no branch `gh-pages` deste repositório. Foi criado um fluxo de trabalho de ações do GitHub que cria e envia automaticamente o livro para este branch em uma solicitação push ou pull para main.

Se desejar desativar essa automação, você pode remover o fluxo de trabalho de ações do GitHub e criar o livro manualmente:

- Navegando para sua construção local; e executar,
- `ghp-import -n -p -f manual-soa/_build/html`

Isso irá automaticamente enviar sua construção para o branch `gh-pages`. Mais informações sobre este processo de hospedagem podem ser encontradas [aqui](https://jupyterbook.org/publish/gh-pages.html#manually-host-your-book-with-github-pages).

## Contribuidores

Acolhemos e reconhecemos todas as contribuições. Você pode ver uma lista dos colaboradores atuais na [aba de colaboradores](https://github.com/jurandysoares/manual-soa/graphs/contributors).

## Créditos

Este projeto é criado usando o excelente código aberto [projeto do Jupyter Book](https://jupyterbook.org/) e o [executablebookscookiecutter-jupyter-book template](https://github.com/executablebooks/cookiecutter-jupyter-book).
