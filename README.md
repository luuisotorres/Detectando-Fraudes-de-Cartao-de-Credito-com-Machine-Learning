<center><img src="https://www.cardrates.com/wp-content/uploads/2020/08/shutterstock_576998230.jpg"></center><br>

# Utilizando Machine Learning para Detectar Fraudes de Cartão de Crédito
--<br><br>
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white) <br>
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) ![Plotly](https://img.shields.io/badge/Plotly-%233F4F75.svg?style=for-the-badge&logo=plotly&logoColor=white)<br>

--

# Introdução

Todos os dias, bilhões de transações de cartão de crédito são feitas ao redor do mundo. No Brasil, cada vez mais as pessoas realizam compras por aplicativos, lojas *online* e afins com seus cartões de crédito.<br><br>
Em um cenário como este, não é difícil imaginar que pessoas mal-intencionadas não busquem meios para fraudar cartões de crédito e realizar compras no nome - e com o dinheiro - de outras pessoas.<br><br>
Visando evitar que clientes sejam cobrados por compras que não fizeram, é de **muita importância** que bancos e empresas de cartões sejam capazes de reconhecer quando determinada transação for fruto de fraude.<br><br>
Este projeto tem o objetivo de atingir este problema, através do uso de algoritmos de **machine learning** para treinar um modelo preditivo que seja capaz de **aprender** e **detectar** quando uma transação for fraudulenta.

# Desenvolvimento

 Para desenvolver nosso modelo preditivo, utilizei **Scikit-Learn**, biblioteca open-source de **machine learning** para Python, e testei o funcionamento dos algoritmos de classificação **Random Forest** e **Decision Tree** para observar qual dos dois atingiria a melhor performance diante de nosso conjunto de dados, observando as métricas de avaliação de classificação, como o **recall**, **precision**, **f1 score**, **matriz de confusão**,etc...<br><br>
 
 Também utilizei pandas, numpy, matplotlib, seaborn e plotly para **explorar**, **manipular** e **visualizar** características relevantes do dataset.<br><br>
 
 O conjunto de dados utilizado foi o <a href= "https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud">Credit Card Fraud Detection</a> postado no Kaggle e que contém transações de cartões de crédito realizadas em Setembro de 2013 por clientes europeus durante dois dias.O dataset possui as variáveis **time**, que registra os segundos que se passaram entre cada transação e a **primeira transação** do dataset, enquanto **amount** registra o valor em Euros da transação e, por fim, a variável **class**, que registra se aquela transação é fraudulenta ou não, onde **1 = fraude** e **0 = genuína**.As variáveis V1,V2,V3...V28 sofreram transformações de <a href = "https://pt.wikipedia.org/wiki/An%C3%A1lise_de_componentes_principais">análise de componentes principais</a> e não tiveram seu conteúdo informado, devida a alta confidencialidade de suas informações.<br><br>
 
 Durante o desenvolvimento, utilizamos métodos do **Sklear**, como o **StandardScaler** para alterar a escala de valores de transação, evitando que a discrepância de valores nesta variável afetasse a performance de nosso modelo, e o **SMOTE** da bibliotecam **imblearn** para lidar com o **desbalanceamento** dos dados de transações genuínas e fraudulentas.<br><br>
 
 # Métricas de Performance
 
 Para auxiliar no entendimento de como os algoritmos **Random Forest** e **Decision Tree** performaram diante do dataset utilizado, deixei uma breve explicação no *notebook* de como funcionam as métricas de avaliação dos modelos de classificação.<br><br>
 Uma forma muito simples de visualizar a performance do modelo é a **matriz de confusão**, organizada da seguinte forma:<br><br>
<center><img src= "https://miro.medium.com/max/1400/1*j0TSVygS7ZPfK-lZkojNcQ.png"></center><br><br>
A <b>matriz de confusão</b> consegue nos mostrar as classificações corretas e incorretas de cada classe e nos indica se o modelo está favorecendo uma classe em detrimento da outra ou não.<br><br>
Além da matriz de confusão, temos as seguintes métricas de avaliação do modelo:<br><br>

##### Acurácia <br><br> 
Nos diz o quanto o modelo classificou corretamente, independente da classe dos exemplos. É definida pela seguinte fórmula:<br>
<center><img src = "https://miro.medium.com/max/1178/1*tNTpugu1beoC3f6ivswnsA.png"></center><br>
Onde: TP = Verdadeiro Positivo;<br>
TN = Verdadeiro Negativo;<br>
FP = Falso Positivo e<br>
FN = Falso Negativo. <br><br> 

##### Precisão <br><br> 
É a razão entre o número de exemplos positivos classificados corretamente e o total de exemplos classificados como positivos, incluindo os falsos positivos, e busca responder qual a proporção de classificações positivas foi realmente correta. É definida pela seguinte fórmula:<br>
<center><img src = "https://miro.medium.com/max/476/1*pJrHo_sp-pnLFl6Ww3imUw.png"></center><br><br>

##### Recall <br><br> 
Pode ser definida como a taxa de verdadeiro positivo e busca responder o quão bem o modelo prevê a classe de positivos. É definida pela seguinte fórmula:<br>
<center><img src = "https://miro.medium.com/max/396/1*zgmkLfNNRtFwCHp8m46AKA.png"></center><br><br>

##### F1 Score <br><br> 
O F1 Score é o balanço entre a **precisão** e o **recall** e é definida pela seguinte fórmula:<br>
<center><img src = "https://miro.medium.com/max/520/1*sBVtY3BJoJbOs47ZZx46tA.png"></center><br><br>

# Conclusão
Após utilizarmos o SMOTE para aplicarmos o **oversampling** dos dados, percebemos, através da **matriz de confusão**, que o algoritmo já **não** favorece mais transações genuínas em detrimento das transações fraudulentas, obtendo, como resultado:<br><br>
- 85.132 verdadeiros positivos.<br>
- 17 falsos positivos.<br>
- 1 falso negativo.<br>
- 85.439 verdadeiros negativos.<br><br>

Obtivemos:
- Uma acurácia de 99.98%;<br> 
- Precisão de 99.98%;<br>
- Recall de 99.99%;<br>
- E um F1 Score de 99.98%.<br><br>

Todas as métricas alcançaram resultados excelentes, o que indica que nosso modelo **aprendeu** e se tornou **capaz de identificar transações fraudulentas** de cartão de crédito com altas taxas de acerto.

-----

# Referências
<a href="https://medium.com/data-hackers/entendendo-o-que-%C3%A9-matriz-de-confus%C3%A3o-com-python-114e683ec509">Entendendo o que é Matriz de Confusão com Python</a><br><br>
<a href="https://medium.com/kunumi/m%C3%A9tricas-de-avalia%C3%A7%C3%A3o-em-machine-learning-classifica%C3%A7%C3%A3o-49340dcdb198">Métricas de Avaliação em Machine Learning: Classificação</a><br>

# Author
**Luís Fernando Torres**
