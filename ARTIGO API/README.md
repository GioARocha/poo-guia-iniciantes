# 🌐 Guia Prático sobre API

## 📌 Introdução

As **APIs (Application Programming Interfaces)** é um conjunto de regras e protocolos que permite que diferentes 
softwares se comuniquem e troquem dados de forma padronizada e segura, atuando como um intermediário de software. 
Em termos simples, ela define como um programa pode solicitar informações ou funcionalidades de outro sistema, 
sem precisar conhecer os detalhes complexos de como essas funções são realizadas internamente. 


---

## 1️⃣ O que é API?

> API é um **conjunto de regras e definições** que permite a comunicação entre diferentes softwares.

Exemplo do dia a dia:

* Quando você faz login em um site usando o **Google** ou **Facebook**, uma **API** está permitindo essa integração.

🔑 Características principais:

* **Intermediária**: conecta sistemas diferentes.
* **Padronizada**: usa protocolos e métodos definidos.
* **Escalável**: facilita integrações futuras.

---

## 2️⃣ Métodos HTTP e Status Codes

As APIs web geralmente usam o protocolo **HTTP**. Cada requisição pode ter um **método** e retornar um **status code**.

### 📍 Métodos HTTP mais comuns:

* `GET`: Buscar informações no servidor.
* `POST`: Enviar informações para o servidor.
* `PUT`: Atualizar informações existentes.
* `DELETE`: Remover informações.

### 📍 Principais Status Codes:

| Código  | Significado           | Exemplo                         |
| ------- | --------------------- | ------------------------------- |
| **200** | OK                    | Requisição feita com sucesso    |
| **201** | Created               | Novo recurso criado com sucesso |
| **400** | Bad Request           | Erro de sintaxe na requisição   |
| **401** | Unauthorized          | Falta de autenticação           |
| **404** | Not Found             | Recurso não encontrado          |
| **500** | Internal Server Error | Erro inesperado no servidor     |

---

## 3️⃣ Criando uma API com ExpressJS

O **ExpressJS** é um dos frameworks mais populares para criação de APIs em **Node.js**.

### ⚙️ Passo a passo:

1. Crie uma pasta e inicialize o projeto:

```bash
mkdir api-exemplo
cd api-exemplo
npm init -y
npm install express
```

2. Crie o arquivo `index.js`:

```javascript
const express = require("express");
const app = express();

app.use(express.json());

// Rota GET
app.get("/", (req, res) => {
  res.status(200).send("🚀 Bem-vindo à nossa API!");
});

// Rota POST
app.post("/usuarios", (req, res) => {
  const { nome } = req.body;
  res.status(201).send({ mensagem: `Usuário ${nome} criado com sucesso!` });
});

// Servidor rodando
app.listen(3000, () => {
  console.log("Servidor rodando em http://localhost:3000");
});
```

3. Execute a API:

```bash
node index.js
```

4. Teste no navegador ou no **Postman/Insomnia**:

* `GET http://localhost:3000/`
* `POST http://localhost:3000/usuarios` com `{ "nome": "Ana" }`

---

## ✅ Conclusão

As APIs são fundamentais para a comunicação entre sistemas e aplicações modernas.
Aprendemos:

* O conceito de API
* Métodos HTTP e status codes
* Como criar uma API simples usando **ExpressJS**

---
