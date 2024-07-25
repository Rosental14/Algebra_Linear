# Machine Learning e Álgebra Linear
Projeto para praticar o conhecimento adquirido sobre álgebra linear, envolvendo distâncias Euclidiana e de Manhattan,  algorítmos kNN e Regressão, além de ofuscação de dados 


**Descrição do Projeto**
A companhia de seguros Proteja Seu Amanhã deseja implementar soluções de aprendizado de máquina para melhorar suas operações e o atendimento ao cliente. Este projeto envolve a realização de quatro tarefas principais, que incluem encontrar clientes semelhantes, prever pagamentos de seguro, e proteger os dados pessoais dos clientes.

**Tarefa 1:** Encontrar Clientes Semelhantes
Objetivo: Identificar clientes semelhantes a um determinado cliente para auxiliar nas estratégias de marketing da empresa.  

**Resolução:** Para esta tarefa foi utilizado o algoritmo kNN, considerando 4 combinações entre distância Euclidiana e distância de Manhatan, com dados escalonados e não-escalonados, com objetivo de comparar os resultados obtidos em cada uma das combinações.  

**Conclusão:**  Quando os dados não são previamente escalados, as distâncias são muito maiores, impactando muito nos resultados. Isso se dá porque os dados não escalados podem ter características distintas em diferentes escalas, o que pode impactar a métrica de distância no KNN. No nosso caso específico, isso se dá principalmente pela característica 'income' (salário) que possui valores muito altos se comparados aos valores das demais características.  

**Tarefa 2:** Previsão de Pagamento de Seguro  

**Objetivo:** Prever se um novo cliente provavelmente receberá um pagamento de seguro.  

**Resolução:** Construiremos um classificador baseado em kNN e mediremos sua qualidade com a métrica F1 para k=1 até k=10 tanto para os dados originais quanto para os escalados. 
Construiremos um modelo dummy, que é aleatório para este caso.  Vamos testar o modelo com quatro valores de probabilidade: 0, a probabilidade de fazer qualquer pagamento de seguro, 0.5, 1.
Com os pagamentos de seguro sendo mais do que zero como objetivo, compararemos o resultado do modelo  kNN com os resultados do modelo dummy.  

**Conclusão:**  O modelo kNN, em geral, apresentou resultados muito melhores do que os obtidos com o modelo Dummy, pois com os dados escalados, nosso modelo kNN obteve um F1 de 0.95, o que é um resultado muito satisfatório, enquanto que o melhor resultado de F1 obtido com o modelo Dummy foi de apenas 0.20.

**Tarefa 3:** Previsão do Número de Pagamentos de Seguro  

**Objetivo:** Prever o número de pagamentos de seguro que um novo cliente provavelmente receberá. Com os pagamentos de seguro como objetivo, avaliaremos qual seria o REQM para um modelo de Regressão Linear com dados originais e escalados e compararemos os resultados.  

**Conclusão:** O REQM obtido foi o mesmo para os dados escalados e para os dados originais, o que nos demonstra que para um modelo de Regressão Linear, a transformação dos dados não afeta o resultado do REQM e R2, diferentemente do que foi observado com os modelos kNN, que tiveram resultados bem alterados após transformação dos dados.

**Tarefa 4:** Proteção de Dados Pessoais  

**Objetivo:** Desenvolver um algoritmo de mascaramento de dados para proteger as informações pessoais dos clientes sem prejudicar a qualidade dos modelos de aprendizado de máquina.  

**Resolução:** Realizar a transformação dos dados pessoais dos clientes utilizando multiplicação da matriz de características por uma matriz invertível e depois recuperar seus valores originais.
