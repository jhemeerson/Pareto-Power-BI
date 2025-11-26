# Pareto-Power-BI
Visualização de Pareto Frete por Estado

# O que é gráfico de Pareto?

Um gráfico de Pareto é uma ferramenta de análise que utiliza um gráfico de barras para exibir as causas de um problema, ordenadas da mais frequente para a menos frequente, com uma linha que mostra o total acumulado. 
Ele ajuda a focar nos problemas mais significativos, aplicando a regra **80/20**, onde se assume que cerca de **80% dos resultados vêm de 20% das causas**, permitindo que os gestores priorizem ações.

<br>

*No exemplo vamos exploar dados de frete de uma empresa para explorar quais estados represetam a maior porcentagem em relação ao todo.*

<br>

<div align="center">
<img src="https://github.com/user-attachments/assets/bea00cc7-4569-42d5-8534-e59a7ec0f86e" />
</div>

<br>

* **20%** dos estados correespondem a **80%** dos valores de frete. 
* **84,02%** dos fretes estão concentrados em 3 estados: **SP, MG e PR**.
* Apenas o estado de **SP** corresponde a **65,83%** do total acumulado.

<br>

---

<br>

### 1º Criando Ranking dos Estados com maior valor de frete.

<br>

<div align="center">
<img src="https://github.com/user-attachments/assets/6b90004a-a3ca-4abc-bb5b-d5c63a6c4c60" />
</div>

<br>

* Função **RANKX:** Cria um ranking em ordem crescente
* Função **ALLSELECTED:** Garante que a função RANKX considere todos os estados ao criar o ranking
com base na somatória de frete.

<br>

#### 2º Criando Valores Acumulados de Frete.

<br>

<div align="center">
<img src="https://github.com/user-attachments/assets/1c1eae96-412d-42a2-99da-2a8d10b4abbd" />
</div>

<br>

* Para que obtenhamos os valores acumulados, precisamos aninhar função **TOPN** como argumento de filtro da
Função **CALCULATE**.
* Função **TOPN:** retorna os N valores desejados de uma tabela especificada e acumula valores.
* Função **ALLSELECTED:** Garante que a função **TOPN** considere o ranking dos estados ao criar o acumulado na somatória de frete.

<br>

#### 3º Criando Percentual (%) Acumulado de Frete.

<br>

<div align="center">
<img src="https://github.com/user-attachments/assets/27f911ce-6c60-4828-8773-a6ccdbbf7051" />
</div>

<br>

* Função **ALLSELECTED:** Garante que a função **DIVIDE** considere o valor total do frete por estados ao criar o percentual acumulado.

<br>

---

<br>

### Validação das fórmulas DAX utilizando visual de tabela:

<br>

<div align="center">
<img src="https://github.com/user-attachments/assets/934ce3d9-be3d-4afb-89c6-cc06d2f5d420"/>
</div>

<br>

* **20%** dos estados correespondem a **80%** dos valores de frete. 
* **84,02%** dos fretes estão concentrados em 3 estados: **SP, MG e PR**.
* Apenas o estado de **SP** corresponde a **65,83%** do total acumulado.


