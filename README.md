# Case iFood - Predição de Conversão de Ofertas

Projeto de Machine Learning para prever se uma oferta será completada por um cliente, utilizando dados de ofertas, perfil de clientes e transações.

---

## 📁 Estrutura do Projeto

```
ifood-case/
├── data/
│   ├── raw/                    # Dados brutos (JSON)
│   │   ├── offers.json         # Informações das ofertas
│   │   ├── profile.json        # Perfil dos clientes
│   │   └── transactions.json   # Transações e eventos
│   └── processed/              # Dados processados (Parquet)
│       └── data.parquet        # Dataset final integrado
├── notebooks/
│   ├── 1_data_processing.ipynb # Processamento e limpeza de dados
│   └── 2_modeling.ipynb        # Modelagem e avaliação
├── presentation/               # Materiais de apresentação
├── requirements.txt            # Dependências do projeto
└── README                      
```

---

## 🔧 Requisitos

### Ambiente Recomendado:
- **Databricks** (ambiente nativo do projeto)
- **Python 3.10+**

### Instalação Local (Opcional):
Se quiser executar localmente fora do Databricks, é necessário ter o Spark instalado:

```bash
pip install -r requirements.txt
```

---

## 🚀 Como Executar

### **Passo 1: Preparar os Dados**

Certifique-se de que os arquivos de dados brutos estão na pasta correta:
```
data/raw/
  ├── offers.json
  ├── profile.json
  └── transactions.json
```

### **Passo 2: Processamento de Dados**

Execute o notebook **`1_data_processing`**:

```python
# Caminho: /notebooks/1_data_processing
```

**Tempo estimado:** ~2-5 minutos

---

### **Passo 3: Modelagem e Avaliação**

Execute o notebook **`2_modeling`**:

```python
# Caminho: /notebooks/2_modeling
```

**Tempo estimado:** ~5-10 minutos (GridSearch pode variar)

---

## 📊 Resultados Esperados

### **Melhor Modelo: XGBoost**

| Métrica | Valor |
|---------|-------|
| **Accuracy** | 80.2% |
| **AUC-ROC** | 0.895 |
| **Precision** | 76.7% |
| **Recall** | 81.5% |
| **F1-Score** | 79.1% |

---

## 📝 Ordem de Execução

**IMPORTANTE:** Execute os notebooks nesta ordem:

1. **`1_data_processing`** (obrigatório primeiro)
   - Gera o arquivo `data/processed/data.parquet`
   
2. **`2_modeling`** (depende do Passo 1)
   - Requer que o arquivo Parquet exista

---
