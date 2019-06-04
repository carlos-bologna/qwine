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

