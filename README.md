# corretor-provas
Meu primeiro repositório no GitHub!


def cadastro_alunos(): #Função para cadastrar o total de alunos
    n = int(input('Quantos alunos terão a provas corrigida? '))
    for x in range(n): #De acordo com a quantidade informada o loop será executado
        nome = input("NOME: ")
        nota = 0
        for i in range(1, 11): #Solicita respostas para procva de 10 questões
            resp = input("Resposta Questão {}: ".format(i))
            gabarito.append(resp) #Grava as respostas na lista gabarito
        for i in range(len(provas)): #Conforme o tamanho da lista provas, compara as respostas dos alunos com o gabarito da prova
            if gabarito[i] == provas[i]: #A cada vez que o gabarito retorna igualdade soma 1 ponto na nota
                nota += 1

        principal.append({"nome": nome, "nota": nota}) # Grava o nome e a nota do aluno na lista principal
        

def verifica_nota(): #Função que vai retornar nome e nota de cada aluno
    for i in range(len(principal)): #A cada resultado encontrado na lista principal, vai retornar um nome e nota
        print("ALUNO: {} NOTA: {}".format(principal[i]["nome"].ljust(8), principal[i]["nota"]))
        

def lista_aprovados(): #Função que apresenta os alunos aprovados
    for i in range(len(principal)): #Percorre a lista e retorna os alunos que tiveram a nota maior que 7
        if (principal[i]["nota"]) >= 7:
            print("ALUNO: {} ".format(principal[i]["nome"].ljust(8)))



gabarito = []
principal = []


#Programa principal
print('Cadastre o gabarito da disciplina que deseja corrigir: ')
provas = list()
for i in range (1,11):
    resp = input("Questão {}: ".format(i))
    provas.append(resp)
print('Agora faça o cadastro do gabarito dos alunos.')
cadastro_alunos()
print('-='*15)
print('As notas de cada aluno são: ')
verifica_nota()
print('-='*15)
print('Os alunos aprovados foram: ')
lista_aprovados()
print()
print(' <<< PROGRAMA FINALIZADO >>> ')
