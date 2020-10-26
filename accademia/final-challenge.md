---
layout: default
title: Final challenge
---

# Final challenge - Autorizador 

Você está encarregado de implementar um aplicativo que autoriza uma transação para uma conta específica utilizando o cartão de crédito após um conjunto de regras predefinidas.

Leia as instruções abaixo e fique à vontade para pedir esclarecimentos, se necessário.

### Descrição do projeto

Seu arquivo README deve conter uma descrição do seu projeto, junto com instruções sobre como construir
e executar seu aplicativo.

### Exemplo de uso

Seu programa receberá um objeto json como entrada no endpoint e deve fornecer uma saída de json para cada um.

#### Endpoint com todas as autorizações:
```json
{"account": {"active-card": true, "available-limit": 100}}
{"transaction": {"merchant": "Burger King", "amount": 20, "time": "2019-02- 13T10:00:00.000Z"}}
{"transaction": {"merchant": "Mercado Livre", "amount": 90, "time": "2019-02- 13T11:00:00.000Z"}}
```

#### Operações filtradas por uma conta específica:
```json
{"account": {"active-card": true, "available-limit": 100}, "violations": []} 
{"account": {"active-card": true, "available-limit": 80}, "violations": []} 
{"account": {"active-card": true, "available-limit": 80}, "violations": ["insufficient-limit"]}
```

### Estado da aplicação

Para implementar esse projeto, espero que vocês criem uma API utilizando Spring.

Vocês poderão utilizar o bando de dados de sua preferencia, assim como também podem utilizar alternativas para armazenar nossos dados apenas em memória, como H2 ou até utilizar um HashTable para fazer a vez do banco... It's up to you guys 

### Operações

O programa lida com dois tipos de operações, decidindo qual delas de acordo com a linha que está sendo processada:

1. Criação de conta
2. Autorização de transação

Para simplificar, você pode assumir que todos os valores monetários são inteiros positivos usando uma moeda sem centavos.



### 1. Criação de uma conta

**Entrada**

Cria a conta com limite disponível e conjunto de cartão ativo. Para simplificar, vamos assumir
o aplicativo lidará com apenas uma conta.

**Resultado**

O estado atual da conta criada + quaisquer violações da lógica de negócios. 

**Regras do negócio**

Depois de criada, a conta não deve ser atualizada ou recriada: `account-already- initialized`.



Exemplos


_input_
```json
{"account": {"active-card": true, "available-limit": 100}}
{"account": {"active-card": true, "available-limit": 350}}
```

_output_
```json
{"account": {"active-card": true, "available-limit": 100}, "violations":[]}
{"account": {"active-card": true, "available-limit": 100}, "violations": ["account-already-initialized" ]}
```


### 2. Autorização de transação

**Entrada**

Tenta autorizar uma transação para um determinado comerciante, quantidade e hora de acordo com o estado da conta e a última transações autorizadas.

**Resultado**

O estado atual da conta + quaisquer violações da lógica de negócios.

**Regras do negócio**

Você deve implementar as seguintes regras, tendo em mente que novas regras aparecerão no futuro:

* Nenhuma transação deve ser aceita sem uma conta devidamente inicializada: `account-not- initialized`
* Nenhuma transação deve ser aceita quando o cartão não está ativo: `card-not-active`
* O valor da transação não deve exceder o limite disponível: `insufficient-limit`
* Não deve haver mais de 3 transações em um intervalo de 2 minutos: `high-frequency- small-interval`  (a ordem de entrada não pode ser invocada, uma vez que as transações podem eventualmente estar fora de ordem, respectivamente em seus horários)
* Não deve haver mais de 1 transação semelhante (mesmo valor e comerciante) em um intervalo de 2 minutos:
  `doubled-transaction`


Exemplo

Dado que existe uma conta com  ` active-card: true` e `available-limit: 100`:

_input_
```json
{"transaction": {"merchant": "Burger King", "amount": 20, "time": "2019-02-13T10:00:00.000Z"}}
```
_output_
```json
{"account": {"active-card": true, "available-limit": 80}, "violations": []}
```

Dado que existe uma conta com `active-card: true` e `available-limit: 80`:


_input_
```json
{"transaction": {"merchant": "Mercado Livre", "amount": 90, "time": "2019-02-13T11:00:00.000Z"}}
```
_output_
```json
{"account": {"active-card": true, "available-limit": 80}, "violations":["insufficient-limit"]}
```

### Expectativas

Neste exercício vou analisar os seguintes pontos:

* Clareza de código: quero ver como vocês organizam o código, dão nomes para atributos e classe e afins. **Ps: English is a important skill at coding jobs** 🤗
* Orientação a Objeto implementada no projeto
* Implementação dos verbos e status HTTP
* Versionamento de código utilizando git e GitHub. Vou analizar a árvore de desenvolvimento e ver se todos do grupo participaram da codificação

