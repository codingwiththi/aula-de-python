# UNIVERSIDADE FEDERAL DE CIÊNCIAS DA COMPUTAÇÃO
## Disciplina: Programação I - Python
### Lista de Exercícios - Avaliação Final
**Professor:** Dr. Claude Santos  
**Semestre:** 2025.1  
**Data de Entrega:** 20/06/2025  
**Valor:** 100 pontos

---

## INSTRUÇÕES GERAIS

1. Todos os exercícios devem ser implementados em Python 3.x
2. O código deve ser bem comentado e seguir boas práticas de programação
3. Use nomes descritivos para variáveis e funções
4. Implemente tratamento de erros quando necessário
5. Teste seu código com diferentes cenários de entrada
6. Entregue um arquivo .py para cada exercício, nomeado como `exercicio_X.py`

---

## EXERCÍCIOS - ESTRUTURAS DE SELEÇÃO (20 pontos)

### Exercício 1 (5 pontos)
**Sistema de Classificação de Triângulos**

Desenvolva um programa que receba as medidas de três lados de um triângulo e determine:
- Se é possível formar um triângulo (a soma de dois lados deve ser maior que o terceiro)
- Caso seja possível, classifique o triângulo como:
  - **Equilátero**: todos os lados iguais
  - **Isósceles**: dois lados iguais
  - **Escaleno**: todos os lados diferentes

**Entrada:** Três números reais positivos representando os lados  
**Saída:** Classificação do triângulo ou mensagem de erro

### Exercício 2 (8 pontos)
**Sistema de Aprovação Acadêmica**

Implemente um sistema que calcule a média final de um aluno e determine sua situação acadêmica com base nas seguintes regras:

- **Média das provas (P)**: média aritmética de 3 provas
- **Nota de trabalhos (T)**: média de trabalhos práticos
- **Presença (F)**: percentual de frequência

**Fórmula da média final:** MF = (P × 0.7) + (T × 0.3)

**Critérios de aprovação:**
- Frequência ≥ 75% E Média Final ≥ 7.0: **APROVADO**
- Frequência ≥ 75% E 5.0 ≤ Média Final < 7.0: **RECUPERAÇÃO**
- Frequência < 75% OU Média Final < 5.0: **REPROVADO**

**Entrada:** 3 notas de provas, 1 nota de trabalhos, percentual de frequência  
**Saída:** Média final e situação do aluno

### Exercício 3 (7 pontos)
**Calculadora de Imposto de Renda**

Desenvolva um calculadora que determine o imposto de renda baseado na tabela progressiva:

| Faixa Salarial | Alíquota | Dedução |
|---------------|----------|---------|
| Até R$ 2.112,00 | Isento | R$ 0,00 |
| De R$ 2.112,01 a R$ 2.826,65 | 7,5% | R$ 158,40 |
| De R$ 2.826,66 a R$ 3.751,05 | 15% | R$ 370,40 |
| De R$ 3.751,06 a R$ 4.664,68 | 22,5% | R$ 651,73 |
| Acima de R$ 4.664,68 | 27,5% | R$ 884,96 |

**Fórmula:** Imposto = (Salário × Alíquota) - Dedução

**Entrada:** Salário bruto mensal  
**Saída:** Alíquota aplicada, imposto devido e salário líquido

---

## EXERCÍCIOS - ESTRUTURAS DE REPETIÇÃO (25 pontos)

### Exercício 4 (8 pontos)
**Sequência de Fibonacci Otimizada**

Implemente um gerador da sequência de Fibonacci que:
- Solicite ao usuário quantos termos deseja gerar (N)
- Exiba os N primeiros termos da sequência
- Calcule e exiba a razão áurea aproximada (Fn+1/Fn) dos últimos dois termos
- Valide se N está entre 1 e 100

**Exemplo de saída para N=8:**
```
Sequência: 0, 1, 1, 2, 3, 5, 8, 13
Razão áurea aproximada: 1.625
```

### Exercício 5 (9 pontos)
**Análise de Números Primos**

Desenvolva um programa que:
- Solicite um intervalo [A, B] onde A < B
- Encontre todos os números primos no intervalo
- Exiba os primos encontrados
- Calcule estatísticas: quantidade total, maior primo, menor primo
- Implemente o algoritmo do Crivo de Eratóstenes para otimização

