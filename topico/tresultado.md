## Resultado

Clique [AQUI](../media/sgbd-2024-1-bcc-resumo.pdf) para ver as notas.

#### `Avaliação em 11/04/2024`
Para minimizar o impacto causado ... cache<br>
O princípio da localidade pode ser ...<br>
Se a memória principal e a memória cache ...<br>
Se os registradores e a cache ...<br>
O acesso a dados por meio de bloco ...<br>
Várias transações do banco de dados podem ...<br>
O emprego de pin-count nas páginas ...<br>
Uma página é substituída de seu buffer ...<br>
Em registros de tamanho variável ... O espaço livre está ... A operação de exclusão ...<br>
Uma página em cache do banco de dados ...<br>
O Sistema Gerenciador de Banco de Dados ...

#### `Avaliação em 14/04/2024`

Sobre arquivos não ordenados, são aplicáveis:<br>
&#x26BE; As organizações de registros ...<br>
&#x26BE; Os registros de tamanho ...<br>
&#x26BE; Estruturas adicionais ...<br>
Sobre a modificação de um registro de comprimento variável:<br>
&#x26BE; O registro modificado ...<br>
&#x26BE; Pode ocorrer a exclusão ...<br>
&#x26BE; Pode ocorrer a movimentação ...<br>
Dentre as estratégias estudadas para a exclusão de registros em arquivos não ordenados, aquelas que requerem reorganização periódica do arquivo são:<br>
&#x26BE; Aplicar uma marcação  ...<br>
&#x26BE; Ter uma lista  ...<br>
Um arquivo tem r = 40.000 registros ...<br>
&#x26BE; (a): ~~R = (40+1) + (9+1) + (0,4 * (39+1)) + (9+1) + (0,5*(7+1)) + (1+1) + (0,25*(3+1)) + (3+1) + 1 = 89 bytes~~<br>
&#x26BE; (a): R = (40+1) + (9+1) + (0,4 * (40+1)) + (9+1) + (0,5*(8+1)) + (1+1) + (0,25*(4+1)) + (3+1) + 1 = 90,15 bytes<br>
&#x26BE; (b): ~~Função Piso &#8213; bfr = ⎣ B / R ⎦ = ⎣ 1024 / 89 ⎦ =  ⎣ 11.5 ⎦ = 11 registros por bloco~~<br>
&#x26BE; (b): Função Piso &#8213; bfr = ⎣ B / R ⎦ = ⎣ 1024 / 90,15 ⎦ = ⎣ 11,36 ⎦ = 11 registros por bloco<br>
&#x26BE; (c): ~~Função Teto &#8213; b = ⎡ (r * R) / bfr ⎤ = ⎡ 40000 * 89 / 1024 ⎤ = ⎡ 3476,6 ⎤ = 3477 blocos~~<br>
&#x26BE; (c): Função Teto &#8213; b = ⎡ r / bfr ⎤ = ⎡ 40000  / 11 ⎤ = ⎡ 3636,36 ⎤ = 3637 blocos

#### `Avaliação em 02/05/2024`

Sobre o hashing externo ... <br>
&#x26BE; A presença de buckets de overflow ...<br>
Sobre a técnica hashing extensível ... <br>
&#x26BE; \<\< _nenhuma alternativa verdadeira_ \>\><br>
Sobre a técnica hashing linear ... <br>
&#x26BE; Pode ocorrer que um ou mais ... <br>
&#x26BE; Se um novo registro é inserido ... <br>
&#x26BE; O tamanho máximo do diretório ... <br>
Sobre a técnica hashing dinâmico ... <br>
&#x26BE; Um diretório é estruturado ... <br>
Sobre arquivos sequenciais ... <br>
&#x26BE; As organizações de registros ... <br>
&#x26BE; Os registros de ... <br>
&#x26BE; Estruturas adicionais ... <br>
Some as ... <br>
&#x26BE; Após a divisão de ... <br>
Some as ... <br>
&#x26BE; A função h<sub>j+1</sub>(K) ...

#### `Avaliação em 13/06/2024`

