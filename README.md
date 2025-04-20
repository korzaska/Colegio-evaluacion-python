![image](https://github.com/user-attachments/assets/5737404c-cd73-4c8e-b470-1e9c42536db5)# Colegio-evaluacion-python
calcula el promedio de notas de estudiantes con un buclue repetivo 
def calcular_promedio(notas):
    """Calcula el promedio de una lista de notas."""
    suma = sum(notas)
    promedio = suma / len(notas)
    return promedio

def determinar_calificacion(promedio):
    """Determina la calificación final basada en el promedio."""
    if promedio >= 6:
        return "Excelente"
    elif 5 <= promedio < 6:
        return "Muy Bien"
    elif 4 <= promedio < 5:
        return "Bien"
    elif 3 <= promedio < 4:
        return "Aprobado"
    else:
        return "Insuficiente"

#Algoritmo Principal Sobre las Notas De los Estudiantes Creado Por Ignacio Duran 
while True:
    try:
        num_notas = int(input("Ingrese el número de notas del estudiante: "))
        if num_notas <= 0:
            print("Por favor, ingrese un número de notas válido (mayor que cero).")
            continue  # Vuelve al inicio 
    except ValueError:
        print("Entrada inválida. Ingrese un número entero.")
        continue  # Vuelve al inicio 

    notas = []
    for i in range(num_notas):
        while True:
            try:
                nota = float(input(f"Ingrese la nota {i+1} (entre 1 y 7): "))
                if 1 <= nota <= 7:
                    notas.append(nota)
                    break  # Sale del bucle interno si la nota es válida
                else:
                    print("Nota inválida. Ingrese una nota entre 1 y 7.")
            except ValueError:
                print("Entrada inválida. Ingrese un número.")

    promedio = calcular_promedio(notas)
    calificacion_final = determinar_calificacion(promedio)

    print(f"Promedio del estudiante: {promedio:.2f}")  # Limita a 2 decimales
    print(f"Calificación final: {calificacion_final}")

    continuar = input("¿Desea ingresar las notas de otro estudiante? (s/n): ").lower()
    if continuar != 's':
        break  # Sale del bucle principal si no quiere continuar