**Validações:**
- A e B devem ser números inteiros positivos
- A deve ser menor que B
- O intervalo não pode ter mais de 10.000 números

### Exercício 6 (8 pontos)
**Jogo de Adivinhação Inteligente**

Crie um jogo onde:
- O programa gera um número aleatório entre 1 e 1000
- O usuário tem no máximo 10 tentativas para acertar
- Após cada tentativa, o programa dá dicas: "muito alto", "muito baixo" ou "próximo" (±10)
- Mantenha um histórico das tentativas
- Calcule e exiba uma pontuação baseada no número de tentativas

**Pontuação:**
- 1-3 tentativas: 1000 pontos
- 4-6 tentativas: 500 pontos
- 7-10 tentativas: 100 pontos

---

## EXERCÍCIOS - MODULARIZAÇÃO (25 pontos)

### Exercício 7 (12 pontos)
**Biblioteca de Funções Matemáticas**

Implemente uma biblioteca com as seguintes funções:

```python
def calcular_mdc(a, b):
    """Calcula o Máximo Divisor Comum usando algoritmo de Euclides"""
    pass

def calcular_mmc(a, b):
    """Calcula o Mínimo Múltiplo Comum"""
    pass

def eh_numero_perfeito(n):
    """Verifica se um número é perfeito (soma dos divisores = número)"""
    pass

def fatorar_numero(n):
    """Retorna lista com a fatoração prima de um número"""
    pass

def converter_base(numero, base_origem, base_destino):
    """Converte número entre bases (2 a 16)"""
    pass
```

**Implemente também um programa principal que:**
- Apresente um menu com todas as operações
- Permita ao usuário executar múltiplas operações
- Valide todas as entradas
- Trate erros adequadamente

### Exercício 8 (13 pontos)
**Sistema de Gestão de Notas**

Desenvolva um sistema modular para gestão de notas acadêmicas:

```python
def cadastrar_aluno(nome, matricula):
    """Cadastra um novo aluno"""
    pass

def adicionar_nota(matricula, disciplina, nota, peso=1.0):
    """Adiciona uma nota para um aluno em uma disciplina"""
    pass

def calcular_media_aluno(matricula, disciplina):
    """Calcula média ponderada de um aluno em uma disciplina"""
    pass

def gerar_relatorio_aluno(matricula):
    """Gera relatório completo de um aluno"""
    pass

def gerar_relatorio_turma(disciplina):
    """Gera relatório de desempenho da turma em uma disciplina"""
    pass

def exportar_dados(formato='txt'):
    """Exporta dados para arquivo (txt ou csv)"""
    pass
```

**Requisitos adicionais:**
- Use dicionários para armazenar os dados
- Implemente validações rigorosas
- Crie um menu interativo
- Permita persistência dos dados em arquivo

---

## EXERCÍCIOS - ESTRUTURAS DE DADOS (30 pontos)

### Exercício 9 (15 pontos)
**Sistema de Gestão de Biblioteca**

Desenvolva um sistema completo de biblioteca utilizando as estruturas de dados apropriadas:

**Estruturas de dados necessárias:**
```python
# Dicionário para livros
livros = {
    'ISBN': {
        'titulo': str,
        'autor': str,
        'ano': int,
        'categoria': str,
        'exemplares_total': int,
        'exemplares_disponiveis': int
    }
}

# Lista para histórico de empréstimos
historico_emprestimos = [
    ('ISBN', 'CPF_usuario', 'data_emprestimo', 'data_devolucao', 'status')
]

# Conjunto para usuários ativos
usuarios_ativos = {'CPF1', 'CPF2', ...}

# Dicionário para categorias e seus livros
categorias = {
    'Ficção': ['ISBN1', 'ISBN2'],
    'Técnico': ['ISBN3', 'ISBN4']
}
```

**Funcionalidades obrigatórias:**
1. Cadastrar/remover livros
2. Cadastrar/remover usuários
3. Realizar empréstimos (máximo 3 livros por usuário)
4. Processar devoluções
5. Consultar disponibilidade por título/autor/categoria
6. Gerar relatórios: livros mais emprestados, usuários mais ativos
7. Calcular multas por atraso (R$ 2,00 por dia)

### Exercício 10 (15 pontos)
**Analisador de Texto Acadêmico**

