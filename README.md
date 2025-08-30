# 🧠 Projeto: Elaboração de uma Rede Neural para o Problema do XOR

Este projeto tem como objetivo a **implementação e exploração de Redes Neurais Artificiais** aplicadas ao problema clássico do **XOR (Exclusive OR)**.  
O trabalho contempla desde a geração de dados sintéticos, visualização e preparação até a modelagem, treinamento, avaliação e experimentação de diferentes arquiteturas de redes neurais *feedforward* (MLPs — *Multi-Layer Perceptrons*).

---

## 📑 Sumário

- [Descrição do Problema](#-descrição-do-problema)
- [Objetivos do Projeto](#-objetivos-do-projeto)
- [Arquitetura e Modelagem](#-arquitetura-e-modelagem)
- [Resultados Obtidos](#-resultados-obtidos)
- [Visualizações e Saídas](#-visualizações-e-saídas)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Instalação e Execução](#-instalação-e-execução)
- [Requisitos](#-requisitos)
- [Próximos Passos](#-próximos-passos)
- [Licença](#-licença)

---

## 📌 Descrição do Problema

O **problema do XOR** é um desafio clássico em Inteligência Artificial que demonstra a limitação de modelos lineares. Ele não pode ser resolvido por um único perceptron, exigindo uma rede com **camadas intermediárias** (*hidden layers*) para aprender a fronteira de decisão não linear.  

A solução aqui apresentada utiliza **dados sintéticos** que simulam distribuições em torno de quatro centros correspondentes às combinações do XOR.

---

## 🎯 Objetivos do Projeto

- Implementar modelos de redes neurais do tipo MLP para classificar o problema do XOR.
- Demonstrar a evolução do treinamento por meio de métricas e visualizações.
- Avaliar o impacto de **diferentes arquiteturas** e **hiperparâmetros**.
- Explorar as melhores combinações para **acurácia, simplicidade e eficiência**.

---

## 🏗️ Arquitetura e Modelagem

1. **MLP Baseline (MLP1)**  
   - Camada oculta com 8 neurônios (`tanh`).  
   - Camada oculta adicional com 4 neurônios (`tanh`).  
   - Camada de saída com 1 neurônio (`sigmoid`).  

2. **MLP Exploratória (MLP2)**  
   - Variação da quantidade de camadas e neurônios.  
   - Exploração de diferentes hiperparâmetros.  
   - Comparação de otimizadores (`Adam`, `SGD`).  

3. **Treinamento e Avaliação**  
   - Função de perda: `binary_crossentropy`.  
   - Métrica: `binary_accuracy`.  
   - Avaliação de desempenho por **acurácia final** e curvas de treinamento.

---

## 📊 Resultados Obtidos

- O modelo baseline (MLP1) alcançou **acurácia superior a 95%**, com convergência estável.  
- Configurações mais profundas (MLP2) atingiram **100% de acurácia** em diversas combinações.  
- A visualização mostrou claramente a capacidade da rede em separar classes não linearmente separáveis.  

Exemplo de saída:

Entrada: [0 0] → Esperado: 0 | Previsto: 0 (0.0123)
Entrada: [0 1] → Esperado: 1 | Previsto: 1 (0.9987)
Entrada: [1 0] → Esperado: 1 | Previsto: 1 (0.9971)
Entrada: [1 1] → Esperado: 0 | Previsto: 0 (0.0089)

---

## 📈 Visualizações e Saídas

### 🔹 Distribuição dos Dados (XOR)

<p align="center">
  <img src="images/xor_dataset.png" alt="Distribuição dos dados XOR" width="500"/>
</p>

---

### 🔹 Curva de Treinamento — Loss

<p align="center">
  <img src="images/model_loss.png" alt="Curva de Loss" width="500"/>
</p>

---

### 🔹 Curva de Treinamento — Accuracy

<p align="center">
  <img src="images/model_accuracy.png" alt="Curva de Accuracy" width="500"/>
</p>

---

### 🔹 Exemplo de Previsões do Modelo

<p align="center">
  <img src="images/model_predictions.png" alt="Exemplo de previsões do modelo" width="500"/>
</p>

> As imagens acima podem ser geradas a partir do notebook e salvas na pasta `images/` para visualização no GitHub.

---

## 🛠️ Tecnologias Utilizadas

- **Python 3.9+**
- [NumPy](https://numpy.org/)
- [Pandas](https://pandas.pydata.org/)
- [Matplotlib](https://matplotlib.org/)
- [TensorFlow / Keras](https://www.tensorflow.org/)

---

## ⚙️ Instalação e Execução

1. Clone este repositório:
   ```bash
   git clone https://github.com/<seu-usuario>/<seu-repositorio>.git
   cd <seu-repositorio>

   python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows

pip install -r requirements.txt

jupyter notebook Projeto_Elaboração_de_uma_Rede_Neural.ipynb

numpy==1.26.4
pandas==2.2.2
matplotlib==3.9.0
tensorflow==2.16.1
Referências

Keras Documentation

TensorFlow Guides

Deep Learning Book - Ian Goodfellow


