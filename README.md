# 🧹 CEAPS Data Wrangling — Limpeza e Tratamento de Dados do Senado Federal

Projeto de limpeza e tratamento de dados das despesas de senadores brasileiros (CEAPS — Cota para o Exercício da Atividade Parlamentar dos Senadores), cobrindo o período de **2019 a 2022**.

> **Parte do desafio [#7DaysOfCode](https://7daysofcode.io/) de Data Science — Dia 1/7**

---

## 📋 Sobre o Projeto

O CEAPS é o sistema de cotas parlamentares do Senado Federal que cobre despesas como passagens aéreas, hospedagem, alimentação, contratação de consultorias, entre outras. Este projeto foca na etapa fundamental de qualquer pipeline de dados: **a limpeza e preparação dos dados brutos para análise**.

### O que foi feito

- **Carregamento automatizado** de 4 datasets anuais (2019–2022), totalizando **69.356 registros**
- **Diagnóstico completo** de qualidade: valores nulos, duplicados, tipos incorretos
- **Conversão de tipos**: `VALOR_REEMBOLSADO` de texto (com vírgula) para float, `DATA` de string para datetime
- **Feature Engineering**: extração de DIA, MES_NOME, DIA_SEMANA e TRIMESTRE a partir da coluna DATA
- **Padronização de texto**: normalização de nomes de senadores e fornecedores (strip, upper, remoção de espaços duplos)
- **Tratamento de CNPJ/CPF**: limpeza, formatação e classificação automática (CPF vs CNPJ)
- **Tratamento de nulos**: preenchimento estratégico da coluna DETALHAMENTO (44% de valores ausentes)
- **Exportação** do dataset tratado para uso nos dias seguintes do desafio

### Principais descobertas durante a limpeza

| Métrica | Valor |
|---------|-------|
| Total de registros | 69.356 |
| Senadores únicos | 153 |
| Tipos de despesa | 7 |
| Fornecedores únicos | 8.740 |
| Total reembolsado (2019–2022) | R$ 98.006.806,17 |
| Maior despesa individual | R$ 120.000,00 |
| Mediana das despesas | R$ 426,69 |

---

## 🛠️ Tecnologias Utilizadas

- **Python 3.13**
- **pandas** — Manipulação e limpeza de dados
- **NumPy** — Operações numéricas
- **re** — Expressões regulares para tratamento de CNPJ/CPF

---

## 📁 Estrutura do Projeto

```
ceaps-data-wrangling/
├── data_wrangling_ceaps.ipynb   # Notebook com todo o pipeline de limpeza
├── README.md                     # Este arquivo
├── requirements.txt              # Dependências do projeto
└── .gitignore                    # Arquivos ignorados pelo Git
```

---

## 🚀 Como Executar

### 1. Clone o repositório
```bash
git clone https://github.com/Bernardinense/ceaps-data-wrangling.git
cd ceaps-data-wrangling
```

### 2. Instale as dependências
```bash
pip install -r requirements.txt
```

### 3. Baixe os dados
Os datasets originais estão disponíveis no portal de dados abertos do Senado Federal:

🔗 [Portal de Dados Abertos do Senado Federal — CEAPS](https://www12.senado.leg.br/transparencia/dados-abertos-transparencia/dados-abertos-ceaps)

Baixe os arquivos CSV dos anos **2019, 2020, 2021 e 2022** e coloque na raiz do projeto:
```
despesa_ceaps_2019.csv
despesa_ceaps_2020.csv
despesa_ceaps_2021.csv
despesa_ceaps_2022.csv
```

### 4. Execute o notebook
```bash
jupyter notebook data_wrangling_ceaps.ipynb
```

---

## 🔗 Parte do Desafio #7DaysOfCode

Este projeto é o **Dia 1** de um desafio de 7 dias cobrindo o pipeline completo de Data Science:

| Dia | Projeto | Tema |
|-----|---------|------|
| **1** | **ceaps-data-wrangling** | **Limpeza e Tratamento de Dados** |
| 2 | ceaps-storytelling | Visualização e Storytelling |
| 3 | ceaps-forecasting  | Previsão com Prophet |
| 4 | movie-recommendation-system | Sistema de Recomendação |
| 5 | movie-recommendation-api | API REST com FastAPI |
| 6 | ab-testing-hypothesis | Teste A/B e Validação de Hipóteses |

📌 Veja a jornada completa: [7DaysOfCode-DataScience](https://github.com/Bernardinense/7DaysOfCode-DataScience)

---

## 👤 Autor

**Bruno Corrêa** —  Engenheiro | Especialista em Ciência de Dados

[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/bfpc7/)
[![GitHub](https://img.shields.io/badge/GitHub-black?style=flat&logo=github)](https://github.com/Bernardinense)

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
