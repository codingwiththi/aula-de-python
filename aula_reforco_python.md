# Aula de Reforço - Programação Python
## Estruturas de Seleção, Repetição, Modularização e Tipos de Dados

---

## 1. ESTRUTURAS DE SELEÇÃO

### 1.1 Conceito
Estruturas de seleção permitem que o programa tome decisões baseadas em condições.

### 1.2 Tipos de Estruturas de Seleção

#### IF Simples
```python
idade = 18
if idade >= 18:
    print("Maior de idade")
```

#### IF-ELSE
```python
nota = 7.5
if nota >= 7:
    print("Aprovado")
else:
    print("Reprovado")
```

#### IF-ELIF-ELSE
```python
nota = 8.5
if nota >= 9:
    print("Excelente")
elif nota >= 7:
    print("Bom")
elif nota >= 5:
    print("Regular")
else:
    print("Insuficiente")
```

### 1.3 Operadores de Comparação
- `==` (igual)
- `!=` (diferente)
- `>` (maior)
- `<` (menor)
- `>=` (maior ou igual)
- `<=` (menor ou igual)

### 1.4 Operadores Lógicos
- `and` (E lógico)
- `or` (OU lógico)
- `not` (NÃO lógico)

```python
idade = 20
tem_carteira = True

if idade >= 18 and tem_carteira:
    print("Pode dirigir")
```

### 1.5 Exercício Prático
```python
# Sistema de classificação de IMC
peso = float(input("Digite seu peso (kg): "))
altura = float(input("Digite sua altura (m): "))

imc = peso / (altura ** 2)

if imc < 18.5:
    classificacao = "Abaixo do peso"
elif imc < 25:
    classificacao = "Peso normal"
elif imc < 30:
    classificacao = "Sobrepeso"
else:
    classificacao = "Obesidade"

print(f"IMC: {imc:.2f} - {classificacao}")
```

---

## 2. ESTRUTURAS DE REPETIÇÃO

### 2.1 FOR - Repetição com Contador

#### FOR com range()
```python
# Números de 0 a 4
for i in range(5):
    print(i)

# Números de 1 a 10
for i in range(1, 11):
    print(i)

# Números pares de 0 a 10
for i in range(0, 11, 2):
    print(i)
```

#### FOR com Listas
```python
frutas = ["maçã", "banana", "uva"]
for fruta in frutas:
    print(f"Eu gosto de {fruta}")
```

#### FOR com enumerate()
```python
nomes = ["Ana", "João", "Maria"]
for indice, nome in enumerate(nomes):
    print(f"{indice}: {nome}")
```

### 2.2 WHILE - Repetição com Condição

```python
contador = 0
while contador < 5:
    print(f"Contador: {contador}")
    contador += 1
```

#### WHILE com validação de entrada
```python
senha = ""
while senha != "123456":
    senha = input("Digite a senha: ")
    if senha != "123456":
        print("Senha incorreta. Tente novamente.")
print("Acesso liberado!")
```

### 2.3 Controle de Fluxo

#### BREAK - Interrompe o loop
```python
for i in range(10):
    if i == 5:
        break
    print(i)
# Imprime: 0, 1, 2, 3, 4
```

#### CONTINUE - Pula para próxima iteração
```python
for i in range(5):
    if i == 2:
        continue
    print(i)
# Imprime: 0, 1, 3, 4
```

### 2.4 Exercício Prático
```python
# Calculadora de média de notas
notas = []
while True:
    entrada = input("Digite uma nota (ou 'fim' para terminar): ")
    if entrada.lower() == 'fim':
        break
    try:
        nota = float(entrada)
        if 0 <= nota <= 10:
            notas.append(nota)
        else:
            print("Nota deve estar entre 0 e 10")
    except ValueError:
        print("Digite um número válido")

if notas:
    media = sum(notas) / len(notas)
    print(f"Média: {media:.2f}")
else:
    print("Nenhuma nota foi inserida")
```

---

## 3. MODULARIZAÇÃO

### 3.1 Conceito
Modularização é dividir o código em partes menores e reutilizáveis (funções e módulos).

### 3.2 Funções

#### Função Simples
```python
def saudacao():
    print("Olá, mundo!")

saudacao()  # Chama a função
```

#### Função com Parâmetros
```python
def saudacao_personalizada(nome):
    print(f"Olá, {nome}!")

saudacao_personalizada("João")
```

#### Função com Retorno
```python
def somar(a, b):
    return a + b

resultado = somar(5, 3)
print(resultado)  # 8
```

#### Função com Parâmetros Padrão
```python
def calcular_desconto(preco, desconto=10):
    return preco * (1 - desconto/100)

print(calcular_desconto(100))     # 90.0 (desconto padrão 10%)
print(calcular_desconto(100, 20)) # 80.0 (desconto 20%)
```

