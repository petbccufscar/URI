# Problema:

Leia um valor de ponto flutuante com duas casas decimais. Este valor representa um valor monetário. A seguir, calcule o menor número de notas e moedas possíveis no qual o valor pode ser decomposto. As notas consideradas são de 100, 50, 20, 10, 5, 2. As moedas possíveis são de 1, 0.50, 0.25, 0.10, 0.05 e 0.01. A seguir mostre a relação de notas necessárias.

###### Problema completo: https://www.urionlinejudge.com.br/judge/pt/problems/view/1021

# Resolução:

O problema, basicamente, exige que, dado um valor monetário como entrado, calculemos quantas e quais notas/moedas serão necessárias, buscando utilizar a menor quantidade possível para alcançar o valor determinado.

Na função main(), iremos declarar uma variável para armazenar o valor monetário a ser inserido pelo usuário. Como o enunciado exige um valor de **ponto flutuante**, utilizaremos o tipo de variável `double`.
Devemos declarar, também, variáveis para guardar a quantidade necessária de cada nota e moeda. Visto que só é possível termos quantidades inteiras (não existindo 0,5 nota ou moeda), estas serão do tipo `int`, inicializadas com valor igual a zero.

```c
        double N;
        int notas100=0, notas50=0, notas20=0, notas10=0, notas5=0, notas2=0;
        int moedas1r=0, moedas50=0, moedas25=0, moedas10=0, moedas5=0, moedas1c=0;
```


Em seguida, faremos a leitura do valor monetário utilizando a função `scanf()`, a qual deve conter o argumento `%lf`, representando que trata-se de uma variável do tipo `double`.
Além disso, para que o exercício apresente a solução correta, precisaremos acrescentar 0.001 no valor da entrada, garantindo que o valor das 2 primeiras casas decimais (o enunciado solicita apenas esta precisão) não serão arredondadas.

```c
        scanf("%lf", &N);
        N = N + 0.001;
```

Para cumprir a exigência de entrada exemplificada no exercício [O arquivo de entrada contém um valor de ponto flutuante N (0 ≤ N ≤ 1000000.00)], iremos inserir uma estrutura `if`. Dentro desta, estará contida tanto a lógica do problema, quanto a impressão das saídas resultantes. Além disso, é importante iniciarmos nossos cálculos pelos maiores valores de notas/moedas, prezando, assim, pela menor quantidade possível destas ao final.
Tendo a entrada armazenada em `N`, verificamos se seu valor é maior ou igual ao maior valor existente (no caso, a nota de R$100,00), pois somente neste cenário conseguiremos utilizá-la. Em caso afirmativo, deve-se armazenar na variável `notas100` a quantidade máxima que podemos usufruir, a qual é obtida realizando a divisão do valor total pelo valor atual (neste caso: `N/100`). Como o valor de `N` pode conter parte decimal, o resultado desta divisão também tem possibilidade de apresentar-se do mesmo modo. Todavia, queremos apenas a parte inteira do resultado, a qual representa quantas notas de 100 reais precisaremos usar. Para que isto ocorra, é necessário inserir `(int)` anteriormente à conta.
Como próximo passo, o valor da entrada tem de ser atualizado, subtraindo o valor de todas as notas de 100 utilizadas, ou seja, **[valor da nota] * [quantidade de notas]**. E, por fim, será feito o uso da função `printf()` para exibir a quantidade de notas R$100,00 necessárias, cujo valor está armazenado na variável de tipo `int`, fazendo com que o argumento desta função seja `%d`.

```c
    if(0<=N<=1000000.00){
      printf("NOTAS:\n");

      if(N>=100){
        notas100 = (int)(N/100);
        N = N - (100*notas100);
      }
      printf("%d nota(s) de R$ 100.00\n", notas100);
    }
```

Este mesmo procedimento deve ser realizado para as demais notas e moedas contidas no enunciado do problema, mantendo-se dentro do primeiro `if`.


##### Para revisar sobre variáveis de ponto flutuante: [Tipos Float e Double](https://www.cprogressivo.net/2012/12/Os-tipos-float-e-double-numeros-decimais-reais-em-C.html)
##### Para revisar sobre variáveis do tipo inteiro: [Tipo Inteiro](https://www.cprogressivo.net/2012/12/O-tipo-inteiroint-na-linguagem-C.html)
##### Para revisar sobre a estrutura condicional: [If e Else](https://www.cprogressivo.net/2013/01/O-testecondicional-IF-ELSE.html)
##### Para revisar sobre formatação de saída: [Printf](https://alvinalexander.com/programming/printf-format-cheat-sheet/)


Caso tenha alguma dúvida sobre este problema ou sobre a resolução, entre em contato com o PET-BCC pelo nosso
[Facebook](https://www.facebook.com/petbcc/),
[Instagram](https://www.instagram.com/petbcc.ufscar/)
ou envie um e-mail com o assunto "URI" para petbcc.ufscar@gmail.com
