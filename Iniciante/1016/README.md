# Problema:

Dois carros (X e Y) partem em uma mesma direção. O carro X sai com velocidade constante de 60 Km/h e o carro Y sai com velocidade constante de 90 Km/h.

**Em uma hora (60 minutos) o carro Y consegue se distanciar 30 quilômetros do carro X, ou seja, consegue se afastar um quilômetro a cada 2 minutos.**

Leia a distância (em Km) e calcule quanto tempo leva (em minutos) para o carro Y tomar essa distância do outro carro.

###### Problema completo: https://www.urionlinejudge.com.br/judge/pt/problems/view/1016

# Resolução:

Como o carro Y leva 2 minutos para se afastar 1 km do outro, conforme o enunciado, por conta da velocidade de distanciação, já que **30km/h = 30km/60min = 1km/2min** , lê-se a distância e a multiplica por 2, para calcular o tempo necessário. 

Para representar o valor da distância em nosso programa, fazemos: 

```c
        int dist;
```

Para ler a entrada, usa-se `scanf`:

```c
        scanf("%d", &dist);
```

Em seguida, calculamos e escrevemos o resultado, `dist*2` na tela utilizando a função `printf`:

```c
        printf("%d minutos\n", dist*2);
```

Caso tenha alguma dúvida sobre este problema ou sobre a resolução, entre em contato com o PET-BCC pelo nosso
[Facebook](https://www.facebook.com/petbcc/),
[Instagram](https://www.instagram.com/petbcc.ufscar/)
ou envie um e-mail com o assunto "URI" para petbcc.ufscar@gmail.com

