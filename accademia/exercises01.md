---
layout: default
title: Exercícios 01
---

# Exercícios

> Vamos criar um novo projeto utilizando nossa IDE e o Gradle - *você pode olhar este [tutorial](https://www.jetbrains.com/help/idea/getting-started-with-gradle.html#test_gradle) caso ache necessário)*

## 1 - Criar uma classe Account

A classe `Account`, ou o nome que você desejar, deve conter pelo menos os seguintes métodos:

* `deposit` que recebe um valor como parâmetro e retira esse valor do saldo da conta
* `withdraw` que recebe um valor como parâmetro e adiciona esse valor ao saldo da conta
* `accountIncome` que não recebe parâmetro e devolve o valor do saldo multiplicado por `0.7`

Lembre-se também de criar uma classe de "Teste", onde será possível implementar a nossa classe `Account` e testar os imputs e outputs de nosso exercício.

> fique a vontade para usar a imaginação e pensar em quais operações bancárias podemos adicionar em nossa classe - lembrando que estamos passando por um momento de revolução nos métodos tradicionais que conhecemos 🤓

### Para treinar ainda mais 

O objetivo destes exercícios é fixar ainda mais o conhecimento, então dedique um tempinho para eles também :D

#### Classe `Student`

Crie uma `Student`, coloque seu nome e idade iniciais, faça alguns aniversários (aumentando a idade) e imprima seu nome e sua idade.

```
Classe: Student
Atributos: name, age
Método: void happyBirthday()       
```

#### Classe `Door`

Crie uma `Door`, abra e feche a mesma, pinte-a de várias cores, altere suas dimensões e use o método `isOpen` para verificar se ela está aberta.

```
Classe: Door
Atributos: open, color, dimensionX, dimensionY,dimensionZ
Método: void open(),       
        void close(),
        void colorIt(String color),
        boolean isOpen()

```

#### Classe `House`

Crie uma casa e pinte-a. Crie três portas e coloque-as na casa; abra e feche as mesmas como desejar. 
Utilize o método `howManyDoorsAreOpen` para imprimir o número de portas abertas.

```
Classe: House
Atributos: color, firstDoor, secondDoor, thirdDoor
Método: void colorIt(String color), 
        int howManyDoorsAreOpen()
```

