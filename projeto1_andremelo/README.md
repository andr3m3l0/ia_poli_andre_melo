# Classificação de Dígitos com MLP: Impacto do Número de Camadas Ocultas e Ruído Gaussiano

Este projeto investiga como a profundidade de uma rede neural MLP afeta sua performance na tarefa de classificação de dígitos manuscritos (dataset MNIST), especialmente em cenários com ruído adicionado às imagens de entrada.

---

## Estrutura do Projeto

- `mnist_mlp_ruido.ipynb`: Notebook principal com treinamento, avaliação e visualização dos modelos.
- `imagens/`: Contém imagens geradas para a apresentação (matrizes de confusão, curvas de aprendizado, erros de classificação, etc).
- `apresentacao_final.pptx`: Slides com os resultados e análises do experimento.

---

## Como Executar

1. Clone o repositório
2. Instale as dependências
3. Abra o notebook no Google Colab ou Jupyter.
4. Execute todas as células sequencialmente.
5. As bibliotecas utilizadas são: `numpy`, `matplotlib`, `seaborn`, `tensorflow`, `sklearn`.

---

## Objetivo

- Investigar o impacto da quantidade de camadas ocultas em uma MLP na tarefa de classificação de dígitos (MNIST), avaliando o desempenho com e sem a adição de ruído gaussiano às imagens de teste.

---

## Metodologia

- **Base de dados**: MNIST, com 60.000 imagens de treino e 10.000 de teste (28x28 pixels).
- **Modelos testados**: MLPs com 1, 5 e 10 camadas ocultas.
- **Treinamento**:
  - Épocas: 50
  - Batch size: 128
  - Otimizador: Adam
  - Função de perda: Categorical Crossentropy
- **Ruído**: Adição de ruído gaussiano às imagens de teste com média 0 e desvio padrão 0.1.
- **Avaliação**: Acurácia, curvas de aprendizado, matrizes de confusão, análise visual de erros.

---

## Resultados

- Acurácia com dados limpos e ruidosos comparada para cada modelo.
- Curvas de aprendizado (acurácia e perda em treino e validação).
- Matrizes de confusão lado a lado.
- Exemplos de predições incorretas em imagens com ruído.

Observou-se que modelos com mais camadas tendem a ser mais robustos ao ruído, mas também mais propensos ao overfitting.

---

## Funções e Componentes

- `criar_modelo_mlp(...)`: Cria uma rede MLP com número variável de camadas ocultas.
- `adicionar_ruido_gaussiano(...)`: Aplica ruído gaussiano nas imagens.
- `plotar_matriz_confusao(...)`: Gera a matriz de confusão.
- `plotar_historico(...)`: Exibe curvas de aprendizado.
- `mostrar_erros_de_classificacao(...)`: Mostra imagens onde o modelo errou.

---

## Referências

- [MNIST Dataset](http://yann.lecun.com/exdb/mnist/)
- TensorFlow Documentation: https://www.tensorflow.org/
- Deep Learning with Python (François Chollet)
