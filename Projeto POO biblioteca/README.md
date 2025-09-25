
---

# 📚 Sistema de Gestão de Biblioteca

Projeto simples em **Python** utilizando **Programação Orientada a Objetos (POO)** para gerenciar uma biblioteca.

## 🚀 Funcionalidades

* Adicionar livros na biblioteca
* Listar livros disponíveis e emprestados
* Emprestar livros
* Devolver livros

## 🛠 Tecnologias utilizadas

* Python 3

## 📂 Estrutura do Código

### Classe **Livro**

Representa um livro com título, autor e status de disponibilidade.

### Classe **Biblioteca**

Gerencia a coleção de livros, permitindo adicionar, listar, emprestar e devolver.

## 📌 Código de Exemplo

```python
class Livro:
    def __init__(self, titulo, autor):
        self.titulo = titulo
        self.autor = autor
        self.disponivel = True

    def emprestar(self):
        if self.disponivel:
            self.disponivel = False
            print(f'O livro "{self.titulo}" foi emprestado.')
        else:
            print(f'O livro "{self.titulo}" não está disponível.')

    def devolver(self):
        self.disponivel = True
        print(f'O livro "{self.titulo}" foi devolvido.')


class Biblioteca:
    def __init__(self):
        self.livros = []

    def adicionar_livro(self, livro):
        self.livros.append(livro)

    def listar_livros(self):
        for livro in self.livros:
            status = "Disponível" if livro.disponivel else "Emprestado"
            print(f'{livro.titulo} - {livro.autor} ({status})')


# Exemplo de uso
biblio = Biblioteca()

livro1 = Livro("A Rainha Vermelha", "Victoria Aveyard")
livro2 = Livro("Dom Casmurro", "Machado de Assis")

biblio.adicionar_livro(livro1)
biblio.adicionar_livro(livro2)

biblio.listar_livros()
livro1.emprestar()
biblio.listar_livros()
livro1.devolver()
biblio.listar_livros()
```

## ▶️ Como executar

1. Tenha o **Python 3** instalado na sua máquina
2. Clone este repositório:

   ```bash
   git clone https://github.com/SEU_USUARIO/sistema-biblioteca.git
   ```
3. Acesse a pasta do projeto:

   ```bash
   cd sistema-biblioteca
   ```
4. Execute o arquivo Python:

   ```bash
   python biblioteca.py
   ```

## 📖 Conceitos de POO aplicados

* **Classe**: Livro, Biblioteca
* **Objeto**: Instâncias de Livro criadas no código
* **Atributos**: `titulo`, `autor`, `disponivel`, `livros`
* **Métodos**: `emprestar()`, `devolver()`, `adicionar_livro()`, `listar_livros()`

---



