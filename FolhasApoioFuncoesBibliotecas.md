# Funções e Bibliotecas em Python

Esta sebenta apresenta os principais conceitos relacionados com funções, modularização, bibliotecas e boas práticas em Python.

O objetivo é compreender como organizar código de forma clara, reutilizável e fácil de manter, começando pela criação de funções simples e avançando progressivamente para módulos, pacotes e estruturação de projetos.

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

---

# 1. Introdução às Funções

Uma função é um bloco de código reutilizável criado para executar uma tarefa específica dentro de um programa.

Em Python, as funções permitem dividir programas complexos em partes mais pequenas, organizadas e fáceis de compreender. Cada função deve ter uma responsabilidade clara, contribuindo para tornar o código mais modular.

As funções são fundamentais porque ajudam a reduzir repetição, facilitam a manutenção e tornam o programa mais legível.

## Vantagens

A utilização de funções permite:

- melhorar a organização do código;
- evitar repetição desnecessária;
- reutilizar lógica em diferentes partes do programa;
- simplificar a manutenção;
- facilitar a deteção e correção de erros;
- tornar o código mais fácil de testar.

## Exemplo

```python
def mostrar_mensagem():
    print("Bem-vindo ao Python!")

mostrar_mensagem()
```

Neste exemplo, `def` define a função, `mostrar_mensagem` é o seu nome e o código indentado corresponde ao corpo da função. A função só é executada quando é chamada.

---

# 2. Criar e Chamar Funções

Criar uma função significa definir um conjunto de instruções que pode ser reutilizado sempre que necessário.

Em Python, uma função é criada com a palavra-chave `def`, seguida do nome da função, parênteses e dois pontos.

```python
def saudacao():
    print("Olá!")
```

Depois de criada, a função pode ser executada através do seu nome seguido de parênteses.

```python
saudacao()
```

Resultado:

```text
Olá!
```

## Exemplo completo

```python
def saudacao():
    print("Olá!")

print("Antes da função")

saudacao()

print("Depois da função")
```

Resultado:

```text
Antes da função
Olá!
Depois da função
```

Este exemplo mostra que a função apenas é executada quando é chamada explicitamente.

## Erros frequentes

### Falta de indentação

```python
def saudacao():
print("Olá!")
```

Forma correta:

```python
def saudacao():
    print("Olá!")
```

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

### Esquecer os parênteses

```python
saudacao
```

Forma correta:

```python
saudacao()
```

---

# 3. `print()` vs `return`

Ao criar funções, é essencial distinguir `print()` de `return`.

- `print()` mostra informação no ecrã;
- `return` devolve um valor ao programa.

Esta diferença é importante porque uma função que apenas usa `print()` apresenta informação, mas não disponibiliza esse valor para ser reutilizado.

## Utilização de `print()`

```python
def mostrar():
    print("Olá")

mostrar()
```

Resultado:

```text
Olá
```

## Utilização de `return`

```python
def dobro(x):
    return x * 2

resultado = dobro(5)

print(resultado)
```

Resultado:

```text
10
```

Neste caso, o valor devolvido pela função é guardado na variável `resultado`.

## Comparação

| `print()` | `return` |
|---|---|
| Mostra informação no ecrã | Devolve informação ao programa |
| Serve para apresentação | Serve para processamento |
| Não permite reutilizar diretamente o resultado | Permite reutilizar o resultado |
| É útil em mensagens e menus | É útil em cálculos e lógica |

## Boa prática

Sempre que possível, deve separar-se cálculo e apresentação.

```python
def calcular_area(largura, altura):
    return largura * altura

def mostrar_area(area):
    print(f"Área: {area}")
```

Esta separação torna o código mais organizado, reutilizável e fácil de testar.

---

# 4. Parâmetros e Argumentos

As funções podem receber dados do exterior. Esses dados permitem que a mesma função seja utilizada com valores diferentes.

Os valores recebidos pela função são definidos através de parâmetros e enviados através de argumentos.

## Parâmetros

Parâmetros são variáveis indicadas na definição da função.

```python
def somar(a, b):
    return a + b
```

Neste exemplo, `a` e `b` são parâmetros.

## Argumentos

Argumentos são os valores enviados para a função quando esta é chamada.

```python
somar(10, 20)
```

Neste caso, `10` e `20` são argumentos.

## Argumentos posicionais

```python
def apresentar(nome, idade):
    print(f"{nome} tem {idade} anos.")

apresentar("Ana", 16)
```

Resultado:

```text
Ana tem 16 anos.
```

A ordem dos argumentos é importante.

## Argumentos nomeados

