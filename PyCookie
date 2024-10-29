import os
import pickle

produtos = {}
try:
  arqu_produ = open('produtos.dat', 'rb')
  produtos = pickle.load(arqu_produ)
except:
  arqu_produ = open('produtos.dat', 'wb')
arqu_produ.close()

pedidos = {}
try:
  arqu_vendas = open('vendas.dat', 'rb')
  pedidos = pickle.load(arqu_vendas)
except:
  arqu_vendas = open('vendas.dat', 'wb')
arqu_vendas.close()

clientes = {}
try:
  arqu_clientes = open('clientes.dat', 'rb')
  clientes = pickle.load(arqu_clientes)
except:
  arqu_clientes = open('clientes.dat', 'wb')
arqu_clientes.close()


################################################################
################################################################
##########               F U N Ç Õ E S                ##########
################################################################
################################################################

def menu_principal():
  os.system('clear')
  print("############################################")
  print("######       Projeto PyCookie         ######")
  print("############################################")
  print("#####      1 - Módulo Produtos         #####")
  print("#####      2 - Módulo Vendas           #####")
  print("#####      3 - Módulo Clientes         #####")
  print("#####      4 - Módulo Relatórios       #####")
  print("#####      5 - Módulo Informações      #####")
  print("#####      0 - Sair                    #####")
  op_princ = input("##### Escolha sua opção: ")
  return op_princ
  
def cadastrar_produtos():
  os.system('clear')
  print()
  print("############################################")
  print("#####          Cadastra Produto        #####")
  print("############################################")
  print()
  cod = input('##### Código do produto(Use a sigla como código): ')
  print()
  nome = input("##### Nome do Produto: ")
  print()
  peso = int(input("##### Peso do Produto: "))
  print()
  preco = float(input("##### Preço do produto: "))
  print()
  produtos[cod] = [nome,peso,preco]
  print("Produto cadastrado com sucesso!")
  input("Tecle <ENTER> para continuar...")
def exibir_produtos():
  os.system('clear')
  print()
  print("############################################")
  print("#####       Exibe Dados do Produto     #####")
  print("############################################")
  print()
  cod = input('Digite o código do produto: ')
  print()
  print('-'*44)
  print('-'*44)
  if cod in produtos:
    print("##### Nome do Produto: {}".format(produtos[cod][0]))
    print("##### peso: {}g".format(produtos[cod][1]))
    print("##### preço: {:.2f} R$".format(produtos[cod][2]))
  else:
    print('Prduto inesxistente!')
  print()
  input("Tecle <ENTER> para continuar...")
def alterar_produto():
  os.system('clear')
  print()
  print("############################################")
  print("#####      Altera Dados do Produto     #####")
  print("############################################")
  print()
  cod = input('##### Código do produto: ')
  if cod in produtos:
    print()
    nome = input("##### Nome: ")
    print()
    peso = input("##### Peso: ")
    print()
    preco = float(input("##### Preço: "))
    print()
    produtos[cod] = [nome,peso,preco]
    print("Produto alterado com sucesso!")
  else:
    print('Produto inexistente!')
  input("Tecle <ENTER> para continuar...")
def excluir_produto():
  os.system('clear')
  print()
  print("############################################")
  print("#####          Exclui Produto          #####")
  print("############################################")
  print()
  cod = input("##### Número do produto: ")
  if cod in produtos:
    del produtos[cod]
    print('Produto excluído com sucesso!')
  else:
    print('Produto não existente!')
  input("Tecle <ENTER> para continuar...")
def menu_produtos():
  os.system('clear')
  print()
  print("############################################")
  print("#####          Módulo Produtos         #####")
  print("############################################")
  print("##### 1 - Cadastrar Produto            #####")
  print("##### 2 - Exibir Dados dos produtos    #####")
  print("##### 3 - Alterar Dados de um produto  #####")
  print("##### 4 - Excluir Produto              #####")
  print("##### 0 - Retornar ao Menu Principal   #####")
  op_produ  = input("##### Escolha sua opção: ")
  return op_produ

def menu_vendas():
  os.system('clear')
  print()
  print("############################################")
  print("#####           Módulo Vendas          #####")
  print("############################################")
  print("##### 1 - Cadastrar Venda              #####")
  print("##### 2 - Exibir Dados da Venda        #####")
  print("##### 3 - Alterar Dados da Venda       #####")
  print("##### 4 - Excluir Venda                #####")
  print("##### 0 - Retornar ao Menu Principal   #####")
  op_pedido = input("##### Escolha sua opção: ")
  return op_pedido

