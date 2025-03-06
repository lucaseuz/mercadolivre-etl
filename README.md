# 🚀 Mercado Livre ETL - Web Scraping e Pipeline de Dados

![Python](https://img.shields.io/badge/Python-3.12+-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.2+-orange?logo=pandas)
![SQLite](https://img.shields.io/badge/SQLite-3.45+-green?logo=sqlite)

Projeto de extração, transformação e carga (ETL) de dados de suplementos alimentares do Mercado Livre, com armazenamento em banco de dados relacional para análise.

[▶️ Demonstração Visual]() | [📚 Documentação Técnica](#estrutura-do-projeto)

## 🌟 Features
- **Web Scraping Avançado**: Extração de dados estruturados com tratamento dinâmico de elementos
- **Pipeline de Dados**: 
  - Validação de campos obrigatórios
  - Transformação de tipos de dados
  - Carga incremental em SQLite
- **Monitoramento**: Logs detalhados e tratamento de erros robusto
- **Dashboard**: Visualização integrada via DBeaver ([ver configuração](#-banco-de-dados))

## 🛠️ Tecnologias
![Tech Stack](https://skillicons.dev/icons?i=python,sqlite,git,github,pandas,vscode)

| Componente       | Tecnologias                                                                 |
|------------------|-----------------------------------------------------------------------------|
| Extração         | Requests, BeautifulSoup4, Rotação de User-Agents                           |
| Transformação    | Pandas, Regex, Data Validation                                             |
| Armazenamento    | SQLite (OLTP), Modelo estrela para futura integração com BI                 |
| Controle         | Git Flow, Conventional Commits, GitHub Actions (CI/CD)                     |

## ⚙️ Configuração

### Pré-requisitos
```bash
Python 3.12+
Git
DBeaver (Opcional para visualização)
