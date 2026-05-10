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

Ao criar funções em Python, é fundamental compreender a diferença entre `print()` e `return`.

Embora ambos possam apresentar resultados relacionados com uma função, têm objetivos completamente diferentes.

- `print()` serve para mostrar informação no ecrã;
- `return` serve para devolver um valor ao programa.

Compreender esta distinção é essencial para escrever funções reutilizáveis e bem estruturadas.

---

## Utilização de `print()`

A função `print()` é utilizada para apresentar informação ao utilizador.

```python
def mostrar():
    print("Olá")
```

Neste exemplo, a função apenas escreve a palavra `"Olá"` no ecrã.

Para executar a função:

```python
mostrar()
```

Resultado:

```text
Olá
```

---

## Características do `print()`

Quando utilizamos `print()`:

- a informação é apenas apresentada;
- o valor não fica disponível para reutilização;
- a função não devolve resultados úteis ao programa;
- normalmente é utilizado para mensagens, menus ou depuração.

Exemplo:

```python
def somar(a, b):
    print(a + b)

resultado = somar(2, 3)

print(resultado)
```

Resultado:

```text
5
None
```

Neste caso:

- `5` foi mostrado por `print(a + b)`;
- `None` aparece porque a função não devolveu nenhum valor.

Quando uma função não utiliza `return`, Python devolve automaticamente `None`.

---

## Utilização de `return`

A instrução `return` é utilizada para devolver um valor ao programa.

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

Neste exemplo:

- a função calcula o dobro de `x`;
- o valor calculado é devolvido através de `return`;
- o resultado pode ser guardado numa variável;
- o valor devolvido pode ser reutilizado noutros cálculos.

---

## Vantagens do `return`

As funções que utilizam `return` são geralmente mais úteis e reutilizáveis.

Permitem:

- guardar resultados em variáveis;
- reutilizar valores em outros cálculos;
- combinar funções;
- criar programas mais modulares;
- facilitar testes automáticos.

Exemplo:

```python
def calcular_media(a, b):
    return (a + b) / 2

media = calcular_media(12, 16)

if media >= 10:
    print("Aprovado")
```

Neste caso, o valor devolvido pela função é utilizado posteriormente numa condição.

---

## Comparação entre `print()` e `return`

| `print()` | `return` |
|---|---|
| Mostra informação no ecrã | Devolve informação ao programa |
| Utilizado para apresentação | Utilizado para processamento |
| Não permite reutilizar diretamente o resultado | Permite reutilizar o resultado |
| Produz saída visual | Produz valores utilizáveis |
| Frequentemente usado em menus e mensagens | Frequentemente usado em cálculos |

---

## Quando utilizar cada um?

### Utilizar `print()` quando:

- pretendes mostrar mensagens ao utilizador;
- queres apresentar menus ou resultados;
- estás a depurar o programa.

Exemplo:

```python
def mostrar_menu():
    print("1 - Jogar")
    print("2 - Sair")
```

---

### Utilizar `return` quando:

- pretendes devolver resultados;
- queres reutilizar valores;
- a função realiza cálculos;
- o resultado será usado noutras partes do programa.

Exemplo:

```python
def area_retangulo(largura, altura):
    return largura * altura
```

---

## Boa prática recomendada

Em muitos casos, é aconselhável separar:

- funções responsáveis por cálculos;
- funções responsáveis por apresentação.

Exemplo:

```python
def calcular_area(largura, altura):
    return largura * altura

def mostrar_area(area):
    print(f"Área: {area}")
```

Esta abordagem torna o código mais organizado, reutilizável e fácil de testar.

---

# 4. Parâmetros e Argumentos

As funções podem receber dados do exterior para executar operações diferentes consoante os valores fornecidos.

Esses dados são recebidos através de parâmetros e enviados através de argumentos.

Compreender a diferença entre estes dois conceitos é essencial para utilizar funções de forma correta e flexível.

---

## Parâmetros

Os parâmetros são variáveis definidas na criação da função.

