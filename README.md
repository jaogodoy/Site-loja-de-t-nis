# Site-loja-de-tenis

https://app.brmodeloweb.com/#!/publicview/66ce2d0a4bcd3326de0ea4c0

![image](https://github.com/user-attachments/assets/56acafad-43f3-435c-9fcd-986af783b980)

![image](https://github.com/user-attachments/assets/2a1600f5-899d-4261-a642-79476a27f34a)


CREATE DATABASE site_lojadetenis;
USE site_lojadetenis;

CREATE TABLE Usuarios 
( 
 id_usuario INT PRIMARY KEY,  
 nome VARCHAR(n) NOT NULL,  
 email VARCHAR(n),  
 senha VARCHAR(n),  
 data_criacao DATE,  
 UNIQUE (nome)
); 

CREATE TABLE Produtos 
( 
 id_produto INT PRIMARY KEY,  
 nome_produto VARCHAR(n),  
 preco FLOAT,  
 quantidade_estoque INT,  
 data_adicao DATE,  
); 

CREATE TABLE Pedidos 
( 
 id_pedido INT PRIMARY KEY,  
 id_usuario INT,  
 data_pedido DATE,  
); 

CREATE TABLE Itens_Pedido 
( 
 id_item_pedido INT PRIMARY KEY,  
 id_pedido INT,  
 id_produto INT,  
 quantidade INT,  
 preco_unitario FLOAT,  
); 

ALTER TABLE Pedidos ADD FOREIGN KEY(id_usuario) REFERENCES Usuarios (id_usuario)
ALTER TABLE Itens_Pedido ADD FOREIGN KEY(id_pedido) REFERENCES Pedidos (id_pedido)
ALTER TABLE Itens_Pedido ADD FOREIGN KEY(id_produto) REFERENCES Produtos (id_produto)

