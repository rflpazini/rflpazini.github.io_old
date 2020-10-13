---
layout: default
title: Exercícios
---

# Exercícios

A melhor forma de aprender é praticando, então quanto mais prática, melhor é o resultado 

## 1 - Bem-vindo ao Java

Bem-vindo ao mundo Java! Neste desafio, praticaremos a impressão em `stdout`.

Os stubs de código abaixo declaram uma classe de solução e um método principal. Nosso objetivo é concluir ela, imprimindo algum texto de exemplo.

```java
public class Solution {

    public static void main(String[] args) {
        //TODO: Completar a classe para que seja impresso algum valor
    }
}
```



#### Formato de imput

Não existe um formato de imput para este exercício

#### Formato de output

Você deve imprimir pelo menos duas linhas 

1. Imprima `Hello, World` na primeira linha.
2. Imprima `E ai Java, meu nome é {SEU_NOME}` na segunda linha.

#### Exemplo de output

```shell
$ Hello, World
$ E ai Java, meu nome é Rafael :D 
```



## 2 - Entradas e Saídas

No mundo java, quando estamos trabalhando com terminal sempre quase sempre recebemos uma [entrada/stdin](https://en.wikipedia.org/wiki/Standard_streams#Standard_input_.28stdin.29) e uma [saída/stdout](https://en.wikipedia.org/wiki/Standard_streams#Standard_output_.28stdout.29) e agora vamos aprender a brincar com esses valores.

Para lermos estes valores de entrada, vamos utilizar a classe [Scanner](https://docs.oracle.com/javase/8/docs/api/java/util/Scanner.html) que le os valores de um objeto inserido em nosso terminal. No exemplo a seguir mostro como ler uma `String` 

```java
Scanner scanner = new Scanner(System.in);
String insertedString = scanner.nextLine();
scanner.close();

System.out.println("insertedString is: " + insertedString);
```

O código acima cria um objeto `Scanner`  e o usa para ler uma `String`. Em seguida, fecha o objeto Scanner porque não há mais entrada para ler e imprime em stdout usando `System.out.println (String)`. Portanto, se nossa entrada for:

```shell
Accademia começa hoje 13
```

Esse código vai imprimir a seguinte saída:

```shell
insertedString is: Accademia começa hoje 13
```


Caso eu queira ler apenas um número, no caso um `int` , utilizariamos o comando `scanner.nextInt();` ao invéz de `scanner.nextLine();` que le o conteúdo da linha toda.



####Desafio

Você deve criar uma classe que seja capaz de ler od números inteiros de stdin e depois imprimi-los em stdout. Cada número inteiro deve ser impresso em uma nova linha.

#### Formato de imput

Deverão existir 3 linhas de entrada e cada uma com um número inteiro

#### Exemplo de imput	

```
3
4
18
```

Exemplo de output

```
3
4
18
```

