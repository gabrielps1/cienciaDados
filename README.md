# 📊 Projeto — Mobilidade Urbana e Previsão de Velocidade  
**Curso:** Bacharelado em Ciência da Computação  
**Disciplina:** Ciência de Dados  
---

## 📘 1) Problema

A mobilidade urbana é um dos principais desafios das cidades inteligentes.  
Este projeto utiliza Ciência de Dados para **prever a velocidade média (speed)** do tráfego urbano considerando fatores como:

- horário,
- precipitação (chuva),
- temperatura,
- vento,
- volume de veículos,
- região da cidade.

**Pergunta-guia do estudo:**  
> *É possível prever a velocidade média do tráfego urbano com base em clima, horário e volume de veículos?*

**Objetivo principal:** desenvolver um modelo de Machine Learning capaz de prever a velocidade e gerar insights úteis para tomada de decisão.

---

## 📂 2) Dados

### **Fontes dos dados**
Foram utilizados dados abertos e/ou sintéticos baseados em estruturas reais de:
- Mobilidade urbana  
- Clima (chuva, temperatura, vento)  
- Volume de tráfego  

### **Arquitetura dos dados**

data/
raw/
mobilidade_raw.csv
clima_raw.csv
trafego_raw.csv
processed/
dataset_processado.csv



### **Dicionário de Dados (resumo)**

| Variável | Descrição |
|----------|-----------|
| timestamp | Data e hora do registro |
| hour | Hora do dia (0–23) |
| region | Região da cidade |
| speed | Velocidade média (km/h) |
| delay | Atraso médio |
| vehicle_volume | Volume de veículos no período |
| rain_mm | Chuva em milímetros |
| temperature | Temperatura (°C) |
| wind_speed | Velocidade do vento (km/h) |

### **Processamento**
O ETL fez:
- Padronização de datas  
- Combinação dos datasets  
- Remoção de duplicatas  
- Tratamento de nulos  
- Criação de features (ex.: hour, period_of_day)  

Resultado final salvo em `/data/processed/dataset_processado.csv`.

---

## 🧠 3) Método

### **ETL**
Notebook responsável: **01_etl.ipynb**

- Carregamento dos dados brutos  
- Limpeza e padronização  
- Merge entre clima × mobilidade × tráfego  
- Salvar dataset final processado  

---

### **EDA (Análise Exploratória)**
Notebook: **02_eda.ipynb**

Inclui:
- Distribuição das variáveis  
- Séries temporais de velocidade  
- Correlações  
- Comparação entre regiões  
- Efeito da chuva sobre velocidade  
- Identificação de padrões e outliers  

---

### **Modelagem**
Notebook: **03_modelagem.ipynb**

Modelos treinados:
- **Regressão Linear**
- **Random Forest Regressor**

Passos realizados:
- Train/test split  
- OneHot Encoding para variáveis categóricas  
- Avaliação com MAE, RMSE e R²  
- Gráficos real vs. previsto  
- Importância das features  

**Melhor modelo:** Random Forest  
(geralmente com MAE mais baixa e R² mais alto)

---

## 📈 4) Resultados

### **Principais insights:**
- A velocidade cai significativamente em horários de pico.  
- A chuva (rain_mm) reduz a velocidade média em todas as regiões.  
- O volume de veículos é a variável de maior importância no modelo.  


## 📊 5) Visualizações e Dashboard

Gráficos finais estão em:

reports/
figuras/


Incluindo:
- Distribuição de velocidade  
- Correlação das variáveis  
- Real vs previsto  
- Importância das features  


8) Licença e Referências

Dados sintéticos inspirados em datasets de mobilidade urbana.

Scikit-Learn (documentação)

IBGE / INMET para estrutura de dados reais

