
//Problema 1
import java.util.ArrayList;
import java.util.List;

public class lab3 {
    public static void main(String[] args) {
        String[] a = { "java", "test", "university" };
        String[] b = { "car", "university", "plane" };

        List<String> elementeComune = new ArrayList<>();

        for (String elementA : a) {
            for (String elementB : b) {
                if (elementA.equals(elementB)) {
                    elementeComune.add(elementA);
                    break;
                }
            }
        }

        if (!elementeComune.isEmpty()) {
            System.out.println("Elemente comune: " + elementeComune);
        } else {
            System.out.println("Nu există elemente comune în cele două șiruri.");
        }
    }
}

// Problema 2
public class Main {
    public static boolean isPrime(int num) {
        if (num <= 1) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }

    public static void main(String[] args) {
        int[] numbers = { 2, 3, 6, 7, 11, 12, 13, 17 };

        System.out.println("Numere prime din șirul dat:");
        for (int num : numbers) {
            if (isPrime(num)) {
                System.out.println(num);
            }
        }
    }
}
// Problema 3
import java.util.Scanner;

public class Fibonacci {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Introduceți un număr N pentru a afișa șirul Fibonacci până la N: ");
        int n = scanner.nextInt();

        int prev = 0;
        int current = 1;

        System.out.println("Șirul Fibonacci până la " + n + " este:");

        while (prev <= n) {
            System.out.print(prev + " ");

            int next = prev + current;
            prev = current;
            current = next;
        }

        scanner.close();
    }
}
// Problema 4
import java.util.Scanner;

public class PalindromeChecker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Introduceți un cuvânt pentru a verifica dacă este palindrom: ");
        String cuvant = scanner.nextLine();

        if (isPalindrome(cuvant)) {
            System.out.println(cuvant + " este un cuvânt palindrom.");
        } else {
            System.out.println(cuvant + " nu este un cuvânt palindrom.");
        }

        scanner.close();
    }

    public static boolean isPalindrome(String cuvant) {

        cuvant = cuvant.replaceAll("\\s", "").toLowerCase();

        int lungime = cuvant.length();

        for (int i = 0; i < lungime / 2; i++) {
            if (cuvant.charAt(i) != cuvant.charAt(lungime - 1 - i)) {
                return false;
            }
        }

        return true;
    }
}
