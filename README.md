# 📦 Sistema de Banco de Dados para E-commerce

Este projeto apresenta um **Modelo de Banco de Dados Relacional (ERD + SQL DDL)** para um sistema de **E-commerce**, contemplando clientes, fornecedores, produtos, pedidos, pagamentos e entregas.  

O objetivo é demonstrar boas práticas de **modelagem de dados**, **normalização** e **documentação técnica** para projetos de banco de dados.

---

## 🎯 Objetivos do Projeto
- Criar um modelo de banco de dados para **E-commerce**.
- Garantir **consistência** e **integridade referencial**.
- Permitir **consultas otimizadas** sobre pedidos, produtos e clientes.
- Criar documentação clara para uso em portfólio e projetos reais.

---

## 📊 Modelo Entidade-Relacionamento (ERD)

O diagrama abaixo representa as principais entidades e relacionamentos do sistema:

![ERD E-commerce](ecommerce_erd.png)

---

## 🗂️ Estrutura das Entidades

### **Cliente**
- Pessoa Física (**CPF**) ou Jurídica (**CNPJ**) – nunca ambos.
- Pode ter múltiplos endereços.
- Pode realizar múltiplos pedidos.

### **Fornecedor**
- Responsável por fornecer produtos.
- Cada fornecedor pode fornecer vários produtos.

### **Produto**
- Pertence a um fornecedor.
- Controlado no estoque.
- Pode compor múltiplos pedidos.

### **Pedido**
- Criado por um cliente.
- Pode conter vários produtos.
- Possui status e endereço de entrega.
- Pode ser cancelado.

### **Pagamento**
- Associado ao pedido.
- Pode ter múltiplas formas de pagamento.
- Contém valor, método e status.

### **Entrega**
- Associada ao pedido.
- Possui código de rastreio e status.

---

## 🔗 Relacionamentos
- Cliente **1:N** Endereço  
- Cliente **1:N** Pedido  
- Pedido **1:N** Pagamento  
- Pedido **1:1** Entrega  
- Pedido **N:N** Produto (via Pedido_Item)  
- Produto **1:1** Estoque  
- Fornecedor **1:N** Produto  

---

## 💾 Estrutura SQL (DDL)

O script SQL para criação do banco está disponível no arquivo:

📄 [`ecommerce_erd.md`](ecommerce_erd.md)

---

## 🚀 Como Usar
1. Clone este repositório:
   ```bash
   git clone https://github.com/deivid0304/ecommerce-sql-erd.git
   cd ecommerce-db
   ```
2. Crie o banco de dados no MySQL ou MariaDB.
3. Execute o script **DDL** disponível no arquivo `.md`.
4. O banco estará pronto para receber dados e consultas.

---

## 📌 Próximos Passos
- Criar **scripts de inserção (DML)** com dados de exemplo.
- Criar consultas SQL para relatórios (ex.: pedidos por cliente, faturamento por fornecedor).
- Integrar com um backend (Flask/Node.js) para API de consumo.

---

## 👨‍💻 Autor
Projeto desenvolvido por **Deivid Márcio** – [LinkedIn](https://www.linkedin.com) | [GitHub](https://github.com)
