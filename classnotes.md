# Survival Analysis

- Descobrir o tempo de evento ou duranção de um evento;
- Quanto tempo um cliente fica assinando um plano;
- "Banks can also estimate someone's credit risk default likelihood by how long they have been with a bank.";
- Survival Analysis is very common for subscription type business and very apt to study customer churn;
- Imagine a customer decides to cancel their subscription. How long do you wait until you try to get customer?
  - 1 day
  - 1 week
  - 1 month
- Curve: probability x time;
- Analisar o comportamento da curva, ver se tem um cotovelo;
- Saber quando o cliente vai esquecer do serviço;

# Case of study: Long Cancer

- Descobrir o tempo de sobrevivência de um paciente com Cancer;
- Usar a curva de kaplan-meier para estimar as probabilidades;
- Entender as diferenças entre homens e mulheres;
- Usar a curva de kaplan-meier para estimar as estatíticas;
- "Then we are going to perform the survival curves so that we are going to have a look at the Kaplin Meyer estimate."
- Para fazer isso, será feito:
  - Preparar o Dataset;
  - Criar a curva de sobrevivência;
  - Visualizar e interpretar os resultados;
  - Realizar os teste de Log Rank(se for necessário);


# Kaplan-Meier Estimator

- Estatíticas não-parametrica para estimar a função de sobrevivência(probabilidade de uma pessoa sobreviver) de dados de tempo de vida;
- Em pesquisas médicas, é frequentemente usada para medir a fração de pacientes vivos depois de 
um tempo específicos após o tratamento ou diagnóstico;
- Formula:
    $S(t_i) = S(t_{i-1}) * (1 - \frac{d_i}{n_i})$, onde:
  - $S(t_i)$ - probabilidade de sobreviver no tempo t;
  - $d_i$ - número de eventos no tempo t;
  - $n_i$ - número de sobreviventes no tempo t.

# Censoring

- Interval Censoring:
  - We only have data for a specific interval, so it is possivel that the event of interest does not occur during that time.

# Long Rank test

- Testar se duas distribuições são estatíticamente diferentes;
- hipótese nula, Ho:
    Não existe diferença entre as distribuições(grupos);
- hipótese alternativa Ha:
    Há diferenças entre as distribuições(grupo);
- Se o p-value>0.05 então Ho não deve ser rejeitada. Além disso, deve-se considerar um intervalo de confiança alto para o teste.

# Cox model prediction

- Supervised Learning model for data mining;
- Cox proporpotional hazard is essentially a regression model commonly used in statistic;
- used for medical research for survival time of patients;
- time to determine evento happens;
- Exaplanation
  - Survival Analysis does not allow other predictiors;
  - At best you can split in groups of gender, age, etc...and perform a Log-Rank test;
  - Thus, Cox proporpotional hazard regressions helps to determine the relationship between the survival time of a subject and one or more predictor variables. Então, regressão de Cox proporticional ajuda a determinar o relacionamento entre o tempo de sobrevivência de uma amostra e mais outras variáveis preditoras. Usa mais outras variáveis para tentar buscar mais fatores que influencia na função de sobrevivência;
- $exp(b_n)$ are called *Hazerd Ratio (HR)*:
Formula:
    $h(t) = h_o(t) * exp(b_1 * x_1 + b_n * x_n)$

Where:
- $h_o(t)$: baseline hazard;
- $bn$: impact coefficients;
- $xn$: covariates;

Results interpreatation:
- HR > 1: increase;
- HR < 1: decresase;
- HR = 1: neutral;

increase or decresase in the likelihood.
- Multivariate model analyser, remember this;

# CPH: Case of study

- lung cancer
  - Survival in patients with advanced lung cancer from the north central cancer treatment group. 
  1. Driver Analysis with cox proporpotional hazard
  2. Visualize Results

# CHAID

- Acronymm for Chi Square. Automatic Interaction Detection;
- We can do both driver analysis wihich by understanding what matters the most, and we can also do segmentation;
- It`s differente classic clustering technique because we have a dependent variable or an output, and clustering technique only have independent variable for use cases;

- Applications:
  - When you sell beer through newsletters or telemarketing or in-person sales, usally take time to prepare all to sell it;
  - Knowing your target audience is helpfull because you desing your sale in the best way possible;
- Description:
  - Importance ranking: CHAID figures out which drivers matter more, by doing significance tests;
  - Segmented Driver Analysis: CHAID will segment the population and perform driver analysis for each of them;
  - Interpretability: CHAID provides easy to read graphs with customer segments;
  - Divide samples in groups and get a weight for each ones;
- CHAID processes:
  - Looks at all predictors and tries to find the one where the `yes` is most diffenret from the `no`;
  - The statistical process it that trade goes through all of the drivers that we have and  tries to create this type
  of analysis, seeing where the note is most different from this;
- How does it work?
  - CHAID performs a chi-square test. It shows whether the frequencies of the categorical variables are different or not;
  - Very similar to t-test but it is a test of variance, and ideal for categorical variables;
- And then?
  - After if finds the first segment split, tries to find the next where the ''yes'' differs most from the ''no'';
- Last few things consider:
  - Test size: you can choose how many levels the tree will have;
  - Bucket size: you can choose a mininum threshold that you want your buckets to have;
  - Continuous variables: CHAID accepts ONLY categorical variables.