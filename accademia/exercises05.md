---
layout: default
title: Exercícios 05
---

# Exercícios

> Não vamos alterar nosso projeto atual... Vamos apenas brincar com arrays :D 

* Crie uma classe `ArrayTest` e no método main crie um array de contas de tamanho 10. Em seguida, faça um laço para criar 10 contas com saldos distintos e colocá-las no array. Por exemplo, você pode utilizar o índice do laço e multiplicá-lo por 100 para gerar o saldo de cada conta:

* Ainda na classe `TestaArrays`, faça um outro laço para calcular e imprimir a média dos saldos de todas as contas do array.

(opcional) Crie uma classe `TestArraysSplit` que reescreva uma frase com as palavras na ordem invertida. "Socorram-me, subi no ônibus em Marrocos" deve retornar "Marrocos em ônibus no subi Socorram-me,". Utilize o método split da String para te auxiliar. Esse método divide uma String de acordo com o separador especificado e devolve as partes em um array de String, por exemplo:

```java
String phrase = "How you doing ?";
String[] palavras = phrase.split(" ");
```

* (opcional) Crie uma classe `Bank`. O Banco deve ter um nome e um número (obrigatoriamente) e uma referência a uma array de `Account` de tamanho 10, além de outros atributos que você julgar necessário.

* (opcional) A classe `Bank` deve ter um método adiciona, que recebe uma referência a Conta como argumento e guarda essa conta.

Você deve inserir a `Account` em uma posição da array que esteja livre. Existem várias maneiras para você fazer isso: guardar um contador para indicar qual a próxima posição vazia ou procurar por uma posição vazia toda vez. O que seria mais interessante?

Se quiser verificar qual a primeira posição vazia (nula) e adicionar nela, poderia ser feito algo como:

É importante reparar que o método adiciona não recebe titular, agencia, saldo, etc. Essa seria uma maneira nem um pouco estruturada, muito menos orientada a objetos de se trabalhar. Você antes cria uma `Account` e já passa a referência dela, que dentro do objeto possui `holder`, `amount`, etc.

* (opcional) Crie uma classe `BankTest` que possuirá um método main. Dentro dele crie algumas instâncias de `Account` e passe para o banco pelo método `addTo`.

Crie algumas contas e passe como argumento para o `addTo` do banco

Você pode criar essas contas dentro de um loop e dar a cada um deles valores diferentes de depósitos:

Repare que temos de instanciar `CheckingAccount` dentro do laço. Se a instanciação de `CheckingAccount` ficasse acima do laço, estaríamos adicionado cinco vezes a mesma instância de `CheckingAccount` neste `Bank` e apenas mudando seu depósito a cada iteração, que nesse caso não é o efeito desejado.

Opcional: o método `addTo` pode gerar uma mensagem de erro indicando quando o array já está cheio. Por isso é importante validar o tamanho do mesmo.

* (opcional) Percorra o atributo contas da sua instância de Banco e imprima os dados de todas as suas contas. Para fazer isso, você pode criar um método chamado mostraContas dentro da classe Banco:


## Brincando com as posições dos arrays... 

### Grid de corrida

1. Vamos adicionar um novo número na pole do grid de largada. Então dado um array, adicione o novo número ao início do mesm;

Exemplo de array:
``` 
  {323, 3, 4, 345, 12, 433, 9}
  1
```

Exemplo de saida:
```
  1, 323, 3, 4, 345, 12, 433, 9
```

2. Valide qual é o elemento único que existe dentro do array

Exemplo de array:
```
 {2, 3, 3, 4, 5, 5, 2}
```

Exemplo de saida:
```
  4
```

3. Insira um novo valor no meio do array existente.

Exemplo de array:
```
 1, 2, 3, 5, 6
```

Exemplo de saida:
```
 1, 2, 3, 4, 5, 6
```