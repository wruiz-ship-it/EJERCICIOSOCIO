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

package arreglos;

import java.util.Random;
import java.util.Scanner;

public class Ejercicio3 {
    public static void main(String[] args) {
        // Ejercicio 3: Leer n números aleatorios, calcular factoriales y guardarlos en otro arreglo

        Scanner entrada = new Scanner(System.in);
        Random aleatorio = new Random();

        System.out.print("Ingrese n: ");
        int cantidadNumeros = entrada.nextInt();

        int[] numeros = new int[cantidadNumeros];
        long[] factoriales = new long[cantidadNumeros];

        // Generar números aleatorios entre 0 y 10 y calcular factorial
        for (int i = 0; i < cantidadNumeros; i++) {
            numeros[i] = aleatorio.nextInt(11); // número entre 0 y 10
            long factorial = 1;
            for (int j = 2; j <= numeros[i]; j++) factorial *= j;
            factoriales[i] = factorial;
        }

        // Imprimir resultados
        System.out.println("Números:");
        for (int numero : numeros) System.out.print(numero + " ");
        System.out.println("\nFactoriales:");
        for (long f : factoriales) System.out.print(f + " ");
    }
}

package arreglos;

import java.util.Random;

public class Ejercicio4 {
    public static void main(String[] args) {
        // Ejercicio 4: Leer 25 números aleatorios entre -50 y 50 y encontrar el menor y el mayor

        Random aleatorio = new Random();
        int[] numeros = new int[25];

        // Generar números entre -50 y 50
        for (int i = 0; i < numeros.length; i++) numeros[i] = aleatorio.nextInt(101) - 50;

        // Encontrar menor y mayor
        int menor = numeros[0], mayor = numeros[0];
        for (int numero : numeros) {
            if (numero < menor) menor = numero;
            if (numero > mayor) mayor = numero;
        }

        // Imprimir resultados
        System.out.println("Arreglo:");
        for (int numero : numeros) System.out.print(numero + " ");
        System.out.println("\nMenor: " + menor + " | Mayor: " + mayor);
    }
}

package arreglos;

import java.util.Random;

public class Ejercicio5 {
    public static void main(String[] args) {
        // Ejercicio 5: Inicializar un arreglo con 20 números aleatorios e invertir cada número

        Random aleatorio = new Random();
        int[] numerosOriginales = new int[20];
        int[] numerosInvertidos = new int[20];

        // Generar números aleatorios y calcular su inverso
        for (int i = 0; i < 20; i++) {
            numerosOriginales[i] = aleatorio.nextInt(900) + 100; // número de 3 cifras
            int numero = numerosOriginales[i], inverso = 0;
            while (numero > 0) {
                inverso = inverso * 10 + (numero % 10);
                numero /= 10;
            }
            numerosInvertidos[i] = inverso;
        }

        // Imprimir
        System.out.println("Original:");
        for (int numero : numerosOriginales) System.out.print(numero + " ");
        System.out.println("\nInvertidos:");
        for (int numero : numerosInvertidos) System.out.print(numero + " ");
    }
}

package arraylist;

import java.util.ArrayList;
import java.util.Random;

public class Ejercicio6 {
    public static void main(String[] args) {
        // Ejercicio 6: Leer números enteros aleatorios entre -10 y 10
        // guardarlos en un ArrayList hasta que aparezca el número 10
        // luego mostrar los números, su suma y su media

        ArrayList<Integer> listaNumeros = new ArrayList<>();
        Random aleatorio = new Random();
        int suma = 0;

        // Generar números hasta que salga el 10
        while (true) {
            int numero = aleatorio.nextInt(21) - 10; // rango -10 a 10
            listaNumeros.add(numero);
            suma += numero;
            if (numero == 10) break; // detener cuando salga 10
        }

        // Imprimir resultados
        System.out.println("Números leídos: " + listaNumeros);
        System.out.println("Suma: " + suma);
        System.out.println("Media: " + (double) suma / listaNumeros.size());
    }
}

package arraylist;

import java.util.ArrayList;
import java.util.Scanner;

