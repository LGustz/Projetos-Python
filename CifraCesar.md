# Criptografia/Cifra de Cesar

## O que é?
- A Cifra de César é uma das técnicas de criptografia mais antigas e simples, utilizada por Júlio César para proteger comunicações militares

## Exemplo com deslocamento de 3 casas:
- Cesar &rArr; Fhvdu
- C = F (De C para F pulou 3 casa/letras)
- e = h
- s = v
- a = d
- r = u

## O Código
### Para iniciarmos precisamos ter o alfabeto separado letra por letra, após isso pegar a palavra escolhida e cada letra dela pular a quantidade respectiva de casas configurada.
```
alphabet = "abcdefghijklmnopqrstuvwxyz"

number = int(input("Digite o numero de casas:\n>>> "))
text = input("Digite o texto:\n>>> ")

resultado = ""

for letra in text:
    if letra in alphabet:
        pos = alphabet.index(letra)
        nova_pos = (pos + number) % 26
        resultado += alphabet[nova_pos]
    else:
        resultado += letra  # mantém espaços e símbolos

print("Texto criptografado:", resultado)
```
