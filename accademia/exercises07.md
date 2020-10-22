---
layout: default
title: Exercícios 07
---

# Exercícios

## Praticando Sets...

1. Escreva um programa Java para anexar o elemento especificado ao final de um conjunto hash.

2. Escreva um programa Java para iterar por meio de todos os elementos em uma lista de hash.

3. Escreva um programa Java para obter o número de elementos em um conjunto hash.

4. Escreva um programa Java para esvaziar um conjunto hash.

5. Escreva um programa Java para testar se um conjunto de hash está vazio ou não.

6. Escreva um programa Java para clonar um conjunto de hash para outro conjunto de hash.

7. Escreva um programa Java para converter um conjunto hash em um array.

8. Escreva um programa Java para converter um conjunto hash em um conjunto de árvore.

9. Escreva um programa Java para converter um conjunto de hash em uma Lista / ArrayList.

10. Escreva um programa Java para comparar dois conjuntos de hash.

11. Escreva um programa Java para comparar dois conjuntos e reter elementos que são iguais em ambos os conjuntos.

12. Escreva um programa Java para remover todos os elementos de um conjunto hash.

## Praticando Maps ... 🗺

1. Escreva um programa Java para associar o valor especificado à chave especificada em um HashMap.

2. Escreva um programa Java para contar o número de mapeamentos de valor-chave (tamanho) em um mapa.

3. Escreva um programa Java para copiar todos os mapeamentos do mapa especificado para outro mapa.

4. Escreva um programa Java para remover todos os mapeamentos de um mapa.

5. Escreva um programa Java para verificar se um mapa contém mapeamentos de valores-chave (vazio) ou não.

6. Escreva um programa Java para obter uma cópia superficial de uma instância de HashMap.

7. Escreva um programa Java para testar se um mapa contém um mapeamento para a chave especificada.

8. Escreva um programa Java para testar se um mapa contém um mapeamento para o valor especificado.

9. Escreva um programa Java para criar uma visualização definida dos mapeamentos contidos em um mapa.

10. Escreva um programa Java para obter o valor de uma chave especificada em um mapa.

11. Escreva um programa Java para obter uma visão definida das chaves contidas neste mapa.

12. Escreva um programa Java para obter uma visualização de coleção dos valores contidos neste mapa.

## Testanto performance 🏎💨

Crie um código que insira 30 mil números numa ArrayList e pesquise-os. Vamos usar um método de System para cronometrar o tempo gasto...

```java
    System.out.println("Starting now...");
    long start = System.currentTimeMillis();

    //...restante do código

    long end = System.currentTimeMillis();

    System.out.println("Time spent: " + (end - start));
```
Troque a ArrayList por um HashSet e verifique o tempo que vai demorar

O que é lento? A inserção de 30 mil elementos ou as 30 mil buscas? Descubra computando o tempo gasto em cada for separadamente.

A diferença é mais que gritante. Se você passar de 30 mil para um número maior, como 50 ou 100 mil, verá que isso inviabiliza por completo o uso de uma List, no caso em que queremos utilizá-la essencialmente em pesquisas.

>Repare que, se você declarar a coleção e der new assim:

```java
    Collection<Integer> test = new ArrayList<>();
```
em vez de:

```java
    ArrayList<Integer> test = new ArrayList<>();
```    

É garantido que vai ter de alterar só essa linha para substituir a implementação por HashSet. Estamos aqui usando o polimorfismo para nos proteger que mudanças de implementação venham nos obrigar a alterar muito código. Mais uma vez: programe voltado a interface, e não à implementação!

Esse é um excelente exemplo de bom uso de interfaces, afinal, de que importa como a coleção funciona? O que queremos é uma coleção qualquer, isso é suficiente para os nossos propósitos! Nosso código está com baixo acoplamento em relação a estrutura de dados utilizada: podemos trocá-la facilmente.

Esse é um código extremamente elegante e flexível. Com o tempo você vai reparar que as pessoas tentam programar sempre se referindo a essas interfaces menos específicas, na medida do possível: métodos costumam receber e devolver Collections, Lists e Sets em vez de referenciar diretamente uma implementação. É o mesmo que ocorre com o uso de InputStream e OutputStream: eles são o suficiente, não há porque forçar o uso de algo mais específico.

Obviamente, algumas vezes não conseguimos trabalhar dessa forma e precisamos usar uma interface mais específica ou mesmo nos referir ao objeto pela sua implementação para poder chamar alguns métodos. Por exemplo, TreeSet tem mais métodos que os definidos em Set, assim como LinkedList em relação à List.

Dê um exemplo de um caso em que não poderíamos nos referir a uma coleção de elementos como Collection, mas necessariamente por interfaces mais específicas como List ou Set.

Depois, altere o código para usar o generics e não haver a necessidade do casting, além da garantia de que nosso mapa estará seguro em relação a tipagem usada...

(opcional) Assim como no exercício 1, crie uma comparação entre ArrayList e LinkedList, para ver qual é a mais rápida para se adicionar elementos na primeira posição `(list.add(0, object))`.

Seguindo o mesmo raciocínio, você pode ver qual é a mais rápida para se percorrer usando o get(indice) (sabemos que o correto seria utilizar o enhanced for ou o Iterator). Para isso, insira 30 mil elementos e depois percorra-os usando cada implementação de List.

Perceba que aqui o nosso intuito não é que você aprenda qual é o mais rápido, o importante é perceber que podemos tirar proveito do polimorfismo para nos comprometer apenas com a interface. Depois, quando necessário, podemos trocar e escolher uma implementação mais adequada as nossas necessidades.

Qual das duas listas foi mais rápida para adicionar elementos à primeira posição?

### Desafios
Gere todos os números entre 1 e 1000 e ordene em ordem decrescente utilizando um TreeSet. Como ficou seu código?

Gere todos os números entre 1 e 1000 e ordene em ordem decrescente utilizando um ArrayList. Como ficou seu código?