# regressao-linear-logistica-previsao-tempo-entrega

Projeto de análise de dados e modelagem preditiva para estimar o tempo de entrega (`tempo_entrega_min`) com base em características operacionais de pedidos logísticos.

---

## Objetivo

Desenvolver modelos de regressão linear capazes de prever o tempo de entrega antes do envio, auxiliando no planejamento logístico e na melhoria da previsibilidade para o cliente.

---

## Estrutura da Base de Dados

Cada linha representa um pedido entregue.

### Variáveis

| Tipo | Variáveis |
|------|----------|
| Numéricas | distancia_km, peso_kg, qtd_itens, valor_pedido |
| Categóricas | trafego, clima, tipo_entrega, regiao |
| Identificação | id_pedido |
| Alvo | tempo_entrega_min |
| Derivada | atrasou |

---

## Etapas do Projeto

O projeto segue um fluxo completo de análise de dados:

1. Exploração inicial da base
2. Estatística descritiva
3. Visualização de dados
4. Análise de correlação
5. Regressão linear simples
6. Tratamento de variáveis categóricas
7. Regressão linear múltipla
8. Avaliação do modelo
9. Validação com treino e teste
10. Interpretação dos resultados

---

## Exploração e Estatística

- Verificação de tipos de dados e estrutura
- Análise de valores nulos
- Cálculo de média, mediana e desvio padrão
- Identificação de possíveis outliers

Interpretação:
- Diferença entre média e mediana pode indicar assimetria
- Desvio padrão alto indica maior variação nos tempos de entrega

---

## Visualização

Principais relações observadas:

- O tempo de entrega aumenta com a distância
- O tempo tende a aumentar com peso e quantidade de itens
- Tráfego alto aumenta o tempo de entrega
- Clima adverso impacta negativamente o tempo
- Entrega expressa reduz o tempo

---

## Correlação

- A variável com maior correlação com o tempo de entrega é distancia_km
- Variáveis com baixa correlação isolada ainda podem contribuir no modelo

Observação:
Correlação não implica causalidade.

---

## Regressão Linear Simples

Modelo baseado apenas na distância:

tempo_entrega_min = a * distancia_km + b

Interpretação:
- a representa o aumento do tempo por quilômetro
- b representa o tempo base

Limitações:
- Não considera fatores como tráfego, clima e tipo de entrega
- Pode apresentar baixa precisão em cenários reais

---

## Tratamento de Variáveis Categóricas

Utilização de:

pd.get_dummies(df, drop_first=True)

Função:
- Converter variáveis categóricas em numéricas
- Evitar multicolinearidade

---

## Regressão Linear Múltipla

Modelo utilizando múltiplas variáveis:

- distancia_km
- peso_kg
- qtd_itens
- trafego
- clima
- tipo_entrega
- regiao

Resultado:
- Melhor desempenho em relação ao modelo simples
- Maior capacidade de explicação dos dados

---

## Avaliação do Modelo

Métricas utilizadas:

- MAE (erro médio absoluto)
- RMSE (raiz do erro quadrático médio)
- R² (coeficiente de determinação)

Interpretação:
- MAE indica o erro médio em minutos
- RMSE penaliza erros maiores
- R² indica o quanto o modelo explica os dados

---

## Interpretação dos Coeficientes

- Coeficientes positivos aumentam o tempo previsto
- Coeficientes negativos reduzem o tempo previsto

Exemplos esperados:
- distancia_km aumenta o tempo
- trafego_alto aumenta o tempo
- clima_forte_chuva aumenta o tempo
- tipo_entrega_expressa reduz o tempo

---

## Treino e Teste

- Divisão dos dados em treino (70%) e teste (30%)
- Comparação de desempenho entre os conjuntos

Interpretação:
- Resultados semelhantes indicam boa generalização
- Diferenças grandes indicam possível overfitting

---

## Conclusão

- O modelo de regressão linear múltipla apresenta melhor desempenho
- A previsão do tempo de entrega é viável com os dados disponíveis
- As variáveis mais relevantes são:
  - distancia_km
  - trafego
  - clima
  - tipo_entrega

Limitações:
- Não considera dados em tempo real
- Pode ter menor precisão em situações extremas

---

## Possíveis Melhorias

- Integração com dados de trânsito em tempo real
- Uso de modelos mais avançados
- Aumento da base de dados
- Inclusão de novas variáveis operacionais

---

## Tecnologias Utilizadas

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

---

## Como Executar

1. Clone o repositório
2. Instale as dependências:

pip install pandas numpy scikit-learn matplotlib seaborn

3. Execute o notebook com Jupyter Notebook ou Jupyter Lab