#### Função com Múltiplos Retornos
```python
def dividir(a, b):
    if b == 0:
        return None, "Erro: divisão por zero"
    return a / b, "Sucesso"

resultado, mensagem = dividir(10, 2)
print(f"Resultado: {resultado}, Status: {mensagem}")
```

### 3.3 Escopo de Variáveis

```python
# Variável global
contador_global = 0

def incrementar():
    global contador_global
    contador_global += 1
    # Variável local
    contador_local = 10
    return contador_local

print(incrementar())  # 10
print(contador_global)  # 1
```

### 3.4 Exercício Prático - Sistema de Biblioteca
```python
def validar_isbn(isbn):
    """Valida se ISBN tem 10 ou 13 dígitos"""
    isbn_limpo = isbn.replace("-", "").replace(" ", "")
    return len(isbn_limpo) in [10, 13] and isbn_limpo.isdigit()

def calcular_multa(dias_atraso, valor_diario=2.00):
    """Calcula multa por atraso na devolução"""
    if dias_atraso <= 0:
        return 0
    return dias_atraso * valor_diario

def status_livro(dias_emprestado):
    """Retorna status do empréstimo"""
    if dias_emprestado <= 7:
        return "No prazo"
    elif dias_emprestado <= 14:
        return "Próximo do vencimento"
    else:
        return "Atrasado"

# Testando as funções
isbn = "978-85-7522-123-4"
print(f"ISBN válido: {validar_isbn(isbn)}")

multa = calcular_multa(5)
print(f"Multa: R$ {multa:.2f}")

status = status_livro(10)
print(f"Status: {status}")
```

---

## 4. ESTRUTURAS DE DADOS - TIPOS EMBUTIDOS

### 4.1 LISTAS

#### Criação e Acesso
```python
# Criação
frutas = ["maçã", "banana", "uva"]
numeros = [1, 2, 3, 4, 5]
mista = ["texto", 42, 3.14, True]

# Acesso por índice
print(frutas[0])    # maçã
print(frutas[-1])   # uva (último elemento)
```

#### Métodos Principais
```python
lista = [1, 2, 3]

# Adicionar elementos
lista.append(4)         # [1, 2, 3, 4]
lista.insert(0, 0)      # [0, 1, 2, 3, 4]
lista.extend([5, 6])    # [0, 1, 2, 3, 4, 5, 6]

# Remover elementos
lista.remove(0)         # Remove primeira ocorrência de 0
ultimo = lista.pop()    # Remove e retorna último elemento
segundo = lista.pop(1)  # Remove e retorna elemento no índice 1

# Outros métodos úteis
lista.sort()            # Ordena in-place
lista.reverse()         # Inverte in-place
print(len(lista))       # Tamanho da lista
print(2 in lista)       # Verifica se 2 está na lista
```

#### List Comprehension
```python
# Forma tradicional
quadrados = []
for i in range(1, 6):
    quadrados.append(i ** 2)

# List comprehension
quadrados = [i ** 2 for i in range(1, 6)]  # [1, 4, 9, 16, 25]

# Com condição
pares = [i for i in range(10) if i % 2 == 0]  # [0, 2, 4, 6, 8]
```

### 4.2 TUPLAS

```python
# Criação
coordenadas = (10, 20)
cores = ("vermelho", "verde", "azul")

# Tupla de um elemento (note a vírgula)
singleton = (42,)

# Desempacotamento
x, y = coordenadas
print(f"X: {x}, Y: {y}")

# Métodos
print(cores.count("verde"))  # Conta ocorrências
print(cores.index("azul"))   # Retorna índice

# Tuplas são imutáveis
# coordenadas[0] = 15  # Erro!
```

### 4.3 DICIONÁRIOS

#### Criação e Acesso
```python
# Criação
pessoa = {
    "nome": "João",
    "idade": 30,
    "cidade": "São Paulo"
}

# Acesso
print(pessoa["nome"])           # João
print(pessoa.get("idade"))      # 30
print(pessoa.get("profissao", "Não informado"))  # Valor padrão
```

#### Métodos Principais
```python
# Adicionar/Modificar
pessoa["profissao"] = "Engenheiro"
pessoa.update({"salario": 5000, "idade": 31})

# Remover
del pessoa["cidade"]
salario = pessoa.pop("salario", 0)  # Remove e retorna (com padrão)

# Iteração
for chave in pessoa:
    print(f"{chave}: {pessoa[chave]}")

for chave, valor in pessoa.items():
    print(f"{chave}: {valor}")

# Métodos úteis
print(pessoa.keys())    # Chaves
print(pessoa.values())  # Valores
print(len(pessoa))      # Número de itens
```

