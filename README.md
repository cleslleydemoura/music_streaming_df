<h1>Projeto DataFrame com tema Streaming Musical</h1>

<p> Este projeto foi desenvolvido em Python utilizando a biblioteca Pandas com manipulação do DataFrame, informações importantes sobre cada lançamento agrupadas em uma tabela bem estruturada e informativa, como nome das músicas, artistas, albúns, gênero, ano de lançamento e duração da música.</p>

<p> Ao decorrer do projeto deixei comentários e textos explicativos sobre os métodos, suas funções e funcionamento.</p>
<p>Arquivos .py e .ipynb anexados neste projeto.</p>


```
# Utilizando a biblioteca Pandas, será feito um DataFrame de uma plataforma de Streaming de Música.
# Editor de código: Google Colab.

import pandas as pd # Chamando a biblioteca pandas

nome_musicas = ["Sick Love", "WORTH IT", "DICE", "Midas Touch", "Nothing", "Californication", "Controllah", "The Blonde", "Ma Boo", "Wae ironi", "Yayaya"]
# Essa variável é uma lista que contém os nomes das músicas.
artistas = ["Red Hot Chilli Peppers", "Rex Orange County", "NMIXX", "Kiss Of Life", "Kiss Of Life", "Red Hot Chilli Peppers", "Gorillaz", "TV Girl", "T-ARA", "T-ARA", "T-ARA"]
# É uma lista que armazena os nomes dos artistas correspondentes às músicas.
genero = ["Rock/Alternative", "Pop", "K-pop", "Pop", "Pop", "Rock/Alternative", "Rock/Alternative", "Rock", "Pop", "Pop", "Pop"]
# Essa é uma lista que armazena os gêneros musicais das músicas. Cada elemento da lista corresponde ao gênero de uma música na mesma posição na lista 'nome_musicas'.
nome_album = ["The Getaway", "who Cares?", "ENTWURF", "Midas Touch", "Midas Touch", "Californication", "Cracker Island", "French Exit", "Temptastic", "Temptastic", "Temptastic"]
# Esta lista contém os nomes dos álbuns aos quais as músicas pertencem.
ano_lancamento = [2016, 2022, 2022, 2024, 2024, 1999, 2023, 2024, 2011, 2011, 2011]
# Armazena os anos de lançamento das músicas.
duracao_musica = [3.4, 2.4, 2.4, 2.4, 3.3, 5.2, 2.3, 3.4, 3.2, 3.5, 3.2]
# É uma lista que contém a duração de cada música em segundos.

# --------------------------------------------------------------------------------------------------------------------------------------------
# 'dados_musicais': Esse é um dicionário que combina todas as listas em um único conjunto de dados.
#  Cada chave do dicionário representa uma coluna do DataFrame, e os valores associados a essas chaves são as listas de dados correspondentes.
#  Isso é útil para criar facilmente um DataFrame Pandas.
# --------------------------------------------------------------------------------------------------------------------------------------------
dados_musicais = {
    'Música': nome_musicas,
    'Artista': artistas,
    'Álbum' : nome_album,
    'Ano de lançamento': ano_lancamento,
    'Duração (segundos)' : duracao_musica,
    'Gênero': genero
    # Aqui está sendo definido um nome para as colunas.
}
```
<p>• Utilizando a biblioteca Pandas, foi feito um DataFrame de uma plataforma de Streaming de Música que armazena informações sobre músicas, como: nome da música, artista, álbum, ano de lançamento, duração da música em segundos e gênero.</p>
<p>• Após criados os itens da lista, todos os dados são combinados e armazenados dentro do dicionário 'dados_musicais ', onde os valores de cada lista são associados aos dados correspondentes.</p>

<h1>1. Apresente em tela (output) toda a base de dados.</h1>

```
# 1. Apresente em tela (output) toda a base de dados.
print("1. Apresente em tela (output) toda a base de dados.")
musica_df = pd.DataFrame(dados_musicais) # Criando um DataFrame a partir do dicionário dados_musicais
print(musica_df) # Retorna na tela os itens presentes no DataFrame.
display(musica_df) # Retorna uma tabela estilizada dos itens presentes no DataFrame.
```

<p>• Na linha 3 do código, está sendo criado um DataFrame (musica_df) usando a biblioteca Pandas do Python. O DataFrame é criado a partir do dicionário 'dados_musicais', que contém todas as informações sobre as músicas. Nas linhas seguintes o Dataframe está sendo mostrado ao usuário atráves dos métodos:</p>
<p>      - print(musica_df) : Imprime na tela o DataFrame 'musica_df'.</p>
<p>      - display(musica_df) : Imprime o DataFrame na tela, mas de uma forma estilizada, sendo uma tabela bem formatada para uma visualização mais clara dos dados.</p>

