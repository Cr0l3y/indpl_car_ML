***EN***

Project: Analysis of Marketing Investment Data

This project aims to analyze a marketing database and build classification models that identify customer adherence to investments.

Project Structure

   1. Initial Data Cleaning and Analysis

- No null values ​​were found in the database.

- Some inconsistencies were observed in the categorical variables, such as the use of numbers to represent gender or variation between upper and lower case letters.

- The target variable (adherence to investment) is categorical, which characterizes a classification problem.

- Verification of extreme values ​​in variables such as age (19 to 87 years old, no invalid values) and balance (negative values ​​make sense for debt).

    2. Exploratory Analysis

- Use of graphs (plotly) to analyze the variables.

- Verification of the distribution of categories with histogram and coloring by target variable.

- Use of boxplots to identify possible outliers.

    3. Treatment of Categorical Variables

- Separation of the target variable investment_adherence from the explanatory variables.

- Transformation of categorical variables with One-Hot Encoding.

- For binary variables such as default and made_loan, the drop='if_binary' parameter was used to avoid duplication.

- Storage of the encoder pattern for future data.

- Storage of the names of the new categorical columns after encoding.

- The target variable was transformed with LabelEncoder (1 for "yes" and 0 for "no").

    4. Modeling

- Splitting the data into training and testing with train_test_split.

- Use of the DummyClassifier model as baseline (accuracy of ~60%).

- Application of the Decision Tree model:

- Initial result: 100% (overfitting).

- With max_depth=3: accuracy of 71.6%.

- KNN model (with MinMaxScaler for normalization): accuracy of 68%.

- Saving models with pickle (modelo_onehotenc, modelo_arvore.pkl).

    5. Model Evaluation

- The model was unable to correctly identify defaulting customers: only 43 correct positives against 959 false negatives.

- The confusion matrix showed that accuracy is not the most appropriate metric in this case.

- The Random Forest model performed even worse.

    6. Metrics Used

- Precision: proportion of data classified as positive that are actually positive.

- Recall: proportion of correctly classified positives. The most important metric for the project, as it aims to avoid losses.

- AUC (Area Under the ROC Curve): evaluates the overall performance of the model (the closer to 1, the better; close to 0.5 is random).

- Accuracy of 0.91, but recall for defaulters was only 0.04.

- Analysis of macro and weighted averages for a fairer assessment between classes.

    7. Cross-Validation and Confidence Interval

- Cross-validation to avoid bias caused by unbalanced training/testing splits.

- Use of test_score as an accuracy metric.

- Implementation of the interval_conf() function to calculate the mean and standard deviation of recall and extract confidence interval.

- Cross-validation with recall revealed low values ​​(0.01 to 0.03), but more reliable.

- Use of StratifiedKFold to maintain the proportion of classes in the splits.

- Recall confidence interval showed greater consistency with stratification.

The project explores the main stages of a supervised machine learning pipeline for classification, including preprocessing, modeling, evaluation, and validation. The careful selection of metrics allowed us to better understand the actual performance of the model, going beyond simple accuracy.



---
***PT-BR***

# Projeto

Projeto: Análise de Dados de Investimentos em Marketing

Este projeto tem como objetivo analisar uma base de dados de marketing e construir modelos de classificação que identifiquem a adesão de clientes a investimentos.

Estrutura do Projeto

   1. Limpeza e Análise Inicial dos Dados

- Nenhum valor nulo foi encontrado na base de dados.

- Algumas inconsistências foram observadas nas variáveis categóricas, como uso de números para representar sexo ou variação entre letras maiúsculas e minúsculas.

- A variável alvo (aderência ao investimento) é categórica, o que caracteriza um problema de classificação.

- Verificação de valores extremos em variáveis como idade (19 a 87 anos, sem valores inválidos) e saldo (valores negativos fazem sentido para endividamento).

    2. Análise Exploratória

- Utilização de gráficos (plotly) para análise das variáveis.
- Verificação da distribuição das categorias com histograma e coloração por variável alvo.

- Utilização de boxplots para identificar possíveis outliers.

    3. Tratamento das Variáveis Categóricas

- Separação da variável alvo aderencia_investimento das variáveis explicativas.

- Transformação das variáveis categóricas com One-Hot Encoding.

- Para variáveis binárias como inadimplencia e fez_emprestimo, foi usado o parâmetro drop='if_binary' para evitar duplicidade.

- Armazenamento do padrão do encoder para futuros dados.

- Armazenamento dos nomes das novas colunas categóricas após codificação.

- A variável alvo foi transformada com LabelEncoder (1 para "sim" e 0 para "não").


    4. Modelagem


- Divisão dos dados em treino e teste com train_test_split.

- Utilização do modelo DummyClassifier como baseline (acurácia de ~60%).

- Aplicação do modelo de Árvore de Decisão:

- Resultado inicial: 100% (overfitting).

- Com max_depth=3: acurácia de 71,6%.

- Modelo KNN (com MinMaxScaler para normalização): acurácia de 68%.

- Salvamento dos modelos com pickle (modelo_onehotenc, modelo_arvore.pkl).


    5. Avaliação dos Modelos

- O modelo não conseguiu identificar corretamente clientes inadimplentes: apenas 43 positivos corretos contra 959 falsos negativos.

- A matriz de confusão mostrou que a acurácia não é a métrica mais adequada neste caso.

- O modelo Random Forest teve desempenho ainda pior.

    6. Métricas Utilizadas

- Precisão (Precision): proporção de dados classificados como positivos que realmente são positivos.

- Recall: proporção de positivos corretamente classificados. Métrica mais importante para o projeto, pois visa evitar prejuízos.

- AUC (Área Sob a Curva ROC): avalia a performance geral do modelo (quanto mais próximo de 1, melhor; próximo de 0.5 é aleatório).

- Acurácia de 0.91, mas recall para inadimplentes foi apenas 0.04.

- Análise de médias macro e weighted para avaliação mais justa entre classes.

    7. Validação Cruzada e Intervalo de Confiança

- Validação cruzada para evitar viés causado por divisões de treino/teste desequilibradas.

- Uso de test_score como métrica de acurácia.

- Implementação da função intervalo_conf() para calcular a média e desvio padrão do recall e extrair intervalo de confiança.

- Validação cruzada com recall revelou valores baixos (0.01 a 0.03), mas mais confiáveis.

- Uso de StratifiedKFold para manter a proporção das classes nas divisões.

- Intervalo de confiança do recall mostrou maior consistência com estratificação.



Com isso, o projeto explora as principais etapas de um pipeline de machine learning supervisionado para classificação, incluindo pré-processamento, modelagem, avaliação e validação. A escolha criteriosa das métricas permitiu entender melhor o desempenho real do modelo, indo além da simples acurácia.










































