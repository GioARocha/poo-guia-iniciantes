# poo-guia-iniciantes

📘 Introdução à Programação Orientada a Objetos (POO) em Python

A Programação Orientada a Objetos (POO) organiza o código em torno de objetos, que possuem atributos (características) e métodos (comportamentos).
Vamos entender os três conceitos básicos: classes, atributos e métodos, com exemplos em Python.

🏗️ 1. Classes: O Molde do Objeto

Uma classe é como a planta de uma casa. Ela define a estrutura que os objetos terão, mas ainda não é um objeto em si.

Exemplo em Python:

class Carro:
    # Estrutura inicial da classe Carro
    pass

📝 2. Atributos: As Características

Os atributos são as informações que descrevem o objeto.
Por exemplo, um carro tem marca, modelo e cor.

class Carro:
    def __init__(self, marca, modelo, cor):
        self.marca = marca
        self.modelo = modelo
        self.cor = cor


Agora podemos criar um objeto a partir da classe e acessar seus atributos:

meu_carro = Carro("Toyota", "Corolla", "preto")

print(meu_carro.marca)  # Saída: Toyota
print(meu_carro.cor)    # Saída: preto

⚙️ 3. Métodos: Os Comportamentos

Os métodos são as ações que o objeto pode realizar.
No caso do carro, ele pode acelerar e frear.

class Carro:
    def __init__(self, marca, modelo, cor):
        self.marca = marca
        self.modelo = modelo
        self.cor = cor
        self.velocidade = 0

    def acelerar(self):
        self.velocidade += 10
        print(f"O {self.modelo} acelerou. Velocidade atual: {self.velocidade} km/h")

    def frear(self):
        self.velocidade -= 5
        if self.velocidade < 0:
            self.velocidade = 0
        print(f"O {self.modelo} freou. Velocidade atual: {self.velocidade} km/h")


Testando os métodos:

meu_carro = Carro("Toyota", "Corolla", "preto")

meu_carro.acelerar()  # O Corolla acelerou. Velocidade atual: 10 km/h
meu_carro.acelerar()  # O Corolla acelerou. Velocidade atual: 20 km/h
meu_carro.frear()     # O Corolla freou. Velocidade atual: 15 km/h

✅ Resumo

Classe → o projeto (define atributos e métodos).

Atributos → características do objeto.

Métodos → comportamentos do objeto.
