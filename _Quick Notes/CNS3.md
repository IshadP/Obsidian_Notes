```Java
import java.util.Arrays;

public class Main { 

    static void MakeKey(String k, int[][] key, int len) {
        int x = 0;
        System.out.println("Characters from key string converted to numbers for matrix (A=0, B=1, etc.):");
        for (int i = 0; i < len; i++) {
            for (int j = 0; j < len; j++) {
                key[i][j] = (k.charAt(x)) % 65;
                System.out.print(key[i][j] + " ");
                x++;
            }
            System.out.println("");
        }

        System.out.println("--- End Key Matrix Construction ---");

    }

  

    static void Encrypt(int[][] text, int[][] key, int[][] cipher, int len) {

        for (int i = 0; i < len; i++) {

            cipher[i][0] = 0;

        }

  

        for (int i = 0; i < len; i++) {

            for (int j = 0; j < 1; j++) {

                for (int a = 0; a < len; a++) {

                    cipher[i][j] += key[i][a] * text[a][j];

                }

                cipher[i][j] = cipher[i][j] % 26;

                if (cipher[i][j] < 0) {

                    cipher[i][j] += 26;

                }

            }

        }

    }

  

    static void Decrypt(int[][] cipher, int[][] key, int[][] plain, int len) {

        System.out.println("\n--- Decryption Process ---");

        int[][] inverseKey = getInverseKey(key, len);

  

        if (inverseKey == null) {

            System.out.println("Error: Key matrix is not invertible. Cannot decrypt.");

            return;

        }

        System.out.println("Inverse Key Matrix (mod 26):");

        for (int i = 0; i < len; i++) {

            for (int j = 0; j < len; j++) {

                System.out.print(inverseKey[i][j] + " ");

            }

            System.out.println("");

        }

        System.out.println("--- End Inverse Key Matrix ---");

  

        for (int i = 0; i < len; i++) {

            plain[i][0] = 0;

        }

  

        for (int i = 0; i < len; i++) {

            for (int j = 0; j < 1; j++) {

                for (int a = 0; a < len; a++) {

                    plain[i][j] += inverseKey[i][a] * cipher[a][j];

                }

                plain[i][j] = plain[i][j] % 26;

                if (plain[i][j] < 0) {

                    plain[i][j] += 26;

                }

            }

        }

    }

  

    static int[][] getInverseKey(int[][] key, int n) {

        double rawDet = determinant(key, n);

        System.out.println("Calculated determinant (raw): " + rawDet);

  

        int det = (int) rawDet;

        det = det % 26;

        if (det < 0) {

            det += 26;

        }

        System.out.println("Calculated determinant (mod 26): " + det);

  

        int detInverse = modInverse(det, 26);

        System.out.println("Modular Inverse of determinant (mod 26): " + detInverse);

  
  

        if (detInverse == -1) {

            System.out.println("Determinant " + det + " has no modular inverse (mod 26).");

            return null;

        }

  

        int[][] adj = adjoint(key, n);

        int[][] inverseKey = new int[n][n];

  

        for (int i = 0; i < n; i++) {

            for (int j = 0; j < n; j++) {

                inverseKey[i][j] = (adj[i][j] * detInverse) % 26;

                if (inverseKey[i][j] < 0) {

                    inverseKey[i][j] += 26;

                }

            }

        }

        return inverseKey;

    }

  

    static double determinant(int[][] matrix, int n) {

        double det = 0;

  

        if (n == 1) {

            return matrix[0][0];

        }

  

        if (n == 2) {

            return matrix[0][0] * matrix[1][1] - matrix[0][1] * matrix[1][0];

        }

  

        int[][] temp = new int[n][n];

  

        for (int p = 0; p < n; p++) {

            int i = 0, j = 0;

            for (int row = 1; row < n; row++) {

                for (int col = 0; col < n; col++) {

                    if (col == p) {

                        continue;

                    }

                    temp[i][j++] = matrix[row][col];

                    if (j == n - 1) {

                        j = 0;

                        i++;

                    }

                }

            }

            det += matrix[0][p] * Math.pow(-1, p) * determinant(temp, n - 1);

        }

        return det;

    }

  

    static int modInverse(int a, int m) {

        a = a % m;

        for (int x = 1; x < m; x++) {

            if ((a * x) % m == 1) {

                return x;

            }

        }

        return -1;

    }

  

    static int[][] adjoint(int[][] matrix, int n) {

        int[][] adj = new int[n][n];

  

        if (n == 1) {

            adj[0][0] = 1;

        }

  

        int[][] temp = new int[n][n];

  

        for (int i = 0; i < n; i++) {

            for (int j = 0; j < n; j++) {

                getMinor(matrix, temp, i, j, n);

  

                int sign = ((i + j) % 2 == 0) ? 1 : -1;

                int cofactor = (int) (sign * determinant(temp, n - 1));

  

                adj[j][i] = cofactor; // Transpose for adjoint

            }

        }

        return adj;

    }

  

    static void getMinor(int[][] matrix, int[][] temp, int p, int q, int n) {

        int i = 0, j = 0;

        for (int row = 0; row < n; row++) {

            for (int col = 0; col < n; col++) {

                if (row != p && col != q) {

                    temp[i][j++] = matrix[row][col];

                    if (j == n - 1) {

                        j = 0;

                        i++;

                    }

                }

            }

        }

    }

  

    static void Hill(String str, String k, int len) {

        int[][] key = new int[len][len];

        System.out.println("Key Matrix (mod 26):");

        MakeKey(k, key, len);

  

        int[][] text = new int[len][1];

        for (int i = 0; i < len; i++) {

            text[i][0] = (str.charAt(i)) % 65;

        }

  

        int[][] cipher = new int[len][1];

        Encrypt(text, key, cipher, len);

  

        String cip = "";

        for (int i = 0; i < len; i++) {

            cip += (char)(cipher[i][0] + 65);

        }
        System.out.println("CiperText: " + cip);
        System.out.println("---------------------------");  

        int[][] plain = new int[len][1];

        Decrypt(cipher, key, plain, len);

        String pl = "";
        for (int i = 0; i < len; i++) {
            int charValue = plain[i][0];
            if (charValue < 0) {
                charValue += 26;
            }
            pl += (char)(charValue + 65);
        }
        System.out.println("PlainText: " + pl);
    }

    public static void main(String[] args) {

        System.out.println("HillCipher by Ishad Pande, B2, 25");

        System.out.println("---------------------------------");

        String str = "WOAH";

        int len = 4;

  

        System.out.println("Plain text: " + str);

        System.out.println("Key: " + key);

        System.out.println("Length: " + len);

        System.out.println("Using Hill Cipher");

  

        Hill(str, key, len);

    }

}
```

![[image-20.png]]
