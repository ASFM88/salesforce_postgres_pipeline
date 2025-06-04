# 🐘 Salesforce Postgres Pipeline

Este projeto tem como objetivo criar uma estrutura robusta para extração, transformação e carregamento de dados provenientes da API do Salesforce para um banco de dados PostgreSQL, utilizando Docker para orquestração do ambiente.

## 🔧 Tecnologias Utilizadas

- Python 3.11+
- PostgreSQL 14+
- Docker / Docker Compose
- Salesforce API (via `simple-salesforce`)
- pandas, duckdb, sqlalchemy, psycopg2

## 📌 Estrutura do Projeto

salesforce_postgres_pipeline/
├── docker/ # Infraestrutura Docker
│ ├── postgres/
│ │ └── init.sql # Scripts de inicialização do banco
│ └── docker-compose.yml # Orquestração dos containers
├── scripts/ # Scripts principais do pipeline
│ ├── raw_builder.py # ETL da camada RAW
│ ├── utils/
│ │ ├── conexao_postgres.py # Conexão com PostgreSQL
│ │ └── incremental_update.py # Lógica de atualização incremental
├── notebooks/ # Notebooks para exploração e testes
├── requirements.txt # Dependências Python
├── .env # Variáveis sensíveis (não versionado)
├── .gitignore
└── README.md


## 🚀 Funcionalidades

- Conexão com Salesforce via API
- Extração incremental baseada nos campos `Id` e `LastModifiedDate`
- Armazenamento das alterações em tabelas de histórico (`*_hist_update`)
- Persistência dos dados na camada RAW do PostgreSQL
- Versionamento da estrutura de dados e histórico de alterações

## 🐳 Como Executar

1. Clone o repositório:
```bash
git clone https://github.com/ASFM88/salesforce_postgres_pipeline.git
cd salesforce_postgres_pipeline
```

2. Configure o arquivo .env com as credenciais do Salesforce e PostgreSQL.

3. Suba os containers com Docker:
```bash
docker-compose up -d
```

4. Instale as dependências Python:
```bash
pip install -r requirements.txt
```

5. Execute o pipeline de extração:
```bash
python scripts/raw_builder.py
```

🔒 Segurança
O arquivo .env não deve ser versionado (já está no .gitignore)

Não armazene senhas diretamente nos scripts

🗺️ Próximos Passos
- Criação das camadas stage e trusted
- Otimização de performance para grandes volumes
- Integração com ferramentas de visualização (ex: Metabase, Superset)
- Monitoramento e logging

---
