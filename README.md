# Segmentação de Espécies de Pinguins com K-means: Uma Abordagem de Clusterização em Dados Biológicos

## Visão Geral do Projeto

Este projeto explora a aplicação do algoritmo de *clustering* K-means para segmentar diferentes espécies de pinguins com base em suas características físicas. Diferente das aplicações mais comuns do K-means em marketing ou perfis de clientes, este trabalho demonstra a versatilidade do algoritmo em contextos biológicos.

A análise utiliza o conjunto de dados `penguins` do pacote `seaborn`, que contém informações detalhadas sobre três espécies de pinguins: Adelie, Chinstrap e Gentoo. As variáveis incluem medições físicas dos pinguins coletadas na Antártica.

## Estrutura do Conjunto de Dados

O dataset `penguins` inclui as seguintes variáveis:

* `species`: Espécie do pinguim (Adelie, Chinstrap, Gentoo)
* `island`: Ilha onde o pinguim foi observado (Biscoe, Dream, Torgersen)
* `bill_length_mm`: Comprimento do bico em milímetros
* `bill_depth_mm`: Profundidade do bico em milímetros
* `flipper_length_mm`: Comprimento da barbatana em milímetros
* `body_mass_g`: Massa corporal em gramas
* `sex`: Sexo do pinguim (Male, Female)
* `year`: Ano em que a observação foi feita

## Passos da Análise

O projeto segue os seguintes passos para a clusterização:

1.  ### Pré-processamento de Dados
    * Exclusão de colunas categóricas (`species`, `island`, `sex`).
    * Remoção de linhas com valores nulos (`NaN`) para garantir a integridade dos dados numéricos a serem processados.

2.  ### Análise Descritiva com Pairplot
    * Um `pairplot` do `seaborn` foi utilizado para visualizar as relações entre as variáveis numéricas remanescentes (`bill_length_mm`, `bill_depth_mm`, `flipper_length_mm`, `body_mass_g`).
    * Esta etapa permitiu identificar visualmente a presença de dois a três grupos distintos nos dados, principalmente nos gráficos de `bill_length_mm` versus `flipper_length_mm` e `bill_length_mm` versus `body_mass_g`.

3.  ### Padronização dos Dados
    * Para garantir que todas as características contribuam igualmente para o cálculo das distâncias no K-means, os dados foram padronizados utilizando `StandardScaler`. Isso transforma os dados para que tenham média zero e variância unitária.

4.  ### Aplicação do K-means
    * O algoritmo K-means foi aplicado aos dados padronizados.
    * Como a base de dados original contém 3 espécies de pinguins, o número de clusters (`n_clusters`) foi definido como 3. O `random_state` foi fixado em 42 para reprodutibilidade dos resultados.

5.  ### Análise dos Centroides e Visualização dos Clusters
    * Os centroides dos clusters foram extraídos e transformados de volta para a escala original dos dados, permitindo uma interpretação mais intuitiva das características médias de cada cluster.
    * Matrizes de dispersão foram construídas usando `plotly.express` para visualizar os clusters resultantes, colorindo os pontos de acordo com o cluster atribuído e marcando os centroides. Isso permite comparar os agrupamentos feitos pelo K-means com os padrões visuais observados no `pairplot` inicial.

## Requisitos e Como Rodar

Para executar este projeto, você precisará das seguintes bibliotecas Python:

* `pandas`
* `seaborn`
* `scikit-learn` (para `KMeans` e `StandardScaler`)
* `plotly.express`
* `plotly.graph_objects`

Você pode instalar as dependências usando pip:

```bash
pip install pandas seaborn scikit-learn plotly