Funcionam como espaços reservados para os valores que serão recebidos quando a função for executada.

```python
def somar(a, b):
    return a + b
```

Neste exemplo:

- `a` e `b` são parâmetros;
- representam os valores que a função irá receber;
- apenas existem dentro da função.

---

## Argumentos

Os argumentos são os valores reais enviados para a função no momento da chamada.

```python
somar(10, 20)
```

Neste caso:

- `10` é o argumento associado ao parâmetro `a`;
- `20` é o argumento associado ao parâmetro `b`.

O resultado da função será:

```text
30
```

---

## Relação entre parâmetros e argumentos

| Conceito | Descrição |
|---|---|
| Parâmetro | Variável definida na função |
| Argumento | Valor enviado para a função |

Exemplo completo:

```python
def multiplicar(a, b):
    return a * b

resultado = multiplicar(4, 5)

print(resultado)
```

Resultado:

```text
20
```

---

## Argumentos posicionais

Por defeito, os argumentos são associados aos parâmetros pela ordem em que aparecem.

```python
def apresentar(nome, idade):
    print(f"{nome} tem {idade} anos.")

apresentar("Ana", 16)
```

Resultado:

```text
Ana tem 16 anos.
```

A ordem é importante.

Exemplo incorreto:

```python
apresentar(16, "Ana")
```

Resultado:

```text
16 tem Ana anos.
```

---

## Argumentos nomeados

Python permite enviar argumentos indicando explicitamente o nome do parâmetro.

```python
def apresentar(nome, idade):
    print(f"{nome} tem {idade} anos.")

apresentar(nome="Ana", idade=16)
```

Também é possível alterar a ordem:

```python
apresentar(idade=16, nome="Ana")
```

Os argumentos nomeados tornam o código mais legível e reduzem erros relacionados com a ordem dos valores.

---

## Valores por defeito

Os parâmetros podem ter valores predefinidos.

Se nenhum argumento for fornecido, o valor por defeito será utilizado.

```python
def saudacao(nome="Aluno"):
    print(f"Olá, {nome}")
```

Exemplos:

```python
saudacao()
saudacao("Rita")
```

Resultado:

```text
Olá, Aluno
Olá, Rita
```

---

## Número variável de argumentos com `*args`

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

Neste caso:

- `numeros` é uma tupla;
- a função pode receber qualquer quantidade de valores.

Exemplo adicional:

```python
print(somar_todos(10, 20, 30, 40))
```

Resultado:

```text
100
```

---

## Número variável de argumentos nomeados com `**kwargs`

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

Neste caso:

- `dados` é um dicionário;
- cada argumento nomeado torna-se uma chave e respetivo valor.

Exemplo adicional:

```python
mostrar_dados(nome="Bruno", idade=17, turma="10A")
```

Resultado:

```text
{'nome': 'Bruno', 'idade': 17, 'turma': '10A'}
```

---

## Combinar diferentes tipos de argumentos

É possível combinar:

- argumentos posicionais;
- argumentos nomeados;
- valores por defeito;
- `*args`;
- `**kwargs`.

Exemplo:

```python
def criar_utilizador(nome, idade, ativo=True):
    return {
        "nome": nome,
        "idade": idade,
        "ativo": ativo
    }

utilizador = criar_utilizador("Ana", 16)

print(utilizador)
```

Resultado:

```text
{'nome': 'Ana', 'idade': 16, 'ativo': True}
```

---

## Boas práticas

Ao trabalhar com parâmetros e argumentos:

- utiliza nomes claros e descritivos;
- evita funções com demasiados parâmetros;
- utiliza valores por defeito quando apropriado;
- usa `*args` e `**kwargs` apenas quando necessário;
- prefere argumentos nomeados em funções complexas.

Estas práticas tornam o código mais legível e mais fácil de manter.

---

# 5. Variáveis Locais e Globais

As variáveis utilizadas num programa podem ter diferentes âmbitos de existência e utilização.

Em Python, uma variável pode ser:

- local;
- global.

