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
# Write your query or mutation here

 mutation {
  createTodo(name: "Test task 111") {
    id,
    name
  }
  
  updateTodo(id: 7, name: "Doing test tag 1", date_competed: "2020-01-01") {
    id, name, date_competed
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
  todos(first: 10) {
    data {
      name, created_at, is_completed, date_competed
    }
    paginatorInfo {
      count, currentPage
    }
  }
  
  users {
    id, name
  }
  
  userTodos(id: 1) {
    id,
    name,
    todos {
      id, name, date_competed, is_completed
    }
  }
  
}

```
<img width="1430" alt="Screen Shot 2022-08-09 at 16 04 02" src="https://user-images.githubusercontent.com/19530065/183609976-3b3a703e-d159-4d8b-8ee6-0d0406c72bb0.png">

<img width="1430" alt="Screen Shot 2022-08-09 at 16 05 54" src="https://user-images.githubusercontent.com/19530065/183610225-8679a4f4-54a6-48be-9d7d-85bc8fad2975.png">


