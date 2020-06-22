# Problema:

Leia a hora inicial, minuto inicial, hora final e minuto final de um jogo. A seguir calcule a duração do jogo e mostre o resultado na tela usando a seguinte mensagem: “O JOGO DUROU XXX HORA(S) E YYY MINUTO(S)”.

Obs: O jogo tem duração mínima de um (1) minuto e duração máxima de 24 horas.

##### Problema completo: https://www.urionlinejudge.com.br/judge/pt/problems/view/1047

# Resolução:

O problema quer saber quanto tempo durou um jogo tendo como base a hora em que o jogo começou e a hora que terminou. Para isso é necessário subtrair o tempo final do inicial. Caso o tempo final tenha um valor menor que o tempo inicial, somamos 24 ao valor da hora em que o jogo terminou. Também deve ser considerado que o valor de horas não pode passar de 23 e o valor de minutos não pode ser maior que 59.

Para resolver o exercício precisamos criar 6 variáveis do tipo `int`:
```c
        int h1, m1, h2, m2, th, tm;
```
No enunciado do problema, está escrito para ler quatro valores, que no caso são `h1`, `m1`, `h2` e `m2`, e para imprimir as variáveis `th` e `tm`, que correspondem ao tempo de duração do jogo.

Para ler as variáveis, usa-se `scanf`:
```c	
        scanf("%d%d%d%d", &h1, &m1, &h2, &m2);
```
É possível inserir mais de um dado dentro do mesmo `scanf` usando vários `%d`, que é utilizado para ler uma variável do tipo `int`.

Agora iniciaremos o processo para calcular o tempo de duração do jogo. A primeira coisa a se fazer é verificar se os valores de hora (`h1` e `h2`) e minuto (`m1` e `m2`) são iguais entre si. Isso é verificado usando `==` para saber se os valores são iguais e `&&` para saber se as duas condições ocorrem. Se sim isso significa que o jogo durou um dia, ou seja, 24 horas:
```c
        if ((m1 == m2) && (h1 == h2)) {
            tm = m2 - m1;
            th = 24;
        }
```

Caso a condição acima seja falsa, o programa realiza as operações dentro do `else`. Primeiro faremos o cálculo dos minutos de duração do jogo:
```c
        else {   
            if ((m2 - m1) >= 0)
                tm = m2 - m1;
            else {
                m2 = m2 + 60;
                tm = m2 - m1;
                h2--;
            }
```
Aqui é utilizado uma outra operação condicional, mas agora dentro de um `else`. Isso é chamado de estrutura de decisão encadeada. Aqui separamos o valor de minutos que o jogo durou em dois casos: o primeiro caso em que o valor de minutos inicial (`m1`) é menor ou igual ao valor de minutos final (`m2`), fazendo a subtração para obter o valor `tm`; o segundo caso ocorre o contrário e, para fazer a subtração, é preciso somar 60 minutos no minuto final (`m2`) e subtrair em 1 o valor de hora final (`h2`) para poder calcular os minutos de duração do jogo.

Agora falta calcular quantas horas durou o jogo. Para isso fazemos novamente os dois casos mencionados anteriormente, com a diferença que no segundo caso, ao invés de adicionar 60 ao menor valor, adicionamos 24, que corresponde ao número de horas em um dia:
```c
            if ((h2 - h1) >= 0)
                th = h2 - h1;
            else {
                h2 = h2 + 24;
                th = h2 - h1;
            }
        }
```

E por fim, escrevemos o resultado na tela utilizando a função `printf`:
```c
        printf("O JOGO DUROU %d HORA(S) E %d MINUTO(S)\n", th, tm);
```
O primeiro `%d` será substituído pelo valor contido em `th`, variável que representa o número de horas que o jogo durou. O segundo `%d` será substituído pelo valor contido em `tm`, variável que representa o número de minutos que o jogo durou. O `\n` no fim serve para pular uma linha na tela depois de mostrar o dado.

##### Para aprender um pouco mais sobre operadores lógicos: [Operadores](http://linguagemc.com.br/operadores-logicos-em-c/)
##### Para aprender um pouco mais sobre decisões encadeadas: [Estrutura de decisão encadeada](http://linguagemc.com.br/estruturas-de-decisao-encadeadas-if-else-if-else/)

Caso tenha alguma dúvida sobre este problema ou sobre a resolução, entre em contato com o PET-BCC pelo nosso
[Facebook](https://www.facebook.com/petbcc/),
[Instagram](https://www.instagram.com/petbcc.ufscar/)
ou nos mande um e-mail com o assunto "URI" para  petbcc.ufscar@gmail.com