public class Ejercicio7 {
    public static void main(String[] args) {
        // Ejercicio 7: Inicializar un ArrayList con los 20 primeros pares,
        // insertar un número en orden y borrar otro

        ArrayList<Integer> numerosPares = new ArrayList<>();
        for (int i = 1; i <= 20; i++) numerosPares.add(2 * i);

        System.out.println("ArrayList inicial: " + numerosPares);

        Scanner entrada = new Scanner(System.in);

        // Insertar un número en la posición correcta
        System.out.print("Ingrese un número para insertar: ");
        int valorInsertar = entrada.nextInt();
        int i = 0;
        while (i < numerosPares.size() && numerosPares.get(i) < valorInsertar) i++;
        numerosPares.add(i, valorInsertar);
        System.out.println("Después de insertar: " + numerosPares);

        // Borrar un número
        System.out.print("Ingrese un número para borrar: ");
        int valorBorrar = entrada.nextInt();
        numerosPares.remove((Integer) valorBorrar);
        System.out.println("Después de borrar: " + numerosPares);

        entrada.close();
    }
}

package arraylist;

import java.util.ArrayList;
import java.util.HashMap;
import java.util.Map;
import java.util.Random;

public class Ejercicio8 {
    public static void main(String[] args) {
        // Ejercicio 8: Generar 100 números aleatorios entre 1 y 20
        // contar cuántas veces aparece cada número y mostrar el más frecuente

        ArrayList<Integer> listaNumeros = new ArrayList<>();
        Random aleatorio = new Random();
        for (int i = 0; i < 100; i++) listaNumeros.add(aleatorio.nextInt(20) + 1);

        Map<Integer, Integer> frecuencia = new HashMap<>();
        for (int numero : listaNumeros) frecuencia.put(numero, frecuencia.getOrDefault(numero, 0) + 1);

        System.out.println("Número : Frecuencia");
        int masFrecuente = -1, maxFrecuencia = 0;
        for (int i = 1; i <= 20; i++) {
            int f = frecuencia.getOrDefault(i, 0);
            System.out.println(i + " : " + f);
            if (f > maxFrecuencia) { maxFrecuencia = f; masFrecuente = i; }
        }
        System.out.println("Número más frecuente: " + masFrecuente + " (veces: " + maxFrecuencia + ")");
    }
}

package arraylist;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Random;

public class Ejercicio9 {
    public static void main(String[] args) {
        // Ejercicio 9: Generar 20 números aleatorios entre 1 y 100
        // ordenar ascendente/descendente y separar pares/impares

        ArrayList<Integer> listaNumeros = new ArrayList<>();
        Random aleatorio = new Random();
        for (int i = 0; i < 20; i++) listaNumeros.add(aleatorio.nextInt(100) + 1);

        System.out.println("Original: " + listaNumeros);

        // Orden ascendente
        ArrayList<Integer> ascendente = new ArrayList<>(listaNumeros);
        Collections.sort(ascendente);
        System.out.println("Ascendente: " + ascendente);

        // Orden descendente
        ArrayList<Integer> descendente = new ArrayList<>(ascendente);
        Collections.reverse(descendente);
        System.out.println("Descendente: " + descendente);

        // Separar pares e impares
        ArrayList<Integer> pares = new ArrayList<>();
        ArrayList<Integer> impares = new ArrayList<>();
        for (int numero : listaNumeros) {
            if (numero % 2 == 0) pares.add(numero); else impares.add(numero);
        }
        System.out.println("Pares: " + pares);
        System.out.println("Impares: " + impares);
    }
}

package arraylist;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.Random;

class Partido {
    String equipoLocal, equipoVisitante;
    int golesLocal, golesVisitante;

    Partido(String local, String visitante, int gl, int gv) {
        equipoLocal = local; equipoVisitante = visitante; golesLocal = gl; golesVisitante = gv;
    }

    public String toString() {
        return equipoLocal + " " + golesLocal + " - " + golesVisitante + " " + equipoVisitante;
    }
}

