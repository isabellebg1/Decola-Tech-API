# Lista to-do - API
Projeto feito para demonstrar o uso de ferramentas Java, incluindo Spring Data JPA, OpenAPI e Postgre SQL. É implantado no Railway.
Permite ao usuário fazer listas to-do (lista de tarefas), usando operações CRUD (Create, Read, Update, Delete).

# Tecnologias Utilizadas 
- Spring Boot: framework para aplicações Java
- Spring Data JPA: biblioteca
- H2 Database
- PostgreSQL
- Open API (Swagger)
- Railway
- Maven

# Arquitetura do Projeto 
- Controller: Lida com solicitações HTTP recebidas e retorna respostas; coloca endpoints REST para gerenciar itens de tarefas
- Service Layer: Contém a lógica para gerenciar os itens da lista; interage com a layer de repositório para realizar operações de banco de dados
- Repository Layer: Provem uma interface para interagir com o banco de dados usando Spring Data JPA
- Model Layer: Representa a estrutura de dados e mapas para o banco de dados

# Componentes Chave 
1. Modelo (todo.java): id, title, description e completed - passos do uso da lista; anotado com @Entity para mapear a classe para uma tabela de dados
2. Repositório (todorepository.java): estende JPA Repository para operações CRUD para entidade todo; Spring Data JPA fornece implementações padrão
3. Serviço (todoservice.java): contém metodos para gerenciar os itens da lista:
   - _getAllTodos()_: recupera todos os itens
   - _getTodoById(Long id)_: recupera um item pelo id
   - _CreateTodo(Todo todo)_: cria um novo item
   - _updateTodo(Long id, Todo todoDetails)_: atualiza um item existente
   - _deleteTodo(Long id)_: deleta um item pelo seu id
4. Controller (todoController.java): coloca REST endpoints para gerenciar itens to-do:
   - _GET /api/todos_: repara todos os itens
   - _GET /api/todos/{id}_: recupera um item pelo id
   - _POST /api/todos_: cria um novo item
   - _PUT /api/todos/{id}_: atualiza um item existente
   - _DELETE /api/todos/{id}_: deleta um item pelo id
  
