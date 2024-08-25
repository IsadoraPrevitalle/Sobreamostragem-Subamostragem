## Comparação entre Sobreamostragem e Subamostragem em Algoritmos de Tratamento de Base de Dados

### Introdução

Em muitos problemas de aprendizado de máquina, a qualidade do modelo está diretamente ligada à natureza dos dados. Quando se trabalha com bases de dados desbalanceadas, onde uma ou mais classes possuem significativamente mais dados do que outras, surgem problemas como previsões tendenciosas, desempenho ruim e perda de informações. Para mitigar esses problemas, foram desenvolvidas estratégias como a sobreamostragem e a subamostragem. Este relatório visa comparar essas técnicas de forma prática, implementando exemplos e analisando os resultados para compreender as principais características, desempenho e diferenças entre elas.

### Sobreamostragem

A sobreamostragem é uma técnica que adiciona exemplos à classe minoritária — aquela com menos registros em comparação às outras classes — para equilibrar o conjunto de dados. O processo envolve selecionar aleatoriamente ou gerar novos dados para a classe minoritária, até alcançar uma proporção desejada, geralmente 1:1.

Dentre as técnicas de sobreamostragem, o SMOTE (Synthetic Minority Over-sampling Technique) se destaca por gerar dados sintéticos com base na distância euclidiana entre os vizinhos mais próximos da classe minoritária. No entanto, o SMOTE pode apresentar problemas como overfitting, ao criar um viés muito forte em um espaço pequeno, e sensibilidade a outliers, ao gerar pontos extremos que podem afetar o modelo.

Outra técnica é o ADASYN (Adaptive Synthetic Sampling), que considera a densidade dos dados e foca na geração de exemplos sintéticos nas áreas onde o modelo tem mais dificuldade em aprender. O ADASYN ajusta a quantidade de dados gerados com base na dificuldade de generalização das observações.

No contexto desta análise, foram aplicadas as técnicas SMOTE e ADASYN em um conjunto de dados desbalanceado, composto por 1000 amostras e duas classes (90% da classe 0 e 10% da classe 1). A técnica SMOTE resultou em uma acurácia geral de 97%, com pequenas melhorias nas métricas de avaliação em comparação à base desbalanceada. O ADASYN apresentou resultados similares, alcançando uma acurácia geral de 97% e melhorando a precisão e recall.

### Subamostragem

A subamostragem é uma técnica que reduz o número de instâncias da classe majoritária para promover o balanceamento do conjunto de dados. As instâncias da classe majoritária são removidas aleatoriamente até atingir uma distribuição equilibrada.

Entre as técnicas de subamostragem, o Random Undersampling é um método simples que remove aleatoriamente exemplos da classe majoritária. Embora seja rápido de implementar, pode resultar na perda de informações importantes. Outra técnica, o Cluster-based Under-sampling, realiza a redução da classe majoritária com base em agrupamentos de exemplos redundantes ou menos representativos. Esse método, embora mais sofisticado, pode ser mais lento e complexo de ajustar.

Na análise, foram aplicadas essas técnicas ao mesmo conjunto de dados aleatório. O Random Undersampling obteve uma acurácia média de 92%, enquanto o Cluster-based Under-sampling alcançou uma acurácia média de 93%. Ambos apresentaram desempenho inferior em comparação à base balanceada pelas técnicas de sobreamostragem.

### Conclusão

Os resultados demonstram que, para a base de dados desbalanceada analisada, com 1000 registros e um desbalanceamento de 10% para 90%, a técnica de sobreamostragem se mostrou mais eficaz, alcançando uma acurácia de 97%. A sobreamostragem foi vantajosa porque o objetivo era manter o máximo de dados e expandir a classe minoritária.

Em contraste, a subamostragem foi menos eficiente neste cenário específico, devido à perda de informações e à redução do tamanho do conjunto de dados. No entanto, em situações de desbalanceamento mais suave ou quando a redução do tempo de processamento é uma prioridade, a subamostragem pode ser mais adequada.

Recomenda-se o uso de técnicas híbridas que combinam sobreamostragem e subamostragem para otimizar a representatividade das classes e o desempenho computacional. A escolha da técnica ideal depende do contexto específico do problema e das características dos dados.
