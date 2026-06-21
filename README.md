
![SQL](https://img.shields.io/badge/SQL-Server-blue)
![PowerBI](https://img.shields.io/badge/PowerBI-Dashboard-yellow)
![Python](https://img.shields.io/badge/Python-DataAnalysis-green)
[![github portfolio-analista-dados](https://img.shields.io/badge/Language-Python|R-orange.svg)](https://github.com/joaoanalistadados/portfolio-analista-dados) 
---
<img width="736" height="224" alt="LogoMarca_InforBusiness5 " src="https://github.com/user-attachments/assets/c2cd63b0-46cc-47c0-a114-627ce4b1c22d" />

# 🚀 Portfólio — João Cruz

# Visite o nosso site do <h1> [<img width="202" height="57" alt="logoJulia1" src="https://github.com/user-attachments/assets/c5689532-0327-4894-95e9-167d7629b8fb" />](https://victoriavirtual.com.br/lojavirtual/) 

##  📁 Analista de Dados | 🛢️ SQL | 📊 Power BI | 🐍 Python | 📈 Excel

Profissional com experiência em:
- Análise de Dados
- SQL Server
- Power BI
- ETL
- Modelagem de Dados
- Dashboards Gerenciais
- Integração de Sistemas
- Automação de Processos
- Robos
  
---

# 📊 Projetos em Destaque

---
## 📈 Dashboard SAC - Serviço de Apoio ao Cliente

### Indicadores:
- Total Atendimentos
- Tempo Médio
- Atendimento Médio
- Media Diária Chamados
- % Cancelados
- Total Atedimentos por Ano e Mês
- Total Atedimentos por Problema
- Tempo Médio Atendimento por Ano e Mês
- Total Atedimentos por Nome Atendente
### Tecnologias:
- Power BI
- DAX
- SQL Server

<img width="688" height="384" alt="dashboard-sac" src="https://github.com/user-attachments/assets/0803a029-f3d7-4d5f-90d9-16bcd657db31" />

---

## 📈 Dashboard Comercial

### Indicadores:
- Receita
- Produtos Vendidos
- Quantidade Clentes
- Faturamento Total por Ano e Mês
- Soma de Qtd. Vendida por Genero
- Soma de faturamento por Continente
- Faturamento Total por Marcar

### Tecnologias:
- Power BI
- DAX
- SQL Server

<img width="844" height="466" alt="dashboard-comercial" src="https://github.com/user-attachments/assets/e4509c01-31d4-4436-9b3c-bdf9aad560af" />

---

## 💰 Dashboard Financeiro

### Indicadores:
- Receitas
- Custos
- Despesas
- Lucro Líquido
- KPIs Financeiros
- Fluxo de Caixa

### Tecnologias:
- Power BI
- Excel
- SQL

Geral

<img width="849" height="446" alt="Dashboard-Financeiro-Geral" src="https://github.com/user-attachments/assets/0019cd8d-ff9c-4617-adff-edc963e74261" />

Fluxo de Caixa

<img width="816" height="449" alt="Dashboard-Financeiro-Fluxo-Caixa" src="https://github.com/user-attachments/assets/9e8ac23a-e73f-41c7-a80f-ebf6fb5a4299" />



---

## 👥 Dashboard RH Analytics

### Indicadores:
- Turnover
- Absenteísmo
- Headcount
- Desempenho
- Custos por Colaborador

### Tecnologias:
- Power BI
- Excel
- SQL Server

Colaboradores

<img width="845" height="462" alt="dashboard-rh-colaboradores" src="https://github.com/user-attachments/assets/9679df81-8f08-4232-8404-4c70b3b02169" />

Bem Estar

<img width="846" height="467" alt="dashboard-rh-bemestar" src="https://github.com/user-attachments/assets/c9e8cf4e-01bf-4705-9c98-a8a4bbfa077a" />

Financeiro

<img width="852" height="463" alt="dashboard-rh-financeiro" src="https://github.com/user-attachments/assets/8b850d15-41c7-4c28-891f-2644ce9ef8cc" />


---

# 🛠️ Tecnologias Utilizadas

| Tecnologia | Nível |
|---|---|
| SQL Server | Avançado |
| SSIS - SQL Server Integration Services| Avançado |
| Power BI | Avançado |
| Excel | Avançado |
| Python | Intermediário |
| DAX | Avançado |
| ETL | Avançado |
| SSIS - SQL Server Integration Services| Avançado |

---

# 📂 Estrutura do Projeto

```txt
dashboards/
sql/
python/
datasets/
excel/
docs/
```

---

# 🧠 Principais Competências

- Modelagem de Dados
- Criação de KPIs
- ETL
- Integração de Sistemas
- Dashboards Executivos
- Análise Financeira
- Automação de Relatórios
- Desenvolvimento e Analise de Sistemas (Delphi, C#, AspNet, PHP, Html, Python, Node)
  
---

# 🗄️ Banco de Dados SQL Server

Tabela Clientes
---

CREATE TABLE Clientes (
    IdCliente INT PRIMARY KEY,
    Nome VARCHAR(100),
    Cidade VARCHAR(50),
    Estado VARCHAR(2)
);



Tabela Produtos

---

CREATE TABLE Produtos (
    IdProduto INT PRIMARY KEY,
    Produto VARCHAR(100),
    Categoria VARCHAR(50),
    Preco DECIMAL(10,2)
);


Tabela Vendas

---

CREATE TABLE Vendas (
    IdVenda INT PRIMARY KEY,
    DataVenda DATE,
    IdCliente INT,
    IdProduto INT,
    Quantidade INT,
    ValorTotal DECIMAL(10,2)
);

---

# 📈 Consultas SQL

Total de Vendas

SELECT
    SUM(ValorTotal) AS ReceitaTotal
FROM Vendas;
Top 10 Produtos
SELECT TOP 10
    p.Produto,
    SUM(v.ValorTotal) Receita
FROM Vendas v
INNER JOIN Produtos p
ON v.IdProduto = p.IdProduto
GROUP BY p.Produto
ORDER BY Receita DESC;
Receita por Estado
SELECT
    c.Estado,
    SUM(v.ValorTotal) Receita
FROM Vendas v
INNER JOIN Clientes c
ON v.IdCliente = c.IdCliente
GROUP BY c.Estado
ORDER BY Receita DESC;
Evolução Mensal
SELECT
    YEAR(DataVenda) Ano,
    MONTH(DataVenda) Mes,
    SUM(ValorTotal) Receita
FROM Vendas
GROUP BY
    YEAR(DataVenda),
    MONTH(DataVenda)
ORDER BY Ano, Mes;

---

# 🧠 Medidas DAX

💰 Receita Total

Receita Total = SUM(F_Vendas[Valor])

---

📦 Total de Vendas

Total Vendas = COUNTROWS(F_Vendas)

---

👥 Total de Clientes

Total Clientes = DISTINCTCOUNT(F_Vendas[ID_Cliente])

----
📈 Ticket Médio

Ticket Médio = DIVIDE([Receita Total], [Total Vendas])

---

📊 Receita por Mês

Receita Mês = 
CALCULATE(
    [Receita Total],
    ALLEXCEPT(D_Calendario, D_Calendario[Ano], D_Calendario[Mês])
)

---

📉 Crescimento (%)

Crescimento % = 
VAR Atual = [Receita Total]
VAR Anterior =
    CALCULATE(
        [Receita Total],
        DATEADD(D_Calendario[Data], -1, MONTH)
    )
RETURN
DIVIDE(Atual - Anterior, Anterior)

---
🏆 Top Produto

Ranking Produto = 
RANKX(
    ALL(D_Produtos[Produto]),
    [Receita Total],
    ,
    DESC
)

---

# 📄 **Currículo**

* [Curriculo](https://github.com/joaoanalistadados/portfolio-analista-dados/blob/main/AnalistaDadios_%20Jo%C3%A3o%20Cruz.pdf)

---

# 📬 Contato

- LinkedIn: https://www.linkedin.com/in/joão-cruz-79837722/
- GitHub: https://github.com](https://github.com/joaoanalistadados)
- E-mail: joao.cruz@victoriavirtual.com.br

---

# ⭐ Objetivo

Demonstrar habilidades técnicas em análise de dados, BI e analista e desenvolvimento de soluções corporativas.
