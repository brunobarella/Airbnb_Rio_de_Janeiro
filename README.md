# Airbnb Rio de Janeiro
## _Prevendo o preço das acomodações_

O dataset é uma extração de dados do Airbnb Rio de Janeiro para a data de 22/02/2021, conforme fonte:
http://insideairbnb.com/get-the-data.html.

## Perguntas sobre a modelagem do problema de **previsão do preço** da estadia (feature ‘price’):

- a. Como foi a definição da sua estratégia de modelagem?
- b. Como foi definida a função de custo utilizada? 
- c. Qual foi o critério utilizado na seleção do modelo final?
- d. Qual foi o critério utilizado para validação do modelo? Por que escolheu utilizar este método?
- e. Quais evidências você possui de que seu modelo é suficientemente bom?

a. A estratégia de modelagem foi dividida em 4 etapas: 
- [Avaliação e interpretação das variáveis com o pacote Pandas Profiling e instalando as dependências necessárias;](https://github.com/brunobarella/Airbnb_Rio_de_Janeiro/blob/main/scripts/overview.ipynb)
- [Preprocessamento (remoção de variáveis, extração de padrões, correções etc.);](https://github.com/brunobarella/Airbnb_Rio_de_Janeiro/blob/main/scripts/exploring.ipynb)
- [Criação de variáveis (baseadas nas distâncias entre comodidades, variáveis categóricas);](https://github.com/brunobarella/Airbnb_Rio_de_Janeiro/blob/main/scripts/more_feature.ipynb)
- [Criação e desenvolvimento do modelo preditor.](https://github.com/brunobarella/Airbnb_Rio_de_Janeiro/blob/main/scripts/modeling.ipynb)

b. O problema foi solucionado sob a perspectiva de aprendizado de máquina, dessa forma não possui uma função de custo.

c. O modelo utilizado foi selecionado comparando a performance entre diversos modelos de aprendizado de máquina avaliando o desempenho de todos os estimadores disponíveis na biblioteca (Pycaret) usando validação cruzada. Após isso, foi avaliado o resultado do modelo sobre um conjunto de dados não vistos pelo modelo, a fim de constatar a alta capacidade em estimar o preço das acomodações do Airbnb para a cidade do Rio de Janeiro até a data de 22/02/2021.

d. O critério utilizado para validação do modelo foi avaliar as métricas de performance do modelo (MAE, MSE, RMSE, R², RMSLE, MAPE) sobre uma porção de 15% do total de amostras disponíveis, das quais não foram utilizadas no treinamento. A escolha dessa abordagem se dá, pela exposição do modelo a dados não vistos, simulando a predição sobre dados novos, garantindo a capacidade de generalização.

e. Além das análises sobre as métricas de performance é possível analisar qualitativamente a solução pelos gráficos de erros e de predições sobre a porção de dados não vistos pelo modelo neste [notebook](https://github.com/brunobarella/Airbnb_Rio_de_Janeiro/blob/main/scripts/modeling.ipynb).
