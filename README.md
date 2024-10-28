# Trabalho-Uninassau-ADS

1

```python
def gerador_tabuada(numero):
    for i in range(1, 11):
        print(f'{numero} x {i} = {numero * i}')

numero = int(input("Informe o número para ver a tabuada (1 a 10): "))
if 1 <= numero <= 10:
    gerador_tabuada(numero)
else:
    print("Por favor, insira um número entre 1 e 10.")
```

2

```python
numeros = []
for i in range(10):
    num = int(input("Digite um número inteiro: "))
    numeros.append(num)

pares = sum(1 for num in numeros if num % 2 == 0)
impares = 10 - pares

print(f'Quantidade de números pares: {pares}')
print(f'Quantidade de números ímpares: {impares}')
```

3

```python
def eh_primo(numero):
    if numero < 2:
        return False
    for i in range(2, int(numero ** 0.5) + 1):
        if numero % i == 0:
            return False
    return True

numero = int(input("Digite um número inteiro: "))
if eh_primo(numero):
    print(f'O número {numero} é primo.')
else:
    print(f'O número {numero} não é primo.')
4

```python
populacao_a = 80000
populacao_b = 200000
taxa_crescimento_a = 0.03
taxa_crescimento_b = 0.015

anos = 0

while populacao_a <= populacao_b:
    populacao_a += populacao_a * taxa_crescimento_a
    populacao_b += populacao_b * taxa_crescimento_b
    anos += 1

print(f'Serão necessários {anos} anos para que a população do país A ultrapasse ou iguale a população do país B.')
```

 5

```python
def gerar_tabela_precos():
    print("Lojas Quase Dois - Tabela de preços")
    preco_unitario = 1.99
    for i in range(1, 51):
        print(f"{i} - R$ {i * preco_unitario:.2f}")

quantidade_itens = int(input("Informe a quantidade de itens: "))
if 1 <= quantidade_itens <= 50:
    gerar_tabela_precos()
else:
    print("Por favor, insira uma quantidade entre 1 e 50 itens.")
```

 6

```python
ano_inicial = 1995
salario_inicial = 1000.00
ano_final = 2025

salario = salario_inicial
percentual_aumento = 0.015  # 1.5% em 1996

for ano in range(1996, ano_final + 1):
    salario += salario * percentual_aumento
    percentual_aumento *= 2  # O aumento dobra a cada ano

print(f"Em {ano_final}, o salário do funcionário será de R$ {salario:.2f}")

7

def calcula_divida(valor_inicial):
    print(f"{'Dívida':<15} {'Juros':<10} {'Parcelas':<25} {'Valor da Parcela':<15}")
    print("-" * 65)

    for parcelas, juros in [(1, 0), (3, 10), (6, 15), (9, 20), (12, 25)]:
        valor_juros = valor_inicial * (juros / 100)
        valor_total = valor_inicial + valor_juros
        valor_parcela = valor_total / parcelas
        print(f"R$ {valor_total:<13.2f} R$ {valor_juros:<9.2f} {parcelas:<24} R$ {valor_parcela:<14.2f}")

valor_divida = float(input("Informe o valor da dívida: R$ "))
calcula_divida(valor_divida)

8

def verificar_respostas(gabarito, respostas_aluno):
    return sum(1 for g, r in zip(gabarito, respostas_aluno) if g == r)

def obter_respostas():
    respostas = []
    for i in range(1, 11):
        resposta = input(f"Resposta da questão {i}: ").strip().upper()
        respostas.append(resposta)
    return respostas

gabarito = ['A', 'B', 'C', 'D', 'E', 'E', 'D', 'C', 'B', 'A']
notas = []

while True:
    respostas_aluno = obter_respostas()
    acertos = verificar_respostas(gabarito, respostas_aluno)
    notas.append(acertos)
    print(f"Você acertou {acertos} questões. Sua nota é {acertos}.")

    outro_aluno = input("Outro aluno vai utilizar o sistema? (S/N): ").strip().upper()
    if outro_aluno != 'S':
        break

if notas:
    maior_acerto = max(notas)
    menor_acerto = min(notas)
    total_alunos = len(notas)
    media_notas = sum(notas) / total_alunos

    print("\nResumo:")
    print(f"Maior acerto: {maior_acerto}")
    print(f"Menor acerto: {menor_acerto}")
    print(f"Total de alunos: {total_alunos}")
    print(f"Média da turma: {media_notas:.2f}")
else:
    print("Nenhum aluno utilizou o sistema.")
