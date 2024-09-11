## UFSCAR - Machine Learning in Production - EML4 - Atividade 2

Este repositório possui o intuito de conter os códigos da atividade 2 do componente de EML4, no qual possui o objetivo de por em prática o desenvolvimento de códigos em Python para processar grandes volumes de dados com o intuito de simular a divisão e gerenciamento do conjunto de dados, além de fazer as análises de dados necessárias. Sendo que, neste exercício deve-se realizar o pré-processamento de uma base de dados do Census do Estados Unidos (ou seja, https://www.kaggle.com/datasets/uciml/adult-census-income/data), logo após é necessário agrupar os dados e posteriormente usar os grupos formados para induzir um classificador. Não menos importante, o classificador deverá ser testado utilizando validação cruzada.

Desse modo, a seguir é possível observar alguas referências utilizadas para a execução desta atividade:

Tutorial de como utilizar o Jupyter Lab com Spark:
- https://github.com/whole-tale/all-spark-notebook
- https://github.com/jupyter/docker-stacks

Tutorial de Spark Pipelines:
- https://spark.apache.org/docs/latest/ml-pipeline.html

Tutorial de como utilizar o KMeans via Mlib:
- https://spark.apache.org/docs/latest/api/python/reference/api/pyspark.ml.clustering.KMeans.html

Tutorial de como utilizar o XGBoost Spark:
- https://xgboost.readthedocs.io/en/stable/tutorials/spark_estimator.html

Base de dados do Census do Estados Unidos de 1994:
- https://www.kaggle.com/datasets/uciml/adult-census-income/data
- https://archive.ics.uci.edu/dataset/20/census+income

Códigos de exemplo de como processar uma quantidade massiva de dados e construir pipelines de treinamento e teste de modelos de Machine Learning:
- https://github.com/thiagogcosta/mlp-eml4-codigos/tree/main/big_data/serving-batch/spark

### Estrutura do projeto

```
/mlp-eml4-atividade2/
    /jupyterlab_spark/
        Dockerfile
        adult-preprocessed.data
        jupyter_notebook_config.py
        train_test_ml_model_certo.ipynb
    docker-compose.yml
    Makefile
    .gitignore
    LICENSE
    README.md

```

### Passo-a-passo para interagir com o projeto

* Faça um clone deste repositório
* Execute o seguinte o comando: **make start**, assim serão buildadados e startados os containers:
    -  **jupyterlab_spark**: Instância do JupyterLab com o Spark configurado.
* Logo após os containers serem startados, por favor, vá até o seguinte endereço eletrônico: **http://localhost:8888/** e acesse o diretório chamado: **"work"**.
* Execute end to end o notebook: **train_test_ml_model_certo.ipnyb**. Inclusive, este notebook realiza as seguintes operações:
    - Inicia uma sessão Spark;
    - Carrega os dados do Census do Estados Unidos de 1994;
    - Realiza uma Análise de Dados;
    - Cria um pipeline Spark de preparação das features para a estratégia de clusterização;
    - Prepara os dados utilizando Pyspark para a estratégia de agrupamento; 
    - Treina e testa um modelo de Agrupamento (KMEANS);
    - Cria um pipeline Spark de preparação das features para a estratégia de classificação;
    - Prepara os dados utilizando Pyspark para a estratégia de classificação;  
    - Treina e testa um modelo de Agrupamento (XGBOOST);
    - Encerra-se a sessão Spark.