public class Ejercicio10 {
    public static void main(String[] args) {
        // Ejercicio 10: Mostrar visitante ganador, contar victorias de Barcelona,
        // eliminar no empates y contar victorias del local

        List<String> equipos = Arrays.asList("Barcelona","Real","Atlético","Cali","Nacional","América");
        ArrayList<Partido> partidos = new ArrayList<>();
        Random aleatorio = new Random();

        // Generar partidos aleatorios
        for (int i = 0; i < 10; i++) {
            String local = equipos.get(aleatorio.nextInt(equipos.size()));
            String visitante;
            do { visitante = equipos.get(aleatorio.nextInt(equipos.size())); } while (visitante.equals(local));
            partidos.add(new Partido(local, visitante, aleatorio.nextInt(5), aleatorio.nextInt(5)));
        }

        System.out.println("Partidos:");
        for (Partido p : partidos) System.out.println(p);

        // Visitante ganador
        System.out.println("\nVisitante ganador:");
        for (Partido p : partidos) if (p.golesVisitante > p.golesLocal) System.out.println(p);

        // Veces que ganó Barcelona
        int victoriasBarcelona = 0;
        for (Partido p : partidos) {
            if ((p.equipoLocal.equals("Barcelona") && p.golesLocal > p.golesVisitante) ||
                (p.equipoVisitante.equals("Barcelona") && p.golesVisitante > p.golesLocal)) victoriasBarcelona++;
        }
        System.out.println("\nBarcelona ganó: " + victoriasBarcelona + " veces");

        // Eliminar no empates
        partidos.removeIf(p -> p.golesLocal != p.golesVisitante);
        System.out.println("\nSolo empates:");
        for (Partido p : partidos) System.out.println(p);

        // Contar victorias del local
        int victoriasLocal = 0;
        for (Partido p : partidos) if (p.golesLocal > p.golesVisitante) victoriasLocal++;
        System.out.println("\nVictorias del local: " + victoriasLocal);
    }
}

package matrices;

import java.util.Random;
import java.util.Scanner;

public class Ejercicio11 {
    public static void main(String[] args) {
        // Ejercicio 11: Inicializar una matriz de m filas por n columnas con números aleatorios
        // luego leer un número y determinar si está en la matriz y en qué posición

        Scanner entrada = new Scanner(System.in);
        Random aleatorio = new Random();

        System.out.print("Ingrese número de filas (m): ");
        int filas = entrada.nextInt();
        System.out.print("Ingrese número de columnas (n): ");
        int columnas = entrada.nextInt();

        int[][] matriz = new int[filas][columnas];

        // Rellenar la matriz con números aleatorios entre 0 y 50
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                matriz[i][j] = aleatorio.nextInt(51);
            }
        }

        System.out.print("Ingrese número a buscar: ");
        int numeroBuscado = entrada.nextInt();

        boolean encontrado = false;

        // Buscar el número en la matriz
        for (int i = 0; i < filas && !encontrado; i++) {
            for (int j = 0; j < columnas; j++) {
                if (matriz[i][j] == numeroBuscado) {
                    System.out.println("Número encontrado en fila " + i + ", columna " + j);
                    encontrado = true;
                    break;
                }
            }
        }

        if (!encontrado) System.out.println("Número no encontrado en la matriz");
    }
}

package matrices;

import java.util.Random;
import java.util.Scanner;

public class Ejercicio12 {
    public static void main(String[] args) {
        // Ejercicio 12: Inicializar una matriz n x n con números aleatorios entre -50 y 50
        // calcular la suma de la diagonal secundaria

        Scanner entrada = new Scanner(System.in);
        Random aleatorio = new Random();

        System.out.print("Ingrese tamaño de la matriz (n): ");
        int n = entrada.nextInt();

        int[][] matriz = new int[n][n];

        // Rellenar la matriz con números aleatorios
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                matriz[i][j] = aleatorio.nextInt(101) - 50;
            }
        }

        // Calcular suma de la diagonal secundaria
        int sumaDiagonalSecundaria = 0;
        for (int i = 0; i < n; i++) {
            sumaDiagonalSecundaria += matriz[i][n - 1 - i];
        }

        System.out.println("Suma de la diagonal secundaria: " + sumaDiagonalSecundaria);
    }
}

package matrices;

import java.util.Random;
import java.util.Scanner;

