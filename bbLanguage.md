# Linguagem bb
### Cirar uma "linguagem" nova com python pode ser bem simples, pois não ncessariamente será uma nova linguagem, apenas novos comando para resolver determindados problemas.
## Para isso é preciso:

- Criar um terminal/local inicial, para que o usuário não se perca.
- Definir bem os comando que serão criados, por exemplo( Soma, sub, mult, div ), esses seriam os comandos de matemática, operadores básicos.
- Declaração de variáveis, comparadores, loop's e outros comando básicos

```
import os

def clear():
    os.system('cls' if os.name == 'nt' else 'clear')

# memória de variáveis
variaveis = {}

def parse_valor(valor):
    # tenta converter pra número ou buscar variável
    if valor in variaveis:
        return variaveis[valor]
    try:
        return float(valor)
    except:
        return valor  # texto

def executar_comando(cmd):
    try:
        if ":" not in cmd:
            return "Formato inválido. Use: comando: valores"

        comando, valores = cmd.split(":", 1)
        comando = comando.strip()
        valores = valores.strip()

        match comando:

            # -------------------------
            # DECLARAÇÃO DE VARIÁVEL
            # -------------------------
            case "dec":
                if "=" not in valores:
                    return "Use: dec: x = valor"

                nome, valor = valores.split("=", 1)
                nome = nome.strip()
                valor = valor.strip()

                valor_convertido = parse_valor(valor)
                variaveis[nome] = valor_convertido

                return f"Variável '{nome}' = {valor_convertido}"

            # -------------------------
            # PRINT
            # -------------------------
            case "on":
                partes = valores.split()
                resultado = []

                for p in partes:
                    if p in variaveis:
                        resultado.append(str(variaveis[p]))
                    else:
                        resultado.append(p)

                return " ".join(resultado)

            # -------------------------
            # SOMA
            # -------------------------
            case "som":
                partes = valores.split()
                if len(partes) != 2:
                    return "Use: som: x y"

                x = parse_valor(partes[0])
                y = parse_valor(partes[1])

                return str(float(x) + float(y))

            # -------------------------
            # SUBTRAÇÃO
            # -------------------------
            case "sub":
                partes = valores.split()
                if len(partes) != 2:
                    return "Use: sub: x y"

                x = parse_valor(partes[0])
                y = parse_valor(partes[1])

                return str(float(x) - float(y))

            # -------------------------
            # MULTIPLICAÇÃO
            # -------------------------
            case "mult":
                partes = valores.split()
                if len(partes) != 2:
                    return "Use: mult: x y"

                x = parse_valor(partes[0])
                y = parse_valor(partes[1])

                return str(float(x) * float(y))

            # -------------------------
            # DIVISÃO
            # -------------------------
            case "div":
                partes = valores.split()
                if len(partes) != 2:
                    return "Use: div: x y"

                x = parse_valor(partes[0])
                y = parse_valor(partes[1])

                if float(y) == 0:
                    return "Erro: divisão por zero"

                return str(float(x) / float(y))

            case _:
                return "Comando não reconhecido"

    except:
        return "Erro ao processar comando"


line = "+----------------+"

while True:
    clear()
    print(line)
    print("|  Linguagem bb  |")
    print(line)
    print("| 1. Terminal    |")
    print("| 2. Comandos    |")
    print("| 3. Variáveis   |")
    print("| 4. Sair        |")
    print(line)

    option = input("Escolha uma opção:\n>> ")

    match option:
        case "1":
            clear()
            print(line)
            print("Terminal")
            print(line)
            print("Digite 'sair' para voltar")
            print("Ex:")
            print("dec: x = 10")
            print("som: x 5")
            print(line)

            while True:
                cmd = input(">>> ")

                if cmd == "sair":
                    break

                resultado = executar_comando(cmd)
                print(resultado)

        case "2":
            while True:
                clear()
                print(line)
                print("|    Comandos    |")
                print(line)
                print("| 0. On          |")
                print("| V. Dec         |")
                print("| 1. Som         |")
                print("| 2. Sub         |")
                print("| 3. Mult        |")
                print("| 4. Div         |")
                print("| 5. Voltar      |")
                print(line)

                commandOpt = input("Escolha uma opção:\n>> ")

                clear()

                match commandOpt:
                    case "0":
                        print("on: texto ou variável")
                        teste = input("Testar:\n>> ")
                        print(executar_comando(teste))
                        input("Enter...")

                    case "V" | "v":
                        print("dec: x = 10")
                        teste = input("Testar:\n>> ")
                        print(executar_comando(teste))
                        input("Enter...")

                    case "1":
                        teste = input("som: ")
                        print(executar_comando(f"som: {teste}"))
                        input("Enter...")

                    case "2":
                        teste = input("sub: ")
                        print(executar_comando(f"sub: {teste}"))
                        input("Enter...")

                    case "3":
                        teste = input("mult: ")
                        print(executar_comando(f"mult: {teste}"))
                        input("Enter...")

                    case "4":
                        teste = input("div: ")
                        print(executar_comando(f"div: {teste}"))
                        input("Enter...")

                    case "5":
                        break

                    case _:
                        print("Opção inválida")
                        input("Enter...")

        case "3":
            clear()
            print("Variáveis atuais:")
            for k, v in variaveis.items():
                print(f"{k} = {v}")
            input("Enter...")

        case "4":
            print("Saindo...")
            break

        case _:
            print("Opção inválida")
            input("Pressione Enter...")
```
