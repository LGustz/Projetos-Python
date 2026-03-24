# Sistema de login/ciração de contas
### Para a criar uma conta precisamos de:
- Nome de usuário
- Senha
- Confirmar a senha
### Após isso, teremos que validar is dados, se o nome de usuário bate com a senha que está salva no banco de dado( Apenas possível ver se for admin )
```
users = {"admin": "admin"}

def criar_conta():
    while True:
        nome_usuario = input("Digite o nome de usuário:\n>>> ")

        if nome_usuario in users:
            print("Usuário já existe!")
            continue

        senha = input("Digite a senha:\n>>> ")
        confirmar_senha = input("Confirme a senha:\n>>> ")

        if senha == confirmar_senha:
            users[nome_usuario] = senha
            print("Conta criada com sucesso!")
            break
        else:
            print("Senhas não coincidem!")

def login():
    tentativas = 3

    while tentativas > 0:
        nome_usuario = input("Digite o nome de usuário:\n>>> ")
        senha = input("Digite a senha:\n>>> ")

        if nome_usuario in users and users[nome_usuario] == senha:
            print(f"Logado como {nome_usuario} com sucesso!")

            if nome_usuario == "admin":
                menu_admin()
            else:
                print("Bem-vindo usuário!")

            return

        else:
            tentativas -= 1
            print(f"Informações incorretas! Tentativas restantes: {tentativas}")

    print("Acesso bloqueado!")

def menu_admin():
    while True:
        print("\n1. Ver banco de dados")
        print("2. Criar conta")
        print("3. Sair")

        opcao = input("Escolha uma opção:\n>>> ")

        match opcao:
            case "1":
                print(users)

            case "2":
                criar_conta()

            case "3":
                break

            case _:
                print("Opção inválida")

login()
```
