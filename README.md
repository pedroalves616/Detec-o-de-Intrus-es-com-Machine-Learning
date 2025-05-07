# 🛡️ Detecção de Intrusões com Machine Learning

Projeto de classificação de conexões de rede como normais ou intrusivas utilizando aprendizado de máquina supervisionado.

---

## 📁 1. Dados Utilizados

Utilizei o dataset **Network Intrusion Detection** do [Kaggle]([https://www.kaggle.com/](https://www.kaggle.com/datasets/sampadab17/network-intrusion-detection) contendo registros de conexões classificados como:

- `normal`
- `anomaly` (intrusão)

Arquivos utilizados:
- `Train_data.csv`
- `Test_data.csv`

---

## ⚙️ 2. Pré-processamento

Etapas realizadas para preparar os dados:

- 🔹 Remoção de valores nulos
- 🔹 Codificação de variáveis categóricas com **One-Hot Encoding**:
  - `protocol_type`, `service`, `flag`
- 🔹 Mapeamento da variável alvo:
  - `normal` → `0`
  - `anomaly` → `1`
- 🔹 Normalização com `StandardScaler`
- 🔹 Separação entre treino e teste

---

## 🤖 3. Modelo Escolhido

O modelo utilizado foi o **Random Forest**, ideal para dados tabulares com variáveis mistas.

- 📊 Divisão dos dados:
  - `80%` treino
  - `20%` validação (`train_test_split`)

---

## ✅ 4. Resultados da Classificação

- **Acurácia**: `99,74%`

### 🔍 Matriz de Confusão

|                        | Previsto: Normal | Previsto: Anomaly      |
|------------------------|------------------|-------------------------|
| **Real: Normal**       | 2670             | 4 *(falsos positivos)*  |
| **Real: Anomaly**      | 9 *(falsos negativos)* | 2356          |

📌 O modelo apresentou desempenho excelente com pouquíssimos erros críticos.

---

## 📈 5. Curva ROC e AUC

A **curva ROC** avalia a performance classificatória comparando:

- Taxa de Verdadeiros Positivos (Sensibilidade)
- Taxa de Falsos Positivos

**AUC (Área sob a curva):**

- `AUC ≈ 1.0` → modelo excelente  
- `AUC ≈ 0.5` → modelo aleatório

✨ O modelo obteve um **AUC próximo de 1**, demonstrando excelente separação entre classes.

---

## 🧠 6. Top 10 Features Mais Importantes

As variáveis mais relevantes segundo o Random Forest:

1. `dst_bytes`
2. `src_bytes`
3. `dst_host_srv_count`
4. `flag_SF`
5. `dst_host_diff_srv_rate`
6. `same_srv_rate`
7. `dst_host_srv_serror_rate`
8. `count`
9. `dst_host_same_srv_rate`
10. `diff_srv_rate`

Essas features estão relacionadas ao volume e padrão de tráfego — essenciais para detectar intrusões.

---

## 🎓 7. Conclusão e Aprendizados

Este projeto demonstrou que modelos supervisionados como o **Random Forest** são altamente eficazes para **detecção de intrusões em redes**.

### 📌 Principais aprendizados:

- Importância do **pré-processamento dos dados**
- Interpretação de **métricas de avaliação** como acurácia, matriz de confusão e AUC
- Capacidade de **identificar as variáveis mais importantes** para o modelo

---

> Desenvolvido com 💻 por [Pedro Alves]

