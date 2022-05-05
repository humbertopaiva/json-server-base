# json-server-base

## Endpoints

Utilize o endereço http://localhost:3001/ para fazer requisições ou enviar dados para o servidor.

### Criar um usuário - POST

http://localhost:3001/users

Para criar um usuário é preciso enviar um objeto JSON contendo, pelo menos as informações de email e password. Ex:

{
    
    method: "post",
    headers : {
        "Content-Type": "application/json",
    },

    body: {
        "email": "user@mailexample.com",
        "password": "123456"
    }   

}
    

### Criar um post - POST

http://localhost:3001/posts

Para criar um post é preciso enviar um objeto JSON contendo, pelo menos as informações sobre o conteúdo da postagem e o ID do usuário, através da chave "userId", passando o respectivo ID do usuário cadastrado no sitema. Ex:

{
    
    method: "post",
    headers : {
        "Content-Type": "application/json",
        "Authorization": "Bearer" + token
    },
    body: {
        "content": "lorem ipsum",
        "userId": "1"
    }    
}


### Listar as postagens - GET

Para as postagens basta fazer uma requisição para a URL: http://localhost:3001/posts


### Listar uma postagem - GET

Para ter acesso a uma postagem, basta fazer uma requisição para a URL: http://localhost:3001/posts/:id


### Criar um perfil com informações exclusivas do usuário - POST

http://localhost:3001/profile


{

    method: "post",
    headers : {
        "Content-Type": "application/json",
        "Authorization": "Bearer" + token
    },
    body: {
        "content": "lorem ipsum",
        "userId": "1"
    }  

}

### Ler as informações exclusivas dos perfis de todos os usuários - GET

Para fazer essa operação, é obrigatório estar logado no sistema.

http://localhost:3001/profile/

{

    method: "get",
    headers : {
        "Content-Type": "application/json",
        "Authorization": "Bearer" + token
      
}

### Ler as informações de um perfil específico de usuário - GET

Para fazer essa operação, é obrigatório estar logado no sistema.

http://localhost:3001/profile/:id

{

    method: "get",
    headers : {
        "Content-Type": "application/json",
        "Authorization": "Bearer" + token
      
}