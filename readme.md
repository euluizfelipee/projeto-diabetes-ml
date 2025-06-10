# 📊 Predição de Diabetes Mellitus com Machine Learning

## 📌 Descrição

Este projeto tem como objetivo prever a ocorrência de **diabetes tipo 2** em pacientes a partir de dados clínicos, utilizando algoritmos de **aprendizado de máquina supervisionado**. O estudo é baseado no **dataset Pima Indians Diabetes**, amplamente utilizado para benchmark de modelos preditivos na área de saúde.

## 🎯 Objetivos

* Identificar variáveis clínicas mais relevantes para o diagnóstico de diabetes
* Comparar o desempenho dos modelos:

  * **Regressão Logística**
  * **Random Forest**
  * **Support Vector Machine (SVM)**
  * **XGBoost**
* Avaliar o desempenho dos modelos com as métricas:

  * **Acurácia**, **Precisão**, **Recall**, **F1-Score**
  * **AUC-ROC**

## 🧠 Tecnologias e Bibliotecas

* Python 3.x
* `pandas`, `numpy`
* `scikit-learn`
* `xgboost`
* `joblib`

## 📂 Organização do Projeto

```
📁 projeto-diabetes-ml/
🗋 trabalhoartigo.pdf              # Artigo acadêmico com análise comparativa
📄 diabetes_predicao.py           # Script completo com pipeline de ML
📊 resultados_modelos.csv         # Resultados salvos em CSV
🔐 melhor_modelo.pkl              # Modelo treinado e salvo com melhor desempenho (XGBoost)
📄 README.md                      # Este arquivo
```

## 📊 Dataset

* **Nome:** Pima Indians Diabetes
* **Fonte:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/529/pima+indians+diabetes)
* **Tamanho:** 768 registros
* **Atributos:**

  * Pregnancies, Glucose, BloodPressure, SkinThickness, Insulin, BMI, DiabetesPedigreeFunction, Age
  * `Outcome` (variável-alvo: 0 = não diabético, 1 = diabético)

## 🔍 Etapas do Projeto

### 1. Pré-processamento

* Substituição de zeros inválidos por NaN
* Imputação com **mediana**
* Normalização dos dados com `StandardScaler`
* Divisão treino/teste estratificada (80%/20%)

### 2. Treinamento de Modelos

* Otimização de hiperparâmetros via **GridSearchCV**
* Validação cruzada (5-folds)
* Avaliação no conjunto de teste com métricas classificatórias

### 3. Resultados

| Modelo              | Acurácia | Precisão | Recall | F1-Score | AUC-ROC    |
| ------------------- | -------- | -------- | ------ | -------- | ---------- |
| XGBoost             | 78.57%   | 76.92%   | 60.00% | 67.42%   | **82.14%** |
| Random Forest       | 77.92%   | 75.00%   | 58.33% | 65.63%   | 81.25%     |
| SVM                 | 76.62%   | 72.73%   | 56.67% | 63.64%   | 79.17%     |
| Regressão Logística | 75.32%   | 70.59%   | 53.33% | 60.71%   | 77.08%     |

### 4. Importância das Variáveis (XGBoost)

* **Glicose:** 37.2%
* **IMC (BMI):** 18.5%
* **Idade:** 14.1%

Essas variáveis se destacaram como as mais influentes na predição da doença.

## 💾 Como Executar

```bash
# Clonar o repositório
git clone https://github.com/seuusuario/projeto-diabetes-ml.git
cd projeto-diabetes-ml

# Instalar dependências
pip install -r requirements.txt

# Executar o script
python diabetes_predicao.py
```

## 📅 Arquivos Gerados

* `resultados_modelos.csv`: Tabela com desempenho de todos os modelos
* `melhor_modelo.pkl`: Arquivo com o modelo treinado (XGBoost), pronto para uso/predição

## 👨‍💼 Autores

* **Luiz Felipe Freire Miguel**
* **José Mario da Silva Santos**

## 📚 Referências

* Brownlee, J. (2016). *Pima Indians Diabetes Dataset*. UCI Machine Learning Repository.
* IDF Diabetes Atlas. 10ª ed. Brussels: International Diabetes Federation, 2021.
* Chen, T. & Guestrin, C. (2016). *XGBoost: A Scalable Tree Boosting System*.
* Berry, M. W. (2019). *Machine Learning in Medicine: A Primer for Physicians*.
