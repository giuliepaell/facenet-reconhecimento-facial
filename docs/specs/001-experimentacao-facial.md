# SPEC-001 — Experimentação e avaliação de reconhecimento facial

## 1. Objetivo

Investigar experimentalmente o desempenho do FaceNet na verificação facial, comparando estratégias de similaridade e avaliando o impacto do fine-tuning.

## 2. Requisitos funcionais

- RF01 — Carregar datasets públicos adequados à avaliação de reconhecimento facial.
- RF02 — Preparar as imagens para entrada no modelo FaceNet.
- RF03 — Gerar embeddings faciais de 512 dimensões.
- RF04 — Comparar pares de embeddings por similaridade de cosseno e distância euclidiana.
- RF05 — Selecionar limiares de decisão utilizando dados de desenvolvimento, sem utilizar o conjunto de teste.
- RF06 — Avaliar o desempenho do modelo pré-treinado.
- RF07 — Executar e avaliar fine-tuning parcial do modelo.
- RF08 — Registrar métricas e comparar resultados.
- RF09 — Avaliar exploratoriamente um pequeno dataset privado, sem publicar dados biométricos.

## 3. Requisitos não funcionais

- RNF01 — Preservar a separação entre treinamento, validação e teste.
- RNF02 — Registrar configurações e hiperparâmetros dos experimentos.
- RNF03 — Disponibilizar código e documentação para reprodução dos experimentos públicos.
- RNF04 — Não publicar fotografias, embeddings ou checkpoints derivados de dados privados.
- RNF05 — Respeitar os termos de utilização dos datasets públicos.
- RNF06 — Apresentar resultados privados somente de maneira agregada.

## 4. Critérios de aceitação

- CA01 — Avaliar 6.000 pares do LFW por validação cruzada em 10 folds.
- CA02 — Comparar cosseno e distância euclidiana utilizando acurácia.
- CA03 — Realizar experimentos no CelebA com separação de identidades entre treinamento, validação e teste.
- CA04 — Comparar o FaceNet original e a versão com fine-tuning utilizando ROC-AUC.
- CA05 — Documentar hipóteses, configurações, métricas, resultados e limitações.
- CA06 — Justificar a escolha do modelo para a Parte 2 com base nas evidências experimentais.
- CA07 — Garantir que os arquivos públicos do repositório não exponham dados biométricos privados.

## 5. Decisão técnica

A escolha do modelo está documentada em `docs/decisions/ADR-001-escolha-modelo.md`.

## 6. Escopo

Esta especificação corresponde à Parte 1 do trabalho. O desenvolvimento da aplicação funcional de reconhecimento facial pertence à Parte 2 e não está incluído nesta etapa.
