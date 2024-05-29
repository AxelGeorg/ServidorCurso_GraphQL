# ServidorCurso_GraphQL
Aplicação utilizando a linguage Go, GraphQL e SQLite

- Site para os primeiros passos com GraphQL:
https://gqlgen.com/

- Caso o schema graphQL seja alterado no arquivo schema.graphqls é necessário rodar o comando: 
```sh
 go run github.com/99designs/gqlgen generate
```

- Para criação do Banco de Dados:
```sh
 sudo sqlite3 data.db
 create table categories (id string, name string, description string);
 create table courses (id string, name string, description string, categoryId string);
```

- Testes no GraphQL ([http://localhost:8080])
```sh
 sudo go run cmd/server/server.go 
```

- Testes mutation:
```sh
 mutation createCategory {
   createCategory(input: {name: "Tecnologia", description: "Cursos de tecnologia"}){
 		id
     name
     description
   }
 }

 mutation createCourse {
  createCourse(input: {name: "Full Cycle", description: "The best", categoryId: "ad610ef8-ba74-44ff-aba8-3b8c015dd354"}){
		id
    name
    description
  }
```


- Testes query:
```sh
 query queryCategory {
 	categories {
 	 id
     name
     description
   }
 }
 
 query queryCategory {
 	categories {
 	 id
     name
   }
 }

 query queryCategory {
 	categories {
 	 id
   }
 }

 query queryCourse {
	courses {
	 id
     name
     description
  }
}
```