public class Ejercicio13 {
    public static void main(String[] args) {
        // Ejercicio 13: Inicializar una matriz n x n con números aleatorios
        // determinar si es simétrica y mostrar las esquinas

        Scanner entrada = new Scanner(System.in);
        Random aleatorio = new Random();

        System.out.print("Ingrese tamaño de la matriz (n): ");
        int n = entrada.nextInt();

        int[][] matriz = new int[n][n];

        // Rellenar la matriz con números aleatorios
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                matriz[i][j] = aleatorio.nextInt(50);
            }
        }

        // Verificar simetría
        boolean simetrica = true;
        for (int i = 0; i < n && simetrica; i++) {
            for (int j = 0; j < n; j++) {
                if (matriz[i][j] != matriz[j][i]) {
                    simetrica = false;
                    break;
                }
            }
        }

        System.out.println("¿La matriz es simétrica?: " + simetrica);

        // Mostrar esquinas
        System.out.println("Esquinas:");
        System.out.println("Superior izquierda: " + matriz[0][0]);
        System.out.println("Superior derecha: " + matriz[0][n-1]);
        System.out.println("Inferior izquierda: " + matriz[n-1][0]);
        System.out.println("Inferior derecha: " + matriz[n-1][n-1]);
    }
}

package matrices;

public class Ejercicio14 {
    public static void main(String[] args) {
        // Ejercicio 14: Inicializar una matriz m x n con valores predeterminados
        // encontrar su transpuesta e imprimir ambas

        int[][] matriz = {
            {1, 2, 3},
            {4, 5, 6}
        }; // matriz de 2 filas x 3 columnas

        int filas = matriz.length;
        int columnas = matriz[0].length;

        int[][] transpuesta = new int[columnas][filas];

        // Calcular transpuesta
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                transpuesta[j][i] = matriz[i][j];
            }
        }

        // Imprimir matriz original
        System.out.println("Matriz original:");
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                System.out.print(matriz[i][j] + " ");
            }
            System.out.println();
        }

        // Imprimir transpuesta
        System.out.println("Matriz transpuesta:");
        for (int i = 0; i < columnas; i++) {
            for (int j = 0; j < filas; j++) {
                System.out.print(transpuesta[i][j] + " ");
            }
            System.out.println();
        }
    }
}

package matrices;

import java.util.Random;
import java.util.Scanner;

public class Ejercicio15 {
    public static void main(String[] args) {
        // Ejercicio 15: Inicializar una matriz m x n con números aleatorios
        // intercambiar la primera fila con la segunda e imprimir la matriz

        Scanner entrada = new Scanner(System.in);
        Random aleatorio = new Random();

        System.out.print("Ingrese número de filas (m): ");
        int filas = entrada.nextInt();
        System.out.print("Ingrese número de columnas (n): ");
        int columnas = entrada.nextInt();

        int[][] matriz = new int[filas][columnas];

        // Rellenar la matriz con números aleatorios
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                matriz[i][j] = aleatorio.nextInt(100);
            }
        }

        // Intercambiar primera y segunda fila
        for (int j = 0; j < columnas; j++) {
            int temp = matriz[0][j];
            matriz[0][j] = matriz[1][j];
            matriz[1][j] = temp;
        }

        // Imprimir matriz resultante
        System.out.println("Matriz después de intercambiar filas:");
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                System.out.print(matriz[i][j] + " ");
            }
            System.out.println();
        }
    }
}

package parcial;

import java.util.Random;

