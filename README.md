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

Instalação

# Clone o repositório
git clone https://github.com/seu-user/mercadolivre-etl.git

# Configure ambiente virtual
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows

# Instale dependências
pip install -r requirements.txt

# Configure variáveis de ambiente
cp .env.example .env


🕹️ Uso

# Execução completa do pipeline
python src/main.py --pages 5 --output-format csv+db

# Opções disponíveis
--pages        Número de páginas a processar (padrão: 5)
--output-format Formato de saída (csv, db, ou ambos)
--log-level    Nível de detalhamento dos logs (DEBUG, INFO, WARN)

🗃️ Banco de Dados

-- Exemplo de consulta analítica
SELECT 
  marca,
  ROUND(AVG(preco),2) AS preco_medio,
  COUNT(*) AS produtos
FROM produtos
WHERE avaliacao >= 4.0
GROUP BY marca
ORDER BY preco_medio DESC;


🧱 Estrutura do Projeto

mercadolivre-etl/
├── src/                  # Lógica principal
│   ├── extraction/       # Módulos de scraping
│   ├── transformation/   # Validação e limpeza
│   └── load/             # Carga em banco de dados
├── data/                 # Armazenamento local
│   ├── raw/              # Dados brutos (não versionado)
│   └── processed/        # Dados tratados (não versionado)
├── docs/                 # Documentação técnica
├── tests/                # Testes unitários
└── .github/              # Fluxos CI/CD
