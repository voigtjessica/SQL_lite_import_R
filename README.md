# SQL_lite_import_R
Working with big repositories using SQL lite in R

*Fonte:* [https://www.r-bloggers.com/r-and-sqlite-part-1/](https://www.r-bloggers.com/r-and-sqlite-part-1/)

### Sobre SQL lite

SQL lite é um open source que utiliza bases relacionais e foi desenhada para ser utilizada em outras aplicações. Relacional significa que, ao invés de armazenar os dados em uma única tabela como faz o Excel (ou como costumamos trabalhar no próprio R), os dados são armazenados em diferentes tabelas que se relacionam umas com as outras. Assim, o dado é normalizado e a redundância é reduzida.

Com o SQL lite as bases são registradas dentro da aplicação.

#### Instalando o pacote e criando a base de dados

Para criar a base de dados, use a função dbConnect() do RSQLite. Se a base de dados ainda não exsite, uma é criada. O comando abre uma conexão com a Test.sqlite database e , quando esta ainda não existe, cria no diretório de trabalho do R.

```R
install.packages("sqlfd")
library(sqldf)

db <- dbConnect(SQLite(), dbname="nome_da_tabela_que_eu_quiser")

setwd("dir")

read.csv.sql("arquivo.csv", sql = "CREATE TABLE arquivo AS SELECT * FROM file", dbname = "nome_da_tabela_que_eu_quiser")

# sep = separador, eol = "caractere que quebra a linha"

```
Você pode apensar quantas tabelas forem necessárias no seu banco SQL. 
Daí você pode salvar o SQL como um objeto Rdata ou salvar cada arquivo SQL separadamente.
