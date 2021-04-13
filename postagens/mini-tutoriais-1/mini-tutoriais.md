---
description: Tutoriais rápidos de poucas linhas.
---

# Como instalar um tema no Hugo.

## Como instalar um tema no Hugo \(gerador de sites estáticos\).

Entrar na pasta raiz do projeto Hugo e digitar os comandos abaixo.

```text
git init

git submodule add https://github.com/vantagedesign/ace-documentation themes/ace-documentation
```

Depois editar o arquivo **config.toml** acrescentando a ultima linha como segue. Fazer a mesma coisa para qualquer outro tema.

```text
baseURL = "https://example.com"
languageCode = "en-us"
title = "My New Hugo Site"
theme = "ace-documentation" #<- Acrescentar essa linha
```



