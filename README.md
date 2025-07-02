# Teste A/B em jogo de celular

Para verificar o desempenho do jogo Cookie Cats da Tactile Entertainment, utilizei o teste A/B na métrica de retenção do jogador. Este conjunto de dados inclui resultados de 90.189 jogadores para examinar o que acontece quando o primeiro gate do jogo é movido do nível 30 para o nível 40. Para isso, o jogador, ao instalar o jogo, ele é aleatoriamente atribuído ao gate_30 ou ao gate_40.
Para conferir os dados acesse: [Kaggle](https://www.kaggle.com/datasets/mursideyarkin/mobile-games-ab-testing-cookie-cats/data).

## Banco de dados
Foram analisados 90.189 jogadores, sendo 5 varíaveis: 

* **userid:** Um número único que identifica cada jogador.
* **version:** Se o jogador foi colocado no grupo de controle (gate_30 - um gate no nível 30) ou no grupo com o gate de tratamento (gate_40 - um gate no nível 40).
* **sum_gamerounds:** o número de rodadas jogadas pelo jogador durante os primeiros 14 dias após a instalação.
* **retention_1:** O jogador voltou a jogar 1 dia após a instalação?
* **retention_7:** O jogador voltou a jogar 7 dias após a instalação?

A atribuição do jogador entre o gate_30 e gate_40 foi de 50% para 50%.

## Hipótese
* Hipótese Nula: h0 = não há diferença entre a retenção entre o gate_30 e gate_40.
* Hipótese Alternativa: h1 = há diferença na retenção entre os gates.


## Testes
**Para número de rodadas jogadas (sum_gamerounds)**

Foi utilizado o Teste t:

* Estatística t: -0.3468
* Valor-p: 0.7287

Não houve diferença significativa no número médio de rodadas jogadas entre os grupos (p > 0.05).

**Para retenção no 1º e 7º dia (retention_1 e retention_7)**

Foi utilizado o Teste Qui-Quadrado

Para retenção no 1º dia:
* Estatística χ²: 2.7469
* Valor-p: 0.0974

Para retenção no 7º dia:
* Estatística χ²: 13.6357
* Valor-p: 0.0002

## Conclusões
