# Exercícios das listas do Everest da AdaTech

## Lista 1

### 1. Identifique nas alternativas abaixo como verdadeiras ou falsas, funções do Pandas utilizadas principalmente na limpeza de dados: <br>

`dropna`: **VERDADEIRO** <br>
info: **FALSO** <br>
`duplicated`: **VERDADEIRO** <br>
`read_csv`: **FALSO** <br>

### 2. Identifique nas alternativas abaixo como verdadeiras ou falsas, funções que podem ser utilizadas para localizar pontos específicos (em termos de linha e coluna) de um conjunto de dados: <br>

`loc`: **VERDADEIRO** <br>
`concat`: **FALSO** <br>
`fillna`: **FALSO** <br>
`iloc`: **VERDADEIRO** <br>

### 3. Identifique as alternativas abaixo como verdadeiras ou falsas, para as funções que são nativas do Pandas: <br>

`head`: **VERDADEIRO** <br>
`randint`: **FALSO** <br>
`describe`: **VERDADEIRO** <br>
`value_counts`: **VERDADEIRO** <br>

### 4. Qual o nome do processo onde solicita-se a implementação de um novo código ou alteração de um já existente em um repositório Git? <br>

`pull request`: O pull request faz a solicitação de mescla dos dados novos com o repositório. <br>

### 5. Dado o array [1, 3, 4, 8, 2], qual seria o resultado ao aplicar a função argmax do NumPy? <br>

`3`: Está é a posição no array onde tem o maior valor. <br>

### 6. Qual é a função do Pandas que calcula as frequências de um determinado atributo, sendo esta frequência absoluta ou relativa? <br>

`value_counts`: Função do Pandas para calcular as frequências em determinado atributo. <br>

### 7. Complete as lacunas do trecho de código abaixo, para o exemplo de como normalmente é estruturado um commit no Git: <br>

git `add` . <br>
git `commit` -m Digite uma Mensagem <br>
git `push` <br>

### 8. Identifique a opção correta para acessar todos as linhas da terceira coluna de uma matriz chamada mtx, criada com NumPy? <br>

`mtx[:, 2]`: Nesta configuração, seleciona todas as linhas da terceira coluna. <br>

### 8. Complete as lacunas do trecho de código abaixo, onde utiliza-se algumas funções do pandas para explorar os dados: <br>

df=pd. `read_csv` (data) <br>
df[target]. `value_counts` (normalize = True) <br>
df. `describe` () <br>

### 9. Complete as lacunas do trecho de código abaixo sobre a utilização do pandas para carregar e visualizar dados: <br>

`data` = {'col0': [1.68, 1.81, 1.75], 'col1': [80, 75, 90]} <br>
df = pd.`DataFrame`(data) <br>
df. `head` () <br>

### 10. Identifique nas alternativas abaixo como verdadeiras ou falsas, funções matemáticas nativas do NumPy: <br>

`unique`: **FALSO** <br>
`cos`: **VERDADEIRO** <br>
`dot`: **VERDADEIRO** <br>
`array`: **FALSO** <br>

### 11. Qaul é a função do Pandas utilizada para criar um DataFrame, independente da utilização de dados externos? <br>

`pd.DataFrame()` <br>

## Lista 4 - Everest

### 1. Cálculo da Imagem Integral de uma Matriz de Pixels Utilizando NumPy em Processamento de Imagens <br>

Você é um cientista de dados de uma empresa de tecnologia que está desenvolvendo um algoritmo de detecção de bordas em imagens digitais. Para implementar o algoritmo, é necessário calcular a imagem integral da imagem original. <br>

Imagem integral é um conceito muito utilizado no processamento de imagens para acelerar o cálculo de operações como filtros, detecção de bordas e reconhecimento de objetos. Ela consiste em uma matriz que armazena a soma acumulada dos pixels de uma imagem em todas as posições à esquerda e acima de um determinado pixel. Dessa forma, o valor de um determinado retângulo na imagem pode ser calculado em tempo constante, independente do tamanho do retângulo. A imagem integral é amplamente utilizada em aplicações de visão computacional, como detecção de faces e análise de objetos em tempo real. <br>

**Solução**

```python
import numpy as np
def calcula_imagem_integral(imagem: np.ndarray) -> np.ndarray:
	np_cumsum_zero = np.cumsum(imagem, axis=0)
	np_cumsum_um = np.cumsum(np_cumsum_zero, axis=1)	
	return np_cumsum_um
```

### 2. Análise de transações financeiras com NumPy <br>

