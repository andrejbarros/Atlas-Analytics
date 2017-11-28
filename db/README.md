# Banco de Dados do Atlas da Notícia

O baco de dados do **Atlas da Notícia** foi concebido para ser completo e, ao mesmo tempo, fácil de utilizar. Tabelas em Excel, Google Sheets e CSV são fáceis, mas, devido ao volume de informações, podem ser uma alternativa lenta para muitos computadores, além de trabalhosa (são diversos arquivos).

Dentre muitas opções hoje em dia para estruturar bancos de dados, escolhemos fazer em SQLite, para que fosse possível que qualquer um explorasse os dados utilizando softwares gratuitos, comuns e de fácil instalação.

Para visualizar e analisar este conjunto de dados, recomendamos o uso do [DB Browser](http://sqlitebrowser.org/), que possui software para Mac OSX, Linux e Windows. Existem também outras opções, como [SQLite Studio](https://sqlitestudio.pl/index.rvt) 

## Geral

Para acessar o banco de dados do Atlas da Notícia, inicialize o DB Browser e abra o arquivo `atlas.db`. 

Esse arquivo contém todas as tabelas brutas utilizadas no Atlas, assim como tabelas do [Índice de Desenvolvimento Humano Municipal](http://atlasbrasil.org.br/2013/) para eventual cruzamento de informações. 

Ele também contém *views*, ou seja, recortes dos dados já realizados pela equipe do Volt Data Lab, como total consolidado de veículos, ou apenas de jornais e apenas de online, ou ainda a taxa a cada 100 mil habitantes.

Para visualizar as tabelas e views,  vá para a aba *Execute SQL*, digite: `SELECT * FROM nome_tabela` e pressione F5 ou Ctrl+R. Por exemplo, para acessar os dados contidos apenas no levantamento do Atlas, digite: `SELECT * FROM atlas`. Para ver o número de jornais impressos mapeados por regiões metropolitanas, digite: SELECT * FROM atlas_slim_rm_idhm_jornal`, e assim por diante.
Isso lhe dará acesso a todas as informações necessárias.

Para filtrar as informações das tabelas, por exemplo, apenas por Estado, você pode rodar o comando: `SELECT * FROM atlas where UF = "MT"`, o que lhe retornaria os resultados relativos ao Mato Grosso da tabela com os levantamentos do atlas. 

Para ordenar os resultados em ordem crescente ou descrescente de uma coluna, acrescente ao final do código: `ORDER BY nome_coluna ASC` para crescente e `ORDER BY nome_coluna DESC` para decrescente. No exemplo anterior, para visualizar a lista dos veículos mapeados no Mato Grosso por ordem alfabética, o comando seria: `SELECT * FROM atlas where UF = "MT" ORDER BY nome_coluna ASC` 

Se quiser baixar as visualizações em .csv, clique em  `Export to CSV`.




