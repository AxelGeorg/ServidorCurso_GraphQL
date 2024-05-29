# ServidorCurso_GraphQL
Aplicação utilizando a linguage Go, GraphQL e SQLite

Site para os primeiros passos com GraphQL: 
https://gqlgen.com/

caso o schema graphQL seja alterado no arquivo x é necessário rodar o comando: 
 go run github.com/99designs/gqlgen generate

Para criação do Banco de Dados:
 sudo sqlite3 data.db
 create table categories (id string, name string, description string);

Testes no GraphQL (http://localhost:8080/#)
 sudo go run cmd/server/server.go 

Teste mutation:

 mutation createCategory {
   createCategory(input: {name: "Tecnologia", description: "Cursos de tecnologia"}){
 		id
     name
     description
   }
 }



Testes query:

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

