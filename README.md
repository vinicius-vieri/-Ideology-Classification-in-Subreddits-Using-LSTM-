# Classificação de Orientações Ideológicas em Artigos Jornalísticos

Este projeto utiliza Processamento de Linguagem Natural (PLN) e Redes Neurais do tipo Long Short-Term Memory (LSTM) para classificar orientações ideológicas (liberal ou conservadora) de artigos postados em subreddits específicos. O foco é identificar diferenças ideológicas computáveis entre os textos.

## Objetivo
Classificar postagens dos subreddits `r/Liberal` e `r/Conservative` em dois rótulos:
- **0**: Liberal
- **1**: Conservador

O projeto visa verificar a predominância de críticas ou apoios nos textos e explorar possíveis padrões ideológicos.

## Dataset
O dataset utilizado é composto por 22.544 artigos de cada subreddit. Ele foi obtido através do [Reddit Ideology Database](https://paperswithcode.com/paper/classifying-the-ideological-orientation-of).

### Pré-processamento dos dados:
1. **Unificação dos arquivos**: Concatenação dos arquivos `Liberal.json` e `Conservative.json` em um único dataset no formato Parquet.
2. **Limpeza de Texto**: Aplicação de técnicas de PLN como remoção de stopwords e uso de REGEX.
3. **Tokenização**: Transformação dos textos em sequências numéricas.
4. **Padding**: Adição de padding às sequências para manter um tamanho consistente.
5. **Divisão dos dados**: Separação em treino (80%) e teste (20%).

## Modelo Utilizado
O modelo LSTM foi implementado para classificar os textos ideológicos, com as seguintes etapas:
- **Arquitetura**: LSTM com camadas de embedding, LSTM e densa.
- **Treinamento**: Otimização utilizando a função de loss `binary_crossentropy` e o otimizador Adam.

## Resultados
O modelo alcançou uma acurácia aproximada de **77%** na tarefa de classificação binária.
