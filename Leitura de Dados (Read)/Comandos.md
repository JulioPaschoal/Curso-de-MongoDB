# 1 Importar banco
	mongoimport books.json -d booksCollection -c books
# 2 Encontrando todos os dados
	db.books.find({}) OU
	db.books.find({}).pretty()