def cadastrar_venda():
  os.system('clear')
  print()
  print("############################################")
  print("#####         Cadastrar Venda          #####")
  print("############################################")
  print()
  ki = input('Você deseja casdastra uma venda(s/n)? ')
  ki = ki.lower()
  while ki == 's':
    print()
    cpf = input('Digite o CPF do cliente: ')
    print()
    if cpf in clientes:
      cupom_fiscal = input('Crie um cupom fiscal(001,002....): ')
      print()
      if cupom_fiscal in pedidos:
        print('Esse cupom fiscal já existe!')
      else:
        nomepe = input("Escreva o codigo do produto(Digite a sigla como código):\n")
        print()
        quant = int(input("quantidade: "))
        print()
        data = input('Digite a data da venda: ')
        pedidos[cupom_fiscal] = [nomepe,quant,data]
        print("Venda cadastrado com sucesso!")
    elif cpf not in clientes:
        print('Esse CPF não está cadastrado!')
    print()
    print('#'*44)
    print()
    ki = input('Deseja mais alguma coisa(s/n)? ')
    ki = ki.lower()
  print()
  input("Tecle <ENTER> para continuar...")

def exibir_vendas():
  os.system('clear')
  print()
  print("############################################")
  print("#####       Exibe Dados da Venda       #####")
  print("############################################")
  print()
  cpf = input('Digite o CPF do cliente: ')
  print()
  if cpf in clientes:
    cupom_fiscal = input('Digite o cupom fiscal da compra: ')
    print()
    print('-'*44)
    print('-'*44)
    if cupom_fiscal in pedidos:
      print("##### CPF: {}".format(cpf))
      print('##### nome do cliente: {}'.format(clientes[cpf][0]))
      print("##### Produto vendido: {}".format(produtos[pedidos[cupom_fiscal][0]][0]))
      print('##### Preço da venda: {:.2f} R$'.format((produtos[pedidos[cupom_fiscal][0]][2]*pedidos[cupom_fiscal][1])))
      print('##### Quantidade: {}'.format(pedidos[cupom_fiscal][1]))
      print('##### Endereço: {}'.format(clientes[cpf][1]))
      print('##### Número de celular: {}'.format(clientes[cpf][2]))
      print('##### E-mail do cliente: {}'.format(clientes[cpf][3]))
    else: 
      print('Esse cupom fiscal não existe!')
  else:
    print('Esse CPF não está cadastrado!')
  print()
  input("Tecle <ENTER> para continuar...")

def alterar_venda():
  os.system('clear')
  print()
  print("############################################")
  print("#####     Altera Dados das Vendas      #####")
  print("############################################")  
  print()
  cpf = input('Digite o CPF do cliente: ')
  print()
  cupom_fiscal = input('Digite o cupom fiscal: ')
  if cpf in clientes and cupom_fiscal in pedidos:
    print()
    nomepe = input("##### Escreva o codigo do produto(Digite a sigla como código):\n")
    print()
    quant = int(input("##### quantidade: "))
    print()
    data = input('Digite a data da venda: ')
    print()
    pedidos[cupom_fiscal] = [nomepe, quant, data]
    print("Venda alterada com sucesso!")
  else:
    print('Esse CPF não está cadastrado!')
  input("Tecle <ENTER> para continuar...")

def excluir_venda():
  os.system('clear')
  print()
  print("############################################")
  print("#####          Excluir Vendas          #####")
  print("############################################")
  print()
  cupom_fiscal = input("##### Cupom fiscal: ")
  if cupom_fiscal in pedidos:
    del pedidos[cupom_fiscal]
    print()
    print("Venda excluída com sucesso!")
  else:
    print('Esse cupom não está cadastrado!')
  input("Tecle <ENTER> para continuar...")

def menu_clienetes():
  os.system('clear')
  print()
  print("############################################")
  print("#####           Módulo Clientes        #####")
  print("############################################")
  print("##### 1 - Cadastrar Cliente            #####")
  print("##### 2 - Exibir Dados do Cliente      #####")
  print("##### 3 - Alterar do Cliente           #####")
  print("##### 4 - Excluir Cliente              #####")
  print("##### 0 - Retornar ao Menu Principal   #####")
  op_cliente = input("##### Escolha sua opção: ")
  return op_cliente

