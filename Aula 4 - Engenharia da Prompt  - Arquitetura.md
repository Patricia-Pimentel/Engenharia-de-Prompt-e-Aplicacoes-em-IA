**O Desafio:** Transformar uma instrução vaga em um Prompt Mestre estruturado.

**Ferramentas:** ChatGPT ou GitHub Copilot.

**A Tarefa:**
1. Escolha um problema de código simples ou necessidade de documentação de um projeto pessoal.
2. Crie uma primeira iteração (vaga) e documente a resposta ruim.
3. Aplique a Equação do Prompt (Persona + Contexto + Restrições + Formato).
4. Refine iterativamente até obter o resultado perfeito em formato YAML ou Markdown.

# 2.Faça um código que seja uma calculadora.

## Resposta

### O Código (Python)

Com certeza! Vou criar uma calculadora em Python, que é uma linguagem excelente para esse tipo de lógica inicial por ser clara e direta.

Esta versão utiliza funções para organizar cada operação e um laço de repetição para que você possa fazer vários cálculos sem precisar reiniciar o programa.

```python
def soma(a, b):
    return a + b

def subtracao(a, b):
    return a - b

def multiplicacao(a, b):
    return a * b

def divisao(a, b):
    if b == 0:
        return "Erro! Divisão por zero não é permitida."
    return a / b

def calculadora():
    print("--- Calculadora Simples ---")
    print("Escolha a operação:")
    print("1. Soma")
    print("2. Subtração")
    print("3. Multiplicação")
    print("4. Divisão")
    print("5. Sair")

    while True:
        escolha = input("\nDigite o número da operação (1/2/3/4/5): ")

        if escolha == '5':
            print("Encerrando a calculadora. Até mais!")
            break

        if escolha in ('1', '2', '3', '4'):
            try:
                num1 = float(input("Digite o primeiro número: "))
                num2 = float(input("Digite o segundo número: "))
            except ValueError:
                print("Entrada inválida! Por favor, digite apenas números.")
                continue

            if escolha == '1':
                print(f"Resultado: {num1} + {num2} = {soma(num1, num2)}")
            elif escolha == '2':
                print(f"Resultado: {num1} - {num2} = {subtracao(num1, num2)}")
            elif escolha == '3':
                print(f"Resultado: {num1} * {num2} = {multiplicacao(num1, num2)}")
            elif escolha == '4':
                print(f"Resultado: {num1} / {num2} = {divisao(num1, num2)}")
        else:
            print("Opção inválida! Tente novamente.")

if __name__ == "__main__":
    calculadora()
```
Por que o código foi feito assim?
Funções Individuais: Separar soma, subtracao, etc., torna o código mais limpo e fácil de dar manutenção.

Tratamento de Erros: Usei o bloco try/except para evitar que o programa "quebre" caso o usuário digite uma letra em vez de um número.

Verificação de Divisão: O código impede a divisão por zero, o que causaria um erro matemático no sistema.



# 3.Você é um estudante iniciante de Python. Crie um código para uma calculadora simples com os conceitos iniciais da linguagem, adicione comentários que ajude a ententer o que esta sendo feito. Coloque toda a sua resposta e considerações em md copiável.

# 🐍 Minha Primeira Calculadora em Python

E aí! Como estou começando agora no Python, tentei manter o código o mais limpo possível, usando só o básico que aprendi até aqui: **variáveis**, **input de dados**, **conversão de tipos** (float) e as **estruturas condicionais** (`if`, `elif`, `else`).

A ideia é que o usuário escolha a operação e o programa faça o resto. Dá uma olhada em como ficou:

---

## 💻 O Código

```python
# --- CALCULADORA SIMPLES PARA INICIANTES ---

# 1. Entrada de dados:
# Usamos float() porque o input() sempre recebe o dado como texto (string).
# O float permite que a gente aceite números inteiros ou com vírgula (ponto).
num1 = float(input("Digite o primeiro número: "))
num2 = float(input("Digite o segundo número: "))

# 2. Menu de opções:
print("\nEscolha a operação:")
print("+ : Soma")
print("- : Subtração")
print("* : Multiplicação")
print("/ : Divisão")

operacao = input("\nDigite o símbolo da operação desejada: ")

# 3. Lógica da Calculadora (Estrutura Condicional):
if operacao == "+":
    resultado = num1 + num2
    print(f"Resultado: {num1} + {num2} = {resultado}")

elif operacao == "-":
    resultado = num1 - num2
    print(f"Resultado: {num1} - {num2} = {resultado}")

elif operacao == "*":
    resultado = num1 * num2
    print(f"Resultado: {num1} * {num2} = {resultado}")

elif operacao == "/":
    # Regra matemática: não dá para dividir por zero!
    if num2 != 0:
        resultado = num1 / num2
        print(f"Resultado: {num1} / {num2} = {resultado}")
    else:
        print("Erro: Não é possível dividir por zero.")

else:
    # Caso o usuário digite um símbolo que não está no menu
    print("Operação inválida! Use +, -, * ou /.")

print("\nCálculo finalizado. Valeu!")
```

## 📝 Considerações de Estudante:

* **A importância do `float()`:** No começo, eu esquecia de converter e o Python tentava somar textos em vez de números. Sem a conversão, se o usuário digitasse 5 e 5, o resultado seria `55` (junção de textos) em vez de `10.0`. Agora entendi que converter o tipo é essencial para matemática!
* **f-strings:** Esse formato `f"Texto {variavel}"` é muito prático! Facilita demais a leitura do código em comparação com ficar usando vírgulas ou sinais de `+` para juntar as frases. Deixa o código muito mais limpo.
* **Indentação:** Aprendi que o Python é "chato" com os espaços. Se o código dentro do `if` não estiver com o recuo (Tab ou 4 espaços) certinho, ele simplesmente não funciona. É o jeito dele organizar o que pertence a cada bloco lógico.
* **Tratamento de Erros:** Coloquei a verificação da divisão por zero porque descobri que o programa trava (dá um erro de sistema) se tentarmos fazer isso. É sempre bom deixar o programa "blindado" contra entradas que a matemática não permite.