Compreender esta diferença é importante para evitar erros e tornar o código mais previsível e organizado.

---

## Variáveis locais

Uma variável local é criada dentro de uma função e só pode ser utilizada no interior dessa função.

```python
def teste():
    numero = 10
    print(numero)
```

Neste exemplo:

- `numero` é uma variável local;
- apenas existe enquanto a função está a ser executada;
- não pode ser utilizada fora da função.

Para executar a função:

```python
teste()
```

Resultado:

```text
10
```

---

## Tentativa de acesso fora da função

Uma variável local deixa de existir fora da função.

Exemplo:

```python
def teste():
    numero = 10

print(numero)
```

Neste caso, Python gera um erro:

```text
NameError: name 'numero' is not defined
```

Isto acontece porque `numero` apenas existe dentro da função `teste()`.

---

## Vantagens das variáveis locais

As variáveis locais ajudam a:

- evitar conflitos entre nomes;
- proteger dados internos da função;
- tornar o código mais seguro;
- reduzir efeitos secundários inesperados.

Em geral, é recomendável utilizar variáveis locais sempre que possível.

---

## Variáveis globais

Uma variável global é criada fora das funções e pode ser utilizada em diferentes partes do programa.

```python
mensagem = "Olá"

def mostrar():
    print(mensagem)
```

Neste exemplo:

- `mensagem` é uma variável global;
- foi criada fora da função;
- pode ser lida dentro da função.

Executando a função:

```python
mostrar()
```

Resultado:

```text
Olá
```

---

## Utilização de variáveis globais

As funções conseguem aceder a variáveis globais para leitura.

Exemplo:

```python
contador = 5

def mostrar():
    print(contador)

mostrar()
```

Resultado:

```text
5
```

---

## Alterar variáveis globais

Alterar variáveis globais dentro de funções geralmente não é recomendado, porque pode tornar o programa mais difícil de compreender e manter.

Exemplo:

```python
contador = 0

def aumentar():
    global contador
    contador += 1

aumentar()

print(contador)
```

Resultado:

```text
1
```

Neste caso:

- a palavra-chave `global` indica que a função pretende alterar a variável global;
- sem `global`, Python criaria uma variável local com o mesmo nome.

---

## Problemas das variáveis globais

O uso excessivo de variáveis globais pode:

- dificultar a manutenção do código;
- gerar comportamentos inesperados;
- aumentar a probabilidade de erros;
- tornar os programas mais difíceis de testar.

Por essa razão, o uso de variáveis globais deve ser limitado.

---

## Alternativa recomendada

Em muitos casos, é preferível receber valores através de parâmetros e devolver resultados com `return`.

Exemplo recomendado:

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

Esta abordagem é mais segura, previsível e modular.

---

## Regra LEGB

Quando Python procura uma variável, segue normalmente a regra LEGB.

| Letra | Significado | Localização |
|---|---|---|
| L | Local | Dentro da função atual |
| E | Enclosing | Funções exteriores |
| G | Global | Ficheiro atual |
| B | Built-in | Nomes internos do Python |

Exemplo:

```python
x = "global"

def exterior():
    x = "exterior"

    def interior():
        x = "local"
        print(x)

    interior()

exterior()
```

Resultado:

```text
local
```

Python procura primeiro no âmbito mais próximo antes de avançar para os restantes níveis.

---

## Boas práticas

Ao trabalhar com variáveis:

- prefere variáveis locais;
- evita alterar variáveis globais sempre que possível;
- utiliza parâmetros e `return` para comunicar dados entre funções;
- escolhe nomes claros e descritivos;
- limita o âmbito das variáveis ao mínimo necessário.

Estas práticas ajudam a criar programas mais organizados, seguros e fáceis de manter.

---

# 6. Validação e Tratamento de Erros

Os programas reais recebem frequentemente dados inválidos ou inesperados.

Por exemplo:

- um utilizador pode introduzir texto em vez de números;
- uma lista pode estar vazia;
- pode ocorrer uma divisão por zero;
- um ficheiro pode não existir.

