# Classificação de câncer de mama com MLP

Checkpoint 04 · Redes Neurais Artificiais, Deep Learning e Algoritmos Genéticos · FIAP 2026

**Aluno:** Bruno Henrique Ferreira Ambrosio · RM 571218

## O problema

Classificar tumores de mama como **benignos** ou **malignos** a partir de 30 medidas do núcleo celular. Os dados são do Breast Cancer Wisconsin (Diagnostic): 569 pacientes, 63% com tumor benigno e 37% com maligno.

## O que foi feito

1. **Análise exploratória** com seis perguntas sobre os dados. Exemplos: tumores malignos são maiores? Quais medidas mais se relacionam com o diagnóstico?
2. **Divisão em treino e teste** (holdout 70/30) estratificada, para manter a proporção de benignos e malignos nos dois conjuntos.
3. **Padronização** com `StandardScaler`, ajustado só no treino para evitar vazamento de dados.
4. **Rede neural** MLP com duas camadas ocultas (16 e 8 neurônios), ativação ReLU e otimizador Adam.
5. **Avaliação** com matriz de confusão, precisão, recall e F1, além da comparação entre treino e teste para checar overfitting.

## Resultados (171 pacientes de teste)

| Métrica | Valor |
|---|---|
| Acurácia no teste | **97,08%** |
| Recall da classe maligna | **0,98** |
| Acurácia no treino | 99,75% (diferença de 2,67 p.p.: sem overfitting relevante) |

O recall alto na classe maligna é o resultado mais importante: quase nenhum tumor maligno passou como benigno, e esse é o erro mais perigoso no diagnóstico.

## Como abrir

O notebook [`MLP_Cancer_de_Mama.ipynb`](MLP_Cancer_de_Mama.ipynb) já está executado e pode ser lido direto no GitHub.

Para rodar de novo, abra no Google Colab (File → Upload notebook). O dataset já vem no scikit-learn.

**Tecnologias:** Python, pandas, scikit-learn, matplotlib e seaborn.
