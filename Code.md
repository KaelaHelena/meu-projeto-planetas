planetas = {
  'Mercúrio':   {'tamanho':   4879,   'distancia':   57.9,   'apelido':   'O Planeta de fogo'},
  'Vênus':   {'tamanho':   12104,   'distancia':   108.2,   'apelido':   'Vesper'},
  'Terra':   {'tamanho':   12742,   'distancia':   149.6,   'apelido':   'Planeta Azul'},
  'Marte':   {'tamanho':   6779,   'distancia':   227.9,   'apelido':   'Planeta Vermelho'},
  'Júpiter':   {'tamanho':   142984,   'distancia':   778.5,   'apelido':   'Rei dos planetas'},
  'Saturno':   {'tamanho':   120536,   'distancia':   1433.5,   'apelido':   'Planeta dos anéis'},
  'Urano':   {'tamanho':   51118,   'distancia':   2872.5,   'apelido':   'Gigante de gelo'},
  'Netuno':   {'tamanho':   49244,   'distancia':   4504.3,   'apelido':   'Planeta azul-esverdeado'}
}

def editar_planeta():
    nome = input('Digite o nome do planeta que deseja editar: ')
    if nome in planetas:
        novo_tamanho = input('Digite o novo tamanho: ')
        nova_distancia = input('Digite a nova distancia: ')
        novo_apelido = input('Digite o novo apelido: ')
        planetas[nome]['tamanho'] = novo_tamanho
        planetas[nome]['distancia'] = nova_distancia
        planetas[nome]['apelido'] = novo_apelido
        print(f'O planeta {nome} foi editado com sucesso!')
    else:
        print('Planeta não encontrado.')
        
def adicionar_planeta():
    nome = input('Digite o nome do planeta: ')
    tamanho = input('Digite o tamanho do planeta:')
    distancia = input('Digite a distancia do Sol: ')
    apelido = input('Digite o apelido do planeta: ')
    
    planetas[nome] = {'tamanho': tamanho, 'distancia': distancia, 'apelido': apelido}
    print(f'O planeta com o {nome} foi adicionado com sucesso!')
    
def  remover_planeta():
     nome = input('Digite o nome do planeta que deseja ser removido: ')
     if nome in planetas:
         del planetas[nome]
         print(f'O planeta {nome} foi removido com sucesso! ')
     else: 
         print('Planeta não encontrado. ')
         
def listar_planetas(): 
  if not planetas: 
    print('Não há planetas cadastrados.')
  else: 
    for planeta, info in planetas.items(): 
      print(f'Planeta:  {planeta}')
      print(f'Tamanho:  {info["tamanho"]}')
      print(f'Distância do Sol:  {info["distancia"]}')
      print(f'Apelido:  {info["apelido"]}')
      print('-' * 40)
      
def buscar_planeta():
    nome = input('Digite o nome do planeta a ser buscado:  ')
    if nome in planetas:
      print(f'Planeta:  {nome}')
      print(f'Tamanho:  {planetas[nome]["tamanho"]}')
      print(f'Distância do Sol:  {planetas[nome]["distancia"]}')
      print(f'Apelido:  {planetas[nome]["apelido"]}')
      print('-' * 40)
    else:
      print('Planeta não encontrado')

# Programa Principal 

fim = False
while not fim: 
    print('\nGerenciador de Planetas')
    print('1. Adicionar Planeta')
    print('2. Remover Planeta')
    print('3. Listar Planetas')
    print('4. Buscar Planeta')
    print('5. Editar Planeta')
    print('0. Sair')
    
    opcao = input('Digite a opção desejada:   ')
    
    if opcao == '1': 
        adicionar_planeta()
    elif opcao == '2': 
        remover_planeta()
    elif opcao == '3': 
        listar_planetas()
    elif opcao == '4': 
        buscar_planeta()
    elif opcao == '5': 
        editar_planeta()
    elif opcao == '0': 
        print('\nObrigado por utilizar nosso sistema')
        fim = True
    else: 
        print('Opção inválida')