Por essa razão, é importante validar dados e tratar erros de forma adequada.

A validação e o tratamento de erros ajudam a criar programas:

- mais robustos;
- mais seguros;
- mais previsíveis;
- mais fáceis de utilizar.

---

## Validação simples

Validar dados significa verificar se os valores recebidos cumprem determinadas condições antes de serem utilizados.

Exemplo:

```python
def validar_idade(idade):
    return idade >= 0
```

Neste exemplo:

- a função verifica se a idade é maior ou igual a zero;
- devolve `True` caso seja válida;
- devolve `False` caso seja inválida.

Exemplo de utilização:

```python
if validar_idade(18):
    print("Idade válida")
else:
    print("Idade inválida")
```

Resultado:

```text
Idade válida
```

---

## Validação com mensagens de erro

Também é possível devolver mensagens mais informativas.

```python
def validar_idade(idade):
    if idade < 0:
        return "Idade inválida"

    return "Idade válida"
```

Embora esta abordagem funcione, em programas maiores costuma ser preferível utilizar exceções.

---

## Exceções

Uma exceção é um erro que ocorre durante a execução do programa.

Quando ocorre uma exceção, Python interrompe normalmente a execução do programa, a menos que o erro seja tratado.

Exemplo:

```python
def dividir(a, b):
    if b == 0:
        raise ZeroDivisionError("Divisão por zero")

    return a / b
```

Neste exemplo:

- a função verifica se `b` é igual a zero;
- se for, é lançada uma exceção com `raise`;
- caso contrário, a divisão é executada normalmente.

---

## A instrução `raise`

A palavra-chave `raise` permite lançar exceções manualmente.

Sintaxe geral:

```python
raise NomeDaExcecao("mensagem")
```

Exemplo:

```python
raise ValueError("Valor inválido")
```

As mensagens ajudam a identificar o problema ocorrido.

---

## Exceções comuns em Python

| Exceção | Situação comum |
|---|---|
| `TypeError` | Tipo de dado incorreto |
| `ValueError` | Valor inválido |
| `ZeroDivisionError` | Divisão por zero |
| `IndexError` | Índice inexistente |
| `KeyError` | Chave inexistente num dicionário |
| `FileNotFoundError` | Ficheiro não encontrado |

---

## Tratamento de erros com `try` e `except`

O bloco `try` permite tentar executar código que pode gerar erros.

O bloco `except` permite capturar e tratar esses erros.

```python
try:
    numero = int(input("Número: "))
except ValueError:
    print("Valor inválido")
```

Neste exemplo:

- `int()` tenta converter o valor introduzido para inteiro;
- se o utilizador escrever texto inválido, ocorre um `ValueError`;
- o bloco `except` trata o erro e mostra uma mensagem.

---

## Funcionamento do `try` e `except`

| Bloco | Função |
|---|---|
| `try` | Executa código potencialmente problemático |
| `except` | Trata erros específicos |

---

## Exemplo completo

```python
try:
    numero = int(input("Número: "))
    print(numero)
except ValueError:
    print("Introduz um número válido")
```

Possível resultado:

```text
Número: abc
Introduz um número válido
```

O programa continua a funcionar sem terminar abruptamente.

---

## Capturar o erro numa variável

Também é possível guardar a exceção numa variável.

```python
try:
    numero = int(input("Número: "))
except ValueError as erro:
    print("Erro:", erro)
```

Exemplo de resultado:

```text
Erro: invalid literal for int() with base 10: 'abc'
```

---

## `else`

O bloco `else` executa apenas se não ocorrer nenhum erro.

```python
try:
    numero = int(input("Número: "))
except ValueError:
    print("Valor inválido")
else:
    print("Número válido")
```

---

## `finally`

O bloco `finally` executa sempre, independentemente de ocorrer erro ou não.

```python
try:
    numero = int(input("Número: "))
except ValueError:
    print("Erro")
finally:
    print("Fim da tentativa")
```

O `finally` é frequentemente utilizado para:

- fechar ficheiros;
- libertar recursos;
- executar limpeza final.

---

## Exemplo: divisão segura

```python
def dividir(a, b):
    if b == 0:
        raise ZeroDivisionError("Não é possível dividir por zero")

    return a / b

try:
    resultado = dividir(10, 0)
except ZeroDivisionError as erro:
    print("Erro:", erro)
```

Resultado:

```text
Erro: Não é possível dividir por zero
```

---

## Vantagens da validação e tratamento de erros

Estas técnicas permitem:

- evitar falhas inesperadas;
- melhorar a experiência do utilizador;
- tornar os programas mais robustos;
- identificar problemas com maior facilidade;
- separar lógica principal do tratamento de erros.

---

## Boas práticas

Ao validar dados e tratar erros:

- valida dados importantes antes de os utilizar;
- utiliza exceções para situações realmente problemáticas;
- captura apenas os erros necessários;
- evita esconder erros importantes;
- escreve mensagens claras e informativas;
- separa a lógica principal do tratamento de erros.

Estas práticas ajudam a criar programas mais profissionais e mais fáceis de manter.

---
# 7. Objetos Mutáveis e Imutáveis

Em Python, todos os valores são objetos.

Alguns objetos podem ser alterados depois de serem criados, enquanto outros não podem.

Por essa razão, os objetos dividem-se em dois grandes grupos:

- objetos mutáveis;
- objetos imutáveis.

Compreender esta diferença é muito importante para evitar comportamentos inesperados, especialmente ao trabalhar com listas, dicionários e funções.

---

## Objetos imutáveis

Um objeto imutável não pode ser alterado depois de ser criado.

Quando parece que o valor mudou, na realidade Python cria um novo objeto.

Exemplos de tipos imutáveis:

- `int`
- `float`
- `str`
- `bool`
- `tuple`

Exemplo:

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

Neste exemplo:

- `outro` mantém o valor `10`;
- ao executar `numero += 1`, Python cria um novo objeto;
- o objeto original não é alterado.

---

## Strings imutáveis

As strings também são imutáveis.

Exemplo:

```python
texto = "Python"

texto.upper()

print(texto)
```

Resultado:

```text
Python
```

O método `upper()` devolve uma nova string, mas não altera a original.

Forma correta:

```python
texto = texto.upper()

print(texto)
```

Resultado:

```text
PYTHON
```

---

## Objetos mutáveis

Um objeto mutável pode ser alterado depois de ser criado.

Exemplos de tipos mutáveis:

- `list`
- `dict`
- `set`

---

## Exemplo com listas

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

Neste caso:

- `lista` e `outra` referem-se ao mesmo objeto;
- quando a lista é alterada com `append()`, a alteração é visível em ambas as variáveis.

---

## Referências a objetos

Em Python, as variáveis guardam referências para objetos e não os objetos diretamente.

Exemplo:

```python
a = [1, 2]

b = a
```

Visualmente:

```text
a ──► [1, 2]
b ──► [1, 2]
```

As duas variáveis apontam para a mesma lista.

---

## Criar cópias de listas

Para evitar alterações inesperadas, pode ser necessário criar uma cópia do objeto.

Exemplo:

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

Neste caso:

- `copy()` cria uma nova lista independente;
- as alterações deixam de afetar ambas as variáveis.

---

## Mutabilidade em funções

Os objetos mutáveis podem ser alterados dentro de funções.

Exemplo:

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

A lista original foi modificada dentro da função.

---

## Efeitos secundários

Um efeito secundário acontece quando uma função altera dados externos à própria função.

Nem sempre isso é desejável.

Exemplo com efeito secundário:

```python
def adicionar(lista):
    lista.append(5)
```

Neste caso, a função altera diretamente a lista recebida.

---

## Versão mais segura

Uma abordagem mais segura consiste em criar uma cópia do objeto.

```python
def adicionar(lista):
    nova_lista = lista.copy()

    nova_lista.append(5)

    return nova_lista
```