public class Ejercicio1 {
    public static void main(String[] args) {
        // Ejercicio 1: Generar un arreglo de 13 números aleatorios (0–9) que representen un código EAN-13
        // Calcular el dígito de control y verificar si el código es válido

        Random aleatorio = new Random();
        int[] codigo = new int[13];

        // Generar los 13 dígitos aleatorios
        for (int i = 0; i < 13; i++) {
            codigo[i] = aleatorio.nextInt(10);
        }

        // Calcular dígito de control usando los primeros 12 dígitos
        int suma = 0;
        for (int i = 0; i < 12; i++) {
            if (i % 2 == 0) { // posición par (0,2,4...) multiplicar por 1
                suma += codigo[i] * 1;
            } else { // posición impar (1,3,5...) multiplicar por 3
                suma += codigo[i] * 3;
            }
        }

        // Encontrar múltiplo de 10 mayor o igual a la suma
        int multiplo10 = ((suma + 9) / 10) * 10;
        int digitoControl = multiplo10 - suma;
        if (digitoControl == 10) digitoControl = 0;

        // Comparar con el último dígito
        System.out.print("Código generado: ");
        for (int i = 0; i < 13; i++) System.out.print(codigo[i]);
        System.out.println("\nDígito calculado: " + digitoControl);
        System.out.println("Dígito en el código: " + codigo[12]);

        if (digitoControl == codigo[12]) {
            System.out.println("El código es válido.");
        } else {
            System.out.println("El código es inválido.");
        }
    }
}

package parcial;

import java.util.Random;

public class Ejercicio2 {
    public static void main(String[] args) {
        // Ejercicio 2: Generar una matriz rectangular con números aleatorios
        // Multiplicar por su identidad y sumar los números pares de la matriz resultante

        int filas = 3;
        int columnas = 3;
        int[][] matriz = new int[filas][columnas];
        Random aleatorio = new Random();

        // Rellenar matriz con números aleatorios
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                matriz[i][j] = aleatorio.nextInt(10);
            }
        }

        // Multiplicar por identidad (en realidad, la matriz queda igual)
        int[][] resultado = new int[filas][columnas];
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                resultado[i][j] = matriz[i][j]; // identidad no cambia valores
            }
        }

        // Sumar números pares de la matriz resultante
        int sumaPares = 0;
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                if (resultado[i][j] % 2 == 0) sumaPares += resultado[i][j];
            }
        }

        // Imprimir matriz y suma
        System.out.println("Matriz generada:");
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                System.out.print(matriz[i][j] + " ");
            }
            System.out.println();
        }
        System.out.println("Suma de números pares: " + sumaPares);
    }
}

package parcial;

public class Ejercicio3 {
    public static void main(String[] args) {
        // Ejercicio 3: Procesar líneas de números
        // Eliminar ceros, eliminar líneas llenas de ceros y sumar dígitos pares

        String[] lineas = {
            "120307",
            "0000",
            "00007900",
            "8708908",
            "503214007",
            "00005600",
            "43210670"
        };

        for (int i = 0; i < lineas.length; i++) {
            String linea = lineas[i];

            // Verificar si la línea es solo ceros
            if (linea.matches("0+")) {
                System.out.println("Línea eliminada (solo ceros): " + linea);
                continue;
            }

            // Eliminar ceros
            String sinCeros = linea.replace("0", "");

            // Sumar dígitos pares
            int sumaPares = 0;
            for (int j = 0; j < sinCeros.length(); j++) {
                int digito = Character.getNumericValue(sinCeros.charAt(j));
                if (digito % 2 == 0) sumaPares += digito;
            }

            // Mostrar resultados
            System.out.println("Línea original: " + linea);
            System.out.println("Sin ceros: " + sinCeros);
            System.out.println("Suma de pares: " + sumaPares);
            System.out.println("---------------------------");
        }
    }
}

package parcial;

import java.util.Scanner;

public class EjemploArreglo1 {
    public static void main(String[] args) {
        // Programa: Leer n números en un arreglo, calcular el promedio y encontrar el mayor

        Scanner entrada = new Scanner(System.in);

        System.out.print("Ingrese cantidad de números: ");
        int cantidad = entrada.nextInt();

        int[] numeros = new int[cantidad];

        // Leer números
        for (int i = 0; i < cantidad; i++) {
            System.out.print("Número " + (i+1) + ": ");
            numeros[i] = entrada.nextInt();
        }

        // Calcular promedio y mayor
        int suma = 0;
        int mayor = numeros[0];
        for (int i = 0; i < cantidad; i++) {
            suma += numeros[i];
            if (numeros[i] > mayor) mayor = numeros[i];
        }

        double promedio = (double) suma / cantidad;

        System.out.println("Promedio: " + promedio);
        System.out.println("Mayor: " + mayor);
    }
}

package parcial;

import java.util.Random;
import java.util.Scanner;

