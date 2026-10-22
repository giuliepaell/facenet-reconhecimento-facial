# ADR-001 — Escolha do modelo de reconhecimento facial

## Contexto

O projeto investiga o uso de redes neurais para verificação facial, buscando uma solução com bom desempenho, custo computacional adequado e possibilidade de utilização em uma aplicação futura.

## Alternativas avaliadas

1. FaceNet pré-treinado em VGGFace2, sem treinamento adicional.
2. FaceNet com fine-tuning parcial das últimas camadas.
3. Comparação dos embeddings por similaridade de cosseno.
4. Comparação dos embeddings por distância euclidiana.

## Evidências experimentais

No dataset LFW, o FaceNet pré-treinado alcançou acurácia média de 98,43% com similaridade de cosseno e 98,30% com distância euclidiana.

No dataset CelebA, o modelo original apresentou AUC de teste de 0,994748, enquanto o modelo após a primeira época de fine-tuning apresentou AUC de 0,995070.

A melhoria observada após o fine-tuning foi pequena, e a segunda época apresentou piora na validação.

## Decisão

Utilizar o FaceNet (InceptionResnetV1), pré-treinado em VGGFace2, sem fine-tuning adicional, como modelo preferencial para a continuidade do projeto.

A similaridade de cosseno será a estratégia inicial de comparação dos embeddings, sujeita à calibração de threshold conforme o protocolo de avaliação da aplicação.

## Justificativa

A escolha considera o elevado desempenho do modelo original, a pequena diferença obtida com fine-tuning, a menor complexidade de implementação e a redução do custo computacional.

## Consequências e limitações

O modelo escolhido ainda precisará ser avaliado nas condições específicas da aplicação da Parte 2.

O desempenho observado nos datasets públicos não garante o mesmo desempenho em imagens de usuários reais.

Os dados biométricos privados não deverão ser publicados ou incorporados a arquivos distribuídos pelo repositório.