Desta forma:

- a lista original não é alterada;
- a função torna-se mais previsível;
- o código fica mais fácil de testar.

---

## Problema comum com valores por defeito

Um erro frequente ocorre quando se utilizam listas como valores por defeito em funções.

Exemplo problemático:

```python
def adicionar_item(item, lista=[]):
    lista.append(item)

    return lista
```

Neste caso:

- a mesma lista pode ser reutilizada entre chamadas da função;
- podem surgir comportamentos inesperados.

---

## Forma recomendada

```python
def adicionar_item(item, lista=None):
    if lista is None:
        lista = []

    lista.append(item)

    return lista
```

Esta abordagem evita reutilizações involuntárias da mesma lista.

---

## Comparação entre mutáveis e imutáveis

| Tipo | Mutável? |
|---|---|
| `int` | Não |
| `float` | Não |
| `str` | Não |
| `tuple` | Não |
| `list` | Sim |
| `dict` | Sim |
| `set` | Sim |

---

## Boas práticas

Ao trabalhar com objetos mutáveis:

- evita alterar listas e dicionários sem necessidade;
- cria cópias quando necessário;
- tem atenção aos efeitos secundários;
- evita utilizar listas como valores por defeito;
- prefere funções previsíveis e controladas.

Estas práticas ajudam a reduzir erros e tornam o código mais seguro e mais fácil de compreender.

---

# 8. Boas Práticas

Escrever código funcional é importante, mas escrever código claro, organizado e fácil de manter é igualmente essencial.

As boas práticas ajudam a:

- melhorar a legibilidade;
- reduzir erros;
- facilitar manutenção;
- simplificar testes;
- tornar os programas mais profissionais.

Ao criar funções, é importante pensar não apenas no funcionamento do código, mas também na sua clareza e organização.

---

## Utilizar nomes claros e descritivos

O nome de uma função deve indicar claramente o que ela faz.

Nomes vagos ou demasiado curtos dificultam a compreensão do programa.

Mau exemplo:

```python
def f(x):
    return x * 2
```

Neste caso:

- o nome `f` não explica o objetivo da função;
- `x` é demasiado genérico.

Melhor:

```python
def calcular_dobro(numero):
    return numero * 2
```

Agora:

- o nome da função descreve a operação realizada;
- o parâmetro é mais claro e informativo.

---

## Recomendações para nomes

Ao escolher nomes:

- utiliza palavras descritivas;
- evita abreviações desnecessárias;
- utiliza verbos em funções;
- mantém consistência no projeto.

Exemplos adequados:

```python
calcular_media()
validar_idade()
mostrar_menu()
guardar_ficheiro()
```

---

## Uma função deve ter uma única responsabilidade

Cada função deve realizar apenas uma tarefa principal.

Funções demasiado grandes tornam-se:

- difíceis de compreender;
- difíceis de testar;
- difíceis de reutilizar;
- mais propensas a erros.

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

Esta função:

- calcula a média;
- apresenta resultados;
- decide aprovação.

Está a assumir demasiadas responsabilidades.

---

## Melhor abordagem

Separar tarefas em funções diferentes.

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

Vantagens:

- código mais organizado;
- funções mais reutilizáveis;
- testes mais simples;
- manutenção mais fácil.

---

## Evitar repetição de código

Quando o mesmo código aparece várias vezes, provavelmente deve ser transformado numa função.

Antes:

```python
media1 = (10 + 12 + 14) / 3
media2 = (15 + 16 + 18) / 3
```

Melhor:

```python
def calcular_media(notas):
    return sum(notas) / len(notas)

media1 = calcular_media([10, 12, 14])
media2 = calcular_media([15, 16, 18])
```

---

## Separar cálculo de apresentação

Uma boa prática consiste em separar:

- funções que calculam;
- funções que mostram resultados.

Exemplo:

```python
def calcular_area(largura, altura):
    return largura * altura

def mostrar_area(area):
    print(f"Área: {area}")
```

Isto facilita:

- reutilização;
- testes automáticos;
- manutenção.

---

## Evitar funções demasiado grandes

Uma função muito extensa geralmente indica má organização.

Sinais de alerta:

- demasiadas linhas;
- muitos `if` e ciclos;
- múltiplas tarefas diferentes;
- dificuldade em explicar a função numa frase.

Quando isso acontece, normalmente a função deve ser dividida em partes menores.

---

## Código legível é importante

Um programa é frequentemente lido mais vezes do que é escrito.

Por isso:

- utiliza indentação correta;
- mantém espaçamento consistente;
- escreve código simples;
- evita complexidade desnecessária.

Código legível reduz erros e facilita colaboração.

---

## Checklist de boas práticas

Antes de considerar uma função terminada, verifica:

- o nome é claro?
- a função tem apenas uma responsabilidade?
- os parâmetros fazem sentido?
- existe repetição desnecessária?
- o código é legível?
- a função pode ser reutilizada?
- existem validações importantes?

---

# 9. Docstrings e Type Hints

À medida que os programas aumentam de dimensão, torna-se importante documentar e clarificar o código.

As docstrings e os type hints ajudam a:

- melhorar a legibilidade;
- facilitar manutenção;
- tornar o código mais compreensível;
- auxiliar ferramentas de desenvolvimento;
- facilitar colaboração entre programadores.

---

## Docstrings

Uma docstring é um texto utilizado para documentar uma função, classe ou módulo.

A docstring é colocada logo após a definição da função.

```python
def calcular_media(notas):
    """Calcula a média."""
    return sum(notas) / len(notas)
```

Neste exemplo:

- a frase `"Calcula a média."` descreve o objetivo da função;
- a documentação fica associada à função.

---

## Objetivo das docstrings

As docstrings ajudam a:

- explicar o funcionamento da função;
- indicar parâmetros esperados;
- descrever valores devolvidos;
- documentar possíveis erros.

São especialmente importantes em projetos maiores.

---

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

---

## Consultar docstrings

A documentação pode ser consultada com a função `help()`.

```python
help(calcular_media)
```

Isto mostra a docstring associada à função.

---

## Type Hints

Os type hints permitem indicar os tipos de dados esperados nos parâmetros e no valor devolvido.

```python
def somar(a: int, b: int) -> int:
    return a + b
```

Neste exemplo:

- `a` e `b` devem ser inteiros;
- a função devolve um inteiro.

---

## Objetivo dos type hints

Os type hints ajudam a:

- tornar o código mais claro;
- facilitar deteção de erros;
- melhorar ferramentas de análise;
- auxiliar editores de código;
- melhorar autocompletar.

---

## Type hints não obrigam tipos

Python continua a ser uma linguagem dinâmica.

Isto significa que os type hints:

- não impedem automaticamente valores incorretos;
- funcionam principalmente como documentação e apoio ao desenvolvimento.

Exemplo:

```python
def somar(a: int, b: int) -> int:
    return a + b

print(somar("2", "3"))
```

Embora exista indicação de tipos, Python continuará a executar o código.

Resultado:

```text
23
```

---

## Type hints com listas

```python
def calcular_media(notas: list[float]) -> float:
    return sum(notas) / len(notas)
```

Neste caso:

- a função espera uma lista de números reais;
- o resultado será um número real.

---

## Combinar docstrings e type hints

As duas abordagens complementam-se muito bem.

```python
def converter_celsius_para_fahrenheit(celsius: float) -> float:
    """
    Converte uma temperatura de Celsius para Fahrenheit.
    """

    return celsius * 9 / 5 + 32
```

Este tipo de código torna-se:

- mais legível;
- mais profissional;
- mais fácil de manter.

---

## Boas práticas

Ao utilizar docstrings e type hints:

- documenta funções importantes;
- escreve descrições curtas e claras;
- utiliza type hints de forma consistente;
- evita documentação redundante;
- mantém a documentação atualizada.

Estas práticas ajudam a criar programas mais organizados, compreensíveis e profissionais.

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
