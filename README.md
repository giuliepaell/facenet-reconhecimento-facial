
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
## Datasets públicos utilizados

### LFW — Labeled Faces in the Wild

- **Fonte oficial:** https://vis-www.cs.umass.edu/lfw/
- **Finalidade:** Dataset acadêmico utilizado para pesquisa e avaliação de algoritmos de reconhecimento e verificação facial em imagens capturadas em condições não controladas.
- **Termos de utilização:** O dataset é disponibilizado para fins de pesquisa. Sua utilização deve respeitar as condições estabelecidas pelos responsáveis e os direitos relacionados às fotografias.
- **Utilização no projeto:** Foram avaliados 6.000 pares de imagens utilizando o FaceNet pré-treinado. Foram comparadas a similaridade de cosseno e a distância euclidiana, com validação cruzada em 10 folds.

### CelebA — CelebFaces Attributes Dataset

- **Fonte oficial:** https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html
- **Finalidade:** Dataset acadêmico de imagens faciais com informações de identidade e atributos, utilizado em pesquisas de visão computacional.
- **Termos de utilização:** O CelebA possui restrições de uso acadêmico e não comercial. Sua redistribuição é limitada pelas condições estabelecidas pelos responsáveis.
- **Utilização no projeto:** Foram utilizadas 2.000 imagens de 100 identidades, separadas em treinamento, validação e teste por identidade. O experimento comparou o FaceNet original com o modelo após fine-tuning.

Os arquivos originais dos datasets públicos não são disponibilizados neste repositório. Para reproduzir os experimentos, é necessário obtê-los nas fontes oficiais e respeitar seus respectivos termos de utilização.
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
## Ambiente utilizado nos experimentos

Os experimentos foram executados no Google Colab, com as seguintes versões:

- Python: versão do ambiente Colab
- PyTorch: 2.11.0+cu130
- Torchvision: 0.26.0+cu130
- facenet-pytorch: 2.6.0
- Scikit-learn: 1.6.1
- NumPy: 2.1.3
- Pandas: 2.2.3

O notebook utiliza o comando:

    %pip install --no-deps facenet-pytorch

A opção `--no-deps` evita a instalação automática das
dependências. As versões registradas descrevem o ambiente
utilizado, mas não garantem compatibilidade em outros ambientes.

O arquivo requirements.txt registra parte das dependências.
A instalação do PyTorch e do Torchvision deve considerar
a compatibilidade com o ambiente de execução.
## Configuração dos caminhos

O notebook utiliza o Google Drive para armazenar os resultados.

Para executar no Google Colab, é necessário autorizar
a montagem do próprio Google Drive.

O caminho utilizado originalmente foi:

/content/drive/MyDrive/IA_Reconhecimento_Facial/resultados

O usuário pode alterar a variável `pasta_resultados`
para escolher outro local de armazenamento.

O código cria automaticamente a pasta de resultados,
caso ela ainda não exista.

Outros caminhos de entrada e saída presentes no
notebook também devem ser conferidos antes da execução.
## Dataset CelebA

O experimento CelebA utiliza o arquivo
`identity_CelebA.txt`, que associa as imagens
às respectivas identidades.

O caminho utilizado no desenvolvimento foi:

`/content/drive/MyDrive/IA_Reconhecimento_Facial/dados_treinamento/identity_CelebA.txt`

Para reproduzir o experimento, é necessário
obter o dataset CelebA por uma fonte autorizada,
respeitando suas condições de uso, e ajustar
os caminhos no notebook.

Os arquivos originais do dataset não estão
incluídos neste repositório.
## Conclusão e escolha do modelo

Foram realizados experimentos de verificação facial utilizando FaceNet, com avaliação no LFW e fine-tuning no CelebA.

**Experimento LFW:** a similaridade do cosseno alcançou acurácia média de 98,43%, enquanto a distância euclidiana alcançou 98,30%, utilizando validação cruzada em 10 folds.

**Experimento CelebA:** o FaceNet original obteve AUC de teste de aproximadamente 0,99475. O modelo após a primeira época de fine-tuning obteve AUC de teste de aproximadamente 0,99507.

A diferença de desempenho no CelebA foi pequena, não sendo suficiente, isoladamente, para demonstrar uma melhoria consistente e generalizável com o treinamento adicional.

**Escolha:** o FaceNet pré-treinado é a opção preferencial para continuidade do projeto, pois apresentou desempenho elevado sem exigir fine-tuning adicional. A escolha considera o desempenho observado, a simplicidade e o custo de treinamento.

**Limitações:** os resultados dependem dos datasets e protocolos utilizados. O experimento privado foi exploratório, com seis fotografias de uma única pessoa, não permitindo calcular acurácia de reconhecimento ou avaliar generalização para outras identidades.
## Apresentação em vídeo

A apresentação da Parte 1 do projeto aborda o problema de reconhecimento facial, os datasets utilizados, a arquitetura FaceNet, a metodologia, os experimentos, o treinamento, os resultados e a justificativa da escolha do modelo.

**Vídeo da apresentação:** [Assistir à apresentação](## Apresentação em vídeo

A apresentação da Parte 1 do projeto aborda o problema de reconhecimento facial, os datasets utilizados, a arquitetura FaceNet, a metodologia, os experimentos, o treinamento, os resultados e a justificativa da escolha do modelo.

**Vídeo da apresentação:** [Assistir à apresentação](https://youtu.be/VcDzbpkFQBs?si=5dOM_Ga8IBibm3Je)
