<div align="center">
<img src="images/diamonds-transparent-background-20.png" width="400">

# RICK'S DIAMONDS
<div align="left">
Uso de uma base de dados de características e preços de diamantes, limpeza de dados e construção de um modelo de regressão linear para prever os preços de uma segunda base de dados. 


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

Para esta projeto usaremos duas bases de dados, a primeira servirá para treinar e testar o nosso modelo a segunda para usar efetivamente nosso modelo, o resultado será feito o upload em um site que avaliará o sucesso de nosso modelo.

Primeiramente realizamos a importação da base e verificamos o seu estado.

<img src=images/diamond_001.png>

Logo de cara percebemos diversas variáveis categóricas para simplificar usamos o código abaixo para realizar a sua conversão em variáveis categóricas com labels numéricas.

<img src=images/diamond_002.png>
  
Continuamos a nossa análise e usamos o Pairplot para plotar um comparativo de todas as variáveis com a variável preço.
  
<img src=images/fpair%20(3).png>  

Outro fator de preocupação seria o fato do valor mínimo das dimensões era zero, assim por se tratar de um objeto físico era impossível ter dimensões nulas, e dimensões máximas muito grandes, assim plotamos um boxplot para verificar como estava a distribuição de valores.
   
<img src=images/diamond_003.png>

Foi plotado um Boxplot com as dimensões y e z e foi verificado a presença de alguns outliers.
  
<img src=images/box1%20(1).png>
  
Assim foi optado por remover os objetos com dimensão maior que 10 vem como os com dimensão nula
  
<img src=images/diamond_004.png>

Após a remoção percebemos que comparando com a imagem anterior que removemos 26 linhas da base de dados. Um valor muito baixo se comparado ao total de linhas.
Foi feito um plot de um segundo Boxplot e verificamos uma distribuição bem mais uniforme.
  
<img src=images/box_2%20(1).png>

Realizamos novamente o pairplot e tivemos uma atenuação do formato price x carat
  
<img src=images/spair%20(1).png>
  
Vamos analisar mais a fundo esta variável plotamos ela individualmente.
Percebemos uma distância variável da região de concentração.

<img src=images/line_01.png>
  
Aplicamos a escala logarítmica para suavizar o ruído e obtivemos sucesso agora a distância está mais uniforme.  
Assim fazia sentido usar escala logarítmica na construção de nosso modelo.
  

  
<img src=images/line_02.png>  
 
  
Por fim a base ficou desta forma e decidimos adicionar a variável volume que seria a multiplicação dos 3 eixos
em um teste de correlação apresentou uma correlação maior que os eixos individuais. 
  
<img src=images/diamond_005.png>

Na de estimação de dados tivemos uma linha com ausência de alguns dados, assim para a coluna que faltava apenas o z usaremos a fórmula fornecida pelo codebook, e para a linha com ausência de dados nas 3 dimensões vamos usar uma coluna para doar os dados
assim pegamos uma informação de outra coluna com mesmo depth e mesma table.


<img src=images/diamond_006.png>
  
Assim aplicamos esta função para o cálculo do volume.
  
<img src=images/diamond_007.png>

E esta função para o cálculo das dimensões faltantes.

<img src=images/diamond_008.png>

Executamos as funções foi necessário adicionar 1 nas categorias, pois como usaríamos escala logarítmica o valor zero daria erro na função assim reajustamos a escala para partir de 1.


<img src=images/diamond_009.png>

Construindo o modelo, para as variáveis dimensionais tínhamos pouco ruído assim decidi não aplicar a elas a função logarítmica.

  
<img src=images/diamond_010.png>

Rodamos o teste da função e os números para o teste parecem muito promissores apesar de estarem em escala logarítmica ainda assim deram um valor baixo.

<img src=images/diamond_011.png>

Agora aplicamos nosso modelo ao dataset que queremos prever os preços.

<img src=images/diamond_012.png>

Salvamos em um arquivo .csv
  
Futuramente, seria interessante, testar mais extensamente as combinações de função logarítmica e dados sem transformação e usar outros métodos como decision forest para obter melhores resultados.


## Recursos Usados

  - Importação de Database
  - Limpeza de dados
  - Criação de um DataFrame
  - Análise de parâmetros estatísticos
  - Análise de gráficos
  - Construção de um modelo de regressão linear
  - Teste e validação deste modelo
  

## Links

  - Repositório: https://github.com/Alexandremsn/Ricks_Diamonds
  - Se for encontrado um bug, favor entrar em contato alexandremsneto1986@gmail.com


## Versão

1.0.0.0


## Autor

* **Alexandre Machado da Silva Neto**: @alexandremsn (https://github.com/alexandremsn)