1. Índice primário; índice de agrupamento; índice secundário.
2. Índice secundário.
3. Índice secundário.
4. Cenário: Um índice multinível com dois níveis.<br>
<img src="../media/fig-indice-multinivel-9.jpg" width="90">

Nível 01: Um arquivo ordenado com 04 blocos.<br>
Nível 02: Um arquivo ordenado com 01 (um) bloco.<br><br>
Custo da pesquisa via índice de único nível (Nível 01): log<sub>2</sub>4 = 2 blocos.<br>
Custo da pesquisa via índice multinível (Níveis 02 e 01): 1 + 1 = 2 blocos.

5. O índice primário produz acesso de menor custo ao arquivo de dados.<br>
O número de registros (entradas) no índice primário é o número de blocos do arquivo de dados.

Sejam:<br>
r<sub>p</sub> o número de registros do arquivo de índice primário<br>
r<sub>a</sub> o número de registros do arquivo de índice de agrupamento<br>
b<sub>p</sub> o número de blocos do arquivo de índice primário<br>
b<sub>a</sub> o número de blocos do arquivo de índice de agrupamento<br>
Então:<br>
**r<sub>p</sub> < r<sub>a</sub>** ; possivelmente **b<sub>p</sub> < b<sub>a</sub>** ; possivelmente **log<sub>2</sub> b<sub>p</sub> < log<sub>2</sub> b<sub>a</sub><br>**
Em adição:<br>
O número de blocos de dados acessados via índice primário: 01 bloco.<br>
O número de blocos de dados acessados via índice de agrupamento: pode ser maior que 01 bloco.

#### `Avaliação em 20/06/2024`

B = 1024 bytes ; V = 9 bytes ; P<sub>a</sub> = 6 bytes ; P<sub>d</sub> = 7 bytes

1. **(a)** A ordem **p** para os nós internos.

|Árvore B|Árvore B<sup>+</sup>|
|-|-|
|((p-1) * V) + ((p-1) * P<sub>d</sub>)) + (p * P<sub>a</sub>) &#8804; B<br>(9p - 9) + (7p - 7) + (6p) &#8804; 1024<br>22p &#8804; 1040 &#8756; **p = piso (1040/22)**|((p-1) * V) + (p * P<sub>a</sub>) &#8804; B<br>(9p - 9) + (6p) &#8804; 1024<br>15p &#8804; 1033 &#8756; **p = piso (1033/15)**|

1. **(b)** A ordem **p<sub>folha</sub>** para os nós folhas.

|Árvore B|Árvore B<sup>+</sup>|
|-|-|
|**p<sub>folha</sub> = p = piso (1040/22)**|( p<sub>folha</sub> * (P<sub>d</sub> + V) ) + P<sub>a</sub> &#8804; B<br>( p<sub>folha</sub> * (7 + 9) ) + 6 &#8804; 1024<br>16p<sub>folha</sub> &#8804; 1018 &#8756; **p<sub>folha</sub> = piso (1018/16)**|

1. **(c)** A quantidade **n<sub>0</sub>** de valores do campo de indexação no **Nível 0** da árvore (nó raiz).

|Árvore B|Árvore B<sup>+</sup>|
|-|-|
|Nós internos e folhas estão 70% cheios:<br>&#9888; p = 0,7 * p<br><br>Há apenas um nó em Nível 0.<br>Este nó possui (p – 1) valores do campo de indexação.<br>n<sub>0</sub> = 1 * (p – 1)<br>**n<sub>0</sub> = (0,7 * piso(1040/22)) – 1**|Nós internos e folhas estão 70% cheios:<br>&#9888; p = 0,7 * p<br><br>Há apenas um nó em Nível 0.<br>Este nó possui (p – 1) valores do campo de indexação.<br>n<sub>0</sub> = 1 * (p – 1)<br>**n<sub>0</sub> = (0,7 * piso(1033/15)) – 1**|

1. **(d)** A quantidade **n<sub>1</sub>** de valores do campo de indexação no **Nível 1** da árvore (nós folhas).

