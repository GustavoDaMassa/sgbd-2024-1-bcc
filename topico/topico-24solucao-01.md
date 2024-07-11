Classifique os escalonamentos abaixo como:<br>
&#9745; Não-Recuperável (NR)<br>
&#9745; Recuperável (R)<br>
&#9745; Recuperável Sem Aborto em Cascata (RSAC)

|id|Escalonamento|Classificação|
|-|-|:-:|
|S<sub>1</sub>|r<sub>1</sub>(X); r<sub>2</sub>(X); w<sub>1</sub>(X); r<sub>1</sub>(Y); w<sub>1</sub>(Y); w<sub>2</sub>(X); c<sub>2</sub>; c<sub>1</sub>;|RSAC|
|S<sub>2</sub>|r<sub>1</sub>(X); w<sub>1</sub>(X); r<sub>2</sub>(X); r<sub>1</sub>(Y); w<sub>1</sub>(Y); c<sub>1</sub>; w<sub>2</sub>(X); c<sub>2</sub>;|R|
|S<sub>3</sub>|r<sub>1</sub>(X); w<sub>1</sub>(X); r<sub>2</sub>(X); r<sub>1</sub>(Y); w<sub>1</sub>(Y); w<sub>2</sub>(X); c<sub>1</sub>; c<sub>2</sub>;|R|
|S<sub>4</sub>|r<sub>1</sub>(X); w<sub>1</sub>(X); r<sub>2</sub>(X); r<sub>1</sub>(Y); w<sub>1</sub>(Y); w<sub>2</sub>(X); c<sub>2</sub>; c<sub>1</sub>;|NR|
|S<sub>5</sub>|r<sub>1</sub>(X); w<sub>1</sub>(X); r<sub>2</sub>(X); r<sub>1</sub>(Y); w<sub>2</sub>(X); w<sub>1</sub>(Y); c<sub>1</sub>; c<sub>2</sub>;|R|
|S<sub>6</sub>|r<sub>1</sub>(X); w<sub>1</sub>(X); r<sub>2</sub>(X); r<sub>1</sub>(Y); w<sub>2</sub>(X); w<sub>1</sub>(Y); c<sub>2</sub>; c<sub>1</sub>;|NR|
|S<sub>7</sub>|r<sub>1</sub>(X); r<sub>2</sub>(X); w<sub>1</sub>(X); r<sub>1</sub>(Y); w<sub>1</sub>(Y); w<sub>2</sub>(X); c<sub>1</sub>; c<sub>2</sub>;|RSAC|
|S<sub>8</sub>|r<sub>1</sub>(X); w<sub>1</sub>(X); r<sub>2</sub>(X); r<sub>1</sub>(Y); w<sub>2</sub>(X); c<sub>2</sub>; w<sub>1</sub>(Y); c<sub>1</sub>;|NR|
|S<sub>9</sub>|r<sub>1</sub>(X); w<sub>1</sub>(X); r<sub>2</sub>(X); w<sub>2</sub>(X); r<sub>1</sub>(Y); w<sub>1</sub>(Y); c<sub>1</sub>; c<sub>2</sub>;|R|
|S<sub>10</sub>|r<sub>1</sub>(X); w<sub>1</sub>(X); r<sub>2</sub>(X); w<sub>2</sub>(X); r<sub>1</sub>(Y); w<sub>1</sub>(Y); c<sub>2</sub>; c<sub>1</sub>;|NR|
|S<sub>11</sub>|r<sub>1</sub>(X); w<sub>1</sub>(X); r<sub>2</sub>(X); w<sub>2</sub>(X); r<sub>1</sub>(Y); c<sub>2</sub>; w<sub>1</sub>(Y); c<sub>1</sub>;|NR|
|S<sub>12</sub>|r<sub>1</sub>(X); w<sub>1</sub>(X); r<sub>2</sub>(X); w<sub>2</sub>(X); c<sub>2</sub>; r<sub>1</sub>(Y); w<sub>1</sub>(Y); c<sub>1</sub>;|NR|
|S<sub>13</sub>|r<sub>1</sub>(X); r<sub>2</sub>(X); w<sub>1</sub>(X); r<sub>1</sub>(Y); w<sub>2</sub>(X); w<sub>1</sub>(Y); c<sub>1</sub>; c<sub>2</sub>;|RSAC|
