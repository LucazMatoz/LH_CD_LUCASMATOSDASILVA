# LH_CD_LUCASMATOSDASILVA
# Desafio Indicium – Ciência de Dados

Este repositório contém a solução desenvolvida por **Lucas Matos da Silva** para o Desafio de Ciência de Dados da Indicium (2025-11).  
O projeto tem como objetivo analisar uma base de filmes, responder às questões propostas e desenvolver modelos para previsão da nota do IMDB.  
Todo o trabalho foi feito no Google Colab, onde organizei a análise, gráficos e modelagem.
---

## Estrutura do projeto
```
LH_CD_LUCASMATOSDASILVA/
│── notebooks/
│   └── DesafioIndicium.ipynb     # Notebook principal (exportado do Colab)
│
│── reports/
│   └── LH_CD_LUCASMATOSDASILVA.pdf       # Relatório em PDF exportado do notebook
│
│── models/
│   └── modelo_imdb.pkl           # Modelo Random Forest salvo
│
│── requirements.txt              # Lista de dependências
│── README.md                     # Documento atual
```

---

## Como executar

### Opção 1 – Google Colab (recomendada)
1. Acesse https://colab.research.google.com  
2. Faça upload do arquivo `DesafioIndicium.ipynb`  
3. Execute célula por célula  
4. Para testar o modelo salvo, faça upload de `models/modelo_imdb.pkl` e carregue com `joblib.load`  

### Opção 2 – Execução local
1. Clone este repositório:
   ```bash
   git clone https://github.com/seuusuario/LH_CD_LUCASMATOSDASILVA.git
   cd LH_CD_LUCASMATOSDASILVA
   ```
2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```
3. Execute o notebook:
   ```bash
   jupyter notebook notebooks/DesafioIndicium.ipynb
   ```

---

## Entregas realizadas

### 1. Análise Exploratória
- Criação de variáveis auxiliares: ano em formato numérico, duração em minutos, faturamento numérico e gênero principal.  
- Estatísticas descritivas e análise de valores ausentes.  
- Visualizações: distribuição das notas do IMDB, matriz de correlação, boxplots por gênero, evolução temporal das notas e relação entre votos e faturamento.  

### 2. Questões propostas
- **(a) Filme recomendado:** recomendação baseada em filmes com altas notas e grande volume de votos, como *The Godfather* e *The Dark Knight*.  
- **(b) Fatores de faturamento:** os principais foram número de votos, ano de lançamento, nota do IMDB, metascore e algumas categorias de gênero e certificado.  
- **(c) Coluna Overview:** aplicação de TF-IDF e regressão logística resultou em acurácia próxima de 0,38 contra baseline de 0,29, mostrando que a sinopse auxilia parcialmente na previsão de gênero.  

### 3. Modelagem da nota IMDB
O problema foi tratado como regressão.  
Variáveis utilizadas: metascore, votos, faturamento, duração, ano, gênero principal e certificado.  
Foram testados dois modelos:
- **Ridge Regression:** modelo linear regularizado, utilizado como referência.  
- **Random Forest Regressor:** modelo com melhor desempenho ao lidar com relações não lineares.  

As métricas avaliadas foram RMSE (erro médio em pontos de nota) e R² (explicação da variabilidade). O Random Forest apresentou os melhores resultados.

### 4. Predição prática
Aplicação ao filme *The Shawshank Redemption*, com previsão próxima de 8.8, valor consistente com a avaliação real.

### 5. Modelo salvo
O modelo final está disponível em `models/modelo_imdb.pkl`. Pode ser carregado com:
```python
import joblib
model = joblib.load("models/modelo_imdb.pkl")
```

---

## Requisitos
As bibliotecas necessárias estão listadas em `requirements.txt`.  
Principais pacotes utilizados:
- pandas  
- numpy  
- matplotlib  
- seaborn  
- scikit-learn  
- joblib  

---

## Autor
Trabalho desenvolvido por **Lucas Matos da Silva**  
Candidato ao programa de bolsas em Ciência de Dados.
