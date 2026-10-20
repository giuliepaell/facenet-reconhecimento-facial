
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
