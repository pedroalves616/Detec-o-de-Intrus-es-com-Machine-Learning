Relatório: Detecção de Intrusões com Machine Learning
1. Dados Utilizados
Utilizei o dataset “Network Intrusion Detection” do Kaggle, que contém registros de conexões de rede classificadas como “normal” ou “anomaly” (intrusão).
Os arquivos utilizados foram:

Train_data.csv

Test_data.csv

2. Pré-processamento
Para preparar os dados, realizei os seguintes passos:

✅ Remoção de valores nulos.

✅ Codificação de variáveis categóricas:

protocol_type, service e flag foram convertidas com One-Hot Encoding.

✅ Separação entre treino e teste após a codificação.

✅ Mapeamento da variável-alvo:

normal → 0

anomaly → 1

✅ Normalização dos dados com StandardScaler.

3. Modelo Escolhido
Utilizei o modelo Random Forest, conhecido por sua capacidade de lidar com conjuntos de dados tabulares e mistos.

Divisão dos dados:

80% para treino

20% para validação, usando train_test_split.

4. Resultados da Classificação
Acurácia: 99.74%

Matriz de Confusão:
Previsto Normal	Previsto Anomaly
Real Normal	2670	4 (falso positivo)
Real Anomaly	9 (falso negativo)	2356

📌 O modelo foi altamente eficaz, com poucos erros críticos, o que é essencial para aplicações de segurança.

5. Curva ROC e AUC
A Curva ROC (Receiver Operating Characteristic) avalia a capacidade do modelo de distinguir entre as classes, comparando:

✅ Taxa de Verdadeiros Positivos (sensibilidade)

❌ Taxa de Falsos Positivos

A métrica AUC (Área sob a curva) resume essa performance:

AUC ≈ 1.0: modelo excelente

AUC ≈ 0.5: modelo aleatório

📈 Neste projeto, o Random Forest obteve um AUC muito próximo de 1, indicando que o modelo consegue separar muito bem conexões normais de intrusivas.

6. Top 10 Features Mais Importantes
O modelo identificou as seguintes variáveis como mais influentes:

dst_bytes

src_bytes

dst_host_srv_count

flag_SF

dst_host_diff_srv_rate

same_srv_rate

dst_host_srv_serror_rate

count

dst_host_same_srv_rate

diff_srv_rate

Essas variáveis envolvem padrões de tráfego, volume de dados e comportamento da conexão — todos relevantes para detectar ataques.

7. Conclusão e Aprendizados
Este projeto demonstrou como modelos supervisionados, como o Random Forest, podem ser altamente eficazes na detecção de intrusões de rede.

💡 Aprendizados principais:
A importância da preparação de dados (codificação e normalização).

Como interpretar métricas de desempenho como acurácia, matriz de confusão e AUC.

Como extrair e interpretar as features mais relevantes para o modelo.