public class EjemploMatriz1 {
    public static void main(String[] args) {
        // Programa: Generar una matriz m x n con números aleatorios
        // Calcular la suma de cada fila y de cada columna

        Scanner entrada = new Scanner(System.in);
        Random aleatorio = new Random();

        System.out.print("Ingrese número de filas: ");
        int filas = entrada.nextInt();
        System.out.print("Ingrese número de columnas: ");
        int columnas = entrada.nextInt();

        int[][] matriz = new int[filas][columnas];

        // Rellenar matriz con números aleatorios entre 0 y 9
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                matriz[i][j] = aleatorio.nextInt(10);
            }
        }

        // Imprimir matriz
        System.out.println("Matriz generada:");
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                System.out.print(matriz[i][j] + " ");
            }
            System.out.println();
        }

        // Suma de cada fila
        for (int i = 0; i < filas; i++) {
            int sumaFila = 0;
            for (int j = 0; j < columnas; j++) {
                sumaFila += matriz[i][j];
            }
            System.out.println("Suma de fila " + i + ": " + sumaFila);
        }

        // Suma de cada columna
        for (int j = 0; j < columnas; j++) {
            int sumaColumna = 0;
            for (int i = 0; i < filas; i++) {
                sumaColumna += matriz[i][j];
            }
            System.out.println("Suma de columna " + j + ": " + sumaColumna);
        }
    }
}

package parcial;

import java.util.ArrayList;
import java.util.Scanner;

public class EjemploArrayList1 {
    public static void main(String[] args) {
        // Programa: Crear un ArrayList de enteros
        // Insertar números, eliminar uno y mostrar el resultado

        Scanner entrada = new Scanner(System.in);
        ArrayList<Integer> listaNumeros = new ArrayList<>();

        // Insertar números
        System.out.print("Ingrese cantidad de números: ");
        int cantidad = entrada.nextInt();
        for (int i = 0; i < cantidad; i++) {
            System.out.print("Número " + (i+1) + ": ");
            listaNumeros.add(entrada.nextInt());
        }

        System.out.println("Lista inicial: " + listaNumeros);

        // Eliminar un número
        System.out.print("Ingrese número a eliminar: ");
        int eliminar = entrada.nextInt();
        listaNumeros.remove((Integer) eliminar);

        System.out.println("Lista después de eliminar: " + listaNumeros);
    }
}

package parcial;

import java.util.Random;
import java.util.Scanner;

public class EjemploMatriz2 {
    public static void main(String[] args) {
        // Programa: Generar una matriz m x n y calcular su transpuesta

        Scanner entrada = new Scanner(System.in);
        Random aleatorio = new Random();

        System.out.print("Ingrese número de filas: ");
        int filas = entrada.nextInt();
        System.out.print("Ingrese número de columnas: ");
        int columnas = entrada.nextInt();

        int[][] matriz = new int[filas][columnas];
        int[][] transpuesta = new int[columnas][filas];

        // Rellenar matriz con números aleatorios
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                matriz[i][j] = aleatorio.nextInt(10);
            }
        }

        // Calcular transpuesta
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                transpuesta[j][i] = matriz[i][j];
            }
        }

        // Imprimir matriz original
        System.out.println("Matriz original:");
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                System.out.print(matriz[i][j] + " ");
            }
            System.out.println();
        }

        // Imprimir transpuesta
        System.out.println("Matriz transpuesta:");
        for (int i = 0; i < columnas; i++) {
            for (int j = 0; j < filas; j++) {
                System.out.print(transpuesta[i][j] + " ");
            }
            System.out.println();
        }
    }
}

package parcial;

import java.util.Scanner;

public class EjemploArreglo2 {
    public static void main(String[] args) {
        // Programa: Leer un arreglo de n números y mostrarlo en orden inverso

        Scanner entrada = new Scanner(System.in);

        System.out.print("Ingrese cantidad de números: ");
        int cantidad = entrada.nextInt();

        int[] numeros = new int[cantidad];

        // Leer números
        for (int i = 0; i < cantidad; i++) {
            System.out.print("Número " + (i+1) + ": ");
            numeros[i] = entrada.nextInt();
        }

        // Mostrar en orden inverso
        System.out.println("Arreglo en orden inverso:");
        for (int i = cantidad - 1; i >= 0; i--) {
            System.out.print(numeros[i] + " ");
        }
    }
}

