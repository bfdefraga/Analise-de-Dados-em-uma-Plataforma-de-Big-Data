# Analise de Dados em uma Plataforma de Big Data

Esse projeto visa a criação de uma arquitetura de pipeline de dados em que as mensagens geradas em um chatbot do Telegram são coletadas e processadas pela Plataforma AWS. O objetivo é demonstrar a importância e o funcionamento dessa estrutura de geração de dados para as empresas. Assim, informações são criadas em tempo real para embasar a tomada de decisão em dados pelos gestores da empresa.

Para isso, utilizou-se a linguagem Python com suas Bibliotecas e Pacotes como json, requests, getpass, boto3, os, logging, datetime e pyarrow. 

Na plataforma Telegram, criou-se um chat e um bot que armazenava e enviava as informações via API persistindo arquivos em formato json.

Por sua vez, na Plataforma AWS utilizou-se recursos como o AWS API Gateway, AWS S3, AWS Lambda, AWS IAM, AWS Event Bridge e AWS Athena, onde:
- AWS Gateway: automatizar o recebimento via webhook das mensagens pelo bot;
- AWS S3: local do datalake que consistia em buckets de arquivos brutos e processados;
- AWS LAMBDA: onde constava código Python para gerar dowload, data wrangling (processamento dos dados) com criação de tabelas de dados persistidas no formato Parquet;
- AWS IAM: por sua vez, permitia a escrita pela função do AWS Lambda de arquivos no datalake do AWS S3;
- AWS Event Bridge: ativava diariamente um função de ETL no AWS Lambda para fazer o processamento dos arquivos brutos e armazenamento dos arquivos processados no AWS S3;
- AWS Athena: por fim, consultas SQL eram realizadas e seus resultados eram persistidos em arquivos no formato .csv para posterior análise gráfica.

 Já na plataforma da Google Looker Studio, os arquivos do tipo .csv gerados via consultas SQL no AWS Athena eram adicionados para elaborar a visualização dos dados a fim de permitir a ilustração das informações pertinentes à tomada de decisão.

 