<h1>2. Apresente o tamanho do seu dataframe (quantas colunas x linhas).</h1>

```
# 2. Apresente o tamanho do seu dataframe (quantas colunas x linhas).
print("2. Apresente o tamanho do seu dataframe (quantas colunas x linhas).")
print(df.shape) #Isso imprimirá o tamanho do DataFrame na tela (colunas X linhas).
```

<p>• O método 'df.shape' retorna uma tupla que contém o número de linhas e o número de colunas do DataFrame.</p>
<p>• Ao usar print(musica_df.shape) está sendo mostrado essa tupla na tela, onde o primeiro valor é o número de linhas e o segundo valor é o número de colunas do DataFrame.</p>

<h1>3. Acesse a linha (x) e apresente em tela todas as características do item.</h1>

```
# 3. Acesse a linha (x) e apresente em tela todas as características do item.
print("3. Acesse a linha (x) e apresente em tela todas as características do item.")
df = pd.DataFrame(dados_musicais) # Criando um DataFrame a partir do dicionário dados_musicais
line = df.iloc[4] # O método df.iloc[] irá procurar pela linha correspondente ao index colocado dentro dos cochetes.
print(line)

# Utilizando o método 'df.info':
print("3. Acesse a linha (x) e apresente em tela todas as características do item (usando df.info()):")
print(df.info())
```

<p>• Na linha 4, através do método 'line = df.iloc[x] ' estamos acessando uma linha específica do DataFrame.</p>
<p>• Utiliza-se 'df.iloc[x] ' para acessar linhas por meio de sua posição numérica, onde '*[x]*' indica que queremos acessar alguma linha específica do DataFrame. O conteúdo dessa linha é então armazenado na variável line.</p>

```Obs*: Não se esqueça de que a indexação começa em 0.```

<p>• O método 'df.info() ' cria um resumo das informações, incluindo o tipo de dados de cada coluna e a quantidade de valores não nulos.</p>

<h1>4. Verifique se o dataframe está vazio.</h1>

```
# 4. Verifique se o dataframe está vazio.
# Utilizando Do-WHILE: imprimir na tela "O DataFrame está vazio!" ou "O DataFrame possui itens."
print("4. Verifique se o dataframe está vazio.")

# Utilizando  do-while
while musica_df.empty:
    print("O DataFrame está vazio!")
    break
else:
    print("O DataFrame possui itens.")
print()

# Utilizando o método 'df.empity'
musica_df = pd.DataFrame()
```

<p>• Através do método 'do-while ', utliza-se um loop while com a condição 'empty_df.empty '. Essa condição verifica se o DataFrame está vazio. Se estiver vazio, o loop será executado.</p>
<p>• A inclusão um break após a impressão da mensagem faz com que o loop seja interrompido imediatamente após a primeira vez que o código é rodado, independentemente se o DataFrame está vazio ou não. Logo, o loop só será executado uma única vez.</p>
<p>• Através do método 'df.empity ', ele retornará na tela se o DataFrame está vazio ou se ele possui itens (true ou false).</p>

<h1>5. Apresente em tela os 5 primeiros registros da base de dados.</h1>

```
# 5. Apresente em tela os 5 primeiros registros da base de dados.
print("5. Apresente em tela os 5 primeiros registros da base de dados.")
head = pd.DataFrame(dados_musicais) # Nessa linha, um DataFrame chamado 'head' está sendo criado a partir dos dados contidos na variável 'dados_musicais'.
print(musica_df.head()) # Esta linha imprime os cinco primeiros registros do DataFrame 'head' na tela.
print()
```

<p>• O método '.head() ' é aplicado ao DataFrame para retornar apenas os primeiros cinco registros da tabela.</p>

<h1>6. Exclua um item (linha) de sua base de dados.</h1>

```
# 6. Exclua um item (linha) de sua base de dados.
print("6. Exclua um item (linha) de sua base de dados.")
musica_df = musica_df.drop(6) # O índice escolhido aqui foi o 6, porém pode ser qualquer índice desde que ele exista no código.
print(musica_df) # Exibindo novamente a tabela com a alteração já feita.
print()
```

<p>• Na linha 3, você define a variável 'delete_indice = ' como 6. Isso significa que será excluído a linha com o índice 6 do DataFrame.</p>
<p>• Na linha 4, está sendo excluído uma linha do DataFrame, apartir do método '.drop() '.</p>
<p>• Na linha 5, a tabela está sendo impressa na tela. Agora com a ausência do índice que foi excluído.</p>

<h1>7. Adicione um item (linha) na sua base de dados.</h1>

