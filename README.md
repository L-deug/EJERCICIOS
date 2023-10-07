def calcular_cargo_estacionamiento(horas_estacionado):
    tarifa_minima = 2.00
    tarifa_adicional = 0.50
    maximo_cargo = 10.00
    horas_maximas = 24
    
    if horas_estacionado <= 3:
        cargo = tarifa_minima
    else:
        cargo = tarifa_minima + tarifa_adicional * (horas_estacionado - 3)
    
    return min(cargo, maximo_cargo)

def main():
    print("Cliente\tHoras Estacionado\tCargo")
    
    total_recibos = 0.0
    
    for i in range(3):
        horas_estacionado = float(input(f"Ingrese las horas estacionado para el cliente {i + 1}: "))
        cargo = calcular_cargo_estacionamiento(horas_estacionado)
        total_recibos += cargo
        print(f"Cliente {i + 1}\t{horas_estacionado:.2f}\t\t\t${cargo:.2f}")
    
    print(f"\nTotal de recibos de ayer: ${total_recibos:.2f}")

if __name__ == "__main__":
    main()