Implemente um analisador de texto que processe documentos acadêmicos:

**Funcionalidades:**
1. **Análise básica:**
   - Contar palavras, frases, parágrafos
   - Calcular média de palavras por frase
   - Identificar palavras mais frequentes

2. **Análise avançada:**
   - Detectar palavras únicas (que aparecem apenas uma vez)
   - Calcular índice de diversidade lexical (palavras únicas/total de palavras)
   - Identificar possível plágio (comparar com base de textos)

3. **Análise de estrutura:**
   - Verificar se possui introdução, desenvolvimento e conclusão
   - Identificar uso de conectivos (lista predefinida)
   - Analisar distribuição de parágrafos

**Estruturas de dados sugeridas:**
```python
# Dicionário para frequência de palavras
frequencia_palavras = {'palavra': count}

# Set para palavras únicas
palavras_unicas = {'palavra1', 'palavra2'}

# Lista de tuplas para estatísticas por parágrafo
stats_paragrafos = [(num_palavras, num_frases, complexidade)]

# Dicionário para base de comparação (detecção de plágio)
base_textos = {'id_texto': set_de_palavras}
```

**Entrada:** Arquivo de texto (.txt)  
**Saída:** Relatório completo em formato estruturado

---

## EXERCÍCIO INTEGRADOR (BÔNUS - 10 pontos)

### Exercício 11
**Sistema de E-commerce Simplificado**

Desenvolva um sistema que integre todos os conceitos estudados:

**Requisitos funcionais:**
- Cadastro de produtos (código, nome, preço, categoria, estoque)
- Carrinho de compras com cálculo automático
- Sistema de cupons de desconto
- Diferentes tipos de usuário (comum, premium, admin)
- Relatórios de vendas e estoque
- Persistência de dados em arquivos

**Requisitos técnicos:**
- Use todas as estruturas de dados estudadas apropriadamente
- Implemente modularização com pelo menos 10 funções
- Use estruturas de seleção para regras de negócio
- Implemente loops para menus e validações
- Trate todas as exceções possíveis

**Estrutura mínima:**
```python
def menu_principal():
def cadastrar_produto():
def listar_produtos():
def adicionar_ao_carrinho():
def finalizar_compra():
def aplicar_cupom():
def gerar_relatorio():
def salvar_dados():
def carregar_dados():
```

---

## CRITÉRIOS DE AVALIAÇÃO

### Aspectos Técnicos (70%)
- **Funcionalidade (25%)**: O programa executa corretamente
- **Lógica (20%)**: Algoritmos implementados adequadamente  
- **Estruturas de dados (15%)**: Uso apropriado de listas, dicionários, etc.
- **Modularização (10%)**: Funções bem estruturadas e reutilizáveis

### Aspectos Qualitativos (30%)
- **Legibilidade (10%)**: Código limpo e bem organizado
- **Comentários (5%)**: Documentação adequada
- **Tratamento de erros (10%)**: Validações e exceções
- **Criatividade (5%)**: Soluções elegantes e inovadoras

### Penalizações
- **-10 pontos**: Código não executa ou tem erros críticos
- **-5 pontos**: Falta de comentários ou documentação
- **-3 pontos**: Não seguir padrões de nomenclatura
- **-2 pontos**: Arquivos mal nomeados ou organizados

---

## DICAS PARA O SUCESSO

1. **Planeje antes de codificar** - Desenhe o algoritmo no papel
2. **Teste incrementalmente** - Teste cada função separadamente
3. **Use print() para debug** - Acompanhe o fluxo de execução
4. **Leia o enunciado várias vezes** - Certifique-se de entender todos os requisitos
5. **Comece pelos exercícios mais simples** - Ganhe confiança progressivamente
6. **Não deixe para a última hora** - Programação requer tempo e prática

### Recursos Permitidos
- Documentação oficial do Python
- IDE de sua preferência
- Calculadora para validar cálculos

### Recursos NÃO Permitidos
- Consulta a outros estudantes durante a prova
- Uso de bibliotecas externas não mencionadas
- Acesso à internet durante a execução dos exercícios

---

**Boa sorte! Que seus algoritmos sejam eficientes e seus códigos, elegantes!** 🐍💻

---

*"A programação não é sobre o que você sabe; é sobre o que você pode descobrir." - Chris Pine*