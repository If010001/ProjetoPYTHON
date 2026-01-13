# ProjetoPYTHON
from google.colab import output
import random
import string
continuar = 'S'

print("_______________________________")
print("Seja Bem-Vindo ao meu Programa")
print("_______________________________")

while True:
    decisao_da_pessoa = input("""Escolha uma das opçoes para prosseguir:
    [1]Brincar
    [2]Calcular
    [3]Gerador de senhas
    [4]Sair
    """)
    output.clear()
    if decisao_da_pessoa not in ["1", "2", "3", "4"]:
        print("Escolha apenas um numero de 1 a 4...😑")
        continue

   match decisao_da_pessoa:
   case '1':
       print("Tente adivinhar meu numero!!!🤡")
            while True:
                adivinhacao_do_computador = random.randint(1, 10)
                numero_da_pessoa = input("Digite um numero de 1 a 10: ")
                output.clear()
                if not numero_da_pessoa.isnumeric():
                    print("Apenas numeros, plis!")
                    continue
                numero_da_pessoa = int(numero_da_pessoa)
                if numero_da_pessoa == adivinhacao_do_computador:
                    print(f"\033[32mVoce ganhou!!!! Meu numero é {adivinhacao_do_computador}\033[0m")
               else:
                    print(f"\033[31mNão foi dessa vez, meu numero era {adivinhacao_do_computador} 😂😂\033[0m")
                escolha_da_pessoa = input("Voce quer continuar(S para SIM)? ").upper()
                output.clear()
                if escolha_da_pessoa != 'S':
                        break
        case '2':
            print("Bem-vindo a calculadora!")
            while True:
                numero_1 = input(f"Digite o 1º numero: ")
                numero_2 = input(f"Digite o 2º numero: ")
                output.clear()
                if not numero_1.isnumeric() or not numero_2.isnumeric():
                    print("Apenas numeros podem ser digitados...🤦‍♂️")
                    continue
                forma_de_calculo = input("""Escolha a forma de calculo:
                    [+]
                    [-]
                    [/]
                    [*] """)
                if forma_de_calculo not in ['+', '-', '/', '*']:
                    print("Apenas um dos forma_de_calculo acima podem ser escolhidos")
                output.clear()
                numero_1 = float(numero_1)
                numero_2 = float(numero_2)
                if forma_de_calculo == '+':
                    resposta = numero_1 + numero_2
                    print(f"A soma de {numero_1} + {numero_2} é igual a {resposta}")
                elif forma_de_calculo == '-':
                    resposta = numero_1 - numero_2
                    print(f"A soma de {numero_1} - {numero_2} é igual a {resposta}")
                elif forma_de_calculo == '/':
                    if numero_2 == 0:
                        print("Não é possivel dividir por zero!")
                    else:
                        resposta = numero_1 / numero_2
                        print(f"A soma de {numero_1} / {numero_2} é igual a {resposta}")
                elif forma_de_calculo == '*':
                    resposta = numero_1 * numero_2
                    print(f"A soma de {numero_1} * {numero_2} é igual a {resposta}")
                continuar = input("Voce deseja continuar?(S/N) ").upper()
                if continuar != 'S':
                    break
        case '3':
            print("Bem-vindo ao Gerador de senhas!😎")
            while True:
                tamanho_da_senha = input("Digite o tamanho da senha(Quantidade de caracter): ")
                output.clear()
                if not tamanho_da_senha.isnumeric():
                    print("Digite apenas numeros...(1,2,3,4,5 e etc)")
                    continue
                tamanho_da_senha = int(tamanho_da_senha)
                caracteres = string.ascii_letters + string.digits + string.punctuation
                senha_gereda_para_usuario = ''.join(random.choice(caracteres) for i in range(tamanho_da_senha))
                print("A sua senha é:", senha_gereda_para_usuario)
                continuar = input("Voce deseja continuar?(S/N)").upper()
                if continuar != 'S':
                    break
        case '4':
            print("Programa encerrado.")
            break
