# Huffman-Shannon_fano
# Problem Statement
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 

# Aim:
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

# Tools Required:
Python 3.x

# Program:
```
import numpy as np
import math

L = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of samples: "))

for i in range(n):
    pr = float(input(f"Enter the probability of sample value {i + 1}: "))  
    p.append(pr)

for j in range(n):
    l = float(input(f"Enter the length of the sample value {j + 1}: "))  
    lk.append(l)

for k in range(n):
    L += p[k] * lk[k]

for k in range(n):
    hs += p[k] * math.log(1 / p[k], 2)
hs = round(hs, 3)

eff = round(hs / L, 3)
red = round(1 - eff, 3)

var = sum(p[k] * (lk[k] - L) ** 2 for k in range(n))
var = round(var, 3)

print("\nResults:")
print(f"Average Codeword Length: {L}")
print(f"Entropy: {hs}")
print(f"Efficiency: {eff * 100} %")
print(f"Redundancy: {red}")
print(f"Variance: {var}")
```

# Calculation:
![image](https://github.com/user-attachments/assets/22d047eb-68f7-4bf8-b93c-9a556e0c9374)
![image](https://github.com/user-attachments/assets/a9981745-5f50-4fa2-bf14-015661698ab1)
![image](https://github.com/user-attachments/assets/397e8574-47fa-448e-9adc-721e23a1e8cf)



# Output:
![image](https://github.com/user-attachments/assets/98df6cba-e556-45b9-85d7-edc4c0c984b7)


# Results:
For the given probabilities {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25}:

Average Codeword Length: 2.625
Entropy: 2.625
Efficiency: 100.0%
Redundancy: 0.0
Variance: 0.484
