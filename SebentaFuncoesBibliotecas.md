# Funções e Bibliotecas em Python

Sebenta de estudo sobre funções, modularização, bibliotecas e boas práticas em Python.

---

# Índice

1. [Introdução às Funções](#1-introdução-às-funções)  

2. [Criar e Chamar Funções](#2-criar-e-chamar-funções)  

3. [`print()` vs `return`](#3-print-vs-return)  

4. [Parâmetros e Argumentos](#4-parâmetros-e-argumentos)  

5. [Variáveis Locais e Globais](#5-variáveis-locais-e-globais)  

6. [Validação e Tratamento de Erros](#6-validação-e-tratamento-de-erros)  

7. [Objetos Mutáveis e Imutáveis](#7-objetos-mutáveis-e-imutáveis)  

8. [Boas Práticas](#8-boas-práticas)  

9. [Docstrings e Type Hints](#9-docstrings-e-type-hints)  

10. [Funções Recursivas](#10-funções-recursivas)  

11. [Funções Lambda](#11-funções-lambda)  

12. [Programação Funcional](#12-programação-funcional)  

13. [Bibliotecas, Módulos e Pacotes](#13-bibliotecas-módulos-e-pacotes)  

14. [Biblioteca Padrão](#14-biblioteca-padrão)  

15. [Bibliotecas Externas](#15-bibliotecas-externas)  

16. [Criar Módulos Próprios](#16-criar-módulos-próprios)  

17. [Modularização](#17-modularização)  

18. [Testes](#18-testes)  

19. [Estudo de Caso](#19-estudo-de-caso)  

20. [Exercícios](#20-exercícios)  

---

# 1. Introdução às Funções

## O que é uma função?

Uma função é um bloco de código reutilizável concebido para executar uma tarefa específica dentro de um programa.

Em Python, as funções permitem dividir programas complexos em partes mais pequenas, organizadas e fáceis de compreender. Cada função deve ter uma responsabilidade clara, contribuindo para tornar o código mais estruturado e modular.

As funções são um dos elementos fundamentais da programação, porque ajudam a reduzir a repetição de código e facilitam a manutenção dos programas.

---

## Vantagens da utilização de funções

A utilização de funções apresenta várias vantagens importantes:

- melhora a organização do código;
- evita repetição desnecessária;
- facilita a reutilização de lógica;
- simplifica a manutenção do programa;
- torna o código mais legível;
- facilita a deteção e correção de erros;
- permite criar programas mais modulares.

---

## Exemplo simples

```python
def mostrar_mensagem():
    print("Bem-vindo ao Python!")

mostrar_mensagem()
```

### Explicação do exemplo

Neste exemplo:

- `def` é a palavra-chave utilizada para definir uma função;
- `mostrar_mensagem` é o nome da função;
- os parênteses `()` indicam que se trata de uma função;
- o código indentado pertence ao corpo da função;
- a função apenas é executada quando é chamada.

Quando a função `mostrar_mensagem()` é executada, a mensagem `"Bem-vindo ao Python!"` é apresentada no ecrã.

---

# 2. Criar e Chamar Funções

## Criar uma função

Criar uma função significa definir um conjunto de instruções que poderá ser reutilizado sempre que necessário ao longo do programa.

Em Python, as funções são definidas através da palavra-chave `def`, seguida do nome da função e de parênteses `()`.

```python
def saudacao():
    print("Olá!")
```

### Estrutura da função

No exemplo anterior:

- `def` indica que está a ser criada uma função;
- `saudacao` é o nome atribuído à função;
- os parênteses `()` permitem definir parâmetros, caso existam;
- os dois pontos `:` indicam o início do bloco de instruções;
- o código indentado pertence ao corpo da função.

A indentação é obrigatória em Python e define quais as instruções que fazem parte da função.

---

## Chamar uma função

Depois de criada, a função pode ser executada através do seu nome seguido de parênteses.

```python
saudacao()
```

Quando esta instrução é executada, Python entra na função `saudacao()` e executa o código definido no seu interior.

Neste caso, o resultado será:

```text
Olá!
```

---

## Exemplo completo

```python
def saudacao():
    print("Olá!")

print("Antes da função")

saudacao()

print("Depois da função")
```

### Resultado esperado

```text
Antes da função
Olá!
Depois da função
```

Este exemplo demonstra que a função apenas executa quando é chamada explicitamente no programa.

---

## Importância da ordem

Em Python, uma função deve ser definida antes de ser utilizada.

Exemplo incorreto:

```python
saudacao()

def saudacao():
    print("Olá!")
```

Neste caso, Python gera um erro porque a função ainda não existia no momento em que foi chamada.

Forma correta:

```python
def saudacao():
    print("Olá!")

saudacao()
```

---

## Erros frequentes

### Falta de indentação

```python
def saudacao():
print("Olá!")
```

Python gera um erro porque o corpo da função não está indentado corretamente.

Forma correta:

```python
def saudacao():
    print("Olá!")
```

---

### Falta dos dois pontos

```python
def saudacao()
    print("Olá!")
```

Forma correta:

```python
def saudacao():
    print("Olá!")
```

---

### Esquecer os parênteses na chamada

```python
saudacao
```

Neste caso, a função não é executada. Apenas é feita uma referência ao objeto função.

Forma correta:

```python
saudacao()
```
---

# 3. `print()` vs `return`

## `print()`

Mostra informação no ecrã.

```python
def mostrar():
    print("Olá")
```

## `return`

Devolve um valor ao programa.

```python
def dobro(x):
    return x * 2

resultado = dobro(5)

print(resultado)
```

---

# 4. Parâmetros e Argumentos

## Parâmetros

```python
def somar(a, b):
    return a + b
```

- `a` e `b` são parâmetros.

## Argumentos

```python
somar(10, 20)
```

- `10` e `20` são argumentos.

## Valores por defeito

```python
def saudacao(nome="Aluno"):
    print(f"Olá, {nome}")
```

## `*args`

```python
def somar_todos(*numeros):
    return sum(numeros)

print(somar_todos(1, 2, 3))
```

## `**kwargs`

```python
def mostrar_dados(**dados):
    print(dados)

mostrar_dados(nome="Ana", idade=16)
```

---

# 5. Variáveis Locais e Globais

## Variável local

```python
def teste():
    numero = 10
    print(numero)
```

## Variável global

```python
mensagem = "Olá"

def mostrar():
    print(mensagem)
```

---

# 6. Validação e Tratamento de Erros

## Validação simples

```python
def validar_idade(idade):
    return idade >= 0
```

## Exceções

```python
def dividir(a, b):
    if b == 0:
        raise ZeroDivisionError("Divisão por zero")

    return a / b
```

## `try` e `except`

```python
try:
    numero = int(input("Número: "))
except ValueError:
    print("Valor inválido")
```

---

# 7. Objetos Mutáveis e Imutáveis

## Imutáveis

- `int`
- `float`
- `str`
- `tuple`

## Mutáveis

- `list`
- `dict`
- `set`

## Exemplo

```python
lista = [1, 2]
outra = lista

lista.append(3)

print(outra)
```

---

# 8. Boas Práticas

## Bons nomes

Mau exemplo:

```python
def f(x):
    return x * 2
```

Melhor:

```python
def calcular_dobro(numero):
    return numero * 2
```

## Uma função = uma responsabilidade

Evita funções gigantes.

---

# 9. Docstrings e Type Hints

## Docstring

```python
def calcular_media(notas):
    """Calcula a média."""
    return sum(notas) / len(notas)
```

## Type Hints

```python
def somar(a: int, b: int) -> int:
    return a + b
```

---

# 10. Funções Recursivas

## Fatorial

```python
def fatorial(n):
    if n == 0:
        return 1

    return n * fatorial(n - 1)
```

---

# 11. Funções Lambda

```python
dobro = lambda x: x * 2

print(dobro(5))
```

---

# 12. Programação Funcional

## `map()`

```python
numeros = [1, 2, 3]

resultado = list(map(lambda x: x * 2, numeros))
```

## `filter()`

```python
pares = list(filter(lambda x: x % 2 == 0, numeros))
```

## `sorted()`

```python
nomes = ["Ana", "Bruno", "Carla"]

ordenados = sorted(nomes)
```

---

# 13. Bibliotecas, Módulos e Pacotes

| Conceito | Descrição |
|---|---|
| Biblioteca | Código reutilizável |
| Módulo | Ficheiro `.py` |
| Pacote | Pasta com módulos |

---

# 14. Biblioteca Padrão

## `math`

```python
import math

print(math.sqrt(25))
```

## `random`

```python
import random

print(random.randint(1, 6))
```

## `datetime`

```python
from datetime import datetime

print(datetime.now())
```

## `json`

```python
import json

dados = {"nome": "Ana"}

texto = json.dumps(dados)
```

---

# 15. Bibliotecas Externas

## Instalar com pip

```bash
pip install pandas
```

## `pandas`

```python
import pandas as pd
```

## `matplotlib`

```python
import matplotlib.pyplot as plt
```

---

# 16. Criar Módulos Próprios

## `matematica.py`

```python
def somar(a, b):
    return a + b
```

## `main.py`

```python
import matematica

print(matematica.somar(10, 5))
```

---

# 17. Modularização

## Estrutura recomendada

```text
projeto/
│
├── main.py
├── modelo.py
├── vista.py
└── controlador.py
```

---

# 18. Testes

## `assert`

```python
def dobro(x):
    return x * 2

assert dobro(5) == 10
```

---

# 19. Estudo de Caso

## Gestão de notas

```python
def calcular_media(notas):
    return sum(notas) / len(notas)

def classificar(media):
    if media >= 10:
        return "Aprovado"

    return "Reprovado"
```

---

# 20. Exercícios

## Básicos

1. Criar função `dobro()`
2. Criar função `media()`
3. Criar função `eh_par()`

## Intermédios

1. Validar notas
2. Criar palíndromo
3. Criar fatorial

## Avançados

1. Modularizar projeto
2. Ler CSV
3. Guardar JSON

---

# Resumo Final

| Conceito | Significado |
|---|---|
| Função | Bloco reutilizável |
| Parâmetro | Variável da função |
| Argumento | Valor enviado |
| `return` | Devolve resultado |
| `import` | Importa módulos |

---

# Continuação Recomendada

Depois deste tema, estudar:

- Programação Orientada a Objetos
- Ficheiros
- APIs
- Bases de Dados
- Testes Automáticos
- Git e GitHub
- Projetos reais

---

# Licença

Material educativo em Python.
