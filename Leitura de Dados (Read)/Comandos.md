# 1 Importar banco
	mongoimport books.json -d booksCollection -c books
# 2 Encontrando todos os dados
	db.books.find({}) OU
	db.books.find({}).pretty()
# 3 Encontrando dados com valor especificos
	db.books.find({pageCount:362})
	db.books.findOne( {title: "MongoDB in Action"} )
	db.books.find( {authors: "Jason R. Weiss"} )
# 4 Encontrando dados entre valores
	db.books.find({ categories: { $in:["Java", "Internet"] } })
# 5 Multiplas condiçoes 
	db.books.find({ pageCount: 592, _id: 63}).pretty()
# 6 Maior que algum valor
	db.books.find({pageCount: {$gt: 450 }}).pretty()
# 7 Menor quem algum valor 
	db.books.find({pageCount: {$lt: 120}}).pretty()
	db.books.find({pageCount: {$gt: 1}, pageCount: {$lt: 120}}).pretty()
# 8 Operador $or
	db.books.find({$or:[{pageCount: {$gt: 500}, _id:{$lt: 5}}]}).pretty()
	db.books.find({$or:[{pageCount: {$gt: 700}}, {categories: "Java"}]}).pretty()
# 9 Operador and e or na mesma consulta 
	db.books.find({status: "PUBLISH", $or:[{pageCount: 500}, {authors: "Robi Sen"}]}).pretty()
# 10 Contando múmeros de resultados 
	db.books.find({pageCount:{$gt:600}}).count()