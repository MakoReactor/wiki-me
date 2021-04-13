# Usando o comando grep

#### Como o grep funciona?

No terminal, você pode digitar, por exemplo:

Procurar uma palavra ou frase dentro de um arquivo, digite o comando grep a palavra ou frase que quer procurar \(sempre dentro das aspas\) e depois o nome do arquivo. Veja o exemplo abaixo.

`grep "palavra ou frase" arquivo.txt`

Caso queira fazer a mesma pesquisa só que ampliando para todos os arquivos dentro do diretório.Com isso, o grep vai procurar o trecho em todos os arquivos do diretório atual.

`grep "palavra ou frase" *`

Mas dá para especificar em qual diretório pesquisar. 

`grep "palavra ou frase" /var/www/*`

Também dá para fazer pesquisa recursiva, na qual o grep pesquinsa em todoas as subpastas do diretório especificado. O tempo vai demorar de acordo com a quatidade e o tamanho dos mesmos.

`grep -R "palavra ou frase" /var/www/`

Também dá para fazer a pesquisa ignorando maiúsculas e minúsculas.

`grep -i "palavra ou frase" arquivo.txt`

Caso deseje, pode ser fazer uma pesquisa inversa, onde o grep vai retornar todas as linhas do arquivo que não contiverem o texto selecionado.

`grep -v "palavra ou frase" arquivo.txt`

Agora misturando tudo. no comando abaixo o grep vai procurar recursivamente em todas as subpastas o trecho procurado, ignorando maiúsculas e minúsculas e retornar todas as linhas que **não** o contiverem.

`grep -Riv "palavra ou frase" /var/www/`

Também é possível salvar a saida do comando grep \(também do comando acima\) em um arquivo texto para uma consulta mais detalhada, assim o saida do comando não aparecerá na tela.

`grep "palavra ou frase" arquivo.txt > arquivodesaida.txt`

O grep também pode ser usando para filtrar uma saida de comando, no exemplo abaixo ele é usando para filtar a saida do comando ls \(ls = mostrar os arquivos do diretório\). Neste caso ao invés de mostrar todos os arquivos ele vai mostrar apenas os arquivos ou diretórios que contiverem termo  "teste" no caso do nosso exemplo.

`ls | grep teste`

O grep é um comando poderoso e com os exemplos acima 90% dos problemas são resolvidos \(estimativa baseada no meu uso\) e para saber mais do grep você pode acessar a documentação em: [https://www.gnu.org/software/grep/manual/grep.html](https://www.gnu.org/software/grep/manual/grep.html)

