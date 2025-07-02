# Teste A/B na retenção em jogos de celular

Para verificar o desempenho do jogo Cookie Cats da Tactile Entertainment, utilizei o teste A/B na métrica de retenção do jogador. Este conjunto de dados inclui resultados de 90.189 jogadores para examinar o que acontece quando o primeiro gate do jogo é movido do nível 30 para o nível 40. Ao instala o jogo, o jogador é aleatoriamente atribuído ao grupo gate_30 ou gate_40.
Para conferir os dados acesse: [Kaggle](https://www.kaggle.com/datasets/mursideyarkin/mobile-games-ab-testing-cookie-cats/data).

## Banco de dados

Foram analisados 90.189 jogadores, sendo 5 variáveis:

- **userid:** Um número único que identifica cada jogador.
- **version:** Se o jogador foi colocado no grupo de controle (gate_30 - um gate no nível 30) ou no grupo com o gate de tratamento (gate_40 - um gate no nível 40).
- **sum_gamerounds:** o número de rodadas jogadas pelo jogador durante os primeiros 14 dias após a instalação.
- **retention_1:** O jogador voltou a jogar 1 dia após a instalação?
- **retention_7:** O jogador voltou a jogar 7 dias após a instalação?

A atribuição dos jogadores entre o gate_30 e gate_40 foi de 50% para 50%.

## Hipótese

- **Hipótese nula (H₀)**: não há diferença na retenção entre os grupos gate_30 e gate_40.
- **Hipótese alternativa (H₁)**: há diferença na retenção entre os grupos.

## Testes

Antes de realizar os testes de inferência, foram removidos os valores considerados outliers da variável sum_gamerounds e verificado se havia jogadores que instalaram o jogo, mas não jogaram nenhuma rodada. Foram identificados 3.994 jogadores nessa condição.

Para entender o impacto desses usuários nos resultados, foi feita uma análise específica considerando sua distribuição entre os grupos (gate_30 e gate_40) e suas taxas de retenção. 

Esses jogadores representam 4,4% do total da base, estão bem distribuídos entre os grupos (aproximadamente 51,5% em gate_40 e 48,5% em gate_30) e suas taxas de retenção são muito baixas (2,18% no 1º dia e 0,73% no 7º dia).

Com base nesses resultados, conclui-se que o impacto desses jogadores nos testes estatísticos é mínimo e não influencia significativamente os resultados obtidos nas análises de retenção ou engajamento.

### Número de rodadas jogadas (sum_gamerounds)

Para verificar a diferença entre gate_30 e gate_40 em relação ao número de rodadas jogadas, utilizei o teste t. Sendo esse, uma hipótese estatística que coleta amostras de ambos os grupos para determinar se há uma diferença significativa entre as médias dos dois grupos. 

- Estatística t: -0.3468
- Valor-p: 0.7287

Com esses resultados temos que não há evidência estatística de que os grupos tenham médias diferentes no número de rodadas jogadas. Portanto, não há evidência estatística suficiente para rejeitar a hipótese nula, indicando que a diferença observada não é estatisticamente significativa. Em relação ao valor negativo do teste t, o resultado representa que, depois de remover os outliers, o grupo gate_30 teve uma média de rodadas ligeiramente maior do que o grupo gate_40.

### Retenção no 1º e 7º dia (retention_1 e retention_7)

Para essas duas variáveis foi utilizado o Teste Qui-Quadrado (χ²). O teste do qui-quadrado é um teste estatístico que pode ser usado para determinar quais frequências observadas são significativamente diferentes das frequências esperadas ou não em uma ou mais categorias.

Para retenção no 1º dia:

- Estatística χ²: 2.7469
- Valor-p: 0.0974

Para retenção no 7º dia: 

- Estatística χ²: 13.6357
- Valor-p: 0.0002

A retenção no 1º dia não foi significativamente afetada pela mudança do gate de nível 30 para nível 40. Já a retenção no 7º dia, valor-p < 0.05, indica uma diferença estatisticamente significativa entre os grupos.

Isso significa que a retenção no 7º dia foi impactada pela versão do jogo que o jogador experimentou.

## Conclusões

Com base nos resultados, a retenção de longo prazo (7 dias) foi significativamente maior em um dos grupos, indicando que a posição do gate afeta o engajamento dos jogadores ao longo do tempo. Já a retenção de curto prazo (1 dia) e o número de rodadas jogadas não apresentaram diferença significativa. Assim, recomenda-se considerar o impacto positivo do gate na retenção de longo prazo.