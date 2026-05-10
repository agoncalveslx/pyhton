# Funções e Bibliotecas em Python

Sebenta de estudo sobre funções, modularização, bibliotecas e boas práticas em Python.

---

# Índice

1. Introdução às Funções  
2. Criar e Chamar Funções  
3. `print()` vs `return`  
4. Parâmetros e Argumentos  
5. Variáveis Locais e Globais  
6. Validação e Tratamento de Erros  
7. Objetos Mutáveis e Imutáveis  
8. Boas Práticas  
9. Docstrings e Type Hints  
10. Funções Recursivas  
11. Funções Lambda  
12. Programação Funcional  
13. Bibliotecas, Módulos e Pacotes  
14. Biblioteca Padrão  
15. Bibliotecas Externas  
16. Criar Módulos Próprios  
17. Modularização  
18. Testes  
19. Estudo de Caso  
20. Exercícios  

---

# 1. Introdução às Funções

## O que é uma função?

Uma função é um bloco reutilizável de código que executa uma tarefa específica.

## Vantagens

- organização;
- reutilização;
- menos repetição;
- manutenção mais simples;
- código mais limpo.

## Exemplo simples

```python
def mostrar_mensagem():
    print("Bem-vindo ao Python!")

mostrar_mensagem()
```

---

# 2. Criar e Chamar Funções

## Criar uma função

```python
def saudacao():
    print("Olá!")
```

## Chamar a função

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
