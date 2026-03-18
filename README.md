# EJERCICIOSOCIO
package arreglos;

public class Ejercicio1 {
    public static void main(String[] args) {
        // Ejercicio 1: Inicializar directamente un arreglo con los primeros 10 números primos e imprimirlo

        int[] numerosPrimos = {2,3,5,7,11,13,17,19,23,29}; // arreglo con los 10 primeros primos

        // Recorrer el arreglo e imprimir cada número
        System.out.println("Primeros 10 números primos:");
        for (int i = 0; i < numerosPrimos.length; i++) {
            System.out.print(numerosPrimos[i] + " ");
        }
    }
}

package arreglos;

public class Ejercicio2 {
    public static void main(String[] args) {
        // Ejercicio 2: Inicializar por programa un arreglo con los 100 primeros números pares e imprimirlo

        int[] numerosPares = new int[100]; // arreglo de 100 posiciones

        // Llenar el arreglo con los 100 primeros pares
        for (int i = 0; i < numerosPares.length; i++) {
            numerosPares[i] = 2 * (i + 1);
        }

        // Imprimir en una sola línea
        System.out.println("100 primeros pares en una sola línea:");
        for (int numero : numerosPares) System.out.print(numero + " ");
        System.out.println("\n");

        // Imprimir en 10 líneas con número de línea
        System.out.println("100 primeros pares en 10 líneas:");
        for (int i = 0; i < 10; i++) {
            System.out.print("Línea " + (i + 1) + ": ");
            for (int j = 0; j < 10; j++) {
                System.out.print(numerosPares[i * 10 + j] + " ");
            }
            System.out.println();
        }
    }
}
pene