-----

# 📡 Telecom X – Análise Preditiva de Churn com Machine Learning

-----

## 📌 Sobre

Este repositório apresenta um projeto completo de **Machine Learning** focado em prever a **evasão de clientes (churn)** para a empresa fictícia Telecom X. Utilizando um pipeline robusto, o objetivo foi não apenas construir um modelo preditivo preciso, mas também extrair insights valiosos sobre os principais fatores que levam um cliente a cancelar seu serviço. O projeto transforma dados brutos em uma ferramenta estratégica que permite à empresa agir de forma proativa para reter seus clientes.

-----

## 🎯 Objetivos

  - Preparar os dados para modelagem, incluindo tratamento de variáveis categóricas e normalização.
  - Realizar uma análise de correlação para entender as relações entre as variáveis.
  - Construir, treinar e avaliar múltiplos modelos de classificação.
  - Lidar com o desafio de dados desbalanceados utilizando técnicas de reamostragem.
  - Avaliar a performance dos modelos com métricas apropriadas como Acurácia, Recall e a Matriz de Confusão.
  - Interpretar os resultados do modelo final para identificar os principais impulsionadores (drivers) do churn e gerar recomendações de negócio.

-----

## 📂 Fonte dos Dados

O projeto utiliza o arquivo `dados_tratados.csv`, que contém um conjunto de dados tratado de mais de 7.000 clientes. O arquivo está disponível neste repositório e inclui informações demográficas, detalhes dos serviços contratados e a variável alvo `evasao`.

-----

## ⚙️ Tecnologias e Bibliotecas Utilizadas

  - **Python 3.11**
  - **Jupyter Notebook**
  - **Pandas:** Para manipulação e análise de dados.
  - **Matplotlib & Seaborn:** Para visualizações estáticas e estatísticas.
  - **Plotly:** Para a criação de gráficos interativos e dinâmicos.
  - **Scikit-learn:** Ferramenta central para o projeto, utilizada para:
      - `Pipeline`: Criação de um fluxo de trabalho de pré-processamento e modelagem.
      - `train_test_split`: Divisão dos dados em treino e teste.
      - `StandardScaler`: Normalização das features.
      - `RandomForestClassifier` & `LogisticRegression`: Modelos de classificação utilizados.
      - `classification_report` & `confusion_matrix`: Métricas de avaliação.
  - **Imbalanced-learn:** Biblioteca utilizada para tratar o desbalanceamento de classes com a técnica `SMOTE`.

-----

## 🛠️ Metodologia do Projeto

O projeto foi estruturado em um fluxo de trabalho claro e robusto, desde a análise inicial até a interpretação dos resultados do modelo final.

### 1\. Análise Exploratória de Dados (EDA)

  - **Análise da Variável Alvo:** Verificação do desbalanceamento de classes na variável `evasao`, confirmando a necessidade de técnicas de reamostragem.
  - **Análise de Correlação:** Criação de um mapa de calor para visualizar a correlação entre as variáveis numéricas.
  - **Visualização de Padrões:** Uso de boxplots e histogramas para analisar como features chave (tipo de contrato, tempo de contrato, gastos mensais) se relacionam com a evasão.

### 2\. Construção do Pipeline de Modelagem

Para garantir a robustez e reprodutibilidade, um `Pipeline` do Scikit-learn foi construído para encapsular as etapas de pré-processamento e modelagem. O pipeline para o modelo final (Random Forest) foi composto por:

1.  **Balanceamento de Dados com `SMOTE`:** Aplicado apenas nos dados de treino para criar exemplos sintéticos da classe minoritária (clientes que evadiram), permitindo que o modelo aprendesse seus padrões de forma mais eficaz.
2.  **Normalização de Features com `StandardScaler`:** Padronização da escala das variáveis numéricas, um passo crucial para o bom desempenho de muitos algoritmos de Machine Learning.
3.  **Modelo de Classificação `RandomForestClassifier`:** O algoritmo de Random Forest foi escolhido como o classificador final devido à sua alta performance e capacidade de fornecer a importância das features.

### 3\. Treinamento e Avaliação

  - O pipeline foi treinado utilizando o conjunto de dados de treino (`X_train`, `y_train`).
  - As previsões foram feitas no conjunto de teste (`X_test`), que o modelo nunca havia visto antes.
  - O desempenho do modelo foi avaliado, alcançando uma **acurácia de aproximadamente 79%** no conjunto de teste. A análise da matriz de confusão e do `classification_report` permitiu uma visão detalhada da capacidade do modelo em identificar corretamente ambas as classes (churn e não-churn).

-----

## 💡 Resultados e Recomendações

### Principais Preditores de Churn

A análise de `feature importance` do modelo Random Forest revelou os fatores que mais influenciam um cliente a cancelar o serviço:

1.  **Tipo de Contrato Mensal (`tipo_contrato_Month-to-month`):** De longe, o fator mais impactante. A falta de um vínculo de longo prazo é o principal indicador de risco.
2.  **Tempo de Contrato (`tempo_contrato_meses`):** Clientes mais recentes são muito mais propensos a evadir. A lealdade aumenta com o tempo.
3.  **Gastos Mensais (`gastos_mensais`):** Faturas mensais mais altas estão associadas a um maior risco de churn.
4.  **Gastos Diários (`contas_diarias`):** Métrica derivada que reforça a importância do custo do serviço.
5.  **Tipo de Internet (`tipo_internet_Fibra óptica`):** Clientes com fibra óptica apresentaram maior propensão a cancelar, sugerindo possíveis problemas de qualidade, preço ou suporte neste serviço.

### Recomendações Estratégicas

  - **Ações de Retenção Focadas:** Criar campanhas de retenção direcionadas especificamente para clientes com **contrato mensal** e **poucos meses de serviço**, oferecendo upgrades ou descontos para migração para contratos anuais.
  - **Revisão da Oferta de Fibra Óptica:** Realizar uma análise aprofundada da satisfação dos clientes de fibra óptica para identificar e corrigir problemas de serviço, suporte ou percepção de valor.
  - **Gestão de Preços:** Para clientes de alto risco identificados pelo modelo, considerar ofertas personalizadas ou planos mais flexíveis para evitar o cancelamento por questões de preço.

-----

## 💾 Como Executar

1.  **Clone o repositório**:
    ```bash
    git clone https://github.com/seu-usuario/seu-repositorio.git
    cd seu-repositorio
    ```
2.  **Instale as dependências necessárias**:
    ```bash
    pip install pandas plotly matplotlib seaborn scikit-learn imbalanced-learn
    ```
3.  **Abra e execute** o Jupyter Notebook:
    ```bash
    jupyter notebook Challenge_TelecomX_final.ipynb
    ```

-----

## 📬 Contato

Para dúvidas, sugestões ou feedback, entre em contato: nickolasstreibel@gmail.com

-----

## 👨‍💻 Autor

| [<img src="https://avatars.githubusercontent.com/u/195215720?s=400&u=f536b6f2f37ec4af893cb10f0f872ee9588ff606&v=4" width=115><br><sub>Nickolas Streibel</sub>](https://github.com/Nickolas-Streibel) |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | 
| **Desenvolvedor** |


