# HW1-
Punto 2 de la tare HW1










        public static void main(String[] args) {
        System.out.println("Numeros Gaussianos:");
        for (int i = 0; i < 80; i++) {
            int numeroa = (int) (Math.random() * (50 - (-50) + 1) + (-50));
            int numerob = (int) (Math.random() * (50 - (-50) + 1) + (-50));
            int posiblePrimo = (int) ((int) Math.pow(numeroa, 2) + Math.pow(numerob, 2));

            if (revisaSiEsPrimo(Math.abs(numeroa)) == 1) {
                if (revisaCongruencia(Math.abs(numeroa)) == 1) {
                    System.out.println(numeroa);
                }
            }

            if (revisaSiEsPrimo(posiblePrimo) == 1) {
                if (numerob < 0) {
                    System.out.println(numeroa + "" + numerob + "i");
                } else {
                    System.out.println(numeroa + "+" + numerob + "i");
                }

            }
        }
    }

    public static int revisaSiEsPrimo(int numero) {

        int contador = 0;
        for (int i = 1; i <= numero; i++) {
            int numeronuevo = numero % i;
            if (numeronuevo == 0) {
                contador++;
            }
        }
        if (contador == 2) {
            return 1;
        } else {
            return 0;
        }
    }

    public static int revisaCongruencia(int numero) {
        int numeroRevisar = (Math.abs(numero) - 3) % 4;

        if (numeroRevisar == 0) {

            return 1;
        } else {
            return 0;
        }

    }