package parcial;

import java.util.Scanner;

public class EjemploArreglo3 {
    public static void main(String[] args) {
        // Programa: Leer un arreglo de n números y calcular el factorial de cada uno

        Scanner entrada = new Scanner(System.in);

        System.out.print("Ingrese cantidad de números: ");
        int cantidad = entrada.nextInt();

        int[] numeros = new int[cantidad];
        long[] factoriales = new long[cantidad];

        // Leer números
        for (int i = 0; i < cantidad; i++) {
            System.out.print("Número " + (i+1) + ": ");
            numeros[i] = entrada.nextInt();
        }

        // Calcular factorial de cada número
        for (int i = 0; i < cantidad; i++) {
            long factorial = 1;
            for (int j = 2; j <= numeros[i]; j++) {
                factorial *= j;
            }
            factoriales[i] = factorial;
        }

        // Imprimir resultados
        System.out.println("Números originales:");
        for (int numero : numeros) System.out.print(numero + " ");
        System.out.println("\nFactoriales:");
        for (long f : factoriales) System.out.print(f + " ");
    }
}

package parcial;

import java.util.Random;
import java.util.Scanner;

public class EjemploMatriz3 {
    public static void main(String[] args) {
        // Programa: Generar una matriz n x n y calcular la suma de la diagonal principal

        Scanner entrada = new Scanner(System.in);
        Random aleatorio = new Random();

        System.out.print("Ingrese tamaño de la matriz (n): ");
        int n = entrada.nextInt();

        int[][] matriz = new int[n][n];

        // Rellenar matriz con números aleatorios
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                matriz[i][j] = aleatorio.nextInt(10);
            }
        }

        // Calcular suma de diagonal principal
        int sumaDiagonal = 0;
        for (int i = 0; i < n; i++) {
            sumaDiagonal += matriz[i][i];
        }

        // Imprimir matriz y suma
        System.out.println("Matriz generada:");
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                System.out.print(matriz[i][j] + " ");
            }
            System.out.println();
        }
        System.out.println("Suma de diagonal principal: " + sumaDiagonal);
    }
}

package parcial;

import java.util.ArrayList;
import java.util.Random;

public class EjemploArrayList2 {
    public static void main(String[] args) {
        // Programa: Generar un ArrayList con 20 números aleatorios entre 1 y 5
        // Contar cuántas veces aparece cada número

        ArrayList<Integer> listaNumeros = new ArrayList<>();
        Random aleatorio = new Random();

        // Generar números
        for (int i = 0; i < 20; i++) {
            listaNumeros.add(aleatorio.nextInt(5) + 1);
        }

        System.out.println("Lista generada: " + listaNumeros);

        // Contar frecuencia
        for (int i = 1; i <= 5; i++) {
            int contador = 0;
            for (int j = 0; j < listaNumeros.size(); j++) {
                if (listaNumeros.get(j) == i) contador++;
            }
            System.out.println("Número " + i + " aparece " + contador + " veces");
        }
    }
}

package parcial;

import java.util.Random;
import java.util.Scanner;

public class EjemploMatriz4 {
    public static void main(String[] args) {
        // Programa: Generar una matriz n x n y verificar si es simétrica

        Scanner entrada = new Scanner(System.in);
        Random aleatorio = new Random();

        System.out.print("Ingrese tamaño de la matriz (n): ");
        int n = entrada.nextInt();

        int[][] matriz = new int[n][n];

        // Rellenar matriz con números aleatorios
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                matriz[i][j] = aleatorio.nextInt(10);
            }
        }

        // Verificar simetría
        boolean simetrica = true;
        for (int i = 0; i < n && simetrica; i++) {
            for (int j = 0; j < n; j++) {
                if (matriz[i][j] != matriz[j][i]) {
                    simetrica = false;
                    break;
                }
            }
        }

        // Imprimir matriz y resultado
        System.out.println("Matriz generada:");
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                System.out.print(matriz[i][j] + " ");
            }
            System.out.println();
        }
        System.out.println("¿Es simétrica?: " + simetrica);
    }
}

