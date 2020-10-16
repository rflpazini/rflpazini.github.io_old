---
layout: default
title: Exercícios 02
---

# Exercícios

> Continuando nosso banco...🏦 🏧 💸 

## 1 - Criar uma classe Account

Reorganize o código para que ele seja colocado em pacotes
Crie a classe `CheckingAccount` no pacote `entity` e  faça com que ela seja filha da classe `Account`
Crie a classe `SavingsAccount` no pacote `entity` e faça com que ela seja filha da classe `Account`

Apesar de já conseguirmos criar os dois tipos de contas, nao conseguimos saber com qual tipo de conta estamos trabalhando. Para resolver isso, podemos criar um método `getType` em cada uma de nossas contas fazendo com que a conta corrente devolva a string "Checking Account" e a conta poupança devolva a string "Savings Account":

Mude o comportamento da operação de `withdraw` de acordo com o tipo de conta que estiver sendo utilizada. Para que possamos passar um "bonus" junto com o saqueda conta corrente, por exemplo, se a pessoa efetuar o saque da conta corrente, damos R$ 0.10 a mais para ela.

Ao tentarmos chamar o método `getType`, o compilador reclama que esse método não existe na classe `Account` apesar de existir nas classes filhas. Como estamos tratando todas as contas genericamente, só conseguimos acessar os métodos da classe mãe. Coloque o método na classe `Account` também retornando o valor dela...

E se tentarmos realizar uma transferência da conta corrente para a conta poupança? O que acontece? Implemente um método `tranfer` na classe `Account`, que receberá um `tranfersAmount` e o objeto `Account`...

### Bonus
Considere o código abaixo:

```java 
    Account account = new Account();
    CheckingAccount checkingAccount = new CheckingAccount();
    SavingsAccount savingsAccount = new SavingsAccount();
```

Se mudarmos esse código para:
```java
    Account account = new Account();
    Account checkingAccount = new CheckingAccount();
    Account savingsAccount = new SavingsAccount();
```

Compila? Roda? O que muda? Qual é a utilidade disso? Realmente, essa não é a maneira mais útil do polimorfismo.

É extremamente importante perceber que não importa como nos referimos a um objeto, o método que será invocado é sempre o mesmo! A JVM vai descobrir em tempo de execução qual deve ser invocado, dependendo de que tipo é aquele objeto, não importando como nos referimos a ele.

Podemos criar também uma `InvestimentsAccount` conseguindo obter rendimentos maiores e brincarmos com isso 
