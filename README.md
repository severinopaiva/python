# python
# Programa que determina o MDC entre lista de números
#Autor: Paiva

# Inicialização Listas a serem usadas
numeros = []
mdcs = []

def maior (x,y):           #Função maior de 2 números
    if x >= y:
       max = x
    else:
       max = y
    return max

def menor (x,y):            #Função menor de 2 números
    if x <= y:
       min = x
    else:
       min = y
    return min

#Função MDC de 2 números (Algorimo Euclides)
def mdc (num1,num2):       
   n1=maior(num1,num2)      
   n2=menor(num1,num2)     
   restodiv  = n1 % n2   
   while restodiv != 0:
         n1 = n2
         n2 = restodiv
         restodiv = n1 % n2
   return n2

#Programa Principal
n = 1
while n < 2:
    n = int(input ("Quantos números para MDC (mínimo de dois: "))

cont = 1
while cont <= n:
   num = int(input ("Digite número para calcular MDC: "))
   numeros.append(num)                  
   cont = cont + 1

numerosbkp = numeros

while len(numeros) > 1:
      for i in range (len(numeros)-1):
          mdcs.append(mdc ( numeros[i],numeros [i+1]))
      if len(mdcs) > 1:
         numeros = mdcs
         mdcs = []
      else:
         break


print ("Os números digitados: ")
for i in numerosbkp:
   print (i)
   
print ("Tem MDC: ", mdcs [0])
