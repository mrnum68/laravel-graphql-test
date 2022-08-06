## About Laravel Graphql
This is project for https://gist.github.com/prageeth/0884bb161ebccaf1da9dbeebf406961c

## Install
```
git clone git@github.com:mrnum68/laravel-graphql-test.git


composer install 

sail up -d

sail artisan migrate

sail artisan db:seed
```
## API 
http://0.0.0.0/api

## Graph query
```
Write your query or mutation here
mutation {
  createTodo(name: "Test task") {
    name
  }
  
  updateTodo(id: 1, name: "Doing test tag", date_competed: "2020-01-01") {
    id, name, date_completed
  }
  
  createTodo(name: "test test") {
    name
  }
  
  deleteTodo(id: 2) {
    name
  }
  
  markingTodo(id: 1, is_completed: false) {
    id, is_completed
  }
  
  todoAssign(user_id: 1, todo_id: 3) {
    user_id, todo_id
  }
  
  todoUnassign(id: 2) {
    user_id, todo_id
  }
}

{
  users {
    id, name
  }
  
  todos(first: 2) {
    data {
      name, created_at, is_completed, date_competed
    }
    paginatorInfo {
      count, currentPage
    }
  }
  
  todoAssigns(user_id: 1) {
    user_id, todo_id
  }
}

```

