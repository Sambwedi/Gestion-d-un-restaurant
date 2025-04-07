# Gestion-d-un-restaurant
Gestion d'un restaurant en java 
mport java.util.Scanner;

public class restaurant {

    public static void afficherMenu() {
        System.out.println("MENU DU RESTAURANT");
        System.out.println("1. Pizza - 30000FC");
        System.out.println("2. Burger - 25000FC");
        System.out.println("3. Salade - 15000FC");
        System.out.println("4. Poisson - 7500FC");
        System.out.println("5. Quitter - le programme");
    }

    public static int obtenirPrix(int choix) {
        switch (choix) {
            case 1: return 30000;
            case 2: return 25000;
            case 3: return 15000;
            case 4: return 7500;
            default: return 0;
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int choix;
        int total = 0;

        do {
            afficherMenu();
            System.out.print("\nFaites votre choix (1-5) : ");
            choix = scanner.nextInt();

            if (choix >= 1 && choix <= 4) {
                int prix = obtenirPrix(choix);
                total += prix;
                System.out.println("Article ajouté ! Total actuel : " + total + " FC");
            } else if (choix == 5) {
                System.out.println("Merci pour votre visite !");
                System.out.println("Total à payer : " + total + " FC");
            } else {
                System.out.println("Choix invalide. Veuillez réessayer.");
            }

        } while (choix != 5);

        scanner.close();
    }
}
