# SEMANA-12
import random

# Datos de ejemplo
ciudades = ["Quito", "Guayaquil", "Cuenca"]
dias_semana = ["Lunes", "Martes", "Miércoles", "Jueves", "Viernes", "Sábado", "Domingo"]
semanas = 4

# Crear matriz 3D con temperaturas aleatorias
temperaturas = [[[random.randint(10, 29) for _ in range(semanas)] for _ in range(len(dias_semana))] for _ in range(len(ciudades))]

# Calcular promedios semanales por ciudad
promedios_semanales = [[0 for _ in range(semanas)] for _ in range(len(ciudades))]

for i, ciudad in enumerate(ciudades):
    for semana in range(semanas):
        suma_temperaturas = 0
        for dia in range(len(dias_semana)):
            suma_temperaturas += temperaturas[i][dia][semana]
        promedio = suma_temperaturas / len(dias_semana)
        promedios_semanales[i][semana] = promedio

# Mostrar promedios
for i, ciudad in enumerate(ciudades):
    for semana in range(semanas):
        print(f"Promedio {ciudad}, Semana {semana + 1}: {promedios_semanales[i][semana]:.2f} °C")