package parcial;

import java.util.ArrayList;
import java.util.Random;

public class EjemploArrayList3 {
    public static void main(String[] args) {
        // Programa: Generar un ArrayList con 15 números aleatorios entre 1 y 50
        // Separar en dos listas: pares e impares

        ArrayList<Integer> listaNumeros = new ArrayList<>();
        ArrayList<Integer> listaPares = new ArrayList<>();
        ArrayList<Integer> listaImpares = new ArrayList<>();
        Random aleatorio = new Random();

        // Generar números
        for (int i = 0; i < 15; i++) {
            listaNumeros.add(aleatorio.nextInt(50) + 1);
        }

        // Separar pares e impares
        for (int i = 0; i < listaNumeros.size(); i++) {
            int numero = listaNumeros.get(i);
            if (numero % 2 == 0) listaPares.add(numero);
            else listaImpares.add(numero);
        }

        // Imprimir resultados
        System.out.println("Lista original: " + listaNumeros);
        System.out.println("Lista pares: " + listaPares);
        System.out.println("Lista impares: " + listaImpares);
    }
}

package parcial;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;

public class EjemploArrayList4 {
    public static void main(String[] args) {
        // Programa: Leer números en un ArrayList y ordenarlos de menor a mayor

        Scanner entrada = new Scanner(System.in);
        ArrayList<Integer> listaNumeros = new ArrayList<>();

        System.out.print("Ingrese cantidad de números: ");
        int cantidad = entrada.nextInt();

        for (int i = 0; i < cantidad; i++) {
            System.out.print("Número " + (i+1) + ": ");
            listaNumeros.add(entrada.nextInt());
        }

        System.out.println("Lista original: " + listaNumeros);

        // Ordenar lista
        Collections.sort(listaNumeros);
        System.out.println("Lista ordenada: " + listaNumeros);
    }
}

package parcial;

import java.util.Random;
import java.util.Scanner;

public class EjemploMatriz6 {
    public static void main(String[] args) {
        // Programa: Generar una matriz m x n y luego intercambiar la primera columna con la última

        Scanner entrada = new Scanner(System.in);
        Random aleatorio = new Random();

        System.out.print("Ingrese número de filas: ");
        int filas = entrada.nextInt();
        System.out.print("Ingrese número de columnas: ");
        int columnas = entrada.nextInt();

        int[][] matriz = new int[filas][columnas];

        // Rellenar matriz
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                matriz[i][j] = aleatorio.nextInt(100);
            }
        }

        // Intercambiar primera y última columna
        for (int i = 0; i < filas; i++) {
            int temp = matriz[i][0];
            matriz[i][0] = matriz[i][columnas - 1];
            matriz[i][columnas - 1] = temp;
        }

        // Imprimir matriz resultante
        System.out.println("Matriz después de intercambiar columnas:");
        for (int i = 0; i < filas; i++) {
            for (int j = 0; j < columnas; j++) {
                System.out.print(matriz[i][j] + " ");
            }
            System.out.println();
        }
    }
}

package parcial;

import java.util.ArrayList;
import java.util.Scanner;

public class EjemploArrayList5 {
    public static void main(String[] args) {
        // Programa: Leer números en un ArrayList y calcular la suma y el promedio

        Scanner entrada = new Scanner(System.in);
        ArrayList<Integer> listaNumeros = new ArrayList<>();

        System.out.print("Ingrese cantidad de números: ");
        int cantidad = entrada.nextInt();

        for (int i = 0; i < cantidad; i++) {
            System.out.print("Número " + (i+1) + ": ");
            listaNumeros.add(entrada.nextInt());
        }

        // Calcular suma y promedio
        int suma = 0;
        for (int i = 0; i < listaNumeros.size(); i++) {
            suma += listaNumeros.get(i);
        }
        double promedio = (double) suma / listaNumeros.size();

        System.out.println("Lista: " + listaNumeros);
        System.out.println("Suma: " + suma);
        System.out.println("Promedio: " + promedio);
    }
}