A biblioteca NumPy é uma ferramenta amplamente utilizada na área financeira para a análise de grandes conjuntos de dados, principalmente na detecção de fraudes bancárias. Como analista de dados de uma instituição financeira, você foi designado para analisar transações financeiras a fim de identificar possíveis fraudes. A instituição coleta os dados das transações realizadas e armazena-os em arrays NumPy. Escreva uma função chamada `analisa_transacoes`, que recebe como entrada um array NumPy de valores de transações e retorna um array NumPy do tipo **float64** com as seguintes medidas estatísticas: <br>

- Média;
- Desvio padrão;
- Valor mínimo;
- Valor máximo;
- Mediana;
- Quartis 25% e 75%.

**Solução**

```python
import numpy as np
def analisa_transacoes(arr: np.ndarray) -> np.ndarray:
	mean = np.mean(arr)
	std = np.std(arr)
	min_value = np.min(arr)
	max_value = np.max(arr)
	median = np.median(arr)
	first_quart = np.percentile(arr, 25)
	third_quart = np.percentile(arr, 75)
	return np.array([mean, std, min_value, max_value, median, first_quart, third_quart])
```

### 3. Cálculo do Índice de Massa Corporal (IMC) em um Dataframe <br>

Você é um nutricionista e precisa criar uma ferramenta para calcular o Índice de Massa Corporal (IMC) de seus pacientes. Para isso, você pode utilizar a biblioteca Pandas do Python. Ela é uma biblioteca Python de código aberto que fornece ferramentas de análise e manipulação de dados de forma rápida e eficiente. O Pandas permite trabalhar com dados em formato de tabela, chamados de DataFrames, com colunas de tipos diferentes, além de oferecer funcionalidades para indexação, agregação, seleção, filtragem e visualização dos dados. Com essa biblioteca, é possível realizar tarefas de limpeza, transformação e modelagem de dados, sendo uma ferramenta muito útil em áreas como ciência de dados, finanças, economia, entre outras. <br>

Escreva uma função chamada `calcula_imc` que receba um DataFrame pandas contendo as informações de nome, idade, sexo, altura e peso de um paciente, calcule o IMC e adicione uma nova coluna no DataFrame contendo o resultado do cálculo. Em seguida, a função deve retornar o DataFrame modificado. <br>

**Solução**

```python
import pandas as pd
def calcula_imc(df: pd.DataFrame) -> pd.DataFrame:
	df['IMC'] = df['Peso'] / (df['Altura'] ** 2)
	return df
```

### 4. Criação de DataFrame Pandas para Apoio a Planejamento de Dieta <br>

Suponha que você esteja desenvolvendo um sistema para apoio a planejamento de dieta, que tem como objetivo auxiliar as pessoas a atingirem seus objetivos de saúde por meio de uma alimentação equilibrada. Uma das funcionalidades desse sistema é o registro das informações pessoais dos usuários, tais como nome, idade, sexo, altura e peso. <br>

Para armazenar essas informações, você pode utilizar a biblioteca pandas do Python, que permite trabalhar com tabelas de dados (DataFrames). Pandas é uma biblioteca Python de código aberto que fornece ferramentas de análise e manipulação de dados de forma rápida e eficiente. O Pandas permite trabalhar com dados em formato de tabela, chamados de DataFrames, com colunas de tipos diferentes, além de oferecer funcionalidades para indexação, agregação, seleção, filtragem e visualização dos dados. Com essa biblioteca, é possível realizar tarefas de limpeza, transformação e modelagem de dados, sendo uma ferramenta muito útil em áreas como ciência de dados, finanças, economia, entre outras. <br>

**Solução**

```python
import pandas as pd
def cria_dataframe(lista: list) -> pd.DataFrame:
	columns = ['Nome', 'Idade', 'Sexo', 'Altura', 'Peso']
	return pd.DataFrame(lista, columns=columns)
```

### 5. Cálculo da soma dos elementos de cada coluna em uma matriz usando NumPy <br>

O processamento digital de imagens é uma área que utiliza técnicas computacionais para processar e analisar imagens digitais. Uma das bibliotecas utilizadas nessa área é o NumPy, uma biblioteca Python que permite trabalhar com matrizes multidimensionais e oferece diversas funções e operações matemáticas. <br>

Suponha que você seja um desenvolvedor de software de processamento digital de imagens e foi designado para criar uma função que calcule a soma dos elementos de cada coluna de uma matriz de entrada. A matriz de entrada pode ter qualquer tamanho e é armazenada como um array NumPy. <br>

