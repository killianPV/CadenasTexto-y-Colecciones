# CadenasTexto-y-Colecciones


* EX_01

import java.util.Scanner;

public class EX_01 {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.println("Introduce un nombre y sus apellidos: ");
        String nom = scan.nextLine();
        
        String[] palabras = nom.split(" ");
        
        if (palabras.length >= 2) {
            String ape = palabras[palabras.length - 1];
            
            StringBuilder iniciales = new StringBuilder();
            
            for (int i = 0; i < palabras.length - 1; i++) {
                String palabra = palabras[i];
                if (!palabra.isEmpty()) {
                    iniciales.append(palabra.charAt(0)).append(". ");
                }
            }
            

            iniciales.deleteCharAt(iniciales.length() - 1);

            System.out.println(ape + ", " + iniciales);
            
        } else {
            System.out.println("Error: Introduzca un nombre y un apellido como mínimo");
        }
        
        scan.close();
    }
}

*EX_02

import java.util.Scanner;

public class EX_02 {
    
    public static void main(String[] args) {
  
        Scanner scan = new Scanner(System.in);

        System.out.println("Introduzca la primera cadena: ");
        String string1 = scan.nextLine();

        System.out.println("Introduzca la segunda cadena: ");
        String string2 = scan.nextLine();


        String result = Combinacion(string1, string2);

        System.out.println("Resultado: " + result);


        scan.close();
    }

    public static String Combinacion(String string1, String string2) {

        char[] chars1 = string1.toCharArray();
        char[] chars2 = string2.toCharArray();

        StringBuilder resultado = new StringBuilder();


        int length = Math.max(chars1.length, chars2.length);

        for (int i = 0; i < length; i++) {
            if (i < chars1.length && chars1[i] != ' ') {
                resultado.append(chars1[i]);
            }



            if (i < chars2.length && chars2[i] != ' ') {
                resultado.append(chars2[i]);
            }
        }



        return resultado.toString();
    }
}

*EX_03

import java.util.Scanner;

public class EX_03 {
    public static void main(String[] args) {

        Scanner scan = new Scanner(System.in);
        System.out.println("Dime una frase: ");
        String frase = scan.nextLine();

        System.out.println("Dime un carácter para saber si coincide con la frase anterior: ");
        char buscar = scan.nextLine().charAt(0);

        int[] posiciones = encontrar(frase, buscar);


        if (posiciones.length > 0) {
            System.out.print("El carácter '" + buscar + "' se encuentra en esta frase: ");
            for (int i = 0; i < posiciones.length; i++) {
                System.out.print(posiciones[i]);
                if (i < posiciones.length - 1) {

                    System.out.print(", ");
                }
            }

            System.out.println();
        } else {

            System.out.println("El carácter '" + buscar + "' no se encuentra en esta frase.");
        }

        scan.close();
    }

    public static int[] encontrar(String frase, char buscar) {
        int cont = 0;
        for (int i = 0; i < frase.length(); i++) {
            if (frase.charAt(i) == buscar) {

                cont++;
            }
        }

        int[] pos = new int[cont];


        int j = 0;
        for (int i = 0; i < frase.length(); i++) {
            if (frase.charAt(i) == buscar) {
                
                pos[j] = i;
                j++;
            }
        }

        return pos;
    }
}

*EX_04

import java.util.Scanner;

public class EX_04 {
    public static void main(String[] args) {

        Scanner scan = new Scanner(System.in);

        System.out.println("Dime una frase: ");
        String frase = scan.nextLine();

        System.out.println("Dime un carácter: ");
        char buscar = scan.nextLine().charAt(0);


        Posiciones(frase, buscar);

        scan.close();
    }

    public static void Posiciones(String frase, char buscar) {
        int seleccion = frase.indexOf(buscar);

        if (seleccion == -1) {
            System.out.println("El carácter '" + buscar + "' no se encuentra en esta frase.");
        } else {
            System.out.print("El carácter '" + buscar + "' se encuentra estas posiciones: ");
            while (seleccion != -1) {

                System.out.print(seleccion + " ");
                
                seleccion = frase.indexOf(buscar, seleccion + 1);
            }
            System.out.println();
        }
    }
}