#### Dictionary Comprehension
```python
# Quadrados de números de 1 a 5
quadrados = {i: i**2 for i in range(1, 6)}
# {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

### 4.4 CONJUNTOS (SETS)

```python
# Criação
numeros = {1, 2, 3, 4, 5}
frutas = set(["maçã", "banana", "uva"])

# Operações
numeros.add(6)
numeros.remove(1)  # Erro se não existir
numeros.discard(10)  # Não dá erro se não existir

# Operações matemáticas
set1 = {1, 2, 3, 4}
set2 = {3, 4, 5, 6}

print(set1 | set2)  # União: {1, 2, 3, 4, 5, 6}
print(set1 & set2)  # Interseção: {3, 4}
print(set1 - set2)  # Diferença: {1, 2}
```

### 4.5 Exercício Integrador - Sistema de Vendas
```python
def sistema_vendas():
    # Produtos disponíveis (dicionário)
    produtos = {
        "001": {"nome": "Notebook", "preco": 2500.00, "estoque": 10},
        "002": {"nome": "Mouse", "preco": 50.00, "estoque": 25},
        "003": {"nome": "Teclado", "preco": 150.00, "estoque": 15}
    }
    
    # Carrinho de compras (lista de tuplas)
    carrinho = []
    
    # Clientes VIP (conjunto)
    clientes_vip = {"12345678901", "98765432109"}
    
    def exibir_produtos():
        print("\n=== PRODUTOS DISPONÍVEIS ===")
        for codigo, info in produtos.items():
            print(f"{codigo}: {info['nome']} - R$ {info['preco']:.2f} (Estoque: {info['estoque']})")
    
    def adicionar_ao_carrinho(codigo, quantidade):
        if codigo in produtos:
            if produtos[codigo]["estoque"] >= quantidade:
                carrinho.append((codigo, quantidade))
                produtos[codigo]["estoque"] -= quantidade
                print(f"Adicionado: {quantidade}x {produtos[codigo]['nome']}")
            else:
                print("Estoque insuficiente!")
        else:
            print("Produto não encontrado!")
    
    def calcular_total(cpf_cliente=""):
        total = 0
        print("\n=== CARRINHO ===")
        for codigo, quantidade in carrinho:
            produto = produtos[codigo]
            subtotal = produto["preco"] * quantidade
            total += subtotal
            print(f"{produto['nome']}: {quantidade}x R$ {produto['preco']:.2f} = R$ {subtotal:.2f}")
        
        # Desconto para clientes VIP
        if cpf_cliente in clientes_vip:
            desconto = total * 0.1
            total -= desconto
            print(f"Desconto VIP (10%): -R$ {desconto:.2f}")
        
        print(f"TOTAL: R$ {total:.2f}")
        return total
    
    # Simulação de uso
    exibir_produtos()
    adicionar_ao_carrinho("001", 1)
    adicionar_ao_carrinho("002", 2)
    calcular_total("12345678901")  # Cliente VIP

# Executar o sistema
sistema_vendas()
```

---

## 5. EXERCÍCIOS PARA FIXAÇÃO

### Exercício 1: Estruturas de Seleção
Crie um programa que determine se um ano é bissexto.

### Exercício 2: Estruturas de Repetição
Crie um programa que calcule o fatorial de um número.

### Exercício 3: Modularização
Crie funções para operações matemáticas básicas (+, -, *, /) com tratamento de erros.

### Exercício 4: Estruturas de Dados
Crie um sistema de cadastro de alunos usando dicionários, com funções para adicionar, remover e listar alunos.

---

## 6. DICAS PARA A PROVA

1. **Leia o enunciado com atenção** - Identifique o que é pedido exatamente
2. **Planeje antes de codificar** - Pense na lógica antes de escrever
3. **Use nomes descritivos** - Variáveis e funções com nomes claros
4. **Teste seu código** - Verifique com diferentes entradas
5. **Trate erros** - Use try/except quando necessário
6. **Comente o código** - Explique partes complexas
7. **Revise a sintaxe** - Indentação, dois pontos, parênteses
8. **Pratique estruturas de dados** - Saiba quando usar lista, tupla, dicionário ou set

### Checklist Final
- [ ] Entendo estruturas de seleção (if, elif, else)
- [ ] Sei usar loops (for, while) e controle de fluxo (break, continue)
- [ ] Consigo criar e usar funções com parâmetros e retorno
- [ ] Domino listas, tuplas, dicionários e sets
- [ ] Sei quando usar cada estrutura de dados
- [ ] Posso combinar todos os conceitos em um programa completo

**Boa sorte na prova!** 🚀