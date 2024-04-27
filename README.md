# Regressão com Abalone
O modelo de regressão foi desenvolvido como parte de uma competição do Kaggle (https://www.kaggle.com/competitions/playground-series-s4e4) com o objetivo desta competição é prever a idade do abalone a partir de várias medidas físicas. A métrica de avaliação para esta competição é o Erro Logarítmico Quadrático Médio.

# Estrutura do Projeto
Este projeto é organizado da seguinte forma:

__input:__ Pasta contendo os dados de entrada.

__src:__ Pasta contendo o código-fonte do projeto.

__model:__ Pasta contendo o modelo final salvo em arquivo pickle.

## Dados

**Sexo:** Esta característica representa o gênero do abalone, categorizado como masculino (M), feminino (F) ou infantil (I).

**Comprimento:** A característica de comprimento denota a medida mais longa da concha do abalone, do ápice à base, medida em milímetros.

**Diâmetro:** O diâmetro representa a medida da concha do abalone perpendicular ao seu comprimento, também medida em milímetros.

**Altura:** Esta característica significa a altura da concha do abalone, medida perpendicularmente ao plano formado pelo comprimento e diâmetro, em milímetros.

**Peso total:** O peso total indica o peso total do abalone, abrangendo tanto a carne quanto a concha, medido em gramas.

**Peso total (Peso sem casca):** Esta característica representa o peso apenas da carne do abalone, medida em gramas. Indica a quantidade de carne extraída da concha.

**Peso total (Peso das vísceras):**  O peso das vísceras significa o peso do intestino do abalone após o sangramento, medido em gramas. Fornece insights sobre o peso dos órgãos internos do abalone.

**Peso da concha:** Esta característica representa o peso apenas da concha do abalone, excluindo a carne, medido em gramas. Fornece insights sobre a distribuição de peso entre a concha e a parte comestível do abalone.

**Anéis:** Os anéis significam o número de anéis presentes na concha do abalone, servindo como indicador da idade do abalone.

# Feature engineering
Foram criadas novas colunas a partir das já existentes:

1. Porcentagem de Peso Total 1 e 2 (Percentage Whole 1 e Percentage Whole 2): Essas características calculam a proporção do peso total da carne em relação ao peso total completo do abalone. Isso pode ser útil para entender a distribuição do peso entre a carne e a concha.

2. Porcentagem de Peso da Concha (Percentage Shell): Esta característica calcula a proporção do peso da concha em relação ao peso total do abalone. Isso fornece insights sobre a contribuição da concha para o peso total.

3. Volume: O volume é calculado usando as dimensões de comprimento e diâmetro da concha, assumindo uma forma esférica. Isso pode ser útil para entender o tamanho total do abalone.

4. Densidade: A densidade é calculada dividindo o peso total do abalone pelo volume. Isso fornece uma medida da densidade da carne do abalone em relação ao seu tamanho.

5. Razão de Comprimento para Diâmetro (Length to Diameter Ratio): Esta característica calcula a relação entre o comprimento e o diâmetro da concha. Pode fornecer informações sobre a forma da concha.

# Modelagem e métrica de avaliação

Para a modelagem do modelo foi utilizado um Stacking Regressor com os seguintes modelos como base:
1. SVR
2. GradientBoostingRegressor
3. XGBRegressor
4. KNeighborsRegressor

E para o meta modelo foi utilizado uma LinearRegression.

Isso gerou um resultado de RMSLE de 0.15

