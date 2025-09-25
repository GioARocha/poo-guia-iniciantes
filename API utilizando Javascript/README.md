# 🎬 API de Frases de Séries

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