**Solução**

```python
import numpy as np
def soma_colunas(matriz: np.ndarray) -> np.ndarray:
	return np.sum(matriz, axis=0)
```

### 6. Concatenação de Arrays Numpy para Análise de Vendas em Diferentes Regiões <br>

Você é um analista de dados em uma empresa de vendas online e recebeu uma tarefa para analisar as vendas de um determinado produto em diferentes regiões do país. As informações de vendas são armazenadas em dois arrays numpy, um com as vendas da região Sul e outro com as vendas da região Norte. O numpy é uma biblioteca do Python utilizada para trabalhar com matrizes e arrays multidimensionais de forma eficiente, que oferece diversas funções e operações para facilitar a manipulação desses objetos. Uma das vantagens do numpy em relação às listas do Python é a velocidade e eficiência nas operações com arrays. Você precisa concatenar os dois arrays para ter uma visão geral das vendas do produto em todo o país. Para isso, você vai criar uma função chamada concatena_array, que recebe como argumentos dois arrays do tipo numpy e retorna um único array do tipo numpy concatenando os dois. <br>

**Solução**

```python
import numpy as np
def concatena_array(arr1: np.ndarray, arr2: np.ndarray) -> np.ndarray:
	return np.concatenate((arr1, arr2))
```

### 7. Criação de uma Matriz Identidade Usando NumPy <br>

Você é um analista de dados em uma empresa de vendas online e recebeu uma tarefa para analisar as vendas de um determinado produto em diferentes regiões do país. As informações de vendas são armazenadas em dois arrays numpy, um com as vendas da região Sul e outro com as vendas da região Norte. O numpy é uma biblioteca do Python utilizada para trabalhar com matrizes e arrays multidimensionais de forma eficiente, que oferece diversas funções e operações para facilitar a manipulação desses objetos. Uma das vantagens do numpy em relação às listas do Python é a velocidade e eficiência nas operações com arrays. Você precisa concatenar os dois arrays para ter uma visão geral das vendas do produto em todo o país. Para isso, você vai criar uma função chamada concatena_array, que recebe como argumentos dois arrays do tipo numpy e retorna um único array do tipo numpy concatenando os dois. <br>

**Solução**

```python
import numpy as np
def cria_matriz_identidade(n:int, m:float) -> np.ndarray:
	return np.eye(n) * m
```

### 8. Média de Avaliações de Jogos Eletrônicos Usando Numpy <br>

Você é um analista de dados em uma empresa de jogos eletrônicos e recebeu uma tarefa para analisar as notas de avaliação de jogos de um banco de dados. As notas de avaliação são armazenadas em um array numpy, uma biblioteca do Python que permite trabalhar com matrizes multidimensionais e oferece diversas funções e operações matemáticas. Uma das vantagens do numpy em relação às listas é que as operações em arrays são mais eficientes computacionalmente, permitindo lidar com grandes quantidades de dados de forma mais rápida. Você precisa calcular a média das notas para ter uma ideia da satisfação dos jogadores com os jogos. Para isso, você vai criar uma função chamada `media_avaliacao`, que recebe como argumento um array do tipo numpy e retorna um único valor _float_ com a média. <br>

**Solução**

```python
import numpy as np
def media_avaliacao(arr: np.ndarray) -> float:
	return np.mean(arr)
```

## Lista 5 - Everest

### 1. Listando Pessoas em uma Faixa Etária Específica em um DataFrame <br>

Em um sistema de gerenciamento de academias, é necessário ter uma forma de buscar alunos em uma faixa etária específica para oferecer promoções e descontos em planos de treinamento. Para isso, será criada uma função que liste todas as pessoas com idades entre idade mínima e idade máxima. <br>

**Solução**

```python
import pandas as pd
def busca_por_faixa_etaria(df: pd.DataFrame, idade_minima: int, idade_maxima: int) -> pd.DataFrame:
	filtro = (df['Idade'] >= idade_minima) & (df['Idade'] <= idade_maxima)
	return df[filtro]
```

### 2. Transformação de colunas de dados categóricos em dados binários em um DataFrame Pandas <br>

Imagine que você está trabalhando em um projeto de Machine Learning e precisa treinar um modelo para classificar diferentes tipos de frutas. Uma das variáveis do conjunto de dados é o nome da fruta, que está na coluna "A" do DataFrame. No entanto, para que esse tipo de variável possa ser usada em um modelo de aprendizado de máquina, ela precisa ser transformada em uma representação numérica. <br>

