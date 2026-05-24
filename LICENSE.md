# ===================================================
# Universidad Nacional Abierta y a Distancia - UNAD
# Curso: Fundamentos de ProgramaciÃ³n
# Fase 5 - EvaluaciÃ³n Final POA
# Problema 2: PromociÃ³n de menÃº de restaurante
# Estudiante: Fenner Chamorro
# ===================================================

# ---------------------------------------------------
# MATRIZ DE PRODUCTOS
# Cada fila almacena:
# [Nombre del producto, CategorÃ­a, Precio Base]
# ---------------------------------------------------

productos = [
    ["Hamburguesa Especial", "Comida Rapida", 18000],
    ["Pizza Familiar", "Comida Rapida", 35000],
    ["Jugo Natural", "Bebidas", 8000],
    ["Helado", "Postres", 7000],
    ["Perro Caliente", "Comida Rapida", 12000],
    ["Malteada", "Bebidas", 15000]
]

# ---------------------------------------------------
# VARIABLES DE CONFIGURACIÃ“N
# categoria_objetivo:
# Define a quÃ© categorÃ­a se aplicarÃ¡ la promociÃ³n
#
# umbral_precio:
# Define el valor mÃ­nimo que debe tener el producto
# para recibir el descuento
# ---------------------------------------------------

categoria_objetivo = "Comida Rapida"
umbral_precio = 15000


# ---------------------------------------------------
# FUNCIÃ“N: calcular_precio_final()
#
# ParÃ¡metros:
# categoria -> categorÃ­a del producto
# precio_base -> precio original del producto
#
# FunciÃ³n:
# Verifica si el producto cumple las condiciones:
# 1. Pertenecer a la categorÃ­a indicada
# 2. Tener un precio mayor al umbral definido
#
# Si cumple:
# Aplica descuento del 15%
#
# Si no cumple:
# Mantiene el precio original
# ---------------------------------------------------

def calcular_precio_final(categoria, precio_base):

    if categoria == categoria_objetivo and precio_base > umbral_precio:
        
        # Se calcula el descuento
        descuento = precio_base * 0.15
        
        # Se resta el descuento al precio inicial
        precio_final = precio_base - descuento

    else:
        
        # Si no cumple condiciones
        # el precio permanece igual
        precio_final = precio_base

    return precio_final


# ---------------------------------------------------
# INFORME DE RESULTADOS
#
# Se usa un ciclo for para recorrer todos
# los productos almacenados en la matriz.
# ---------------------------------------------------

print("\n========== INFORME DE PROMOCIONES ==========\n")

for producto in productos:

    # Se extrae informaciÃ³n de cada fila
    nombre = producto[0]
    categoria = producto[1]
    precio_base = producto[2]

    # Se llama la funciÃ³n y se guarda el resultado
    precio_final = calcular_precio_final(
        categoria,
        precio_base
    )

    # Mostrar resultados en pantalla
    print("Producto:", nombre)
    print("CategorÃ­a:", categoria)
    print("Precio Base: $", precio_base)
    print("Precio Final: $", round(precio_final))
    print("--------------------------------------")

