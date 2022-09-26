<div align="center">
<img src="images/logodiamond.png">

# RICK'S DIAMONDS
<div align="left">
Uso de uma base da dados de características e preços de diamantes, limpeza de dados e contrução de um modelo de regreção linear para prever os preços de uma uma segunda base de dados. 


## Tecnologia

Os softwares  usados neste projeto foram:

* Python version  3.9.5
* Tableau version 2022.2
* MySQL Workbench 0.8 CE

## Serviços Usados

* Github


## Bibliotecas Python

* Requests
* Pandas
* Sqlalchemy
* Dotenv
* Json


## Gráficos Tableau

* Cartões
* Pizza
* Linhas
* Tabelas


## Como foi feito

Será descrito abaixo através de textos e imagens.

Para este projeto usamos a API RAWG, acessível no link: http://rawg.io
Esta API, possui um banco de dados de vários jogos, com seus dados, avaliações, status dos jogos fornecidos por jogadores e diversas outras informações.
Focaremos na varíavel avaliação e gênero, para verificarmos correlações e variações, se a preferência do público se alterou nos últimos 20 anos. Podemos também realizar inferências sobre os status dos jogos e número de votos o jogo recebeu.

<img src=images/001.png>

Usamos uma das APIS chamada Game List, que fornece dados gerais sobre jogos, na imagem vemos os parâmetros que podem ser usados nesta API, 
mais para frente veremos que os parâmetros page e page_size serão utilizados.

<img src=images/002.png>

Também usamos o parâmetro Dates, pois no nosso projeto usaremos o filtro entre 01-01-2000 até 31-21-2020, assim gerando dados completos dos últimos 20 anos.

<img src=images/003.png>

Esta ultima parte dos parâmetros não utilizamos.

<img src=images/004.png>

Após verificar a primeira requisição para ter uma ideia do formado, verificamos dois problemas, todos os dados estavam em uma única célula e que a API só fornecia 40 registros por requisição, assim para solucionar o primeiro problema dividimos cada conjunto de dados de cada jogo em uma linha e criamos um laço for para fazer múltiplas requisições e armazenar todos os dados em um dataframe ainda não normalizado.

<img src=images/005.png>

Após aplicar um segundo laço desempacotamos cada linha e adicionados em um dataframe normalizado e tivemos este resultado, que já está mais amigável.

<img src=images/006.png>

Depois verificamos que o único dado que vamos utilizar que ainda precisaria ser desempacotado seria a coluna com o gênero do jogo, assim criamos uma função para realizar o desempacotamento e guardar este dado em uma lista. Depois selecionamos todas as colunas que utilizaremos, e finalmente verificamos que o código rodou com sucesso.

<img src=images/007.png>

Na parte final do código, criamos uma tabela com id_jogo e gênero, pois os jogos possuem mais de um gênero ao mesmo tempo, assim, podemos usar futuramente um join para fazer a relações entre as tabelas e acessar cada gênero individualmente. Exportamos as tabelas em  .CSV para uso em alguma validação, depois por fim exportamos para um banco de dados MySQL.

<img src=images/008.png>

Testamos com uma query simples para verificar se as tabelas foram carregadas, e podemos ver as tabelas carregadas corretamente.

<img src=images/009.png>

Para a segunda tabela também tivemos sucesso.

<img src=images/010.png>

Na sequência construiremos visuais com criação de linha do tempo, filtros por gênero, e ao longo desta construção verificaremos se conseguimos verificar outras relações que agreguem valor e sejam uteis na construção de outros visuais.

Inciando a construção do Dashboard
Foi feito o plano de fundo e definido a posição dos visuais

<img src=images/012.png>

No tableau importamos as tabelas e criamos o vínculo entre elas pela variável id

<img src=images/013.png>

Assim começamos montando as medidas que darão o somatório de cada status possível informado pelos usuários.

<img src=images/014.png>

Criamos o owned e configuramos a fonte e fundo do visual

<img src=images/015.png>

Depois repetimos os processos para os outros status e aplicamos no dashboard

<img src=images/016.png>

Criamos o gráfico com a evolução da avaliação por ano estratificada por gênero 

<img src=images/017.png>

Criamos os filtros e configuramos para aplicar a filtragem a todos os dados da mesma base 
Posicionamos 

<img src=images/018.png>

Depois criamos uma tabela que detalha os mais bem avaliados dentro do filtro aplicado 

<img src=images/019.png>

Criamos o gráfico com a evolução de avaliações por tempo estratificada por gênero 

<img src=images/020.png>

Depois criamos um gráficos com o percentual de avaliações por gênero

<img src=images/021.png>

E ficamos com este resultado final
Link: https://public.tableau.com/app/profile/alexandre.machado.da.silva.neto/viz/games2_16625096795530/viz?publish=yes

<img src=images/022.png>

Uma vizualização completa das avaliações podendo ser filtrada e comparar gêneros e períodos de tempo

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
