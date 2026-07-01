## Tabular-to-FASTA

```python
import pandas as pd
import sys
```

# Verificar se os argumentos estão corretos
```
if len(sys.argv) != 3:
print("Uso: python3 Tabular-to-fasta.py <input.csv> <output.fasta>")
sys.exit(1)
```
# Nome do arquivo de entrada e de saída

```
input_file = sys.argv[1]
output_file = sys.argv[2]
```
#Carregar a tabela CSV

```
tabela = pd.read_csv(input_file)
except FileNotFoundError:
print(f"Erro: Arquivo {input_file} não encontrado.")
sys.exit(1)
```

# Abrir um arquivo FASTA para escrita
```
with open(output_file, "w") as fasta_file:
for index, row in tabela.iterrows():
# Escrever o identificador da sequência
fasta_file.write(f">{row[0]}\n")
# Escrever a sequência
fasta_file.write(f"{row[1]}\n")

print(f"Conversão concluída! Arquivo FASTA salvo como {output_file}.")
```

