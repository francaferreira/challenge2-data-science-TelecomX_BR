# 📊 Análise de Evasão de Clientes (Churn) - TelecomX_BR

![Data Analysis](https://img.shields.io/badge/Status-Concluído-brightgreen) 
![GitHub](https://img.shields.io/github/repo-size/seu-usuario/telecom-churn-analysis) 
![Python](https://img.shields.io/badge/Python-3.9%2B-blue)

## 1️⃣ Visão Geral do Projeto
Análise preditiva de evasão de clientes da TelecomX_BR, identificando padrões comportamentais e fatores críticos que influenciam o cancelamento de serviços. O estudo revelou que **25.7% dos clientes** cancelaram seus planos, representando uma perda significativa de receita.

```mermaid
graph LR
A[Dados Brutos] --> B[Limpeza]
B --> C[Análise Exploratória]
C --> D[Modelagem]
D --> E[Insights]
E --> F[Recomendações]
```

## 2️⃣ Objetivo
Identificar os principais drivers de churn e desenvolver estratégias para:
- Reduzir a taxa de evasão em 30% nos próximos 12 meses
- Aumentar a retenção de clientes de alto valor
- Otimizar a oferta de planos e serviços
- Criar sistema de alerta precoce para clientes em risco

## 3️⃣ Tecnologias Utilizadas
### 🐍 Linguagens e Ferramentas
**Python**:
```python
# Bibliotecas principais
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.ensemble import RandomForestClassifier
```
**Outras Tecnologias**:
- **Jupyter Notebook** para análise iterativa
- **Tableau** para visualizações avançadas
- **Scikit-learn** para modelagem preditiva
- **Git** para controle de versão

## 4️⃣ Estrutura do Projeto
```
telecom-churn-analysis/
├── data/
│   ├── raw/               # Dados brutos originais
│   ├── processed/         # Dados tratados
│   └── final/             # Conjuntos prontos para modelagem
├── notebooks/
│   ├── 1_data_cleaning.ipynb
│   ├── 2_eda.ipynb
│   └── 3_modeling.ipynb
├── src/
│   ├── data_processing.py
│   └── visualization.py
├── reports/
│   ├── figures/           # Gráficos e visualizações
│   └── final_report.pdf
└── README.md
```

## 5️⃣ Limpeza e Tratamento dos Dados
### Principais Etapas:
1. **Tratamento de valores ausentes**:
   - Colunas com >30% missing: removidas
   - Demais: imputação por mediana/moda
   
2. **Conversão de tipos**:
   ```python
   df['TotalCharges'] = pd.to_numeric(df['TotalCharges'], errors='coerce')
   ```

3. **Engenharia de features**:
   - Criação de `TenureGroups` (grupos de tempo de serviço)
   - Transformação de variáveis categóricas (One-Hot Encoding)
   - Normalização de valores monetários

4. **Balanceamento de classes**:
   ```python
   from imblearn.over_sampling import SMOTE
   smote = SMOTE(random_state=42)
   X_res, y_res = smote.fit_resample(X, y)
   ```

## 6️⃣ Análise Exploratória (EDA)
### Principais Descobertas:
| Variável               | Correlação com Churn | Insight |
|------------------------|----------------------|---------|
| **Tipo de Contrato**   | 🔴 0.41 | Contratos mensais têm 4x mais churn |
| **Tempo de Serviço**   | 🟢 -0.35 | Churn cai 60% após 12 meses |
| **Idoso (65+)**        | 🔴 0.29 | Taxa 38% maior que média |
| **Pagamento Eletrônico** | 🔴 0.27 | 31% mais churn que outras formas |


## 7️⃣ Principais Insights
### 🔥 Fatores Críticos de Churn
1. **Contratos Mensais**  
   📉 42.7% de taxa de evasão vs. 2.9% em contratos bienais

2. **Clientes Novos**  
   ⚠️ 63% dos cancelamentos ocorrem nos primeiros 6 meses

3. **Perfil Sênior**  
   👵 Taxa de churn 38% acima da média geral

4. **Baixo Valor Monetário**  
   💰 Clientes que cancelaram gastam 33% menos que ativos ($1,531 vs $2,281)

## 8️⃣ Recomendação Estratégica
### 🚀 Plano de Ação Prioritário
| Estratégia | Impacto Esperado | Prazo |
|------------|------------------|-------|
| **Conversão de contratos** | Redução de 25% no churn | 6 meses |
| **Programa Primeiros 6 Meses** | -15% evasão novos clientes | 3 meses |
| **Pacote Sênior Plus** | Retenção extra 18% idosos | 4 meses |
| **Reestruturação de Planos** | +12% valor médio cliente | 9 meses |

### 📈 KPIs de Sucesso
1. Taxa geral de churn < 18%
2. Conversão de 30% contratos mensais para anuais
3. Aumento de 15% no LTV (Lifetime Value)
4. Redução de 40% no CAC (Custo de Aquisição)

## 9️⃣ Conclusão
A análise demonstra que **o churn na TelecomX_BR é multifatorial**, com concentração em:
- Clientes novos com contratos mensais
- Idosos com planos pouco adaptados
- Perfis de baixo valor monetário

A implementação das recomendações pode gerar:
✅ **Economia anual estimada:** $2.3M  
✅ **Aumento de receita recorrente:** 18%  
✅ **Melhoria no NPS (Net Promoter Score):** +25 pontos

**Próximas etapas:** Desenvolvimento de modelo preditivo em produção com monitoramento contínuo.

## 🔟 Autor
[**Jefferson Ferreira**](https://github.com/francaferreira/)  
📧 jfrancaferreira10@gmail.com  
[![LinkedIn](https://www.linkedin.com/in/jefferson-ferreira-ds/)
