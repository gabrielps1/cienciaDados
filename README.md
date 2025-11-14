# 📊 Projeto — Mobilidade Urbana e Previsão de Velocidade  
**Curso:** Bacharelado em Ciência da Computação  
**Disciplina:** Ciência de Dados  
**Professora:** Profa. Dra. Flávia Aparecida Oliveira Santos  

---

## 📘 1) Problema

A mobilidade urbana é um dos principais desafios das cidades inteligentes.  
Este projeto utiliza Ciência de Dados para **prever a velocidade média (speed)** do tráfego urbano considerando fatores como:

- horário  
- precipitação (chuva)  
- temperatura  
- vento  
- volume de veículos  
- região da cidade  

**Pergunta-guia:**  
> É possível prever a velocidade média do tráfego urbano com base em clima, horário e volume de veículos?

**Objetivo:** desenvolver um modelo de Machine Learning capaz de prever a velocidade e gerar insights úteis para tomada de decisão nas cidades.

---

## 📂 2) Dados

### **Fontes**
Foram utilizados dados abertos e/ou sintéticos inspirados em estruturas reais de:

- Mobilidade urbana  
- Clima (chuva, temperatura, vento)  
- Tráfego (volume de veículos)  

---

### **Arquitetura dos Dados**

data/
raw/
mobilidade_raw.csv
clima_raw.csv
trafego_raw.csv

processed/
dataset_processado.csv

yaml
Copiar código

---

### **Dicionário de Dados (resumo)**

| Variável        | Descrição                               |
|-----------------|-------------------------------------------|
| timestamp       | Data e hora do registro                   |
| hour            | Hora do dia (0–23)                        |
| region          | Região da cidade                          |
| speed           | Velocidade média (km/h)                   |
| delay           | Atraso médio                              |
| vehicle_volume  | Volume de veículos no período             |
| rain_mm         | Chuva em milímetros                       |
| temperature     | Temperatura (°C)                          |
| wind_speed      | Velocidade do vento (km/h)                |

---

### **Processamento (ETL)**

O processo de ETL realizou:

- Padronização de datas  
- Combinação dos datasets  
- Remoção de duplicatas  
- Tratamento de valores nulos  
- Criação de features (ex.: `hour`, `period_of_day`)  

O dataset final foi salvo em:

/data/processed/dataset_processado.csv

yaml
Copiar código

---

## 🧠 3) Método

### **ETL — Notebook 01_etl.ipynb**
- Carregamento dos dados brutos  
- Limpeza e padronização  
- Merge entre clima × mobilidade × tráfego  
- Geração do dataset final processado  

---

### **EDA (Análise Exploratória) — Notebook 02_eda.ipynb**
Foram realizadas análises como:

- Distribuição das variáveis  
- Séries temporais de velocidade  
- Comparações entre regiões  
- Heatmap de correlação  
- Efeito da chuva sobre velocidade  
- Identificação de padrões, outliers e tendências  

As figuras geradas estão em:

reports/figuras/

yaml
Copiar código

---

### **Modelagem — Notebook 03_modelagem.ipynb**
Modelos treinados:

- Regressão Linear  
- Random Forest Regressor  

Passos realizados:

- Separação treino/teste  
- Pré-processamento (OneHotEncoder)  
- Treinamento e validação  
- Avaliação — MAE, RMSE e R²  
- Gráfico de valores reais vs previstos  
- Importância das features  

**Melhor modelo:**  
👉 *Random Forest Regressor* (maior R² e menor erro)

---

## 📈 4) Resultados (Principais Insights)

- A velocidade cai significativamente em horários de pico.  
- A chuva reduz a velocidade média em todas as regiões.  
- O volume de veículos é a variável de maior importância na previsão.  
- Regiões diferentes apresentam comportamentos distintos ao longo do dia.  

---

## 📊 5) Visualizações e Dashboard

As visualizações da EDA e Modelagem estão disponíveis em:

reports/figuras/

yaml
Copiar código

Incluindo:

- Distribuição da velocidade  
- Boxplot por região  
- Mapa de correlação  
- Série temporal  
- Volume de veículos vs velocidade  
- Real vs previsto (Random Forest)  
- Importância das features  

---

## 🧪 6) Como Executar o Projeto

### **1. Clonar o repositório**
```bash
git clone https://github.com/gabrielps1/cienciaDados
2. Instalar dependências
bash
Copiar código
pip install -r requirements.txt
3. Executar os notebooks na pasta /notebooks
01_etl.ipynb

02_eda.ipynb

03_modelagem.ipynb

📚 7) Referências
Dados sintéticos inspirados em estruturas de datasets reais de mobilidade urbana

Biblioteca Scikit-Learn

INMET (Instituto Nacional de Meteorologia)

IBGE (Instituto Brasileiro de Geografia e Estatística)
