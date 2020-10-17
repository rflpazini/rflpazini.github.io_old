---
layout: default
title: Exercícios 03
---

# Exercícios

> Continuando nosso banco - pt 2...🏦 🏧 💸 

## 1 - Que tal sermos menos concretos e mais abstratos?

> "Todo mundo é um conceito abstrato,uma generalização. Ninguém pode saber o que é melhor para cada um[...]", Crônica: Do seu jeito - Coisas da vida

Repare que a nossa classe Conta é uma excelente candidata para uma classe abstrata. Por quê? Que métodos seriam interessantes candidatos a serem abstratos?

* Transforme a classe Conta em abstrata e veja o que acontece quando fazemos isso...

### Se questione

1. Existe outra maneira de a classe `SavingsAccount` compilar se você não reescrever o método abstrato?

2. Pra que ter o método `getType` na classe Conta se ele não faz nada? O que acontece se simplesmente apagarmos esse método da classe Conta e deixarmos o método `getType` nas filhas?

3. Posso chamar um método abstrato de dentro de um outro método da própria classe abstrata? Por exemplo, imagine que exista o seguinte método na classe `Account`

```java
public String printAllAccountInfo() {
  String info = "Name: " + this.name;
  info += "\nAccount number: " + this.number;
  info += "\nAmount: R$" + this.amount;

  return info;
}
```

Podemos invocar o `getType` dentro deste método? Algo como:
```java
info += "\nAccount Type " + this.getType();
```

