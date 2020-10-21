---
layout: default
title: Exercícios 01
---

# Exercícios

## Praticando listas...

1. Escreva um programa Java para criar uma nova lista de array, adicione algumas cores (string) e imprima a coleção.

2. Escreva um programa Java para iterar por meio de todos os elementos em uma lista de arrays.

3. Escreva um programa Java para inserir um elemento na lista de vetores na primeira posição.

4. Escreva um programa Java para recuperar um elemento (em um índice especificado) de uma determinada lista de matrizes.

5. Escreva um programa Java para atualizar um elemento específico da matriz por determinado elemento.

6. Escreva um programa Java para remover o terceiro elemento de uma lista de arrays.

7. Escreva um programa Java para pesquisar um elemento em uma lista de arrays.

8. Escreva um programa Java para classificar uma determinada lista de matrizes.

9. Escreva um programa Java para copiar uma lista de arrays para outra.

10. Escreva um programa Java para embaralhar elementos em uma lista de array.

11. Escreva um programa Java para reverter elementos em uma lista de vetores.

12. Escreva um programa Java para extrair uma parte de uma lista de arrays.

13. Escreva um programa Java para comparar duas listas de array.

14. Escreva um programa Java de troca de dois elementos em uma lista de array.

15. Escreva um programa Java para juntar duas listas de array.

16. Escreva um programa Java para clonar uma lista de arrays em outra lista de arrays.

17. Escreva um programa Java para esvaziar uma lista de arrays.

18. Escreva um programa Java para testar se uma lista de arrays está vazia ou não.

19. Escreva um programa Java para substituir o segundo elemento de uma ArrayList pelo elemento especificado.

20. Escreva um programa Java para imprimir todos os elementos de uma ArrayList usando a posição dos elementos.

## Exercícios: Ordenação



Vamos ordenar o campo de destino da tela de detalhes da conta para que as contas apareçam em ordem alfabética de titular.

Faça sua classe `Account` implementar a interface Comparable<Account>. Utilize o critério de ordenar pelo titular da conta.

Vamos então criar o método `sort` na classe `SortingAccount`. Use o Collections.sort().

Rode a aplicação, adicione algumas contas e verifique se as contas aparecem ordenadas pelo nome do titular.

Dica: repare que escrevemos um método compareTo em nossa classe e nosso código nunca o invoca!! Isto é muito comum. Reescrevemos (ou implementamos) um método e quem o invocará será um outro conjunto de classes (nesse caso, quem está chamando o compareTo é o Collections.sort, que o usa como base para o algoritmo de ordenação). Isso cria um sistema extremamente coeso e, ao mesmo tempo, com baixo acoplamento: a classe Collections nunca imaginou que ordenaria objetos do tipo Account, mas já que eles são Comparable, o seu método sort está satisfeito.

O que teria acontecido se a classe `Account` não implementasse Comparable<Account> mas tivesse o método compareTo?

Faça um teste: remova temporariamente a sentença implements Comparable<Account>, não remova o método compareTo e veja o que acontece. Basta ter o método, sem assinar a interface?

Como posso inverter a ordem de uma lista? Como posso embaralhar todos os elementos de uma lista? Como posso rotacionar os elementos de uma lista?

Investigue a documentação da classe Collections dentro do pacote java.util.

(opcional) Crie uma nova classe `ListTest` que cria uma ArrayList e insere novas contas com saldos aleatórios usando um laço (for). Adivinhe o nome da classe para colocar saldos aleatórios? Random. Do pacote java.util. Consulte sua documentação para usá-la (utilize o método nextInt() passando o número máximo a ser sorteado).

*Bonus:* Dada uma lista de inteiros,  devolva o segundo maior número desta lista... 