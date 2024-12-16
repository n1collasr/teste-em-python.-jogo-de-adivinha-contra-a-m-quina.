from random import randint

print('Sou seu computador... acabei de pensar em número entre 0 e 10.')
print('Será que consegue adivinhar qual foi?')

# Variável para controlar se o jogador deseja continuar jogando
jogar_novamente = True

while jogar_novamente:
    comp = randint(0, 10)
    acertou = False
    palpites = 0

    while not acertou:
        jogador = int(input('Qual é seu palpite? '))
        palpites += 1
        if jogador == comp:
            acertou = True
        elif jogador < comp:
            print('É maior!')
        elif jogador > comp:
            print('É menor!')

    print('Correto! Foram tentativas. Parabéns!'.format(palpites))

    # Perguntar se o jogador deseja jogar novamente
    resposta = input('Gostaria de jogar novamente? (s/n): ').strip().lower()
    if resposta != 's':
        jogar_novamente = False
        print('Obrigado por jogar! Até a próxima.')
