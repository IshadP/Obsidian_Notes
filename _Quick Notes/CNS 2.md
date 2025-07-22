```java
import java.util.*;

public class PlayfairCipher {
    private char[][] matrix = new char[5][5];
    private Map<Character, int[]> charPosMap = new HashMap<>();

    public PlayfairCipher(String key) {
        generateMatrix(key);
    }

    // Generate 5x5 matrix
    private void generateMatrix(String key) {
        StringBuilder sb = new StringBuilder();
        Set<Character> seen = new LinkedHashSet<>();

        key = key.toLowerCase().replaceAll("[^a-z]", "").replace("j", "i");

        for (char c : key.toCharArray()) {
            seen.add(c);
        }

        for (char c = 'a'; c <= 'z'; c++) {
            if (c == 'j') continue;
            seen.add(c);
        }

        Iterator<Character> it = seen.iterator();
        for (int i = 0; i < 5; i++) {
            for (int j = 0; j < 5; j++) {
                char ch = it.next();
                matrix[i][j] = ch;
                charPosMap.put(ch, new int[]{i, j});
            }
        }
    }

    // Prepare input text
    private String prepareText(String text, boolean encrypting) {
        text = text.toLowerCase().replaceAll("[^a-z]", "").replace("j", "i");

        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < text.length(); i++) {
            char first = text.charAt(i);
            char second = 'x';

            if (i + 1 < text.length()) {
                second = text.charAt(i + 1);
                if (first == second) {
                    second = 'x';
                } else {
                    i++;
                }
            }

            sb.append(first).append(second);
        }

        if (sb.length() % 2 != 0) sb.append('x');
        return sb.toString();
    }

    // Encrypt
    public String encrypt(String text) {
        text = prepareText(text, true);
        StringBuilder sb = new StringBuilder();

        for (int i = 0; i < text.length(); i += 2) {
            char a = text.charAt(i);
            char b = text.charAt(i + 1);
            int[] posA = charPosMap.get(a);
            int[] posB = charPosMap.get(b);

            if (posA[0] == posB[0]) {
                sb.append(matrix[posA[0]][(posA[1] + 1) % 5]);
                sb.append(matrix[posB[0]][(posB[1] + 1) % 5]);
            } else if (posA[1] == posB[1]) {
                sb.append(matrix[(posA[0] + 1) % 5][posA[1]]);
                sb.append(matrix[(posB[0] + 1) % 5][posB[1]]);
            } else {
                sb.append(matrix[posA[0]][posB[1]]);
                sb.append(matrix[posB[0]][posA[1]]);
            }
        }
        return sb.toString();
    }

    // Decrypt
    public String decrypt(String text) {
        text = text.toLowerCase().replaceAll("[^a-z]", "");
        StringBuilder sb = new StringBuilder();

        for (int i = 0; i < text.length(); i += 2) {
            char a = text.charAt(i);
            char b = text.charAt(i + 1);
            int[] posA = charPosMap.get(a);
            int[] posB = charPosMap.get(b);

            if (posA[0] == posB[0]) {
                sb.append(matrix[posA[0]][(posA[1] + 4) % 5]);
                sb.append(matrix[posB[0]][(posB[1] + 4) % 5]);
            } else if (posA[1] == posB[1]) {
                sb.append(matrix[(posA[0] + 4) % 5][posA[1]]);
                sb.append(matrix[(posB[0] + 4) % 5][posB[1]]);
            } else {
                sb.append(matrix[posA[0]][posB[1]]);
                sb.append(matrix[posB[0]][posA[1]]);
            }
        }
        return sb.toString();
    }

    // Print Matrix (Optional)
    public void printMatrix() {
        for (char[] row : matrix) {
            for (char ch : row) {
                System.out.print(ch + " ");
            }
            System.out.println();
        }
    }

    // Main method
    public static void main(String[] args) {
        String key = "Monarchy";
        String plainText = "Hello World";

        PlayfairCipher cipher = new PlayfairCipher(key);

        System.out.println("=== Playfair Cipher ===");
        System.out.println("Key: " + key);
        System.out.println("Plain Text: " + plainText);

        String encrypted = cipher.encrypt(plainText);
        System.out.println("Encrypted: " + encrypted);

        String decrypted = cipher.decrypt(encrypted);
        System.out.println("Decrypted: " + decrypted);

        System.out.println("\nPhrase: Ishad Pande 25");
    }
}

```

Output:
![[image-19.png]]