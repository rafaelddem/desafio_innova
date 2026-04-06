# Desafio Innova – Cadastro de Heróis

Este é o desafio proposto pela **Innova**, que envolve desenvolver um sistema usando **Laravel** e **Vue.js** para cadastro de Heróis e controle das suas atividades.

📄 [Proposta original](https://github.com/InnovaConnect/desafio-desenvolvimento/blob/main/pleno-php.md)

---

## Características do sistema

Sistema mantido usando containers do **Docker** seguindo a lógica:
  - Banco de dados (Postgres)
  - Backend (Laravel)
  - Frontend (Vue.js)

Cada serviço (exceto o banco) é mantido em um repositório separado:

- 🔗 [Backend](https://github.com/rafaelddem/desafio_innova_api)  
- 🔗 [Frontend](https://github.com/rafaelddem/desafio_innova_front)

---

## Executando o sistema

### Passo 1 – Clonar o projeto

Faça o clone desse projeto em sua máquina.
```git clone https://github.com/rafaelddem/desafio_innova.git```

### Passo 2 – Vá até o projeto

Abra um console e vá até ao diretório onde o projeto foi clonado, e entre dentro do projeto (desafio_innova)

### Passo 3 – Iniciando o sistema

Execute o comando para iniciar os containers (será necessário que o Docker já esteja instalado):
```docker-compose up -d```

### Passo 4 – Populando o sistema

Alguns cadastros iniciais são necessários para o funcionamento do sistema (cadastro de Heróis) e maior facilidade de acesso (cadastro de administrador). Para isso, ainda no mesmo console e diretório, execute o comando:
```docker exec -it innova_hero_backend php artisan migrate --seed```

### Passo 4 – Entrando no sistema

Com os cadastros criados, você pode entrar diretamente no sistema atravéz da tela de login, usando uma das seguintes credenciais:
- Cadastro Administrador: 
    - email: admin@email.com
    - senha: 123456

- Cadastro Usuário: 
    - email: arqueiro@email.com
    - senha: 123456

### Passo 5 – Cadastrando novos usuários

Se preferir, pode criar um cadastro novo, através do botão "Cadastro" na tela de login