```python
apresentar(nome="Ana", idade=16)
apresentar(idade=16, nome="Ana")
```

Os argumentos nomeados tornam o código mais claro e reduzem erros relacionados com a ordem.

## Valores por defeito

```python
def saudacao(nome="Aluno"):
    print(f"Olá, {nome}")

saudacao()
saudacao("Rita")
```

Resultado:

```text
Olá, Aluno
Olá, Rita
```

## `*args`

A sintaxe `*args` permite receber vários argumentos posicionais.

```python
def somar_todos(*numeros):
    return sum(numeros)

print(somar_todos(1, 2, 3))
```

Resultado:

```text
6
```

## `**kwargs`

A sintaxe `**kwargs` permite receber vários argumentos nomeados.

```python
def mostrar_dados(**dados):
    print(dados)

mostrar_dados(nome="Ana", idade=16)
```

Resultado:

```text
{'nome': 'Ana', 'idade': 16}
```

## Boas práticas

Ao utilizar parâmetros e argumentos:

- usa nomes claros;
- evita funções com demasiados parâmetros;
- utiliza valores por defeito quando fizer sentido;
- usa `*args` e `**kwargs` apenas quando necessário.

---

# 5. Variáveis Locais e Globais

As variáveis podem ter diferentes âmbitos, isto é, diferentes zonas do programa onde podem ser utilizadas.

Em Python, distinguem-se principalmente variáveis locais e globais.

## Variáveis locais

Uma variável local é criada dentro de uma função e só existe no interior dessa função.

```python
def teste():
    numero = 10
    print(numero)

teste()
```

Resultado:

```text
10
```

A variável `numero` não pode ser utilizada fora da função.

## Variáveis globais

Uma variável global é criada fora das funções e pode ser lida em diferentes partes do programa.

```python
mensagem = "Olá"

def mostrar():
    print(mensagem)

mostrar()
```

Resultado:

```text
Olá
```

## Alterar variáveis globais

Embora seja possível alterar variáveis globais dentro de funções, esta prática deve ser evitada.

```python
contador = 0

def aumentar():
    global contador
    contador += 1
```

O uso excessivo de variáveis globais pode tornar o programa difícil de compreender e testar.

## Alternativa recomendada

```python
def aumentar(valor):
    return valor + 1

contador = 0
contador = aumentar(contador)

print(contador)
```

Resultado:

```text
1
```

Esta abordagem é mais previsível, porque a função recebe um valor e devolve um novo resultado.

## Regra LEGB

Python procura variáveis segundo a regra LEGB:

| Letra | Significado | Localização |
|---|---|---|
| L | Local | Dentro da função atual |
| E | Enclosing | Funções exteriores |
| G | Global | Ficheiro atual |
| B | Built-in | Nomes internos do Python |

---

# 6. Validação e Tratamento de Erros

Programas reais recebem frequentemente dados inválidos ou inesperados. Por exemplo, um utilizador pode introduzir texto quando era esperado um número.

A validação e o tratamento de erros tornam os programas mais robustos e previsíveis.

## Validação simples

```python
def validar_idade(idade):
    return idade >= 0
```

Exemplo de utilização:

```python
if validar_idade(18):
    print("Idade válida")
else:
    print("Idade inválida")
```

## Exceções

Uma exceção representa um erro ocorrido durante a execução do programa.

```python
def dividir(a, b):
    if b == 0:
        raise ZeroDivisionError("Divisão por zero")

    return a / b
```

## Exceções comuns

| Exceção | Situação comum |
|---|---|
| `TypeError` | Tipo de dado incorreto |
| `ValueError` | Valor inválido |
| `ZeroDivisionError` | Divisão por zero |
| `IndexError` | Índice inexistente |
| `KeyError` | Chave inexistente num dicionário |
| `FileNotFoundError` | Ficheiro não encontrado |

## `try` e `except`

```python
try:
    numero = int(input("Número: "))
except ValueError:
    print("Valor inválido")
```

O bloco `try` tenta executar código que pode gerar erro. O bloco `except` trata o erro caso ele ocorra.

## `else` e `finally`

```python
try:
    numero = int(input("Número: "))
except ValueError:
    print("Valor inválido")
else:
    print("Número válido")
finally:
    print("Fim da tentativa")
```

| Bloco | Função |
|---|---|
| `try` | Tenta executar código |
| `except` | Trata erros |
| `else` | Executa se não ocorrer erro |
| `finally` | Executa sempre |

---

# 7. Objetos Mutáveis e Imutáveis

Em Python, todos os valores são objetos. Alguns objetos podem ser alterados depois de criados, enquanto outros não.