*EX_05

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class EX_05 {
    public static void main(String[] args) {
        String contraseña = "Ejemplo#123";

        if (esContrasenaFuerte(contraseña)) {
            System.out.println("La contraseña es fuerte.");
        } else {
            System.out.println("La contraseña es débil.");
        }
    }

    private static boolean esContrasenaFuerte(String contraseña) {
        if (contraseña.length() < 8) {
            return false;
        }
        // Introduce tu contraseña:
        Pattern pattern = Pattern.compile("Contraseña fasil");

        
        Matcher matcher = pattern.matcher(contraseña);

        return matcher.find();
    }
}


*EX_06

public class EX_06 {
    public static void main(String[] args) {
        
        String texto = "Me gusta cuando metalGreymon digievolucionó a WarGreymon";


        for (int i = 0; i < texto.length(); i++) {
            char c = texto.charAt(i);
            int ASCII = (int) c;


            System.out.println("ASCII: " + ASCII + " es igual a: " + c);
        }
    }
}

*EX_07

import java.util.ArrayList;
import java.util.Iterator;

public class EX_07 {
    public static void main(String[] args) {
        ArrayList<String> orden = new ArrayList<>();

        orden.add("Nº 1");
        orden.add("Nº 2");
        orden.add("Nº 3");
        orden.add("Nº 4");
        orden.add("Nº 5");

        Iterator<String> iterator = orden.iterator();


        while (iterator.hasNext()) {
            String string = iterator.next();
            System.out.println(string);
        }
    }
}

*EX_08

import java.util.ArrayList;

public class EX_08 {
    public static void main(String[] args) {

        ArrayList<String> orden = new ArrayList<>();

        orden.add("hola");
        orden.add("adiós");
        orden.add("33");
        orden.add("Manu el Fustas");
        

        orden.forEach(elem -> {
            System.out.println(elem);
        });
    }
}

*EX_09

import java.util.ArrayList;
import java.util.List;

public class EX_09 {
    public static void main(String[] args) {

        List<String> orden = new ArrayList<>();

        orden.add("Gormiti de Aire");
        orden.add("Gormiti de Agua");
        orden.add("Gormiti de Roca");
        orden.add("Gormiti de Fuego");
        


        String[] string = new String[orden.size()];

        string = orden.toArray(string);

        for (String elem : string) {

            System.out.println(elem);
        }
    }
}

*EX_10

import java.util.HashSet;
import java.util.Iterator;

public class EX_10 {

    public static void main(String[] args) {

        HashSet<String> hash = new HashSet<>();

        hash.add("Lakasito");
        hash.add("Phoskitos");
        hash.add("Principe");
        hash.add("Chips Ahoy");
       


        System.out.println("HashSet:");
        Iterator<String> it = hash.iterator();

        while (it.hasNext()) {

            String string = it.next();
            System.out.println(string);
        }
    }
}

*EX_11

import java.util.*;

public class EX_11 {
    public static void main(String[] args) {
        HashMap<String, Integer> hash = new HashMap<>();
        hash.put("1", 5);
        hash.put("2", 4);
        hash.put("3", 3);
        hash.put("4", 2);
        hash.put("5", 1);

        System.out.println("HashMap original: " + hash);

        HashMap<String, Integer> hashMapOrdenado = orden(hash);

        System.out.println("Orden por valor(HashMap): " + hashMapOrdenado);
    }

    // ORDENAR POR VALOR EN HASHMAP

    public static HashMap<String, Integer> orden(HashMap<String, Integer> hashMap) {
        List<Map.Entry<String, Integer>> listaEntradas = new ArrayList<>(hashMap.entrySet());

        Collections.sort(listaEntradas, Map.Entry.comparingByValue());

        HashMap<String, Integer> resultado = new LinkedHashMap<>();
        for (Map.Entry<String, Integer> entrada : listaEntradas) {
            resultado.put(entrada.getKey(), entrada.getValue());
        }

        return resultado;
    }
}







