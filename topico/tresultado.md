## Resultado

Clique [AQUI](../media/sgbd-2024-1-bcc-resumo.pdf) para ver as notas.

#### Avaliação em 11/04/2024
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

#### Avaliação em 14/04/2024

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
&#x26BE; (b): Função Piso &#8213; bfr = ⎣ B / R ⎦ = ⎣ 1024 / 89 ⎦ =  ⎣ 11.5 ⎦ = 11 registros por bloco<br>
&#x26BE; (c): Função Teto &#8213; b = ⎡ (r * R) / bfr ⎤ = ⎡ 40000 * 89 / 1024 ⎤ = ⎡ 3476,6 ⎤ = 3477 blocos
 