## Objetos imutáveis

Objetos imutáveis não podem ser alterados diretamente.

Exemplos:

- `int`
- `float`
- `str`
- `bool`
- `tuple`

```python
numero = 10
outro = numero

numero += 1

print(numero)
print(outro)
```

Resultado:

```text
11
10
```

## Objetos mutáveis

Objetos mutáveis podem ser alterados depois de criados.

Exemplos:

- `list`
- `dict`
- `set`

```python
lista = [1, 2]
outra = lista

lista.append(3)

print(outra)
```

Resultado:

```text
[1, 2, 3]
```

Neste exemplo, `lista` e `outra` apontam para o mesmo objeto.

## Criar cópias

```python
lista = [1, 2]
copia = lista.copy()

lista.append(3)

print(lista)
print(copia)
```

Resultado:

```text
[1, 2, 3]
[1, 2]
```

## Mutabilidade em funções

```python
def adicionar_item(lista):
    lista.append(10)

valores = [1, 2]
adicionar_item(valores)

print(valores)
```

Resultado:

```text
[1, 2, 10]
```

A lista original foi alterada dentro da função.

## Forma mais segura

```python
def adicionar_item(lista):
    nova_lista = lista.copy()
    nova_lista.append(10)

    return nova_lista
```

---

# 8. Boas Práticas

Escrever código funcional é importante, mas escrever código claro e fácil de manter é igualmente essencial.

## Nomes claros

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

O nome da função deve indicar claramente a sua finalidade.

## Uma função deve ter uma responsabilidade

Exemplo pouco recomendado:

```python
def processar_notas(notas):
    media = sum(notas) / len(notas)

    print(media)

    if media >= 10:
        print("Aprovado")
    else:
        print("Reprovado")
```

Esta função calcula, apresenta e classifica.

Melhor:

```python
def calcular_media(notas):
    return sum(notas) / len(notas)

def classificar(media):
    if media >= 10:
        return "Aprovado"

    return "Reprovado"

def mostrar_resultado(media, classificacao):
    print(f"Média: {media}")
    print(f"Classificação: {classificacao}")
```

## Evitar repetição

Sempre que o mesmo código se repete, é provável que deva ser transformado numa função.

## Checklist

Antes de terminar uma função, verifica:

- o nome é claro?
- a função tem apenas uma responsabilidade?
- os parâmetros são necessários?
- o código é legível?
- a função pode ser reutilizada?
- existem validações importantes?

---

# 9. Docstrings e Type Hints

À medida que os programas crescem, torna-se importante documentar o código.

As docstrings e os type hints ajudam a tornar as funções mais claras e fáceis de compreender.

## Docstrings

Uma docstring é uma pequena descrição colocada logo após a definição da função.

```python
def calcular_media(notas):
    """Calcula a média de uma lista de notas."""
    return sum(notas) / len(notas)
```

## Docstring mais completa

```python
def calcular_media(notas):
    """
    Calcula a média aritmética de uma lista de notas.

    Parâmetros:
        notas: lista de números.

    Devolve:
        média das notas.
    """

    return sum(notas) / len(notas)
```

## Type hints

Os type hints indicam os tipos esperados nos parâmetros e no valor devolvido.

```python
def somar(a: int, b: int) -> int:
    return a + b
```

## Exemplo combinado

```python
def converter_celsius_para_fahrenheit(celsius: float) -> float:
    """
    Converte uma temperatura de Celsius para Fahrenheit.
    """

    return celsius * 9 / 5 + 32
```

Os type hints não obrigam Python a verificar tipos automaticamente, mas tornam o código mais claro e ajudam ferramentas de desenvolvimento.

---

# 10. Funções Recursivas

Uma função recursiva é uma função que se chama a si própria.

A recursão é útil para resolver problemas que podem ser divididos em versões mais pequenas do mesmo problema.

## Caso base e caso recursivo

Uma função recursiva deve ter:

- um caso base, que termina a recursão;
- um caso recursivo, que chama novamente a função.

## Exemplo: fatorial

```python
def fatorial(n):
    if n == 0:
        return 1

    return n * fatorial(n - 1)
```

Exemplo:

```python
print(fatorial(4))
```

Resultado:

```text
24
```

Processo:

```text
fatorial(4)
= 4 * fatorial(3)
= 4 * 3 * fatorial(2)
= 4 * 3 * 2 * fatorial(1)
= 4 * 3 * 2 * 1 * fatorial(0)
= 24
```

## Versão com validação

```python
def fatorial(n):
    if n < 0:
        raise ValueError("O fatorial não existe para números negativos")

    if n == 0:
        return 1

    return n * fatorial(n - 1)
```