def cadastrar_clente():
  os.system('clear')
  print()
  print("############################################")
  print("#####        Cadastrar Clientes        #####")
  print("############################################")
  print()
  #Projeto SIG-Escola
  cpf = ler_cpf()
  v = validar_cpf(cpf)
  if v == True:
    print()
    nome_cliente = input("Digite o nome completo do cliente: ")
    print()
    enderço = input("Digite o endereço do cliente: ")
    print()
    telefone = input('Digite o número de celular do cliente: ')
    print()
    email = input('Digite o E-mail do cliente: ')
    print()
    clientes[cpf] = [nome_cliente, enderço, telefone, email]
    print("Cliente cadastrado com sucesso!")
  else:
    print('CPF inválido!')
  input("Tecle <ENTER> para continuar...")

def ler_cpf():
  cpf = input("##### CPF (apenas números): ")
  while not(validar_cpf(cpf)):
    print("##### Ops! O CPF informado é inválido!")
    print("##### Tente novamente...")
    print()
    cpf = input("##### CPF (apenas números): ")
  return cpf


def validar_cpf(cpf):
  cpf = cpf.replace('.', '')
  cpf = cpf.replace('-', '')
  cpf = cpf.replace(' ', '')
  tam = len(cpf)
  if (tam < 11) or (tam > 11):
    return False
  if not(cpf.isdigit()):
    return False
  return True
  
def exibir_clientes():
  os.system('clear')
  print()
  print("############################################")
  print("#####      Exibe Dados do Cliente      #####")
  print("############################################")
  print()
  cpf = input('Digite o CPF do cliente: ')
  if cpf in clientes:
    print()
    print("##### CPF do cliente: {}".format(cpf))
    print("##### Nome do cliente: {}".format(clientes[cpf][0]))
    print("##### Endereço do cliente: {}".format(clientes[cpf][1]))
    print('##### Número de celular do cliente: {}'.format(clientes[cpf][2]))
    print('##### E-mail do cliente: {}'.format(clientes[cpf][3]))
  else:
    print('Esse CPF não está cadastrado!')
  input("Tecle <ENTER> para continuar...")

def alterar_cliente():
  os.system('clear')
  print()
  print("############################################")
  print("#####     Altera Dados do Cliente      #####")
  print("############################################")
  print()
  cpf = input('Digite o CPF do cliente: ')
  if cpf in clientes:
    print()
    nome_cliente = input("Digite o nome completo do cliente: ")
    print()
    enderço = input("Digite o endereço do cliente: ")
    print()
    telefone = input('Digite o número de celular do cliente: ')
    print()
    email = input('Digite o E-mail do cliente: ')
    print("Cliente alterado com sucesso!")
    print()
    clientes[cpf] = [nome_cliente, enderço, telefone, email]
  else:
    print('Esse CPF não está cadastrado!')
  print()
  input("Tecle <ENTER> para continuar...")

def excluir_cliente():
  os.system('clear')
  print()
  print("############################################")
  print("#####          Exclui Cliente          #####")
  print("############################################")
  print()
  cpf = input("##### CPF: ")
  if cpf in clientes:
    del clientes[cpf]
    print('Cliente excluído com sucesso!')
  else:
    print('Esse CPF não está cadastrado!')
  print()
  input("Tecle <ENTER> para continuar...")

def menu_relate():
  print()
  print("############################################")
  print("#####         Módulo Relatório         #####")
  print("############################################")
  print("##### 1 - Lista Geral de Produtos      #####")
  print("##### 2 - Lista Geral de vendas        #####")
  print("##### 3 - Lista Geral de Clientes      #####")
  print("##### 0 - Retornar ao Menu Principal   #####")
  op_relate = input("##### Escolha sua opção: ")
  return op_relate

def lista_geral_produ():
  os.system('clear')
  print()
  print("##################################################################################")
  print("#######################     Relatório Geral de Produtos    #######################")
  print("##################################################################################")
  print("|-----------|-----------------------------|--------------------|-----------------|")
  print("| Código    |       Nome do produto       |        Peso        |      Preço      |")
  print("|-----------|-----------------------------|--------------------|-----------------|")
  for cod in produtos:
    print("| %-9s "%(cod), end='')
    print("| %-27s "%(produtos[cod][0]), end='')
    print("| %-18s "%(produtos[cod][1]), end='')
    print("| %-15s |"%(produtos[cod][2]))
  print('|-----------|-----------------------------|--------------------|-----------------|')
  print()
  input("Tecle <ENTER> para continuar...")

