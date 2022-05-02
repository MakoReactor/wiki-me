---
description: Usando Lamba
---

# Como ordenar um Dicionário em Python

Digite o seguinte comando para ordenar um dicionário.

```
dict_ordered = sorted(dictio.items(), key=lambda item : item[1])
```

Caso queira que seja ordenado do maior para o menor acrescente a cláusula reverse ao comando.

```
dict_ordered = sorted(dictio.items(), key=lambda item : item[1], reverse=True)
```
