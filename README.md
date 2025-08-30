# Projeto: Elaboração de uma Rede Neural para o Problema do XOR

Este projeto tem como objetivo a **implementação e exploração de Redes Neurais Artificiais** aplicadas à resolução do clássico problema da porta lógica XOR. O trabalho contempla desde a geração de dados sintéticos, visualização e preparação até a modelagem, treinamento e avaliação de diferentes arquiteturas de redes neurais, com foco na compreensão do impacto de hiperparâmetros e na obtenção de alta acurácia e eficiência.

## Sumário

- [Descrição do Problema](#descrição-do-problema)
- [Objetivos do Projeto](#objetivos-do-projeto)
- [Arquitetura e Modelagem](#arquitetura-e-modelagem)
- [Resultados Obtidos](#resultados-obtidos)
- [Visualizações e Saídas](#visualizações-e-saídas)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Instalação e Execução](#instalação-e-execução)
- [Requisitos](#requisitos)
- [Licença](#licença)
- [Referências](#referências)

## Descrição do Problema

O **problema do XOR** é um desafio clássico em Inteligência Artificial que demonstra a limitação de modelos lineares e a necessidade de camadas ocultas em redes neurais para resolver problemas não linearmente separáveis. A solução aqui apresentada utiliza **dados sintéticos** que simulam distribuições em torno de quatro pontos no plano cartesiano, representando as entradas da porta XOR (0,0), (0,1), (1,0) e (1,1), com suas respectivas saídas (0, 1, 1, 0).

## Objetivos do Projeto

Os principais objetivos deste projeto são:

- Implementar modelos de redes neurais do tipo Multi-Layer Perceptron (MLP) para classificar o problema do XOR.
- Demonstrar a evolução do treinamento por meio de métricas de desempenho (acurácia, perda) e visualizações gráficas.
- Avaliar o impacto de **diferentes arquiteturas** de rede (número de camadas e neurônios) e **hiperparâmetros** (taxa de aprendizado, tamanho do batch, número de épocas).
- Explorar as melhores combinações para alcançar os seguintes critérios:
    - **Top 1**: Alcançar o melhor resultado possível em termos de acurácia.
    - **Top 2**: Alcançar o menor modelo possível (menor número de parâmetros).
    - **Top 3**: Alcançar o menor número de épocas possível para convergência.

## Arquitetura e Modelagem

O projeto explora duas configurações principais de MLP:

### MLP Baseline (MLP1)

Uma arquitetura simples, projetada para demonstrar a capacidade mínima necessária para resolver o problema XOR:

- **Camada de Entrada**: 2 neurônios (correspondendo às duas entradas do XOR).
- **Camada Oculta**: 4 neurônios com função de ativação `tanh`.
- **Camada de Saída**: 1 neurônio com função de ativação `sigmoid` (para classificação binária).

### MLP2 - Exploração do Problema

Esta seção do notebook permite a experimentação livre com novas configurações de modelo, reconfiguração das features de entrada, e ajuste de hiperparâmetros como taxa de aprendizado, batch sizes e número de épocas. O objetivo é encontrar as configurações ideais para os critérios de Top 1, Top 2 e Top 3 definidos nos objetivos do projeto.

## Resultados Obtidos

O modelo baseline (MLP1) demonstrou uma **acurácia superior a 95%**, com convergência estável da perda e acurácia ao longo do treinamento. Configurações mais profundas (MLP2), após otimização de hiperparâmetros, atingiram **100% de acurácia** em diversas combinações, validando a capacidade da rede neural em separar classes não linearmente separáveis.

**Exemplo de Saída de Previsões:**

```
Entrada: [0 0] → Esperado: 0 | Previsto: 0 (0.0040)
Entrada: [0 1] → Esperado: 1 | Previsto: 1 (0.9975)
Entrada: [1 0] → Esperado: 1 | Previsto: 1 (0.9776)
Entrada: [1 1] → Esperado: 0 | Previsto: 0 (0.0221)
```

## Visualizações e Saídas

As visualizações são cruciais para entender o comportamento do modelo e o processo de aprendizado. O notebook gera os seguintes gráficos:

### Distribuição dos Dados (XOR)

<p align="center">
  <img src="images/xor_dataset.png" alt="Distribuição dos dados XOR" width="500"/>
</p>

### Curva de Treinamento – Loss

<p align="center">
  <img src="images/model_loss.png" alt="Curva de Loss" width="500"/>
</p>

### Curva de Treinamento – Accuracy

<p align="center">
  <img src="images/model_accuracy.png" alt="Curva de Accuracy" width="500"/>
</p>

### Exemplo de Previsões do Modelo

<p align="center">
  <img src="images/model_predictions.png" alt="Exemplo de previsões do modelo" width="500"/>
</p>

> As imagens acima podem ser geradas a partir do notebook e salvas na pasta `images/` para visualização no README. Certifique-se de criar a pasta `images` na raiz do projeto.

## Tecnologias Utilizadas

As seguintes bibliotecas e ferramentas foram empregadas no desenvolvimento deste projeto:

- **Python**
- **TensorFlow / Keras**: Framework de código aberto para aprendizado de máquina e sua API de alto nível. [TensorFlow](https://www.tensorflow.org/)
- **NumPy**: Biblioteca fundamental para computação numérica. [NumPy](https://numpy.org/)
- **Pandas**: Biblioteca para análise e manipulação de dados. [Pandas](https://pandas.pydata.org/)
- **Matplotlib**: Biblioteca para criação de gráficos. [Matplotlib](https://matplotlib.org/)

## Instalação e Execução

Para executar este projeto em seu ambiente local, siga os passos abaixo:

1.  **Clone o Repositório**:
    ```bash
    git clone <URL_DO_SEU_REPOSITORIO>
    cd Projeto_Elaboração_de_uma_Rede_Neural
    ```

2.  **Crie e Ative um Ambiente Virtual**:
    É altamente recomendado criar um ambiente virtual para isolar as dependências do projeto e evitar conflitos com outras instalações Python.
    ```bash
    python -m venv venv
    source venv/bin/activate  # No Linux/macOS
    # .\venv\Scripts\activate  # No Windows (PowerShell)
    # venv\Scripts\activate.bat  # No Windows (CMD)
    ```

3.  **Instale as Dependências**:
    As dependências estão listadas no arquivo `requirements.txt`. Instale-as usando pip:
    ```bash
    pip install -r requirements.txt
    ```

4.  **Execute o Notebook no Jupyter ou Google Colab**:
    Navegue até o diretório do projeto e inicie o Jupyter Notebook:
    ```bash
    jupyter notebook
    ```
    No navegador, abra o arquivo `Projeto_Elaboração_de_uma_Rede_Neural.ipynb`. Alternativamente, você pode abri-lo diretamente no Google Colab.

## Requisitos

As versões específicas das bibliotecas utilizadas são:

```
numpy==1.26.4
pandas==2.2.2
matplotlib==3.9.0
tensorflow==2.16.1
```

## Licença

Este projeto é distribuído sob a licença MIT. Consulte o arquivo `LICENSE` para mais detalhes.

## Referências

- [Keras Documentation](https://keras.io/)
- [TensorFlow Guides](https://www.tensorflow.org/guide)
- [Deep Learning Book - Ian Goodfellow et al.](https://www.deeplearningbook.org/)

