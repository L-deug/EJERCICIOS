EJERCICIO #1
C++
// Función para calcular el cargo por estacionamiento
#include <iostream>
#include <iomanip>

using namespace std;

double calcularCargos(double horas_estacionado) {
    const double tarifa_base = 2.00;
    const double tarifa_adicional_por_hora = 0.50;
    const double cargo_max = 10.00;
    double cargo;
    if (horas_estacionado <= 3) {
        cargo = tarifa_base;
    } else {
        double horas_extra = horas_estacionado - 3;
        cargo = tarifa_base + (horas_extra * tarifa_adicional_por_hora);
    }

    return min(cargo, cargo_max);
}

int main() {
    double horas_cliente1, horas_cliente2, horas_cliente3;
    cout << "Horas de estacionamiento para el Cliente numero 1: ";
    cin >> horas_cliente1;
    cout << "Horas de estacionamiento para el Cliente numero 2: ";
    cin >> horas_cliente2;
    cout << "Horas de estacionamiento para el Cliente numero 3: ";
    cin >> horas_cliente3;
    double cargo_c1 = calcularCargos(horas_cliente1);
    double cargo_c2 = calcularCargos(horas_cliente2);
    double cargo_c3 = calcularCargos(horas_cliente3);
    cout << "Automóvil   horas   cargo" << endl;
    cout << fixed << setprecision(2); 
    cout << "1           " << horas_cliente1 << "      $" << cargo_c1 << endl;
    cout << "2           " << horas_cliente2 << "      $" << cargo_c2 << endl;
    cout << "3           " << horas_cliente3 << "     $" << cargo_c3 << endl;

    double total_recibos = cargo_c1 + cargo_c2 + cargo_c3;
    cout << "Total                    $" << total_recibos << endl;

    return 0;
}
________________________________________________________________________________________________________________________________
PYTHON
# Función para calcular el cargo por estacionamiento
def calcularCargos(horas_estacionado):
    tarifa_base = 2.00
    tarifa_adicional_por_hora = 0.50
    cargo_maximo = 10.00

    if horas_estacionado <= 3:
        cargo = tarifa_base
    else:
        horas_extra = horas_estacionado - 3
        cargo = tarifa_base + (horas_extra * tarifa_adicional_por_hora)

    return min(cargo, cargo_maximo)

horas_cliente1 = float(input("Horas de estacionamiento para el Cliente 1: "))
horas_cliente2 = float(input("Horas de estacionamiento para el Cliente 2: "))
horas_cliente3 = float(input("Horas de estacionamiento para el Cliente 3: "))


cargo_c1 = calcularCargos(horas_cliente1)
cargo_c2 = calcularCargos(horas_cliente2)
cargo_c3 = calcularCargos(horas_cliente3)

print("Automóvil   Horas   Cargo")
print(f"1           {horas_cliente1}      ${cargo_c1:.2f}")
print(f"2           {horas_cliente2}      ${cargo_c2:.2f}")
print(f"3           {horas_cliente3}     ${cargo_c3:.2f}")

total_recibos = cargo_c1 + cargo_c2 + cargo_c3
print(f"Total                    ${total_recibos:.2f}")

SEGUNDO EJERCICIO-----------------------------------------------------------------------------------------------------------
C++
#include <iostream>

using namespace std;

int main() {
    int filas, columnas;

    // Pedir al usuario el número de filas y columnas de la matriz
    cout << "Ingrese el número de filas de la matriz: ";
    cin >> filas;
    cout << "Ingrese el número de columnas de la matriz: ";
    cin >> columnas;
    int tamano = filas * columnas;
    int matriz[tamano];
    cout << "Ingrese los valores de la matriz:" << endl;
    for (int i = 0; i < tamano; i++) {
        cout << "Ingrese el valor " << i + 1 << ": ";
        cin >> matriz[i];
    }

    int nummayor = matriz[0];
    for (int i = 1; i < tamano; i++) {
        if (matriz[i] > nummayor) {
            nummayor = matriz[i];
        }
    }
    
    int suma = 0;
    for (int i = 0; i < tamano; i++) {
        suma += matriz[i];
    }
    double promedio = static_cast<double>(suma) / tamano;

    cout << "El número mayor en la matriz es: " << nummayor << endl;
    cout << "Los datos de la matriz ingresada son:" << endl;
    for (int i = 0; i < tamano; i++) {
        cout << matriz[i] << " ";
        if ((i + 1) % columnas == 0) {
            cout << endl;
        }
    }
    cout << "El promedio de la matriz es: " << promedio << endl;

    return 0;
}
___________________________________________________________________________________________________________________________
PYTHON
def main():
    filas = int(input("Ingrese el número de filas de la matriz: "))
    columnas = int(input("Ingrese el número de columnas de la matriz: "))
    matriz = []
    print("Ingrese los valores de la matriz:")
    for i in range(filas):
        fila = []
        for j in range(columnas):
            valor = int(input(f"Ingrese el valor en la fila {i+1}, columna {j+1}: "))
            fila.append(valor)
        matriz.append(fila)

    numeromayor = max(max(fila) for fila in matriz)

    suma = sum(sum(fila) for fila in matriz)
    promedio = suma / (filas * columnas)
    print("El número mayor en la matriz es:", numeromayor)
    print("Los datos de la matriz ingresada son:")
    for fila in matriz:
        print(' '.join(map(str, fila)))
    print("El promedio de la matriz es:", promedio)

if _name_ == "_main_":
    main()
TERCER EJERCICIO---------------------------------------------------------------------------------------------------------------------
C++
#include <iostream>
using namespace std;

bool esPerfecto(int numero) {
    int suma_divisores = 1; // Inicializamos con 1 porque todo número es divisible por 1
    
    cout << "Divisores de " << numero << ": 1";
    
    for (int i = 2; i <= numero / 2; i++) {
        if (numero % i == 0) {
            suma_divisores += i;
            cout << " + " << i;
        }
    }
    
    cout << endl;
    
    return suma_divisores == numero;
}

int main() {
    int numero;

    cout << "Ingrese un número para verificar si es perfecto: ";
    cin >> numero;

    if (esPerfecto(numero)) {
        cout << numero << " es un número perfecto." << endl;
    } else {
        cout << numero << " no es un número perfecto." << endl;
    }

    return 0;
}
___________________________________________________________________________________________________________________________
PYTHON
def esPerfecto(numero):
    suma_divisores = 1  # Inicializamos con 1 porque todo número es divisible por 1
    
    print(f"Divisores de {numero}: 1", end=" ")
    
    for i in range(2, numero // 2 + 1):
        if numero % i == 0:
            suma_divisores += i
            print(f"+ {i}", end=" ")
    
    print()  # Imprimimos un salto de línea
    
    return suma_divisores == numero

numero = int(input("Ingrese un número para verificar si es perfecto: "))

if esPerfecto(numero):
    print(f"{numero} es un número perfecto.")
else:
    print(f"{numero} no es un número perfecto.")
CUARTO EJERCICIO----------------------------------------------------------------------------------------------------------------
