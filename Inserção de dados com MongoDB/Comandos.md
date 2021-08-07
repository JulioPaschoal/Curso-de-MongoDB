# 1 - Inserindo dadsos no banco
		db.create.insertOne({ nome: "Julio Paschoal", idade: 35,
			esta_trabalhando: true, hobbies: ["jogar", "Programar"]})
# 2 - Inserindo varios dadsos de uma x com insertMany
		db.provas.insertMany([{nome: "Maria", notas: [10, 5, 6]}, 
			{nome: "Joaquina", notas: [10, 8]}])
# 3 - Inserindo dados com insert
		db.collection.insert({nome: "João", idade: 40})
		db.collection.insert([{nome: "Pedro"}, {nome: "Maria"}]) 
# 4 - Determinando meu propio proprio id
		
# 5 write concern
		db.collection.insertMany([ {nome: "Osvaldo", idade: 44},
		 {nome: "Simone", idade: 22} ], {w: "majority", wtimeout: 200}) 
