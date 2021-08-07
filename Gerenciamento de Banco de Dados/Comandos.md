# 1 - Listar Banco de dados existentes no sistemas 
	show dbs
# 2 - Inicializar um novo Banco de Dados
	use <meuBanco>
# 3 - Checar o Banco Atual
	db
# 4 - Inserindo Dados no banco 
	db.banco3.insertOne({nome: "Julio Paschoal", idade: 35})
# 5 - Listar Todos os dados do banco 
	db.banco3.find()
# 6 - Criando Collections
	db.<collection>.insertOne({<dados>})
# 7 - Listando dados específicos com o comando find 
	db.<collection>.find({nome:"Julio"}}
# 8 - A Função Pretty 
	 db.pessoas.find().pretty()
# 9 - Criação de Collection Implicita
	db.createCollection("nome",{opeções})
# 10 - Limitando o Numero de Registro em uma Collection
	db.createCollection("minhaCollection",{capped: true, size: 1000, max: 3})
# 11 - Exibindo todas as Collections 
	show collections
# 12 - Romover uma Collection
	db.<collection>.drop()
# 13 - Removendo Banco de Dados
	db.dropDatabase()
# 14 - Importar banco de Dados
	mongoimport<arquivo> -d <database> -c  <collection>
# 15 - Exportar banco de Dados
	mongoexport -c <collection> -d <database> -o <nomeBanco.json>
# 16 - Exportar Muitas Collections
	mongodump -d <banco> -o <diretorio>
# 17 - Importando dados do Mongodump
	mongorestore <diretorio>
# 18- Minitoramento do MogoDB
	mongostat
# 19- Removendo todos o Banco de uma x so
	Mongo().getDBNames().forEach(function(db) {
		if(['admin', 'config', 'local'].indexOf(db) <0) {
			Mongo().getDB(db).dropDatabase();
			}
	});