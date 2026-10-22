# 💰 Personal Finance API

Uma API RESTful desenvolvida em **Python** utilizando **FastAPI** e **PostgreSQL** para gerenciamento de finanças pessoais, controle de despesas/receitas e geração de relatórios analíticos com agregação via SQL.

---

## 📌 Conteúdo
- [Sobre o Projeto](#-sobre-o-projeto)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Modelo de Dados (DER)](#-modelo-de-dados-der)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Como Executar o Projeto](#-como-executar-o-projeto)
  - [Pré-requisitos](#pré-requisitos)
  - [Passo a Passo](#passo-a-passo)
- [Endpoints da API](#-endpoints-da-api)

---

## 🚀 Sobre o Projeto

A **Personal Finance API** foi desenvolvida para ajudar usuários a gerenciarem suas finanças pessoais de forma segura e simples. O sistema permite cadastrar contas bancárias, categorias personalizadas e lançar transações de receitas e despesas.

### ✨ Diferenciais Técnicos:
- **Agregações em SQL:** Consultas SQL otimizadas (`GROUP BY`, `SUM`, `JOIN`) executadas diretamente no PostgreSQL para geração de relatórios financeiros rápidos.
- **Isolamento de Dados:** Cada usuário possui controle total sobre suas próprias contas, categorias e transações.
- **Ambiente Containerizado:** Instalação e execução facilitadas através do Docker e Docker Compose.

---

## 🛠️ Tecnologias Utilizadas

- **Linguagem:** Python 3.10+
- **Framework:** FastAPI
- **Banco de Dados:** PostgreSQL
- **ORM:** SQLAlchemy
- **Validação de Dados:** Pydantic
- **Migrações:** Alembic
- **Containerização:** Docker & Docker Compose

---

## 📊 Modelo de Dados (DER)

O diagrama abaixo representa a estrutura de entidades e relacionamentos do banco de dados relacional.

![Diagrama de Entidade-Relacionamento](/assets//Screenshot_2026-10-22_17-13-15.png)
---

## 📂 Estrutura do Projeto

```text
personal-finance-api/
├── app/
│   ├── core/             # Configurações globais e banco de dados
│   │   ├── config.py
│   │   └── database.py
│   ├── models/           # Mapeamento do banco de dados (SQLAlchemy)
│   │   └── models.py
│   ├── schemas/          # Schemas para validação de dados (Pydantic)
│   │   └── schemas.py
│   ├── routers/          # Rotas da API
│   │   ├── auth.py
│   │   ├── accounts.py
│   │   ├── categories.py
│   │   ├── transactions.py
│   │   └── reports.py
│   └── main.py           # Ponto de entrada da aplicação
├── .env.example          # Modelo de variáveis de ambiente
├── docker-compose.yml    # Configuração dos contêineres Docker
├── Dockerfile
├── requirements.txt      # Dependências do projeto
└── README.md
```

---

## ⚙️ Como Executar o Projeto

### Pré-requisitos
- [Git](https://git-scm.com)
- [Python 3.10+](https://www.python.org/)
- [Docker](https://www.docker.com/) e [Docker Compose](https://docs.docker.com/compose/)

### Passo a Passo

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/SEU_USUARIO/personal-finance-api.git
   cd personal-finance-api
   ```

2. **Configure as Variáveis de Ambiente:**
   Crie um arquivo `.env` baseado no `.env.example`:
   ```bash
   cp .env.example .env
   ```

3. **Inicie o Banco de Dados com Docker:**
   ```bash
   docker compose up -d
   ```

4. **Crie e ative o ambiente virtual Python:**
   ```bash
   python -m venv venv

   # Linux / macOS:
   source venv/bin/activate

   # Windows (PowerShell / Git Bash):
   source venv/Scripts/activate
   ```

5. **Instale as dependências:**
   ```bash
   pip install -r requirements.txt
   ```

6. **Execute a aplicação:**
   ```bash
   uvicorn app.main:app --reload
   ```

A API estará rodando em: `http://127.0.2.1:8000`

---

## 📖 Endpoints da API

Você pode acessar a documentação interativa e testar todas as rotas diretamente pelo navegador em:
- **Swagger UI:** `http://127.0.0.1:8000/docs`
- **ReDoc:** `http://127.0.0.1:8000/redoc`

### Principais Funcionalidades:
- **`/auth`**: Cadastro e login de usuários.
- **`/accounts`**: Gestão de contas bancárias (criar, listar, atualizar, deletar).
- **`/categories`**: Gestão de categorias de receitas e despesas.
- **`/transactions`**: Lançamentos e histórico financeiro.
- **`/reports`**: Relatórios agregados (gastos por categoria, balanço mensal e saldo total).

---

Feito por [Seu Nome](https://github.com/SEU_USUARIO) 👋