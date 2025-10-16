# RPAD-1
# 🍷 PCA + KMeans: Agrupamento no Dataset de Vinhos

> Projeto em Python que aplica **Análise de Componentes Principais (PCA)** e **K-Means Clustering** no clássico dataset de vinhos do `scikit-learn`, com visualização e avaliação dos resultados.

---

## 📘 Sobre o Projeto

Este projeto demonstra como reduzir a dimensionalidade de um conjunto de dados real usando **PCA (Principal Component Analysis)** e, em seguida, aplicar **K-Means** para identificar grupos semelhantes — tudo isso **sem usar os rótulos verdadeiros**.

O dataset utilizado é o [`load_wine`](https://scikit-learn.org/stable/datasets/toy_dataset.html#wine-dataset) do `scikit-learn`, que contém **178 amostras de vinhos** com **13 atributos químicos** (como teor alcoólico, acidez, magnésio, flavonóides, etc.) divididos em **3 classes de cultivares**.

---

## 🧠 Conceitos Principais

### 🧩 PCA (Principal Component Analysis)
- Reduz a dimensionalidade dos dados mantendo a **maior variância possível**.
- Cada **componente principal** é uma combinação linear das variáveis originais.
- No projeto, usamos **2 componentes** para visualizar os dados em 2D.

Fórmula básica da projeção:
\[
Z = X \cdot W
\]
onde:
- \(X\): dados originais padronizados  
- \(W\): autovetores (componentes principais)  

---

### ⚙️ K-Means Clustering
- Algoritmo **não supervisionado** que agrupa amostras em \(K\) grupos com base na proximidade.
- Define **centroides** que representam cada cluster.
- Cada ponto é atribuído ao **centróide mais próximo** (menor distância Euclidiana).

Etapas do K-Means:
1. Inicializa \(K\) centroides aleatoriamente  
2. Atribui cada ponto ao centróide mais próximo  
3. Atualiza os centroides como a média dos pontos de cada cluster  
4. Repete até convergir

---

## 🧪 Etapas do Código

| Etapa | Descrição |
|:------|:-----------|
| **1. Carregamento dos Dados** | Usa `load_wine()` para obter `X` (atributos) e `y` (classes reais). |
| **2. Padronização (`StandardScaler`)** | Normaliza os dados para média 0 e desvio 1, essencial para o PCA. |
| **3. Redução de Dimensionalidade (`PCA`)** | Reduz as 13 features para 2 componentes principais. |
| **4. Agrupamento (`KMeans`)** | Agrupa os dados em 3 clusters (pois sabemos que há 3 tipos de vinho). |
| **5. Mapeamento de Clusters → Classes** | Ajusta as cores para que os clusters correspondam às classes reais. |
| **6. Visualização** | Plota dois gráficos lado a lado: classes reais vs clusters descobertos. |

---

## 📊 Visualização

| Classes Reais | Clusters (KMeans) |
|----------------|------------------|
| ![classes](https://user-images.githubusercontent.com/your-example-link-left.png) | ![clusters](https://user-images.githubusercontent.com/your-example-link-right.png) |

> 🔹 As cores do gráfico de KMeans são ajustadas para coincidir com as classes reais.  
> 🔸 Os **X vermelhos** representam os **centroides** descobertos pelo algoritmo.

---

## 🧮 Métricas

Durante a execução, são exibidos:

- **Variância explicada pelo PCA** → Ex: `0.55` (55%)  
- **Matriz de confusão** entre classes reais e clusters  
- **Acurácia aproximada** após mapeamento de clusters → Ex: `~0.90`

---

## 🧰 Requisitos

| Biblioteca | Descrição |
|-------------|------------|
| `scikit-learn` | Machine learning e datasets |
| `matplotlib` | Visualização dos gráficos |
| `numpy` | Operações numéricas |
| `pandas` | Manipulação de dados |

Instalação:

```bash
pip install scikit-learn matplotlib numpy pandas
