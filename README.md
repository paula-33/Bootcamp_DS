# 🤖 Projeto Final do Bootcamp de Ciência de Dados e IA: Manutenção Preditiva Industrial

## 🏭 Contexto

Uma empresa do setor industrial buscou a criação de um sistema inteligente de manutenção preditiva para as suas máquinas. Utilizando dados coletados por dispositivos IoT, o sistema visa identificar falhas que possam ocorrer e, se possível, determinar o tipo específico da falha.

Cada amostra de dados é composta por 8 atributos que descrevem o comportamento de desgaste da máquina e as condições do ambiente. O objetivo final é, prever a classe do defeito e fornecer a probabilidade associada à previsão.

## 🎯 Objetivos

* 📊 Realizar uma análise exploratória completa para extrair insights da operação e dos tipos de defeito, gerando visualizações de dados.
* ⚙️ Tratar adequadamente os dados fornecidos, considerando possíveis erros e inconsistências.
* 🧠 Desenvolver, treinar e avaliar modelos de Machine Learning para prever a ocorrência de falhas (`falha_maquina`).
* 🤔 Modelar o problema para identificar os tipos específicos de falha (problema multirrótulo), conforme sugerido pela API de avaliação.
* 📝 Documentar todo o processo de desenvolvimento e organizar o código de forma clara e reprodutível.
* 🎤 Apresentar os resultados e as decisões tomadas de forma clara e objetiva.

## 📈 Descrição dos Dados

Os dados foram disponibilizados em dois arquivos: `Bootcamp_train.csv` para treino e `Bootcamp_test.csv` para previsão final. As colunas presentes no conjunto de dados são:

| Campo | Descrição |
| :--- | :--- |
| `id` | Identificador das amostras do banco |
| `id_produto` | Identificador único do produto. Combinação da variável Tipo e um número de identificação |
| `tipo` | Tipo de produto/máquina (L/M/H) |
| `temperatura_ar` | Temperatura do ar no ambiente (K) |
| `temperatura_processo`| Temperatura do processo (K) |
| `umidade_relativa` | Umidade relativa do ar (%) |
| `velocidade_rotacional`| Velocidade rotacional da máquina em rotações por minutos (RPM) |
| `torque` | Torque da máquina em Nm |
| `desgaste_da_ferramenta` | Duração do uso da ferramenta em minutos |
| `falha_maquina` | Indica se houve falha na máquina (1) ou não (0) |
| `FDF (Falha Desgaste Ferramenta)`| Indica se houve falha por desgaste da ferramenta (1) ou não (0) |
| `FDC (Falha Dissipacao Calor)` | Indica se houve falha por dissipação de calor (1) ou não (0) |
| `FP (Falha Potencia)` | Indica se houve falha por potência (1) ou não (0) |
| `FTE (Falha Tensao Excessiva)` | Indica se houve falha por tensão excessiva (1) ou não (0) |
| `FA (Falha Aleatoria)`| Indica se houve falha aleatória (1) ou não (0) |

*Fonte: Tabela de descrição dos dados*

## 👨‍💻 Metodologia e Desenvolvimento

O desenvolvimento do projeto foi dividido em três etapas principais, documentadas nos seguintes notebooks:

1.  **`01_ead.ipynb` - 🔍 Análise Exploratória de Dados:**
    * Análise inicial das variáveis, incluindo estatísticas descritivas, tipos de dados e valores ausentes.
    * Visualização da distribuição das variáveis numéricas e categóricas.
    * Análise de correlação entre as variáveis para identificar relacionamentos.
    * Investigação do balanceamento das classes de falha.

2.  **`02_Classificação_binaria.ipynb` - ✔️ Modelo de Classificação Binária:**
    * Foco na previsão da variável alvo `falha_maquina`.
    * Pré-processamento dos dados, incluindo normalização e codificação de variáveis categóricas.
    * Treinamento e avaliação de modelos de classificação (ex: Regressão Logística, Random Forest, etc.).
    * Seleção da melhor métrica de avaliação para o problema (ex: Acurácia, F1-Score, AUC).

3.  **`03_Multirrotulo.ipynb` - 🏷️ Modelo de Classificação Multirrótulo:**
    * Abordagem para prever os tipos específicos de falha (`FDF`, `FDC`, `FP`, `FTE`, `FA`).
    * Adaptação dos modelos para um cenário multirrótulo.
    * Avaliação do desempenho do modelo para cada tipo de falha individualmente.
    * Essa abordagem está alinhada com a API de avaliação, que considera o problema como multirrótulo.

## 📁 Estrutura do Projeto

```

.
├── data/              \# Dados brutos e processados
├── notebooks/         \# Jupyter notebooks com o desenvolvimento
│   ├── 01\_ead.ipynb
│   ├── 02\_Classificação\_binaria.ipynb
│   └── 03\_Multirrotulo.ipynb
├── src/               \# Código-fonte e scripts
└── README.md          \# Este arquivo

```

## 📋 Requisitos e Avaliação

* **Código:** O desenvolvimento deve ser feito em Python e disponibilizado em um repositório público no Github.
* **Apresentação:** Os resultados devem ser apresentados em um vídeo de no máximo 10 minutos, focando no processo de pensamento, planejamento e na clareza da comunicação.
* **Avaliação:** A avaliação considera a organização do código, a análise exploratória, a metodologia de modelagem e a clareza na apresentação e justificativa das decisões tomadas.

## ✨ Extras e Próximos Passos

Como diferenciais e próximos passos para este projeto, sugere-se:

* **API:** Disponibilizar o modelo treinado via uma RestAPI (ex: FastAPI).
* **Dashboard:** Desenvolver um dashboard interativo para visualização das previsões (ex: Streamlit).
* **Containerização:** Preparar a aplicação para ser executada com Docker.
```
