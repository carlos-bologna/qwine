# Qualidade do Vinho

### O problema
O presente problema se refere aos dados de vinhos portugueses "Vinho Verde", que possuem
variantes de vinho branco e tinto. Devido a questões de privacidade, apenas variáveis
físico-químicas (input) e sensoriais (output) estão disponíveis (por exemplo, não há dados
sobre tipo de uva, marca do vinho, preço de venda, etc).

### Objetivo
Criar um modelo para estimar a qualidade do vinho.
Informação sobre os atributos
Variáveis input (baseado em testes físico-químicos):
1. Tipo
2. Acidez fixa
3. Volatilidade da acidez
4. Ácido cítrico
5. Açúcar residual
6. Cloretos
7. Dióxido de enxofre livre
8. Dióxido de enxofre total
9. Densidade
10. pH
11. Sulfatos
12. Álcool
Variável output (baseado em dado sensorial):
13. Qualidade (score entre 0 and 10)

# Preparando o Ambiente

  1. Certifique-se que o Anaconca ete instalado. Para instalar: www.continuum.io/downloads
  2. Clone este repositório: 
  ```
  $ git clone https://github.com/carlos-bologna/qwine.git
  ```
  3. Crie um ambiente virtual para este projeto: 
  ```
  $ conda create -n qwine python=3.6
  ```
  4. Ative o ambiente criado: 
  ```
  $ source activate qwine
  ```
  5. Instale os pacotes utilizados a partir da lista contida no arquivo requirements.txt
  ```
  $ conda install --file requirements.txt
  ```
  6. Adicione este ambiente ao Jyputer Notebook: 
  ```
  $ conda install ipykernel
  $ python -m ipykernel install --user --name=qwine
  ```
  7. Agora você já pode acessar o Jupyter Notebook
  ```
  $ jupyter notebook
  ```
  ***Atenção**: não esqueça de mudar o kernel do Jupyter Notebook para "qwine" que você acabou de adicionar.

# Anaconda
Abaixo, alguns comandos úteis que você precisará usar caso faça alguma alteração no código.
Por exemplo, se utilizar um novo pacote Python, atualize o arquivo requirements.txt após ter instalado o pacote.
```
$ conda list -e > requirements.txt
```

# Estratégia
Logo de início observamos o quão desbalanceado é o dataset em relação às classes da variável resposta. Tamanha discrepância impede inclusive a aplicação de técnicas tais como downsample a fim de balanceá-lo.
Sendo assim, decidimos agrupar as classes resultando nas seguintes novas classificações de qualidade do vinho:
* Ruim
* Regular
* Bom

Após essa decisão, a otimização da acurácia pareceu ser a mais adequada, além do quê, a aplicação do negócio ainda é desconhecida.

Testamos dois algoritmos: Random Forest e XGBoost. O primeiro apresentou melhor acurácia na base de teste, isto é, uma fatia do dataset foi separada logo no início, para ser utilizada como uma espécie simulação de uma base em produção. Técnica exaustivamente utilizada em machine learning, contudo, é extremamente importante que esta base .....


# Propostas para Melhorar o Modelo

O modelo apresentado ainda que pudesse ser utilizado em produção, dependendo da necessidade do negócio ou da acurácia atual do processo, ele ainda pode ser bastante melhorado, contudo, acredito que já esteja em uma fase que consiga atingir o objetivo proposto pela avaliação.

Algumas ações que poderiam ser aplicadas a fim de melhorarmos o modelo:

* Balancear as classes da variável respostas de modo que seja igualmente distribuída (downsample).
* Dependendo do negócio, adotar apenas as classes vinho "bom" e vinho "ruim", transformando o modelo em binário e aumentando sua acurácia.
* Tratar outliers de algumas variáveis explicativas.
* Excluir do modelo variáveis de menores importâncias, embora a árvore de decisão acaba fazendo isso intrinsicamente, as vezes o modelo melhora com a retirada delas.
* Criar novas variáveis com a combinação de algumas delas.
* Excluir variáveis altamente correlacionadas.
* Otimizar os hiperparâmetros do algoritmo XGBClassifier (embora esteja no código, eles não foram parametrizados).
* Fazer ensemble dos modelos com Random Forest e XGBClassifier, como Stacking por exemplo, mas dependerá também do ambiente em produção, pois o modelo com ensemble tende a ficar bem mais pesado e as vezes inviável em produção.
