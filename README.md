# Ecommerce API

Esta é uma API de ecommerce construída com Flask no minicurso de "Como Construir uma API com Python e Flask". Ela permite gerenciar usuários, produtos e carrinhos de compras.

## Instalação

1. Clone o repositório:

   ```sh
   git clone https://github.com/HermannDouglas/ecommerce-api
   cd ecommerce-api
   ```

2. Crie um ambiente virtual e ative-o:

   ```sh
   python -m venv venv
   source venv/bin/activate  # No Windows use `venv\Scripts\activate`
   ```

3. Instale as dependências:

   ```sh
   pip install -r requirements.txt
   ```

4. Crie um usuário:

   ```sh
   flask shell
   user = User(username="seu_usuario", password="sua_senha")
   exit()
   ```

5. Execute a aplicação:
   ```sh
   python app.py
   ```

## Endpoints

### Autenticação

- `POST /login`: Faz login de um usuário.
- `POST /logout`: Faz logout de um usuário.

### Produtos

- `POST /api/products/add`: Adiciona um novo produto. (Requer autenticação)
- `GET /api/products/<int:product_id>`: Obtém detalhes de um produto.
- `PUT /api/products/update/<int:product_id>`: Atualiza um produto existente. (Requer autenticação)
- `GET /api/products`: Lista todos os produtos.
- `DELETE /api/products/delete/<int:product_id>`: Deleta um produto. (Requer autenticação)

### Carrinho

- `POST /api/cart/add/<int:product_id>`: Adiciona um produto ao carrinho. (Requer autenticação)
- `DELETE /api/cart/remove/<int:product_id>`: Remove um produto do carrinho. (Requer autenticação)
- `GET /api/cart`: Obtém o conteúdo do carrinho. (Requer autenticação)
- `POST /api/cart/checkout`: Finaliza a compra e limpa o carrinho. (Requer autenticação)

## Configuração

- `SECRET_KEY`: Chave secreta para a aplicação Flask.
- `SQLALCHEMY_DATABASE_URI`: URI do banco de dados.

## Dependências

- Flask==2.3.0
- Flask-SQLAlchemy==3.1.1
- Flask-Login==0.6.2
- Flask-Cors==3.0.10
- Werkzeug==2.3.0
