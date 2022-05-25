# Arroz com Python o poder da progressão geométrica

## O problema do tabuleiro de Xadrez e o Arroz.

Conta a lenda que o xadrez foi inventado na Índia, há mais de 1500 anos. O rei ficou tão fascinado com a invenção e as infinitas variações de movimentos, que resolveu recompensar o inventor.

O rei perguntou: O que você quer de recompensa?

Inventor: Quero um grão de arroz para a primeira casa, dois grãos para a segunda casa, 4 para a terceira, e assim sucessivamente.

“Só isso?”, o rei retrucou.

Então, o rei pediu para os matemáticos do reino fazerem as contas.

1. Na primeira casa, 1 grão = 2^0
2. Na segunda casa, 2 grãos = 2^1,
3. Na terceira casa, 4 grãos = 2^2.

E assim por diante até a casa 64 que seria 2^63.

```python
# colocar todos os valores de cada casa do xadrez em uma lista.
graos_arroz_tab_xadrez = [2**x for x in range(64)]

# Mostrar quantos grãos foram em cada casa do tabuleiro de Xadrez
count = 1
for graos in graos_arroz_tab_xadrez:
  print(f'Casa: {count} Nº de grãos {graos}')
  count += 1
```

```
Casa: 1 Nº de grãos 1
Casa: 2 Nº de grãos 2
Casa: 3 Nº de grãos 4
........
Casa: 62 Nº de grãos 2305843009213693952
Casa: 63 Nº de grãos 4611686018427387904
Casa: 64 Nº de grãos 9223372036854775808
```

#### Agora que sabemos quantos grãos de arroz foram usados em cada casa do tabuleiro , vamos verificar o total de arroz usado, uma vez que o arroz usado na casa anterior é somado no final de tudo.

Exemplo:

* Na casa 1 foi usado 1 grão de arroz
* Na casa 2 foram usados 2 grãos
* Na casa 3 foram usados 4 grãos.

Dessa forma foram usados 1 + 2 + 4 = 7 Grãos aplicando essa fórmula teríamos que somar até a casa 64, mas o Python vai nos ajudar nesse trabalho.

```python
# Somar todos os itens da lista com ao função buit-in sum()
somatoria_graos_arroz = sum(graos_arroz_tab_xadrez)

print(f'Quantidade de Grãos de Arroz supostamente usados no tabuleiro: {somatoria_graos_arroz} ')
```

`Quantidade de Grãos de Arroz supostamente usados no tabuleiro: 18446744073709551615`

Agora que temos o total do número de grãos usados para preencher todo o tabuleiro precisamos saber quanto isso dá em quilogramas.

E nisso uma pessoa com bastante tempo livre já nos deu a resposta.

Nesse post: [Jovem conta quantos grãos de Arroz tem um quilograma](https://tabonito.com/jovem-fez-direto-a-contar-quantos-graos-de-arroz-tem-um-saco-de-1kg/) ele chega ao número de 50966 grãos.

Então com esses dados vamos calcular o arroz em quilogramas e depois em toneladas para facilitar as contas.

```python
# Calcular Total de Grãos do Tabuleiro em Quilograma
total_graos_arroz_em_quilos = somatoria_graos_arroz / 50966

# Agora vamos transformar mais uma vez, só que desta vez para Toneladas.
# Cada tonelada são Mil quilos, então temos que dividir o valor em quilos por 1000
total_arroz_em_toneladas = total_graos_arroz_em_quilos / 1000
print(f'Temos {total_arroz_em_toneladas} de Toneladas de Arroz.')
```

```
> Temos 361942158963.0254 de Toneladas de Arroz.
```

O valor de 361.942.158.963,0254 toneladas é o mesmo que dizer.

361 bilhões 942 milhões 158 mil e 963 TONELADAS de Arroz.

Para se ter uma ideia [a produção de Arroz mundial na safra 2021/2022 foi de 517 Milhões de Toneladas.](https://www.canalrural.com.br/radar/arroz-orgao-do-g-20-eleva-estimativa-para-producao-mundial-em-2021-22/)

Então vamos fazer a conta para saber se isso é muito ou pouco.

```python
# vamos calcular quantos anos seriam necessários (usando a produção atual de arroz) para
# atingirmos o total de arroz usados 
producao_mundial_21_22_toneladas = 517.1
total_anos_para_atingir_valor = total_arroz_em_toneladas / producao_mundial_21_22_toneladas
print(f'Serian necessários {total_anos_para_atingir_valor} de anos com a produção atual para atingir a quantidade de Arroz pedida no tabuleiro')

```

```
Serian necessários 699946159.2787186 de anos com a produção atual para atingir a quantidade de Arroz pedida no tabuleiro
```

## Conclusão

No final temos o valor de 699.946.159,2787186, ou seja precisaríamos de mais de **699 milhões** de anos produzindo arroz na escala atual (2022) para suprir a quantidade de arroz necessária para preencher o tabuleiro.

Esse é o poder da progressão geométrica.