|Árvore B|Árvore B<sup>+</sup>|
|-|-|
|Nós internos e folhas estão 70% cheios:<br>&#9888; p = 0,7 * p<br>&#9888; p<sub>folha</sub> = 0,7 * p<sub>folha</sub><br><br>Há p nós em Nível 1.<br>Cada nó possui (p<sub>folha</sub> – 1) valores do campo de indexação.<br>n<sub>1</sub> = p * (p<sub>folha</sub> – 1)<br>**n<sub>1</sub> = (0.7 * piso(1040/22)) * ((0,7 * piso(1040/22)) – 1)**|Nós internos e folhas estão 70% cheios:<br>&#9888; p = 0,7 * p<br>&#9888; p<sub>folha</sub> = 0,7 * p<sub>folha</sub><br><br>Há p nós em Nível 1.<br>Cada nó possui (p<sub>folha</sub>) valores do campo de indexação.<br>n<sub>1</sub> = p * p<sub>folha</sub><br>**n<sub>1</sub> = (0.7 * piso(1033/15)) * (0,7 * piso(1018/16))**|

#### `Avaliação em 27/06/2024`

|Questão|Resposta|
|-|:-:|
|Um único campo ...|01|
|O fator de bloco ...|03|
|Em um cenário ...|02|
|A execução das operações ...|01|
|Há escalonamentos inválidos ...|00|
|A propriedade isolamento ...|00|
|Escalonamentos não-seriais ...|01|
|A cache (buffer pool) ...|01|
|Os nós internos ...|01|
|Os nós folhas ...|01|
|Árvores B ...|02|
|Índices secundários ...|02|
|O conceito de registro ...|00|
|A técnica hashing linear ...|02|
|No hashing externo, se vários ...|01|
|No hashing externo dinâmico ...|03|
|Na organização de arquivos não-ordenados ...|03|
|No gerenciamento de buffer ...|02|
|Na clock policy ...|03|
|Nem sempre um bloco ...|03|

#### `Avaliação em 04/07/2024`

|Escalonamento|Classificação|
|-|:-:|
|r2(X); r1(X); w1(X); r1(Y); w1(Y); w2(X); c2; c1;|RSAC|
|r2(X); w2(X); r1(X); w1(X); r1(Y); w1(Y); c1; c2;|NR|
|r2(X); w2(X); r1(X); w1(X); r1(Y); w1(Y); c2; c1;|R|
|r2(X); w2(X); r1(X); w1(X); r1(Y); c2; w1(Y); c1;|R|
|r2(X); w2(X); c2; r1(X); w1(X); r1(Y); w1(Y); c1;|RE|
|r2(X); w2(X); r1(X); w1(X); c2; r1(Y); w1(Y); c1;|R|
|r2(X); w2(X); r1(X); c2; w1(X); r1(Y); w1(Y); c1;|R|
|r1(X); r2(X); w2(X); c2; w1(X); r1(Y); w1(Y); c1;|RE|
|r2(X); r1(X); w1(X); r1(Y); w1(Y); c1; w2(X); c2;|RE|
|r2(X); r1(X); w1(X); r1(Y); w1(Y); w2(X); c1; c2;|RSAC|

#### `Avaliação em 11/07/2024`

**Questão 01**<br>
<img src="../media/fig-av-20240711-a.jpg" width="80"><br>
Sim, pois NÃO HÁ CICLO no grafo de precedência.<br>
Escalonamentos seriais equivalentes em conflito:<br>
T3 &#8658; T1 &#8658; T2<br>
T3 &#8658; T2 &#8658; T1<br>
<br>
<img src="../media/fig-av-20240711-b.jpg" width="80"><br>
Não, pois HÁ CICLO no grafo de precedência.<br>

**Questão 02**<br>
1, 6

#### `Avaliação em 12/07/2024`

1. Obtém todos os bloqueios dentro ... 07
2. Obtém todos os bloqueios fora ... 08
3. Possui fase de crescimento ... 07
4. Possui fase de encolhimento ... 13
5. É livre de _deadlock_ ... 08
6. Não é livre de _dadlock_ ... 07
7. Libera os bloqueios exclusivos ... 06
8. Libera os bloqueios compartilhados ... 02
9. É livre de _starvation_ ... 00
10. Garante a ... 15

