# Validador de palindromos
## O que são?
- Palindromos são palavras que quando lidas de tras para frente ficam igual à de frente para tras.
## Exemplo:
- Arara &rArr; ararA
- Radar &rArr; radaR

# O código
## Para realizarmos a validação do palindormo precisamos separar cada letra da palavra e inverter a ordem( Como se fosse lida de tras para frente ), e comparando com a palavra original, se forem iguais a palavra é um palindromo, se não for igual, não é um palindromo.
```
word = input("Digite um palindromo\n>>> ")
breakWord = list(word)

validWord = list(reversed(breakWord))
print(validWord)
print(breakWord)

if  validWord == breakWord:
  print("É um palindromo")
else:
  print("Não é um palindromo")
```