## Recursão vs ciclos

| Iteração | Recursão |
|---|---|
| Usa ciclos | Usa chamadas da própria função |
| Geralmente mais eficiente | Pode ser mais elegante |
| Consome menos memória | Pode consumir mais memória |
| Mais simples para iniciantes | Pode ser menos intuitiva |

---

# 11. Funções Lambda

As funções lambda são funções pequenas e anónimas criadas com a palavra-chave `lambda`.

São úteis quando se pretende criar uma função simples, geralmente utilizada apenas uma vez.

## Sintaxe

```python
lambda parâmetros: expressão
```

## Exemplo

```python
dobro = lambda x: x * 2

print(dobro(5))
```

Resultado:

```text
10
```

A mesma função poderia ser escrita com `def`:

```python
def dobro(x):
    return x * 2
```

## Utilização com `sorted()`

```python
alunos = [
    {"nome": "Ana", "nota": 15},
    {"nome": "Bruno", "nota": 12},
    {"nome": "Carla", "nota": 18}
]

ordenados = sorted(alunos, key=lambda aluno: aluno["nota"])

print(ordenados)
```

## Quando evitar lambda

Deve evitar-se `lambda` quando a lógica é complexa. Nesses casos, é preferível utilizar `def`.

---

# 12. Programação Funcional

A programação funcional é um paradigma baseado na utilização de funções para transformar dados.

Python não é uma linguagem exclusivamente funcional, mas inclui ferramentas inspiradas neste paradigma.

## Funções puras

Uma função pura devolve sempre o mesmo resultado para os mesmos argumentos e não altera dados externos.

```python
def dobro(x):
    return x * 2
```

## `map()`

A função `map()` aplica uma função a todos os elementos de uma sequência.

```python
numeros = [1, 2, 3]

resultado = list(map(lambda x: x * 2, numeros))

print(resultado)
```

Resultado:

```text
[2, 4, 6]
```

Alternativa com list comprehension:

```python
resultado = [x * 2 for x in numeros]
```

## `filter()`

A função `filter()` seleciona elementos que cumprem uma condição.

```python
numeros = [1, 2, 3, 4, 5, 6]

pares = list(filter(lambda x: x % 2 == 0, numeros))

print(pares)
```

Resultado:

```text
[2, 4, 6]
```

Alternativa:

```python
pares = [x for x in numeros if x % 2 == 0]
```

## `sorted()`

```python
nomes = ["Ana", "Bruno", "Carla"]

ordenados = sorted(nomes)

print(ordenados)
```

Resultado:

```text
['Ana', 'Bruno', 'Carla']
```

## Ordenação com `key`

```python
palavras = ["python", "sol", "programacao"]

ordenadas = sorted(palavras, key=len)

print(ordenadas)
```

Resultado:

```text
['sol', 'python', 'programacao']
```

---

# 13. Bibliotecas, Módulos e Pacotes

Depois de compreender funções e formas de organizar código dentro de um ficheiro, é importante perceber como reutilizar código entre vários ficheiros e projetos.

Para isso, Python utiliza bibliotecas, módulos e pacotes.

## Biblioteca

Uma biblioteca é um conjunto de código reutilizável criado para resolver determinados tipos de problemas.

Exemplo:

```python
import math

print(math.sqrt(25))
```

Resultado:

```text
5.0
```

## Módulo

Um módulo é normalmente um ficheiro `.py` com código Python.

Exemplo:

```text
matematica.py
```

Conteúdo:

```python
def somar(a, b):
    return a + b
```

## Pacote

Um pacote é uma pasta que agrupa vários módulos.

```text
meu_pacote/
│
├── __init__.py
├── matematica.py
└── texto.py
```

## Comparação

| Conceito | Descrição |
|---|---|
| Biblioteca | Conjunto de código reutilizável |
| Módulo | Ficheiro `.py` com código Python |
| Pacote | Pasta que agrupa módulos |

---

# 14. Biblioteca Padrão

Python inclui uma vasta biblioteca padrão, disponível sem instalação adicional.

## `math`

```python
import math

print(math.sqrt(25))
print(math.pi)
```

## `random`

```python
import random

print(random.randint(1, 6))
```

## `datetime`

```python
from datetime import datetime

agora = datetime.now()

print(agora)
print(agora.year)
```

## `json`

```python
import json

dados = {
    "nome": "Ana",
    "idade": 16
}

texto = json.dumps(dados, indent=4)

print(texto)
```

## Vantagens

A biblioteca padrão permite:

