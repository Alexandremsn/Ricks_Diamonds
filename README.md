<div align="center">
<img src="images/diamonds-transparent-background-20.png" width="400">

# RICK'S DIAMONDS
<div align="left">
Uso de uma base da dados de características e preços de diamantes, limpeza de dados e contrução de um modelo de regreção linear para prever os preços de uma uma segunda base de dados. 


## Tecnologia

Os softwares  usados neste projeto foram:

* Python version  3.9.5

## Serviços Usados

* Github


## Bibliotecas Python

* Pandas
* Numpy
* Matplotlib.pyplot
* Seaborn
* Sklearn.model_selection.train_test_split
* Sklearn.linear_model.LinearRegression
* Sklearn.metrics
* Sklearn.preprocessing

## Como foi feito

Será descrito abaixo através de textos e imagens.

Para esta projeto usaremos duas bases de dados, a primeira servirá para treinar e testar o nosso modelo a segunda para usar efetivamente nosso modelo, o resultado será feito o upload em um site que alaviará o sucesso de nosso modelo.

primeiramente realizamos a importação da base e verificamos o seu estado.

<img src=images/diamond_001.png>

Logo de cara percebemos diversas variáveis categóricas para simploficar usamos o código abaixo para realizar a sua converção em variáveis categóricas com labels numéricas.

<img src=images/diamond_002.png>
  
Continuamos a nossa análise e usamos o Pairplot para plotar um comparativo de todas as variáveis com a varíavel preço.
  
<img src=images/fpair%20(3).png>  

Outro fator de preucupação seria o fato do valor mínimo das dimenções era zero, asssim por se tratar de um objeto físico era impossível ter dimensões nulas, e dimensõe máximas muito grandes, assim plotamos um boxplot para verificar como estava a distribuição de valores.
   
<img src=images/diamond_003.png>

Foi plotado um Boxplot com as dimenções y e z e foi verificado a presença de alguns outliers.
  
<img src=images/box1%20(1).png>
  
Assim foi optado por remover os objetos com dimensão maior que 10 vem como os com dimensão nula 


<img src=images/diamond_004.png>

Após a remoção precebemos que comparando com a imagem anterior que removemos 26 linhas da base de dados. um valor muito baixo se comparado ao total de linhas.
Foi feito um plot de um segundo Boxplot e verificamos uma distribuição bem mais uniforme.
  
<img src=images/box_2%20(1).png>

Realizamos novamente o pairplot e tivemos uma atenuação do formato price x carat
  
<img src=images/box_2%20(1).png>
  
Vamos analizar mais a fundo esta variável plotamos ela individualmente.
percebemos uma ditância variável da região de concentração.
<img src=images/line_01.png>
  
Aplicamos a escala logarítimica para suavizar o ruido e obtivemos sucesso agora a distância está mais uniforme.  
Assim fazia sentido usar escala lograítimica na contrução de nosso modelo.
  

  
<img src=images/line_02.png>  
 
  
Importando a nossa segunda base para realizar a previsão.
realizamos as mesmas converções de dados das variáveis categóricas.
  
  
<img src=images/diamond_005.png>


<img src=images/diamond_006.png>
  
  
  
<img src=images/diamond_007.png>

<img src=images/diamond_008.png>

<img src=images/diamond_009.png>

<img src=images/diamond_010.png>

<img src=images/diamond_011.png>

<img src=images/diamond_012.png>

  
Futuramente, seria interessante, usar outras apis para incrementar os dados desta base de dados ou dados externos.


## Recursos Usados

  - Importação de Database
  - Limpeza de dados
  - Criação de um DataFrame
  - Criação de arquivo .csv
  - Análise de Tabelas
  - Carga da base de dados em ambiente SQL
  - Criação de um Dashboard
  

## Links

  - Repositório: https://github.com/Alexandremsn/shark_atacks_data_cleaning
  - Se for econtrado um bug, favor entrar em contato alexandremsneto1986@gmail.com


## Versioning

1.0.0.0


## Autor

* **Alexandre Machado da Silva Neto**: @alexandremsn (https://github.com/alexandremsn)
