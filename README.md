# Tallergit
def calcular_tarifa_hora(gastos_mensuales, horas_trabajadas_mes, margen_ganancia):
    """
    Calcula la tarifa por hora recomendada para un freelancer.

    :param gastos_mensuales: Total de gastos mensuales (float)
    :param horas_trabajadas_mes: Horas trabajadas al mes (float)
    :param margen_ganancia: Porcentaje de ganancia deseado (float)
    :return: Tarifa por hora recomendada (float)
    """
    if horas_trabajadas_mes <= 0:
        raise ValueError("Las horas trabajadas deben ser mayores a 0")

    costo_base_por_hora = gastos_mensuales / horas_trabajadas_mes
    tarifa_final = costo_base_por_hora * (1 + margen_ganancia / 100)

    return tarifa_final


def main():
    print("=== CALCULADORA DE PRESUPUESTO FREELANCE ===\n")

    try:
        gastos = float(input("Ingresa tus gastos mensuales totales: "))
        horas = float(input("Ingresa cuántas horas trabajas al mes: "))
        margen = float(input("Ingresa el porcentaje de ganancia deseado (%): "))

        tarifa = calcular_tarifa_hora(gastos, horas, margen)

        print("\n--- RESULTADO ---")
        print(f"Tarifa recomendada por hora: ${tarifa:.2f}")

    except ValueError as e:
        print(f"Error: {e}")


if __name__ == "__main__":
    main()