- resolver muitos problemas rapidamente;
- evitar dependências externas;
- utilizar código já testado;
- aumentar produtividade.

---

# 15. Bibliotecas Externas

Para além da biblioteca padrão, Python possui muitas bibliotecas externas desenvolvidas pela comunidade.

Estas bibliotecas permitem adicionar funcionalidades avançadas aos programas.

## Instalar com `pip`

```bash
pip install pandas
```

Também é comum usar:

```bash
python -m pip install pandas
```

## `pandas`

O `pandas` é utilizado para análise e manipulação de dados.

```python
import pandas as pd

dados = {
    "nome": ["Ana", "Bruno", "Carla"],
    "nota": [15, 12, 18]
}

tabela = pd.DataFrame(dados)

print(tabela)
print(tabela["nota"].mean())
```

## `matplotlib`

O `matplotlib` é utilizado para criar gráficos.

```python
import matplotlib.pyplot as plt

nomes = ["Ana", "Bruno", "Carla"]
notas = [15, 12, 18]

plt.bar(nomes, notas)
plt.title("Notas dos alunos")
plt.xlabel("Aluno")
plt.ylabel("Nota")

plt.show()
```

## Ambientes virtuais

Em projetos maiores, recomenda-se utilizar ambientes virtuais.

```bash
python -m venv .venv
```

Ativar no Windows:

```bash
.venv\Scripts\activate
```

Ativar em Linux ou macOS:

```bash
source .venv/bin/activate
```

## `requirements.txt`

```bash
pip freeze > requirements.txt
pip install -r requirements.txt
```

---

# 16. Criar Módulos Próprios

Além de utilizar módulos já existentes, também é possível criar módulos próprios.

Isto permite organizar código em ficheiros separados e reutilizar funções em diferentes partes do projeto.

## Exemplo: `matematica.py`

```python
def somar(a, b):
    return a + b

def subtrair(a, b):
    return a - b
```

## Exemplo: `main.py`

```python
import matematica

print(matematica.somar(10, 5))
print(matematica.subtrair(10, 5))
```

Resultado:

```text
15
5
```

## Importar funções específicas

```python
from matematica import somar

print(somar(10, 5))
```

## Bloco `if __name__ == "__main__"`

```python
def somar(a, b):
    return a + b

if __name__ == "__main__":
    print(somar(10, 5))
```

Este bloco permite que determinado código só execute quando o ficheiro é executado diretamente, e não quando é importado noutro ficheiro.

---

# 17. Modularização

A modularização consiste em dividir um programa em vários módulos organizados por responsabilidade.

Esta abordagem é especialmente útil em projetos maiores, porque evita concentrar todo o código num único ficheiro.

## Estrutura recomendada

```text
projeto/
│
├── main.py
├── modelo.py
├── vista.py
└── controlador.py
```

## Responsabilidade de cada ficheiro

| Ficheiro | Responsabilidade |
|---|---|
| `main.py` | Ponto de entrada do programa |
| `modelo.py` | Regras de negócio e cálculos |
| `vista.py` | Entrada e saída de dados |
| `controlador.py` | Coordenação do programa |

## Exemplo: `modelo.py`

```python
def calcular_media(notas):
    return sum(notas) / len(notas)
```

## Exemplo: `vista.py`

```python
def mostrar_resultado(resultado):
    print(resultado)
```

## Exemplo: `controlador.py`

```python
from modelo import calcular_media
from vista import mostrar_resultado

def executar():
    media = calcular_media([10, 12, 14])
    mostrar_resultado(media)
```

## Exemplo: `main.py`

```python
from controlador import executar

executar()
```

## Vantagens da modularização

A modularização permite:

- separar responsabilidades;
- testar partes do programa isoladamente;
- reutilizar código;
- melhorar legibilidade;
- facilitar manutenção;
- tornar projetos mais profissionais.

## Evitar dependências circulares

Uma dependência circular acontece quando dois módulos importam diretamente um ao outro.

Exemplo problemático:

```text
modelo.py importa controlador.py
controlador.py importa modelo.py
```

Para evitar este problema:

- mantém responsabilidades claras;
- evita imports desnecessários;
- centraliza a coordenação no controlador;
- separa lógica, apresentação e entrada de dados.

---

# Conclusão

As funções são a base para escrever programas organizados em Python.

Ao longo desta sebenta, foram apresentados conceitos fundamentais como parâmetros, `return`, validação, mutabilidade, boas práticas, recursão, funções lambda, programação funcional, bibliotecas e modularização.

Dominar estes temas permite escrever código mais claro, reutilizável, testável e preparado para projetos maiores.
