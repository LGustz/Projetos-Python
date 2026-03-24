# Atividade 03 - Quilometragem do veículo com Python 🐍
```
quilometragemAtual = float(input("Digite a quilometragem atual do veículo: "))

trocaDeOleoEFiltros = 10000 # 10000Km Apenas troca de óleo e filtros
revisaoPreventiva = 40000 # 40000Km Revisão preventiva
revisaoGeral = 80000 # 80000Km Revisão geral

# Manutencao Corretiva a ciam de 80000Km rodados

if quilometragemAtual <= trocaDeOleoEFiltros:
  print(f"Apenas troca de óleos e filtros necessários!\n Atual quilometragem: {quilometragemAtual}")
elif quilometragemAtual <= revisaoPreventiva:
  print(f"Revisão preventiva necessária!\n Atual quilometragem: {quilometragemAtual}")
elif quilometragemAtual <= revisaoGeral:
  print(f"Revisão geral necessária!\n Atual quilometragem: {quilometragemAtual}")
else:
  print(f"Manutenção corretiva necessária!\n Atual quilometragem: {quilometragemAtual}")
```
