# 🎬 API de Frases de Séries

Uma API simples construída com **Node.js + Express**, que retorna frases icônicas de séries como **The Walking Dead**, **Game of Thrones** e outras.

---

## 🚀 Funcionalidades

* `GET /` → retorna mensagem de boas-vindas.
* `GET /frases` → retorna todas as frases disponíveis.
* `GET /frases/:id` → retorna uma frase específica pelo **id**.
* `GET /random` → retorna uma frase aleatória.

---

## 📦 Tecnologias Utilizadas

* [Node.js](https://nodejs.org/)
* [Express](https://expressjs.com/)

---

## ⚙️ Como Rodar o Projeto

1. Clone este repositório:

```bash
git clone https://github.com/seu-usuario/api-frases-series.git
cd api-frases-series
```

2. Instale as dependências:

```bash
npm install
```

3. Rode a API:

```bash
node index.js
```

4. Acesse no navegador ou Insomnia/Postman:

* `http://localhost:3000/`
* `http://localhost:3000/frases`
* `http://localhost:3000/random`

---

## 📜 Código da API (`index.js`)

```javascript
const express = require("express");
const app = express();
const PORT = 3000;

const frases = [
  { id: 1, serie: "The Walking Dead", frase: "My mercy prevails over my wrath." },
  { id: 2, serie: "Game of Thrones", frase: "Winter is coming." },
  { id: 3, serie: "Breaking Bad", frase: "I am the one who knocks!" },
  { id: 4, serie: "The Walking Dead", frase: "We don’t kill the living." },
  { id: 5, serie: "Stranger Things", frase: "Friends don’t lie." }
];

// Rota inicial
app.get("/", (req, res) => {
  res.send("🎬 Bem-vindo à API de Frases de Séries!");
});

// Todas as frases
app.get("/frases", (req, res) => {
  res.json(frases);
});

// Frase por ID
app.get("/frases/:id", (req, res) => {
  const id = parseInt(req.params.id);
  const frase = frases.find(f => f.id === id);
  frase ? res.json(frase) : res.status(404).json({ erro: "Frase não encontrada" });
});

// Frase aleatória
app.get("/random", (req, res) => {
  const randomIndex = Math.floor(Math.random() * frases.length);
  res.json(frases[randomIndex]);
});

app.listen(PORT, () => {
  console.log(`🚀 Servidor rodando em http://localhost:${PORT}`);
});
```

---

## 🎯 Exemplos de Uso

### ✅ GET `/frases`

```json
[
  { "id": 1, "serie": "The Walking Dead", "frase": "My mercy prevails over my wrath." },
  { "id": 2, "serie": "Game of Thrones", "frase": "Winter is coming." }
]
```

### ✅ GET `/random`

```json
{ "id": 3, "serie": "Breaking Bad", "frase": "I am the one who knocks!" }
```

---

## 📝 Possíveis Melhorias

* Adicionar mais frases de séries.
* Criar rota `POST` para cadastrar frases.
* Conectar a um banco de dados (MongoDB, SQLite, etc).
* Deploy no **Render**, **Vercel** ou **Railway**.

---

Quer que eu já monte a **estrutura de pastas do projeto** (com `package.json`, `index.js`, e talvez uma pasta `routes`) para você só colar e rodar?
