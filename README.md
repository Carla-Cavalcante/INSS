## OPINIÃO PÚBLICA E A FRAUDE DO INSS: UMA ANÁLISE DE SENTIMENTOS DE USUÁRIOS DO X/TWITTER SOBRE LULA E BOLSONARO. 
---
Este repositório é parde de um estudo que analisa a atribuição de culpa pela fraude bilionária no INSS, revelada em abril de 2025, entre usuários do X/Twitter. Utilizando Análise de Sentimento em 4.761 postagens, a pesquisa comparou a responsabilização direcionada ao presidente Luiz Inácio Lula da Silva e ao ex-presidente Jair Messias Bolsonaro. Os resultados indicam que, embora a fraude tenha ocorrido em ambas as gestões (2019-2024), o escrutínio público recaiu mais intensamente sobre o governo atual. Lula foi alvo de um volume de menções significativamente maior, incluindo quase o dobro de postagens negativas em comparação a Bolsonaro. Conclui-se que o escândalo serviu como um catalisador para a polarização afetiva, com vieses partidários e sentimento antipetista.

### Coleta e processamento 
Os dados foram obtidos via web scrapping, conforme citado no artigo (upload em breve), os dados processados estão disponíveis em ```banco_tweets.csv```. Desses dados, 20% (cerca de 920 tweets) foram utilizado no _fine tunning_ do modelo, com BERTimbau, esse subset foi classificado segundindo os seguintes criérios:

**Positivo:** postagens que afirmam que a entidade influenciou positivamente no combate à fraude, ou que negam a culpa da entidade;

**Neutro:** postagens descritivas, que narram acontecimentos ou contam fatos;

**Negativo:** postagens que culpam diretamente a entidade pela fraude.

### Modelo 
O resultado final desta pesquisa foi a produção de um modelo de rede neutral, utilizado para Análise de sentimento baseada em entidade. As métricas do modelo estão expostas abaixo:

| Métrica   | Valor |
|-----------|-------|
| F1-score  | 0,64  |
| Acurácia  | 0,65  |

Os parâmetros usados foram:

| Hiperparâmetro  | Valor     |
|-----------------|-----------|
| Learning rate   | 2.32e-05  |
| Batch size      | 8         |
| Weight decay    | 0.08      |
| Épocas (epochs) | 3         |

O código na integra, com todas as ferramentas e técnicas específicas utilizadas na elaboração do modelo está disponível no arquivo ```aplicacao_final_v2```
