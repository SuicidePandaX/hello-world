# Modulos Informatica JAVA
Ejercicio numero 13 modulos UNLP informatica

/*13. Realizar un módulo que reciba como parámetro el radio de un círculo y retorne su diámetro y su perímetro.
a. Utilizando el módulo anterior, realizar un programa que analice información de planetas obtenidas
del Telescopio Espacial Kepler. De cada planeta se lee nombre, su radio (medido en kilómetros) y la
distancia (medida en años luz) a la Tierra. La lectura finaliza al leer un planeta con radio 0, que no
debe procesarse. Informar:
- Nombre y distancia de los planetas que poseen un diámetro menor o igual que el de la Tierra
(12.700 km) y mayor o igual que el de Marte (6.780 km).
- Cantidad de planetas con un perímetro superior al del planeta Júpiter (439.264 km)*/
package trece;

import java.util.Scanner;

public class TreceMain {

    Scanner in = new Scanner(System.in);
    static int Radio, Distancia, Diametro;
    static int cant;
    static String Nombre;
    static double Perimetro;

    public static void Trece(String nombre, int distancia, int radio) {
        Nombre = nombre;
        Radio = radio;
        Distancia = distancia;
    }

    public static void Calculos() {
        Diametro = 2 * Radio;
        Perimetro = 2 * Math.PI * Radio;
        if (Diametro <= 12700 && Diametro >= 6780) {
            System.out.println("El nombre del planeta con diametro menor que la tierra y mayor"
                               +" que marte es: >> " + Nombre + " Distancia: " + Distancia + "Km");
        }
        if (Perimetro > 439264) {
            cant = cant + 1;
        }
        System.out.println("La cantidad de planetas con perimetro superior a jupiter es: " + cant);
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int radio = -1; //kilometros
        int distancia; //años luz
        String nombre;

        while (radio != 0) {
            System.out.print("Ingrese nombre del planeta: ");
            nombre = in.nextLine();
            in.nextLine();
            System.out.print("Ingrese distancia: ");
            distancia = in.nextInt();
            System.out.print("Ingrese radio: ");
            radio = in.nextInt();

            Trece(nombre, distancia, radio);

            Calculos();
        }
    }
}
