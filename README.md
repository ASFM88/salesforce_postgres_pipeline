# Salesforce Postgre Integration

Projeto Python para integração e processamento de dados entre Salesforce e PostgreSQL.

## 📦 Estrutura do Projeto

```
salesforce_postgree/
├── src/
│   └── salesforce_postgree/
│       ├── __init__.py
│       └── main.py
├── tests/
│   └── test_main.py
├── pyproject.toml
├── poetry.lock
└── README.md
```

## 🚀 Funcionalidades

- Extração de dados do Salesforce (via API)
- Armazenamento ou sincronização em PostgreSQL
- Lógica de atualização incremental e versionamento
- Organização em pacotes com estrutura `src/`
- Testes automatizados com `pytest`

## 🛠️ Pré-requisitos

- Python 3.11+
- [Poetry](https://python-poetry.org/docs/#installation)
- Acesso à API do Salesforce
- Instância de banco de dados PostgreSQL

## ⚙️ Instalação

1. Clone o repositório:

```bash
git clone https://github.com/sua-conta/salesforce_postgree.git
cd salesforce_postgree
```

2. Instale as dependências com Poetry:

```bash
poetry install
```

3. (Opcional) Ative o ambiente virtual:

```bash
poetry shell
```

## ▶️ Como Executar

Execute o script principal:

```bash
poetry run python src/salesforce_postgree/main.py
```

## 🧪 Rodando os Testes

Execute todos os testes com:

```bash
poetry run pytest
```

## 📝 Variáveis de Ambiente

Você pode usar um arquivo `.env` para configurar as credenciais e strings de conexão:

```
SALESFORCE_USERNAME=...
SALESFORCE_PASSWORD=...
POSTGRES_URL=postgresql://user:password@host:port/database
```

## 🗂️ Organização do Código

| Pasta/Arquivo          | Descrição                                      |
|------------------------|-----------------------------------------------|
| `src/`                 | Código-fonte da aplicação                     |
| `src/salesforce_postgree/` | Módulo principal do projeto               |
| `tests/`               | Testes automatizados                          |
| `pyproject.toml`       | Gerenciador de dependências (Poetry)          |

## 📌 TODOs futuros

- [ ] Implementar atualização incremental com controle de histórico
- [ ] Adicionar log estruturado com timestamps
- [ ] Criar dashboard de acompanhamento com Streamlit ou Power BI

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.