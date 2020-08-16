# Problema:

Em Westeros, por exemplo, o humor das pessoas é definido de acordo com as tendências climáticas. Com base nas temperaturas dos três últimos dias, as pessoas podem ficar tristes ou felizes, ficando mais propensas a fazer guerra ou fazer amor, respectivamente. 

1. Se a temperatura desceu do 1º para o 2º dia, mas subiu ou permaneceu constante do 2º para o 3º, as pessoas ficam felizes (primeira figura).
2. Se a temperatura subiu do 1º para o 2º dia, mas desceu ou permaneceu constante do 2º para o 3º, as pessoas ficam tristes (segunda figura).
3. Se a temperatura subiu do 1º para o 2º dia e do 2º para o 3º, mas subiu do 2º para o 3º menos do que subira do 1º para o 2º, as pessoas ficam tristes (terceira figura).
4. Se a temperatura subiu do 1º para o 2º dia e do 2º para o 3º, mas subiu do 2º para o 3º no mínimo o tanto que subira do 1º para o 2º, as pessoas ficam felizes (quarta figura).
5. Se a temperatura desceu do 1º para o 2º dia e do 2º para o 3º, mas desceu do 2º para o 3º menos do que descera do 1º para o 2º, as pessoas ficam felizes (quinta figura).
6. Se a temperatura desceu do 1º para o 2º dia e do 2º para o 3º, mas desceu do 2º para o 3º no mínimo o tanto que descera do 1º para o 2º, as pessoas ficam tristes (sexta figura).
7. Se a temperatura permaneceu constante do 1º para o 2º dia, as pessoas ficam felizes se subiu do 2º para o 3º dia ou tristes caso contrário (respectivamente, sétima e oitava figuras).

![Graficos](https://resources.urionlinejudge.com.br/gallery/images/problems/UOJ_1847.jpg)
###### Problema completo: https://www.urionlinejudge.com.br/judge/pt/problems/view/1847

# Resolução:
Para resolver esse problema receberemos as temperaturas registradas no 1º, 2º e 3º dia, respectivamente, e ao compara-las exibiremos o humor do povo de westeros de acordo com as tendências climáticas, utilizando as condições apresentadas no problema como referência.

Para começar declaramos as variáveis dos 3 dias que receberão valores referentes ao clima:
```c
int a, b, c;
```

Depois recebemos as temperaturas com o comando `scanf`:
```c
scanf("%d %d %d", &a, &b, &c);
```

Como existem várias combinações semelhantes que influenciam de forma diferente o humor, primeiro iremos comparar se o clima do primeirio dia é mais quente que do segundo. Desse forma, agrupamos 3 possibilidades(condições: 1, 5 e 6). 
```c
if(a>b){
	/*
	Próximo Bloco de Código
	*/	
}
```
Ao observar as possibilidades dessas 3 condições percebemos que duas representam o humor feliz(condições: 1 e 5) e uma representa o humor triste(condição 6). Para separá-las verificamos se a temperatura do 3º dia é *menor* que a do 2º *e* se a diferença entre as temperaturas do 2º e 3º dia é *maior ou igual* a diferença das temperaturas do 1º e 2º dia.  
* Se sim, imprimimos o humor triste: :(
* Se não, imprimimos o humor feliz: :)
```c
if(c<b && (b-c)>=(a-b))
		printf(":(\n");
	else 
	    printf(":)\n");
```

Depois, com o comando`else if` comparamos se a temperatura do primeiro dia é menor do que a do segundo. Assim, agrupamos outras 3 possibilidades(condições: 2, 3 e 4)
```c
else if(b>a){
	/*
	Próximo Bloco de Código
	*/
}
```
Observando as possibilidades dessas 3 figuras percebemos duas representam o humor triste(condições: 2 e 3) e uma que representa o humor feliz(condição: 4). Para separá-las verificamos se a temperatura do 3º dia é *maior* que a do 2º *e* se a diferença entre as temperaturas do 2º e 3º dia é *maior ou igual* a diferença das temperaturas do 1º e 2º dia.  
* Se sim, imprimimos o humor feliz: :)
* Se não, imprimimos o humor triste: :(

```c
if(c>b && (c-b)>=(b-a))
		printf(":)\n");
	else
		printf(":(\n");
```
E, por último, verificamos se a temperatura do primeiro dia é igual a do segundo.  Assim, agrupamos as últimas 2 possibilidades(condições: 7 e 8) e verificamos se a temperatura do 3º dia é *maior* que a do 2º.
```c
else if(b==a && c>b)
		printf(":)\n");
	else
		printf(":(\n");
```
* Se sim, imprimimos o humor feliz: :)
* Se não, imprimimos o humor triste: :(

##### Para aprender um pouco mais sobre operadores lógicos: :[Operadores Lógicos](http://linguagemc.com.br/operadores-logicos-em-c/
)

Caso tenha alguma dúvida sobre este problema ou sobre a resolução, entre em contato com o PET-BCC pelo nosso
* [Facebook](https://www.facebook.com/petbcc/),
* [Instagram](https://www.instagram.com/petbcc.ufscar/)
* ou nos mande um e-mail com o assunto "URI" para  petbcc.ufscar@gmail.com


