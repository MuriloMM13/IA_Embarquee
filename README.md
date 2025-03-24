# Projet IA_Embarquee

**Participants:**  
Caio Vinícius Rodrigues Nobre  
Murilo Mattos Muller

**Institution:**  
École Nationale Supérieure des Mines de Saint-Étienne (EMSE-ISMIN)  

---

## Folder structure

  - *Communication_STM32*: contains the python script (“*com.py*”) to test communication with the STM32 board and displays the accuracy (in the terminal). The folder also contains the inputs used, as well as an example of the output that can be viewed in the terminal (“*test_acccuracy*”).
  - *MNIST*: network used to learn how to use cubeMX/IDE, provided by the professor at ecampus.
  - *Machine_Failure*: analysis and validation of the project in cubeMX/IDE with the google colab “*TP_IA_EMBARQUEE*” completed.
  - ** 
---

## Part 1 – Desenvolvimento do Modelo no Google Colab

### Objetivo

Desenvolver uma rede neural para classificação a partir de vetores com 8 entradas, resultando em uma saída categórica com 5 classes. O treinamento foi realizado em ambiente Python no Google Colab, com posterior exportação do modelo para embarque no STM32.

### Etapas Realizadas

1. **Pré-processamento dos Dados**
   - Normalização dos dados de entrada para o intervalo [0, 1].
   - Conversão dos rótulos para formato one-hot (`(n_amostras, 5)`).

2. **Arquitetura da Rede Neural**
   Exemplo de estrutura utilizada:

   ```python
   from keras.models import Sequential
   from keras.layers import Dense

   model = Sequential()
   model.add(Dense(32, activation='relu', input_shape=(8,)))
   model.add(Dense(16, activation='relu'))
   model.add(Dense(5, activation='softmax'))