Uma possível abordagem seria criar uma coluna para cada fruta presente no conjunto de dados e preencher com valores 1 ou 0 indicando se a linha corresponde à fruta daquela coluna ou não. Isso permitiria que o modelo aprendesse padrões nas diferentes frutas e fizesse previsões com base nessas informações. <br>

Crie uma função que permite realizar essa transformação. Ela recebe o DataFrame com as informações das frutas e a coluna que contém os nomes das frutas (coluna "A" no exemplo). Em seguida, ela cria uma coluna separada para cada valor único na coluna "A", preenchendo com valores 1 ou 0 de acordo com a presença ou ausência da fruta em cada linha. O resultado é um novo DataFrame com as colunas transformadas. <br>

**Solução** _(75%)_

```python
import pandas as pd
def transforma_coluna_em_dummy(df: pd.DataFrame, coluna: str) -> pd.DataFrame:

    dummies = pd.get_dummies(df[coluna])

    df_dummies = pd.concat([df.drop(columns=[coluna]), dummies], axis=1)
    
    colunas_dummies = list(dummies.columns)
    df_dummies = df_dummies[['B'] + colunas_dummies]
    
    return df_dummies
```

### 3. Tratamento de Dados Faltantes em DataFrame do Pandas <br>

Você é um analista de dados de uma empresa que trabalha com vendas online e recebeu um conjunto de dados de vendas contendo informações sobre produtos, clientes e transações. Ao analisar o conjunto de dados, você percebeu que existem valores faltantes em algumas colunas, o que pode afetar as análises que precisam ser realizadas. <br>

Dados faltantes, também conhecidos como valores missing, são valores ausentes em um conjunto de dados que não foram coletados ou não puderam ser registrados. Eles são um problema comum em análise de dados e podem causar problemas em modelos de machine learning, estatísticas e visualizações. <br>

Crie uma função que receba como entrada um DataFrame contendo dados de vendas e identifique as colunas que possuem valores faltantes. A função deve substituir os valores faltantes pela média da respectiva coluna. <br>

**Solução**

```python
import pandas as pd
import numpy as np

def trata_dados_faltantes(df: pd.DataFrame) -> pd.DataFrame:
	medias = df.mean()
	return df.fillna(medias)
```

### 4. Detecção de Valores Atípicos com Desvio Padrão <br>

Suponha que você trabalhe em uma empresa de manutenção preditiva industrial, responsável por monitorar a saúde de equipamentos críticos por meio de dados de sensores. Para identificar possíveis falhas antes que ocorram, os dados coletados passam por um processo de análise e tratamento. <br>

Escreva uma função em Python que receba um DataFrame contendo dados de temperatura dos sensores instalados nos equipamentos e utilize a técnica do desvio padrão para identificar valores atípicos nessa coluna (Detecção de outlier). A função deve retornar uma lista contendo os registros que contêm valores atípicos na coluna "Temperatura". Esses valores podem indicar possíveis problemas no equipamento e precisam ser investigados pela equipe de manutenção antes que uma falha ocorra e interrompa a produção. <br>

Detecção de outlier é uma técnica utilizada em análise de dados para identificar valores que se distanciam significativamente da maioria dos outros valores em um conjunto de dados. Esses valores, também conhecidos como valores atípicos, podem afetar negativamente a análise estatística e, portanto, precisam ser identificados e tratados adequadamente. Uma das técnicas para detectar outliers é o uso do desvio padrão. O desvio padrão é uma medida de dispersão que indica o quão distante os valores estão da média do conjunto de dados. O desvio padrão é uma medida de dispersão que indica o quanto os dados estão afastados da média. <br>

**Solução**

```python
import pandas as pd

def identifica_outliers(df: pd.DataFrame, coluna: str) -> pd.DataFrame:
	Q1 = df[coluna].quantile(0.25)
	Q3 = df[coluna].quantile(0.75)

	IQR = Q3 - Q1

	limite_inferior = Q1 - 1.5 * IQR
	limite_superior = Q3 + 1.5 * IQR

	return df[(df[coluna] < limite_inferior) | (df[coluna] > limite_superior)]
```

### 5. Exclusão de Registros em DataFrame <br>

Suponha que você trabalhe em uma empresa que coleta e armazena informações de clientes em um DataFrame para fins de análise de mercado. Devido à entrada em vigor da Lei Geral de Proteção de Dados (LGPD), é necessário excluir os registros de clientes que solicitaram a exclusão de seus dados pessoais. <br>

