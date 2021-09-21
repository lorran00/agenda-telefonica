# agenda-telefonica
meu primeiro projeto em python

from time import sleep
print('CONTATOS')
contatos = {}
lista = []
listanumero = []

while True:
    print('=~'*30)
    print('''MENU
    [1] Adicionar Contato
    [2] Exibir Contatos
    [3] Editar Contatos
    [4] Excluir Contato
    [5] Copiar Agenda
    [6] Excluir Todos os Contatos
    [7] Sair''')
    escolha = int(input('Selecione umma Opção: '))
    print('')

    def adicionar():
        print('=~'*30)
        print('ADICIONAR CONTATOS')
        print('=~'*30)
        nome = str(input('Digite o Nome: '))
        numero = int(input('Digite o Numero: '))
        adc1 = lista.append(nome)
        adc2 = listanumero.append(numero)
        adc3 = contatos[nome] = numero
        for l in lista:
            print('')
            print('=~'*30)
            print('LISTA')
            print('=~'*30)
            sleep(2)
            print(l)
            print('')
            print('Contato Adicionado com Suscesso!')

    def exibir():
        print('')
        print('=~'*30)
        print('CONTATOS')
        print('=~'*30)
        for l in lista:
            print(l)
        print('')
        buscar = str(input('Pesquisar: ')).strip().lower()
        esc = contatos.get(buscar)
        if buscar in contatos.keys():
            print('Buscando...')
            sleep(2)
            print('='*30)
            print(f' {buscar} : {esc} ')
            print('')
            print('='*30)
        else:
            print('CONTATO NAO ENCONTRADO!')

    def editar():
        print('')
        print('=~'*30)
        print('EDITAR CONTATO')
        print('=~'*30)
        for l in lista:
            print(l)
        print('')
        print('='*30)
        novo = str(input('Editar o Numero de: ')).strip().lower()
        if novo in contatos.keys():
            print(f'Editar o Numero de : {novo} ')
            # novonome = str(input('Editar o nome: '))
            novonumero = int(input('Novo Numero: '))
            contatos[novo] = novonumero
            listanumero.append(novonumero)
            sleep(2)
            print('='*30)
            print(f' {novo} : {novonumero} ')
            print('')
            print('Contato Alterado com Suscesso!')
            print('='*30)
            # editar o nome
        elif novo not in contatos.keys():
            print('Contato Não Encontrado!')
            op = str(input('Deseja Adicionar esse Contato a sua Lista? ')).strip().lower()
            if op == 's':
                adicionar()
            else:
                print('Voltando...')
                sleep(3)

    def excluir():
        print('=~'*30)
        print('EXCLUIR CONTATOS')
        print('=~'*30)
        for l in lista:
            print(l)
        print('')
        buscar = str(input('Excluir Contato de: ')).strip().lower()
        if buscar not in contatos.keys():
            sleep(2)
            print('Contato Nao Encontrado')
        elif buscar in contatos.keys():
            esc = str(input('Deseja Excluir esse Contato? ')).strip().lower()
            print('EXCLUINDO...')
            sleep(2)
            print('CONTATO EXCLUIDO!')
            if esc == 's':
                contatos.pop(buscar)
                lista.remove(buscar)
                for l in lista:
                    print('='*30)
                    print(l)
                    print('')
                    print('='*30)
            else:
                for l in lista:
                    print('=' * 30)
                    print(l)
                    print('')
                    print('=' * 30)

    def copiar():
        print('')
        print('=~'* 30)
        print('COPIAR')
        print('=~'* 30)
        cop = str(input('Deseja Copiar os Contatos da sua Agenda? ')).strip().lower()
        if cop == 's':
            cop1 = contatos.copy()
            cop2 = lista.copy()
            sleep(1.5)
            print('CONTATOS COPIADOS COM SUSCESSO!')
            sleep(2)
            for cop2 in lista:
                print('=' * 30)
                print(cop2)
                print('')
                print('=' * 30)
        else:
            print('Voltando...')
            sleep(2)

    def apagartds():
        print('')
        print('=~' * 30)
        print('EXCLUIR TODA AGENDA!')
        print('=~' * 30)
        exc = str(input('Realmente Deseja Excluir Todos os Contatos? ')).strip().lower()
        if exc == 's':
            contatos.clear()
            lista.clear()
            sleep(2)
            print('Contatos Apagados')
            print('=' * 30)
            print(lista)
            print('')
            print('=' * 30)
        else:
            print('=' * 30)
            print(lista)
            print('')
            print('=' * 30)
            print('Voltando...')
            sleep(2)

    if escolha == 1:
        adicionar()

    if escolha == 2:
        exibir()

    if escolha == 3:
        editar()

    if escolha == 4:
        excluir()

    if escolha == 5:
        copiar()

    if escolha == 6:
        apagartds()

    if escolha == 7:
        print('Saindo...')
        sleep(2)
        break
