# ✈️ Revenue Management em Companhias Aéreas: uma simulação econômica

## Sobre o projeto

Este projeto apresenta uma simulação de **Revenue Management (ou Yield Management)** aplicado ao setor aéreo.

O objetivo é responder uma pergunta aparentemente simples:

> Por que uma companhia aérea vende uma passagem por R$ 99 enquanto outras pessoas pagam R$ 500 ou R$ 2.000 pelo mesmo assento?

A resposta envolve uma combinação de:

* Microeconomia;
* Contabilidade de custos;
* Estatística;
* Pesquisa Operacional;
* Otimização de preços.

---

# 🎯 Problema econômico

Uma aeronave possui custos elevados independentemente da quantidade de passageiros.

A simulação considera:

* Aeronave: Airbus A320 / Boeing 737
* Capacidade: 180 passageiros
* Duração do voo: 2h30

Custos estimados:

| Item                                     |         Valor |
| ---------------------------------------- | ------------: |
| Operação, tripulação e manutenção        |     R$ 62.500 |
| Combustível, taxas e custos operacionais |     R$ 29.500 |
| **Custo total do voo**                   | **R$ 92.000** |

Além disso:

* Custo marginal por passageiro: R$ 50

---

# 📌 Hipótese inicial: preço único

Foi simulada uma situação em que todos os passageiros pagam o mesmo preço.

Resultados:

| Preço    | Passageiros |   Receita |  Resultado |
| -------- | ----------: | --------: | ---------: |
| R$ 99    |         180 | R$ 17.820 | -R$ 83.180 |
| R$ 200   |         180 | R$ 36.000 | -R$ 65.000 |
| R$ 500   |         115 | R$ 57.500 | -R$ 40.250 |
| R$ 2.000 |          35 | R$ 70.000 | -R$ 23.750 |

Conclusão:

**Nenhum preço único consegue maximizar o resultado.**

---

# 💡 Revenue Management

A solução é utilizar diferentes classes tarifárias.

A demanda foi dividida em três segmentos:

| Classe        |    Preço | Perfil                         |
| ------------- | -------: | ------------------------------ |
| Promocional   |   R$ 200 | Passageiros sensíveis ao preço |
| Intermediária |   R$ 500 | Viagens planejadas             |
| Última hora   | R$ 2.000 | Passageiros com alta urgência  |

A demanda de cada grupo foi modelada usando distribuição normal:

* Média esperada;
* Desvio-padrão;
* Incerteza da demanda.

---

# 📊 Modelo de otimização

Foi aplicado o algoritmo:

## EMSR-b (Expected Marginal Seat Revenue)

Baseado nos trabalhos de:

* Ken Littlewood (1972) — proteção de capacidade;
* Peter Belobaba (1987–1989) — expansão para múltiplas classes tarifárias.

O algoritmo calcula quantos assentos devem ser protegidos para passageiros de maior valor.

---

# Resultado da simulação

## Estratégia tradicional

Objetivo: maximizar ocupação.

Resultado:

* 180 passageiros;
* 100% de ocupação;
* Receita: R$ 48.000;
* Lucro: **-R$ 53.000**.

---

## Revenue Management

Resultado:

* 163 passageiros;
* 90,6% de ocupação;
* Receita: R$ 119.600;
* Lucro: **R$ 19.450**.

Mesmo com menos passageiros, a estratégia gerou maior resultado econômico.

---

# Monte Carlo

Para incorporar incerteza, foram realizadas:

**5.000 simulações de voos**

Resultados:

| Indicador                 | Resultado |
| ------------------------- | --------: |
| Lucro médio               | R$ 16.297 |
| Probabilidade de prejuízo |       20% |
| Percentil 95%             | R$ 43.458 |

---

# Principais conclusões

O estudo demonstra que:

* Um avião cheio não significa necessariamente lucro;
* Preço baixo para todos pode destruir margem;
* A empresa precisa equilibrar ocupação e valor por passageiro;
* A precificação ótima depende da disposição a pagar dos consumidores.

A pergunta correta não é:

> "Como vender todos os assentos?"

Mas sim:

> "Como maximizar o valor de cada assento disponível?"

---

# Tecnologias utilizadas

* Python
* Pandas
* NumPy
* SciPy
* Matplotlib
* Jupyter Notebook

---

# Autor

Projeto desenvolvido como estudo aplicado de:

Economia + Estatística + Contabilidade de Custos + Pesquisa Operacional.

Parâmetros utilizados são hipotéticos e possuem finalidade educacional.
