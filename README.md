# Mineração de dados sobre gênero na Wikipedia em Espanhol

A Wikipepia é plataforma de referência na colaboração entre
usuários na internet e seu uso resgata o espírito de compartilhamento
inicialmente pensado quando da concepção da rede. Contudo, disparidades
sociais se reproduzem entre seus editores: há uma diferença considerável
entre a quantidade e a participação de editores homens e mulheres. Nesta
análise, utilizamos a metodologia CRISP-DM para explorar o dataset
coletado por Minguillón et al (2021) e responder à pergunta: qual o
provável gênero, dentre os presentes no dataset, dos editores da wikipedia?


## Como explorar esse trabalho

- Veja o código no [Jupyter Notebook](https://github.com/edinadja/Projeto-final-da-disciplina-de-Solu-es-em-Minera-o-de-Dados/blob/main/%5BSOL_MINERACAO_DADOS%5DProjeto_Final_Genero_Wikipedia_JUN_2022_Edinadja_Leilane%20(1).ipynb)
- Leia o [relatório](https://github.com/edinadja/Projeto-final-da-disciplina-de-Solu-es-em-Minera-o-de-Dados/blob/main/projeto_final_dados_wikipediav_JUN_2022_Edinadja_Leilane.pdf) com análise completa.

## Sobre os dados

Segundo as análises dos dados feitas por Minguillón et al. (2021):

* das 4.746 páginas pessoais, 2.029 eram homens (42,8%), 295 eram mulheres
(6,2%) e 2.422 não puderam ser identificados e, portanto, permaneceram
“desconhecidos” (51,0%);
* se forem levados em consideração apenas os perfis de usuário atribuíveis a
mulheres e homens, aqueles identificados como mulheres representarão 12,9%
do número total de editores.

Os editores podem especificar seu gênero nas configurações de preferência de
sua conta na Wikipedia. A configuração de gênero é uma informação pública que pode
ser extraída por meio da API Mediawiki. Quando comparados os resultados da extração
manual de gênero para os 4.746 perfis codificados anteriormente com os gêneros da API
Media wiki, descobriu-se que:

* Existem 2.792 usuários identificados como homens, compreendendo 58,8% do
número total de editores.
* 353 usuários identificados como mulheres (172+58+123, em negrito e itálico),
compreendendo 7,4%.
* Os outros 1.601 usuários permanecem rotulados como “desconhecidos” (33,8%).

## Etapas da Análise

- Entendimento do domínio
- Entendimento dos dados (análise exploratória)
- Preparação dos dados
- Modelagem, com aplicação dos seguintes modelos:
  - KNN
  - LVQ
  - SVM
  - Árvore de Decisão
  - Neural Network (MLP Classifier)
  - Comitês de Classificadores
    - AdaBoost
    - Bagging
    - Voting
    - Stacking
- Avaliação dos modelos e resultados
  - Análise dos resultados dos desempenhos individuais dos modelos e Teste de Kruskal
  - Resultados da validação cruzada e conclusão da avaliação dos modelos
  
  
## Conclusões

É notória a dificuldade dos modelos em predizer membros das classes 0 e 2. A
tendência é esperada, dado que a classe 2 (gênero feminino) é subrepresentada na
plataforma Wikipedia e, por conseguinte, no conjunto de dados utilizado e a classe 0
(gênero desconhecido), apesar de numerosa, não possui comportamento de padrão
facilmente identificável, por incluir tanto pessoas do gênero feminino como masculino e
outros gêneros não possíveis de auto-declaração pelos formulários da plataforma.

Observa-se desempenho satisfatório da Árvore de Decisão como classificador
individual e resultados ainda melhores quando este modelo é aplicado como
classificador-base em comitês de classificação. Pelos experimentos e análises realizados,
indica-se o **Bagging com Árvore de Decisão como base** como classificador mais
adequado para prever as classes do problema de definição do gênero de editores da
Wikipedia em língua espanhola, dado o seu desempenho satisfatório de predições
acuradas e erro diminuto em relação a todos os modelos e arranjos testados nesta
análise.


## Tecnologias utilizadas

Python 3. *Bibliotecas:*
pandas, numpy, re, matplotlib.pylab, seaborn, scipy, statistics, joblib, sklearn (preprocessing, model_selection, preprocessing, linear_model import, metrics), joblib, sys, mlxtend.feature_selection, neupy

## Pessoas desenvolvedoras

[@reirane](https://github.com/reirane), [@edinadja](https://github.com/edinadja)

## Referências principais

[MINGUILLÓN, J.; MENESES, J.; AIBAR, E. FERRAN-FERRER, N. FÀBREGUES, S.
Exploring the gender gap in the Spanish Wikipedia: Differences in engagement and editing
practices. PLoS ONE, vol. 16, n. 2, 2021.](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0246702)

[UCI Machine Learning. Gender Gap in Spanish WP Data Set](https://archive.ics.uci.edu/ml/datasets/Gender+Gap+in+Spanish+WP#)


Para a lista completa de referências, verificar [relatório](https://github.com/edinadja/Projeto-final-da-disciplina-de-Solu-es-em-Minera-o-de-Dados/blob/main/projeto_final_dados_wikipediav_JUN_2022_Edinadja_Leilane.pdf) com análise completa.

