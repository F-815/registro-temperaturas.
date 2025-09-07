# Registro de Temperaturas Diarias con matriz 3D

# Definimos parámetros
ciudades = ["Quito", "Guayaquil", "Cuenca"]
dias_semana = ["Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo"]
num_semanas = 2  # puedes cambiarlo según lo que necesites

# Crear matriz 3D: [ciudad][día][semana]
# Para simplificar, llenamos con datos de ejemplo (temperaturas aleatorias)
import random
matriz_temperaturas = [
    [  # Para cada ciudad
        [random.randint(10, 30) for _ in range(num_semanas)]  # temperaturas por semana
        for _ in dias_semana
    ]
    for _ in ciudades
]

# Mostrar datos de temperaturas
print("=== Registro de temperaturas (ejemplo) ===")
for i, ciudad in enumerate(ciudades):
    print(f"\nCiudad: {ciudad}")
    for d, dia in enumerate(dias_semana):
        for s in range(num_semanas):
            print(f"  Semana {s+1}, {dia}: {matriz_temperaturas[i][d][s]} °C")

# Calcular promedios por ciudad y semana
print("\n=== Promedios por ciudad y semana ===")
for i, ciudad in enumerate(ciudades):
    for s in range(num_semanas):
        suma = 0
        for d in range(len(dias_semana)):
            suma += matriz_temperaturas[i][d][s]
        promedio = suma / len(dias_semana)
        print(f"{ciudad} - Semana {s+1}: {promedio:.2f} °C")
