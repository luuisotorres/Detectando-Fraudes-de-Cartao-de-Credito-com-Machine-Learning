<center><img src="https://www.cardrates.com/wp-content/uploads/2020/08/shutterstock_576998230.jpg"></center><br>

# Utilizando Machine Learning para Detectar Fraudes de Cartão de Crédito
--<br><br>
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white) <br>
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white) ![Plotly](https://img.shields.io/badge/Plotly-%233F4F75.svg?style=for-the-badge&logo=plotly&logoColor=white)<br>

--

# Introdução

Com o avanço do acesso a Internet e a popularização dos *smartphones*, cada vez mais as pessoas utilizam seus cartões de crédito para realizar compras em lojas online, aplicativos e afins.<br><br>
Em um cenário como este, é de se esperar que, infelizmente, algumas pessoas mal-intencionadas busquem meios para fraudar cartões de crédito e realizar compras no nome - e com o dinheiro - de outras pessoas.<br><br>
Para **evitar** que clientes sejam cobrados por compras que não foram feitas por eles, é muito importante que bancos e empresas de cartão de crédito sejam capazes de reconhecer quando determinada transação é fruto de fraude ou não.<br><br>
Neste projeto, utilizarei algoritmos de **machine learning** para treinar um modelo preditivo que seja capaz de aprender e detectar quando uma transação for fraudulenta ou não. Utilizarei os classificadores **Decision Tree**, **Random Forest**, **Ada Boost** e **Gradient Boosting** da biblioteca **Scikit-Learn** para identificar qual dentre estes quatro algoritmos se encaixa melhor em nosso conjunto de dados e produz os melhores resultados de acordo com as métricas de avaliação dos modelos.

# Desenvolvimento

 Para desenvolver nosso modelo preditivo, utilizei **Scikit-Learn**, biblioteca open-source de **machine learning** para Python, e testei o funcionamento dos algoritmos de classificação **Random Forest**,**Decision Tree**, **Ada Boost** e **Gradient Boosting** para observar qual dos dois atingiria a melhor performance diante de nosso conjunto de dados, observando as métricas de avaliação de classificação, como o **recall**, **precision**, **f1 score**, **matriz de confusão**,etc...<br><br>
 
 Também utilizei pandas, numpy, matplotlib, seaborn e plotly para **explorar**, **manipular** e **visualizar** características relevantes do dataset.<br><br>
 
 O conjunto de dados utilizado foi o <a href= "https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud">Credit Card Fraud Detection</a> postado no Kaggle e que contém transações de cartões de crédito realizadas em Setembro de 2013 por clientes europeus durante dois dias. O dataset possui as variáveis **time**, que registra os segundos que se passaram entre cada transação e a **primeira transação** do dataset, enquanto **amount** registra o valor em Euros da transação e, por fim, a variável **class**, que registra se aquela transação é fraudulenta ou não, onde **1 = fraude** e **0 = genuína**. As variáveis V1,V2,V3...V28 sofreram transformações de <a href = "https://pt.wikipedia.org/wiki/An%C3%A1lise_de_componentes_principais">análise de componentes principais</a> e não tiveram seu conteúdo informado, devida a **alta confidencialidade** de suas informações.<br><br>
 
 Durante o desenvolvimento, utilizamos métodos do **Sklearn**, como o **StandardScaler**, para alterar a escala de valores das transações, evitando que a discrepância de valores nesta variável afetasse a performance de nosso modelo, e o **SMOTE** da biblioteca **imblearn** para lidar com o **desbalanceamento** dos dados de transações genuínas e fraudulentas.<br><br>
 
 # Métricas de Performance
 
 Para auxiliar no entendimento de como os algoritmos performaram diante do dataset utilizado, é preciso entender como funcionam as métricas de avaliação dos modelos que utilizamos.<br><br>
 Uma forma muito simples de visualizar a performance do modelo é a **matriz de confusão**, organizada da seguinte forma:<br><br>
<center><img src= "https://miro.medium.com/max/1400/1*j0TSVygS7ZPfK-lZkojNcQ.png"></center><br><br>
A <b>matriz de confusão</b> consegue nos mostrar as classificações corretas e incorretas de cada classe e nos indica se o modelo está favorecendo uma classe em detrimento da outra ou não.<br>
Além da matriz de confusão, temos as seguintes métricas de avaliação do modelo:<br>

## Acurácia <br><br> 
Nos diz o quanto o modelo classificou corretamente, independente da classe dos exemplos. É definida pela seguinte fórmula:<br>
<center><img src = "https://miro.medium.com/max/1178/1*tNTpugu1beoC3f6ivswnsA.png"></center><br>
Onde: TP = Verdadeiro Positivo;<br>
TN = Verdadeiro Negativo;<br>
FP = Falso Positivo e<br>
FN = Falso Negativo. <br><br> 

## Precisão <br><br> 
É a razão entre o número de exemplos positivos classificados corretamente e o total de exemplos classificados como positivos, incluindo os falsos positivos, e busca responder qual a proporção de classificações positivas foi realmente correta. É definida pela seguinte fórmula:<br>
<center><img src = "https://miro.medium.com/max/476/1*pJrHo_sp-pnLFl6Ww3imUw.png"></center><br><br>

## Recall <br><br> 
Pode ser definida como a taxa de verdadeiro positivo e busca responder o quão bem o modelo prevê a classe que queremos prever. É definida pela seguinte fórmula:<br>
<center><img src = "https://miro.medium.com/max/396/1*zgmkLfNNRtFwCHp8m46AKA.png"></center><br><br>

## F1 Score <br><br> 
O F1 Score é o balanço entre a **precisão** e o **recall** e é definida pela seguinte fórmula:<br>
<center><img src = "https://miro.medium.com/max/520/1*sBVtY3BJoJbOs47ZZx46tA.png"></center><br><br>

# Conclusão
Quando trabalhamos com um **modelo de machine learning**, devemos sempre saber de fato o que é que queremos **extrair daquele modelo** e **qual resultado queremos atingir**.<br><br>
Neste projeto, nosso objetivo era criar um modelo que fosse capaz de **detectar transações fraudulentas** quando elas ocorressem e o modelo que melhor performou esta tarefa foi o **Ada Boost**, com um **recall de 90,60%**, corretamente identificando 145 transações fraudulentas em um conjunto de dados que tinha 160 destas transações. Entretanto, é possível perceber que o **Ada Boost** também identificou, dentre os demais algoritmos, o **maior número de falsos positivos**, ou seja, 1.307 transações genuínas (cerca de 1,53% do total de transações genuínas) foram incorretamente identificadas como sendo fruto de fraude.<br><br>
Uma transação genuína sendo classificada como fraude pode impactar em problemas ao cliente!<br><br>
Neste cenário, é importante **entender o modelo de negócio** e fazer alguns questionamentos, como: <br><br>
- O quão caro nos custariam os falsos positivos?<br><br>
- Devemos manter o algoritmo Ada Boost, que teve a melhor performance de identificação de transações fraudulentas, enquanto também teve diversos falsos positivos, ou mudamos para o Random Forest, que também atingiu boas métricas de performance (recall de 83,12%) e classificou apenas 0,02% das transações genuínas como fraudulentas? Mas isto também implicaria em um número maior de fraudes que **não seriam identificadas**...<br><br>

Essas questões, junto com um bom entendimento do negócio e de como queremos abordar as soluções de **machine learning** para lidarmos com problemas são fundamentais para ajudar no processo de tomada de decisão para escolhermos se estamos dispostos ou não a lidar com um número maior de falsos positivos se isso resultar em um modelo capaz de identificar o maior número de fraudes possível.<br><br>

-----

# Kaggle
Para acessar este projeto em Inglês no Kaggle, <a href = "https://www.kaggle.com/code/lusfernandotorres/91-87-recall-with-ada-boost-cc-fraud-detection">clique aqui</a>.<br>
To see this project in English on Kaggle, <a href = "https://www.kaggle.com/code/lusfernandotorres/91-87-recall-with-ada-boost-cc-fraud-detection">click here</a>.


# Referências
<a href="https://medium.com/data-hackers/entendendo-o-que-%C3%A9-matriz-de-confus%C3%A3o-com-python-114e683ec509">Entendendo o que é Matriz de Confusão com Python</a><br><br>
<a href="https://medium.com/kunumi/m%C3%A9tricas-de-avalia%C3%A7%C3%A3o-em-machine-learning-classifica%C3%A7%C3%A3o-49340dcdb198">Métricas de Avaliação em Machine Learning: Classificação</a><br>

# Author
**Luís Fernando Torres**
