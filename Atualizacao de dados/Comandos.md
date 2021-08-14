# 1 Atualizar um dado
	db.books.updateOne({_id: 314}, {$set:{pageCount: 1000}})
# 2 Atualizando vários itens
	db.books.updateMany({categories: "Java"}, {$set:{status: "unpublished"}})
# 3 Adicionando dados com Update
	db.books.updateMany({authors: "Vikram Goyal"}, {$set:{downloads:1000}})
	db.books.updateMany({pageCount: {$gt: 500}},{$set: {bestseller: true}})
	db.books.find({pageCount: {$gt: 500}}).pretty()
	db.books.find({bestseller: true}).count()
# 4 Trocando todo o documento
	db.books.replaceOne({_id: 120}, {foi: "substituido"})
# 5 Adicionar item a um array
	db.books.updateOne({_id:201},{#push:{categories: "PHP"}})