```
# 7. Adicione um item (linha) na sua base de dados.
print("7. Adicione um item (linha) na sua base de dados.")
new_item = { # Adição de novo item ao DataFrame.
    'Música': "Internet",
    'Artista': "Terno Rei",
    'Álbum' : "Gêmeos",
    'Ano de lançamento': "2022",
    'Duração (segundos)' : '2.4',
    'Gênero': "Alternative"
}

musica_df = pd.concat([musica_df, pd.DataFrame(new_item, index=[0])], ignore_index=True) # Utilização do método pd.concat().
                                                        # Vale lembrar que o index sempre começa em zero e não em um.
print(musica_df)
```

<p>• Em 'new_item ' stá sendo definindo um novo item (ou linha) que será adicionado ao DataFrame que contém os valores para cada coluna do DataFrame. Cada chave representa uma coluna e seu valor é o conteúdo que será adicionado a essa coluna para a nova linha.</p>
<p>• A função 'pd.concat() ' é usada para concatenar o DataFrame existente '(musica_df) ' com o novo DataFrame contendo o novo item.</p>
<p>• Na linha 12 está sendo criado um novo DataFrame contendo os dados do novo item. O 'index=[0] ' é utilizado para que o novo DataFrame tenha um índice 0, que é necessário para concátenação correta dentro do DataFrame já existente.</p>

<h1>8. Transponha a coluna para a linha em sua base de dados.</h1>

```
# 8. Transponha a coluna para a linha em sua base de dados.
#refazer.
print("8. Transponha a coluna para a linha em sua base de dados.")
df = pd.DataFrame(dados_musicais)
df_transpor = df.T # Aqui ocorre a transposição do DataFrame original df, convertendo as colunas em linhas e as linhas em colunas.
print(df_transpor)
display(df_transpor)
```

<p>• A transposição é feita usando o método T '(método df.transpouse) ' do Pandas, que converte as colunas do DataFrame em linhas e as linhas em colunas. Isso é feito atribuindo o resultado da transposição a um novo DataFrame chamado df_transpor.</p>
<p>• Logo em seguida é impresso através dos métodos 'print() ' e 'display() ', mostrando a transposição.</p>

<h1>9. Apresente em tela somente a 1ª e a 2ª coluna (rótulo) da base de dados.</h1>

```
# 9. Apresente em tela somente a 1ª e a 2ª coluna (rótulo) da base de dados.
print("9. Apresente em tela somente a 1ª e a 2ª coluna (rótulo) da base de dados.")
display(df.loc[:, ['Música', 'Artista']])
print()
# df.loc[]: Esse é um método de indexação do pandas.
# ':' representa todas as linhas, ou seja, ele irá selecionar todas as linhas.
```

<p>• A linha 'display(df.loc[:, ['Música', 'Artista']]) ' exibe as colunas selecionadas do DataFrame df. Aqui, 'df.loc[:, ['Música', 'Artista']] ' seleciona todas as linhas '(:) 'e apenas as colunas 'Música' e 'Artista'.</p>
<p>• Essas colunas são então mostradas na tela utilizando a função display, mostrando somente as duas colunas escolhidas.</p>

<h1>10: Informe como foi desenvolvido o Projeto.</h1>


<p>Observa-se neste projeto com o tema de Streaming de música, desenvolvido em Python utilizando a biblioteca Pandas com manipulação do DataFrame, informações importantes sobre cada lançamento agrupadas em uma tabela bem estruturada e informativa, como nome das músicas, artistas, albúns, gênero, ano de lançamento e duração da música. Streaming de música foi o tema escolhido por mim pois música é uma das coisas que eu mais gosto e não consigo passar um dia sequer sem escutar uma musiquinha enquanto faço meus afazeres do dia a dia. É algo que me mantém minha mente sã, então coloquei as músicas as que eu mais escutei recentemente e retirei as informações sobre as músicas do Spotify.</p>

<p>Durante o projeto, desenvolvi aplicações para as perguntas propostas. Cada informação atribuída dentro do dicionário representa uma característica sobre uma música. Utilizando os métodos do Pandas e de programação em geral, pude obter mais informações sobre o código, desde seu tamanho, métodos de acesso a partes específicas do código, transposição de linhas e colunas, inserção de novos itens e visualização aprimorada de partes do código. O código foi desenvolvido com base em meus notebooks anteriores desenvolvidos durante as aulas de Estrutura de Dados I ministradas pela professora Kadidja Valéria, livros que foram apresentados durante as aulas e pesquisas sobre os métodos dentro do site Pandas Documentation.</p>

<p>Pude, durante a criação desse DataFrame, entender como usar os métodos da linguagem Python e também, através do desenvolvimento deste projeto, escrever o que aprendi utilizando os textos e comentários deixados ao decorrer do código em cada questão. Isso pode me auxiliar em criações de DataFrames futuros e também ajudar alguém que está sendo introduzido agora ao Pandas no Python.</p>

