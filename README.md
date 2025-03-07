📊 Projeto: Pipeline de Dados - Airflow, Snowflake e dbt

🔥 Sobre o Projeto

Este projeto implementa um pipeline completo de ingestão, transformação e análise de dados de vendas de veículos. A arquitetura utiliza Apache Airflow para orquestrar a carga incremental dos dados do PostgreSQL para o Snowflake, enquanto o dbt transforma os dados e cria modelos analíticos.

🏗️ Tecnologias Utilizadas

Apache Airflow → Orquestração e carga de dados

Snowflake → Data warehouse para armazenamento e análise

dbt (Data Build Tool) → Transformação e modelagem de dados

PostgreSQL → Banco de origem dos dados transacionais

Python & SQL → Desenvolvimento das ETLs e análises

📌 Estrutura do Pipeline

Extração → Airflow coleta os dados do PostgreSQL.

Carga incremental → Os dados são enviados para o Snowflake.

Transformação → dbt modela os dados em tabelas de dimensões e fatos.

Análises → Queries em SQL permitem insights de vendas, preços e desempenho comercial.

Testes → Validação de qualidade dos dados, como conferência de preços praticados vs. valores sugeridos.

📂 Estrutura dos Arquivos

📂 pipeline-dados/
 ├── dags/
 │   ├── dag.py                 # DAG do Airflow para carga incremental
 │
 ├── dbt/
 │   ├── models/
 │   │   ├── staging/           # Tabelas staging (stg_*)
 │   │   ├── dimensions/        # Tabelas dimensão (dim_*)
 │   │   ├── facts/             # Tabela fato (fct_vendas)
 │   │   ├── analysis/          # Consultas analíticas
 │   │   ├── tests/             # Testes de qualidade dos dados
 │
 ├── README.md                  # Documentação do projeto

🚀 Como Executar o Projeto

1️⃣ Configurar as conexões no Airflow

Criar as conexões postgres_conn_id e snowflake_conn_id.

Executar a DAG postgres_to_snowflake.

2️⃣ Rodar as Transformações no dbt

dbt run

3️⃣ Testar a Qualidade dos Dados

dbt test

📈 Análises Realizadas

✅ Vendas por veículo → Quais modelos mais venderam?✅ Desempenho de concessionárias → Quem teve maior faturamento?✅ Comparação de preços → Os vendedores estão respeitando o valor sugerido?✅ Performance por vendedor → Quais vendedores mais faturaram?

📌 Próximos Passos

Adicionar monitoramento com Great Expectations

Criar um dashboard no Power BI ou Streamlit

📢 Gostou do projeto? Contribua ou entre em contato! 🚀