Este projeto visa calcular a nota de um filme no dataset IMDB por meio de métodos de regressão baseados em árvores.

# Versões
Matplotlib: versão 3.7.1

Seaborn: versão 0.13.1

Pandas: versão 2.0.3

Numpy: versão 1.25.2

Python: versão 3.10

# Melhor modelo
Para obter os resultados do melhor modelo, sendo df o dataset com treino e teste, deve-se seguir os seguintes passos
```python
# Dividir os dados em treino e teste 

X_train,X_test,y_train,y_test = train_test_split(df.drop('IMDB_Rating',axis=1),df['IMDB_Rating'],test_size=0.2,random_state=42)

# Reseta os indices das linhas
X_train.reset_index(drop=True,inplace=True)
X_test.reset_index(drop=True,inplace=True)

# Aqui ocorre o treino do modelo no código

# Tratamento do teste final
data = pd.DataFrame(data)
data['Runtime']=data['Runtime'].str.strip('min').astype('int64')
data['Released_Year']=data['Released_Year'].astype('int64')
data['Gross']=data['Gross'].str.replace(',','')
data = pd.concat([data, data['Genre'].str.split(', ', expand=True)], axis=1)

# Caso a coluna Genre possua apenas um valor, deve-se preencher outras duas colunas com None:
data[1] = None
data[2] = None
Retira a antiga coluna gênero 
data.drop('Genre',axis=1,inplace=True)

# Por fim, para obter os resultados com o melhor modelo, usa-se as funções

X_d,data_d = pre_processing(X_train, data,'randomforest')
X_dr , data_r = alinha_index(X_d, data_d, 1)


```
