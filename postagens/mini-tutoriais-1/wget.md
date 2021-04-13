---
description: Formas de usar o wget no linux via linha de comando.
---

# Wget dicas de uso

## Instalar wget \(debian, ubuntu, linuxmint\).

```text
$> sudo apt install wget
```

### Baixar uma página ou arquivo da internet.

Página

```text
$> wget <url da página>
```

Arquivo

```text
$> wget <url da página>.<arquivo>
```

Download vários arquivos salvos em um arquivo texto, cujo seja um arquivo como final do link.

```text
$> wget -i arquivo_com_links_para_baixar.txt
```

Mudar o nome do arquivo no downlod.

```text
$> wget -O nome_do_aquivo <url>
```

Baixando uma pasta online \(ftp por exemplo\).

```text
$> wget -r ftp://servidor-ftp.com/diretório
```

### Baixar site completo usando o wget

```text
$> wget -m --convert-links --page-requisites <url-do-site>
```

