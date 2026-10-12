# Data Warehouse & Data Marts with DuckDB

Projeto de Engenharia de Dados para praticar SQL, ETL e modelagem dimensional, transformando arquivos CSV em um Data Warehouse e Data Marts para análise de vagas de emprego.

## Tecnologias
- DuckDB
- SQL
- Google Cloud Storage
- Git e GitHub

## Projeto

O projeto consiste em construir um pipeline ETL que extrai dados de arquivos CSV, organiza as informações em um Data Warehouse e cria Data Marts para facilitar consultas analíticas.

### Data Warehouse
Implementação de um modelo estrela (*Star Schema*), com tabelas de fatos, dimensões e relacionamentos entre vagas, empresas e habilidades.

### Data Marts
- **Flat Mart:** reúne informações das vagas em uma tabela desnormalizada.
- **Skills Mart:** permite analisar a demanda por habilidades ao longo do tempo.
- **Priority Mart:** organiza vagas prioritárias e utiliza `MERGE INTO` para atualizações incrementais.
- **Company Mart:** análise de tendências de contratação por empresa, cargo e localização (opcional).

## Principais conceitos praticados
- Criação e manipulação de tabelas com SQL.
- Extração e carga de dados do Google Cloud Storage.
- Modelagem dimensional e *Star Schema*.
- Transformação e limpeza de dados.
- Uso de `JOIN`, CTEs e funções de data.
- `INSERT INTO ... SELECT` e `MERGE INTO`.
- Organização e execução de scripts SQL.

## Estrutura do projeto

```text
2_DW_Mart_Build/
├── 01_create_tables_dw.sql
├── 02_load_schema_dw.sql
├── 03_create_flat_mart.sql
├── 04_create_skills_mart.sql
├── 05_create_priority_mart.sql
├── 06_update_priority_mart.sql
├── 07_create_company_mart.sql
├── build_dw_marts.sql
└── README.md
```

## Execução

Com o DuckDB instalado e o acesso aos dados de origem configurado, execute o script principal:

```bash
duckdb dw_marts.duckdb -c ".read build_dw_marts.sql"
```

Para executar no MotherDuck, após configurar a autenticação e criar a database:

```bash
duckdb md:dw_marts -c ".read build_dw_marts.sql"
```

## Objetivo

Projeto desenvolvido como parte dos meus estudos em Engenharia de Dados, com foco em SQL, pipelines ETL, modelagem dimensional e análise de dados.
