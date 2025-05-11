import random
import string

def gerar_senha(tamanho=12, usar_maiusculas=True, usar_numeros=True, usar_simbolos=True):
    caracteres = string.ascii_lowercase

    if usar_maiusculas:
        caracteres += string.ascii_uppercase
    if usar_numeros:
        caracteres += string.digits
    if usar_simbolos:
        caracteres += string.punctuation

    senha = ''.join(random.choice(caracteres) for _ in range(tamanho))
    return senha

if __name__ == "__main__":
    print("Gerador de Senhas Seguras")

    try:
        tamanho = int(input("Tamanho da senha (padrão 12): ") or 12)
        usar_maiusculas = input("Incluir letras maiúsculas? (s/n): ").lower() == 's'
        usar_numeros = input("Incluir números? (s/n): ").lower() == 's'
        usar_simbolos = input("Incluir símbolos? (s/n): ").lower() == 's'

        senha_gerada = gerar_senha(tamanho, usar_maiusculas, usar_numeros, usar_simbolos)
        print(f"\nSenha gerada: {senha_gerada}")
    except ValueError:
        print("Entrada inválida. Certifique-se de digitar um número para o tamanho da senha.")

