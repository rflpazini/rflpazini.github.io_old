---
layout: default
title: Exercícios 04
---

# Exercícios

> Continuando nosso banco - pt 3...🏦 🏧 💸 

## 1 - Que tal sermos menos concretos e mais abstratos?

* Nosso banco precisa tributar dinheiro de alguns bens que nossos clientes possuem. Para isso vamos criar uma interface `Taxable` no pacote entity do nosso projeto.

* Crie um método `getTaxes`, que retorne um double.

Lemos essa interface da seguinte maneira: "todos que quiserem ser tributável precisam saber retornar o valor do imposto, devolvendo um double".

Alguns bens são tributáveis e outros não, `SavingsAccount` não é tributável, já para `CheckingAccount` você precisa pagar 1% de manutenção de conta e vamos supor que tivessemos um seguro `LifeInsurence` tem uma taxa fixa de 42 reais mais 2% do valor do seguro.

> Aproveite a IDE! Quando você escrever o código implements em uma classe ela sugere para implementar os novos métodos da interface.

* Crie a classe `LifeInsurence`, com os atributos `value`, `owner`, `insurenceNumber`. Com seus respectivos getters and setters. E implemente a lógica de cobrança do valor do imposto que comentei na linha acima. 

* Além disso, escreva o método `getType` retornando do que se trata nosso novo seguro.

* Em nossa classe de testes e tente cadastrar um novo seguro de vida.

* Faça com que seja possível saber que uma conta corrente pode ter um seguro de vida vinculado a ela.

* Calcule todos os tributos que serão retirados de uma conta, por exemplo, o valor de administração da conta `CheckingAccount` e o valor total do `LifeInsurence`.

É interessante enxergar que as interfaces (como aqui, no caso, Taxable) costumam ligar classes muito distintas, unindo-as por uma característica que elas tem em comum. No nosso exemplo, `LifeInsurence` e `CheckingAccount` são entidades completamente distintas, porém ambas possuem a característica de serem tributáveis.

Se amanhã o governo começar a tributar até mesmo `InvestimentAccount`, basta que essa classe implemente a interface `Taxable`! Repare no grau de desacoplamento que temos: a classe GerenciadorDeImpostoDeRenda nem imagina que vai trabalhar como `InvestimentAccount`. Para ela, o único fato que importa é que o objeto respeite o contrato de um tributável, isso é, a interface `Taxable`. Novamente: programe voltado à interface, não à implementação.

Quais os benefícios de manter o código com baixo acoplamento ???

* Crie a classe TaxableTest com um método main para testar o nosso exemplo:

```java
public class TaxableTest {

   //...
        CheckingAccount checkingAccount = new CheckingAccount();
        checkingAccount.deposit(100);
        System.out.println(checkingAccount.getTaxes());

        // testando polimorfismo:
        Taxable tax = checkingAccount;
        System.out.println(tax.getTaxes());
    }
}
```

Tente chamar o método `getAmount` através da referência tax, o que ocorre? Por quê?

## Exercicio opcional 

> Pra treinar em casa e em OUTRO PROJETO pleaseee ...

* Transforme a classe `Account` em uma interface.

* Adapte `CheckingAccount` e `SavingsAccount` para essa modificação:

Algum código vai ter de ser copiado e colado? Isso é tão ruim?

Às vezes, é interessante criarmos uma interface que herda de outras interfaces: essas, são chamadas subinterfaces. Essas, nada mais são do que um agrupamento de obrigações para a classe que a implementar.

```java
public interface TaxableAccount extends Account, Taxable {
  // methods...
}
```

Dessa maneira, quem for implementar essa nova interface precisa implementar todos os métodos herdados das suas superinterfaces (e talvez ainda novos métodos declarados dentro dela):

```java
public class CheckingAccount implements TaxableAccount {
  // métodos
}
```


```java
Account account = new CheckingAccount();
Taxable taxable = new CheckingAccount();
```

Repare que o código pode parecer estranho, pois a interface não declara método algum, só herda os métodos abstratos declarados nas outras interfaces.

Ao mesmo tempo que uma interface pode herdar de mais de uma outra interface, classes só podem possuir uma classe mãe (herança simples).