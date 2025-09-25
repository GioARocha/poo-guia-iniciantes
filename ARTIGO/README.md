# Artigo: Programação Orientada a Objetos (POO)

## 📌 Introdução
A **Programação Orientada a Objetos (POO)** é um paradigma de programação que organiza o software em **objetos**, cada um contendo **dados** (atributos) e **comportamentos** (métodos).  
Diferente da programação procedural, que segue uma sequência de comandos, a POO busca **modularidade, reutilização e abstração**, facilitando a manutenção e expansão de sistemas.

---

## 🧩 Conceitos Fundamentais

### 1. Classes e Objetos
- **Classe**: molde ou estrutura que define atributos e métodos de um objeto.
- **Objeto**: instância de uma classe, representando algo real no código.

**Exemplo em Python:**
```python
class Carro:
    def __init__(self, marca, modelo):
        self.marca = marca
        self.modelo = modelo

meu_carro = Carro("Toyota", "Corolla")
print(meu_carro.marca)  # Saída: Toyota
````

---

### 2. Atributos e Métodos

* **Atributos**: variáveis que armazenam dados do objeto.
* **Métodos**: funções que definem comportamentos do objeto.

```python
class Pessoa:
    def __init__(self, nome, idade):
        self.nome = nome
        self.idade = idade

    def cumprimentar(self):
        print(f"Olá, meu nome é {self.nome} e tenho {self.idade} anos.")

pessoa1 = Pessoa("Ana", 25)
pessoa1.cumprimentar()
```

---

### 3. Encapsulamento

Restringe o acesso direto aos atributos, permitindo controle através de métodos **getters** e **setters**.

```python
class ContaBancaria:
    def __init__(self, saldo):
        self.__saldo = saldo  # atributo privado

    def depositar(self, valor):
        self.__saldo += valor

    def obter_saldo(self):
        return self.__saldo

conta = ContaBancaria(1000)
conta.depositar(500)
print(conta.obter_saldo())  # Saída: 1500
```

---

### 4. Herança

Permite que uma classe **filha** herde atributos e métodos de uma **classe pai**, promovendo reutilização de código.

```python
class Animal:
    def __init__(self, nome):
        self.nome = nome

    def emitir_som(self):
        pass

class Cachorro(Animal):
    def emitir_som(self):
        print("Au au!")

dog = Cachorro("Rex")
dog.emitir_som()  # Saída: Au au!
```
---

## 🛠 Boas Práticas em POO

* Utilizar encapsulamento sempre que possível.
* Evitar classes muito grandes.
* Documentar métodos e classes com docstrings.
* Reaproveitar código com herança e composição.

---

## 🚀 Conclusão

A POO é essencial para criar sistemas **modulares, legíveis e fáceis de manter**. Compreender conceitos como **classe, objeto, encapsulamento, herança, polimorfismo e abstração** permite desenvolver aplicações mais robustas e escaláveis.

---