def lista_clientes():
  os.system('clear')
  print()
  print("######################################################################################################")
  print("################################    Relatório Geral de Clientes     ##################################")
  print("######################################################################################################")
  print("|-------------------|--------------------------------|---------------------------|-------------------|")
  print("|      CPF          |         Nome Completo          |           E-mail          |     Celular       |")
  print("|-------------------|--------------------------------|---------------------------|-------------------|")
  # Organizada por ChatGPT
  for cpf in clientes:
      print("| %-17s " % (cpf.center(17)), end='')  
      print("| %-30s " % (clientes[cpf][0].center(30)), end='')  
      print("| %-25s " % (clientes[cpf][1].center(25)), end='')  
      print("| %-15s |" % (clientes[cpf][2].center(15)))  

  print("|-------------------|--------------------------------|---------------------------|-------------------|")
  print()
  input("Tecle <ENTER> para continuar...")

def list_vende():
  os.system('clear')
  print()
  print("##################################################################################")
  print("#######################     Relatório Geral de Vendas      #######################")
  print("##################################################################################")
  print("|-------------|---------------------------|--------------------|-----------------|")
  print("|Cupom fiscal |  Nome código do produto   |     Quantidade     |  Data da venda  |")
  print("|-------------|---------------------------|--------------------|-----------------|")
  for cupom_fiscal in pedidos:
    print("| %-11s "%(cupom_fiscal), end='')
    print("| %-25s "%(pedidos[cupom_fiscal][0]), end='')
    print("| %-18s "%(pedidos[cupom_fiscal][1]), end='')
    print("| %-15s |"%(pedidos[cupom_fiscal][2]))
  print("|-------------|---------------------------|--------------------|-----------------|")
  print()
  input("Tecle <ENTER> para continuar...")



  
################################################################
################################################################
##########    P R O G R A M A   P R I N C I P A L     ##########
################################################################
################################################################

op_princ = ''
while op_princ != '0':
  op_princ = menu_principal()
  if op_princ == '1':
    op_produ = ''
    while op_produ != '0':
      op_produ = menu_produtos()
      print()
      if op_produ == '1':
        cadastrar_produtos()
      elif op_produ == '2':
        exibir_produtos()
      elif op_produ == '3':
        alterar_produto()
      elif op_produ == '4':
        excluir_produto()
        
  elif op_princ == '2':
    op_pedido = ''
    while op_pedido != '0':
      op_pedido = menu_vendas()
      print()
      if op_pedido == '1':
        cadastrar_venda()
      elif op_pedido == '2':
        exibir_vendas()
      elif op_pedido == '3':
        alterar_venda()
      elif op_pedido == '4':
        excluir_venda()

  elif op_princ == '3':
    op_cliente = ''
    while op_cliente != '0':
      op_cliente = menu_clienetes()
      if op_cliente == '1':
        cadastrar_clente()
      elif op_cliente == '2':
        exibir_clientes()
      elif op_cliente == '3':
        alterar_cliente()
      elif op_cliente == '4':
        excluir_cliente()
        
  elif op_princ == '4':
    op_relate = ''
    while op_relate != '0':
      op_relate = menu_relate()
      if op_relate == '1':
        lista_geral_produ()
      elif op_relate == '2':
        list_vende()
      elif op_relate == '3':
        lista_clientes()
        
        
      
  elif op_princ == '5':
      print()
      print("############################################")
      print("#####  Você está no Módulo Informações  ####")
      print("############################################")
      print()
      print("##### Projeto de Gestão de uma Fábrica. ####")
      print("##### Equipe de desenvolvimento:        ####")
      print("##### GitHub: @LuizFelixDev             ####")
      print("##### instagram: luiz.felix07           ####")
      print("##### Email: luizhenriquefelix138@gmail ####")
      print()
      input("Tecle <ENTER> para continuar...")


print("Você encerrou o programa!")
print("Até logo!")

arqu_produ = open('produtos.dat', 'wb')
pickle.dump(produtos, arqu_produ)
arqu_produ.close()

arqu_vendas = open('vendas.dat', 'wb')
pickle.dump(pedidos, arqu_vendas)
arqu_vendas.close()

arqu_clientes = open('clientes.dat', 'wb')
pickle.dump(clientes, arqu_clientes)
arqu_clientes.close()