A LGPD é a Lei Geral de Proteção de Dados, que entrou em vigor em setembro de 2020 e tem como objetivo regulamentar o uso, a proteção e a transferência de dados pessoais no Brasil. A lei estabelece regras para empresas e órgãos públicos em relação à coleta, tratamento, armazenamento e compartilhamento de informações de indivíduos, garantindo a privacidade e a segurança dos dados. A LGPD também prevê sanções para quem descumpri-la, como multas e até mesmo a proibição do tratamento de dados pessoais. <br>

Escreva uma função que receba um DataFrame com informações de clientes e uma lista de índices a serem excluídos. A função deve remover os registros correspondentes aos índices da lista e retornar o DataFrame modificado. O objetivo dessa função é garantir a conformidade com as regulamentações da LGPD e garantir a privacidade dos dados pessoais dos clientes. <br>

**Solução**

```python
import pandas as pd
def deleta_registros(df: pd.DataFrame, indices: list) -> pd.DataFrame:
	return df.drop(indices).reset_index(drop=True)
```

### 6. Criação de Série Pandas a partir de Listas de Valores e Índices <br>

Suponha que você é um analista de dados de uma empresa de varejo e precisa manipular uma lista com informações de vendas de diferentes produtos. Para facilitar a análise desses dados, você decidiu criar uma função que transforma essa lista em uma série do pandas. <br>

Crie uma função que receba uma lista de valores e uma lista de índices e retorne uma série pandas com esses dados. <br>


**Solução**

```python
import pandas as pd
def criar_serie(valores: list, indices: list) -> pd.Series:
	return pd.Series(valores, index=indices)
```

### 7. Substituição de Cores em DataFrame de Frutas <br>

Você é responsável pela gestão de uma frutaria que vende maçãs, bananas e uvas. A frutaria tem uma parceria com uma empresa de decoração de eventos que deseja encomendar algumas frutas para uma festa temática. A empresa de decoração solicitou especificamente que as bananas fossem douradas e que as maçãs tivessem uma tonalidade rosa. Porém, o seu sistema de registro das frutas só possui as cores tradicionais: vermelha para maçãs, amarela para bananas e roxa para uvas. <br>

Você precisa de uma solução para atualizar o registro das cores das frutas da frutaria de forma que o pedido da empresa de decoração possa ser atendido. <br>

Crei uma função "substitui_cores" que recebe como parâmetros o DataFrame com as informações das frutas, a coluna das cores que precisa ser atualizada, os valores antigos das cores (vermelha e amarela) e os novos valores que precisam ser substituídos (rosa e dourado). Com essa função, você poderá atender ao pedido da empresa de decoração sem precisar alterar manualmente todas as informações no sistema. <br>

**Solução**

```python
import pandas as pd
def substitui_cores(df: pd.DataFrame, coluna: str, dicionario_cores: dict) -> pd.DataFrame:
	df[coluna] = df[coluna].replace(dicionario_cores)
	return df
```

### 8. Substituição Condicional de Valores em um DataFrame <br>

Imagine que você é um cientista de dados responsável pela análise de dados de uma empresa que produz chocolates. Você recebeu um DataFrame que contém informações sobre o processo produtivo, incluindo a temperatura, o tempo de mistura e a qualidade dos ingredientes. <br>

Durante a análise, você percebeu que alguns registros apresentam um valor muito alto na coluna que representa a qualidade dos ingredientes, o que pode afetar a qualidade final do produto. Para resolver esse problema, você decidiu criar uma função que substitua todos os valores iguais ou maiores que um determinado limite por um valor pré-determinado, para garantir que a qualidade dos ingredientes esteja sempre dentro dos padrões de qualidade estabelecidos pela empresa. <br>

Assim, você cria uma função que recebe o DataFrame com os dados dos ingredientes, a coluna, o valor limite que deve ser verificado e o valor que deve ser substituído caso o valor seja maior ou igual ao limite. Essa função irá te ajudar a garantir que a qualidade dos ingredientes utilizados na produção dos chocolates seja sempre a melhor possível, resultando em um produto final de qualidade superior e satisfação dos clientes. <br>

**Solução** _(50%)_

```python
import pandas as pd
def substitui_valores(df: pd.DataFrame, coluna:str, limite: int, valor_padrao: int) -> pd.DataFrame:
	df[coluna] = df[coluna].where(df[coluna] > limite, valor_padrao)
	return df
```