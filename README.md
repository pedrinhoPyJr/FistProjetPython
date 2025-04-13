# Importa o módulo random para gerar números aleatórios
import random

# Função principal do jogo
def jogar():
    # Imprime uma mensagem de boas-vindas
    print("Bem-vindo ao jogo de adivinhação!")

    # Gera um número aleatório entre 1 e 10
    numero_secreto = random.randint(1, 10)

    # Inicializa o número de tentativas
    tentativas = 0

    # Enquanto o jogador não adivinhar o número
    while True:
        # Tenta converter o input do usuário em número inteiro
        try:
            chute = int(input("Digite um número entre 1 e 10: "))
        except ValueError:
            # Se o jogador digitar algo que não é número, exibe mensagem e continua
            print("Por favor, digite um número válido.")
            continue

        # Incrementa o número de tentativas
        tentativas += 1

        # Verifica se o chute está correto
        if chute == numero_secreto:
            print("Parabéns! Você acertou!")
            break  # Sai do loop
        elif chute < numero_secreto:
            print("O número secreto é maior.")
        else:
            print("O número secreto é menor.")

    # Exibe o total de tentativas
    print("Número de tentativas:", tentativas)

# Função extra: exibe um menu simples
def menu():
    print("\nMenu:")
    print("1 - Jogar")
    print("2 - Sair")

# Função principal do programa
def main():
    # Estrutura de repetição usando while para manter o programa rodando
    while True:
        menu()  # Mostra o menu
        opcao = input("Escolha uma opção: ")

        # Condicional para verificar a escolha do usuário
        if opcao == "1":
            jogar()  # Inicia o jogo
        elif opcao == "2":
            print("Saindo do jogo.")
            break  # Encerra o programa
        else:
            print("Opção inválida. Tente novamente.")

# Chama a função principal para iniciar o programa
main()
