
# Reconhecimento Facial com FaceNet

## Trabalho 1 — Experimentos de Reconhecimento Facial

Projeto acadêmico desenvolvido para investigar o desempenho do modelo FaceNet em tarefas de verificação facial.

## Objetivo

Avaliar o desempenho do FaceNet em diferentes conjuntos de imagens, utilizando métricas de avaliação, comparação de modelos e análise experimental.

## Tecnologias utilizadas

- Python
- PyTorch
- facenet-pytorch
- Google Colab
- MTCNN
- FaceNet (InceptionResnetV1)

## Experimentos realizados

### 1. LFW — Labeled Faces in the Wild

- Avaliação com 6.000 pares de imagens.
- Validação cruzada com 10 divisões.
- Comparação entre similaridade de cosseno e distância euclidiana.
- Acurácia média com cosseno: 98,43%.
- Acurácia média com distância euclidiana: 98,30%.

### 2. CelebA

- Avaliação do FaceNet original e após fine-tuning.
- Separação dos conjuntos de treinamento, validação e teste por identidade.
- AUC no teste do modelo original: 0,994748.
- AUC no teste do modelo com fine-tuning (época 1): 0,995070.

### 3. Dataset privado

- Conjunto de 6 fotografias próprias.
- Detecção facial utilizando MTCNN.
- Geração de embeddings utilizando FaceNet.
- Realização de 15 comparações por similaridade de cosseno.
- Maior similaridade observada: 0,9043.
- Menor similaridade observada: 0,4714.

O experimento privado é exploratório e não constitui uma avaliação de acurácia, pois contém apenas uma identidade.

## Privacidade e proteção de dados

As fotografias pessoais e os embeddings faciais não são disponibilizados neste repositório.

O processamento do dataset privado foi realizado localmente. Arquivos biométricos e checkpoints não devem ser publicados.

## Documentação

Os códigos, as configurações experimentais e as análises são apresentados no notebook do projeto.
## Como executar o projeto

O projeto foi desenvolvido principalmente no Google Colab, utilizando Python e a biblioteca `facenet-pytorch`.

### Requisitos

- Python 3
- Google Colab (recomendado)
- Bibliotecas utilizadas no notebook, incluindo `torch`, `torchvision`, `facenet-pytorch`, `numpy`, `pandas`, `scikit-learn` e `matplotlib`
- Acesso aos datasets públicos LFW e CelebA, conforme as condições de uso de cada conjunto de dados

### Execução

1. Abra o arquivo `FaceNet_Reconhecimento_Facial_GitHub.ipynb` no Google Colab.
2. Configure o ambiente de execução e instale as dependências indicadas nas células do notebook.
3. Disponibilize os datasets públicos nos caminhos esperados pelo código.
4. Execute as células na ordem apresentada, ajustando os caminhos do Google Drive quando necessário.
5. Consulte os arquivos CSV na pasta `resultados/` para visualizar os resultados registrados dos experimentos.

### Observações

- O notebook pode exigir ajustes de caminhos e versões de bibliotecas conforme o ambiente utilizado.
- Os resultados podem variar conforme a configuração, a aleatoriedade e as versões das dependências.
- As fotografias do experimento privado não são disponibilizadas no repositório para preservar a privacidade.
- A execução completa dos experimentos com CelebA pode exigir recursos computacionais adicionais.
