```java
import javax.crypto.Cipher;

import javax.crypto.KeyGenerator;

import javax.crypto.SecretKey;

import javax.crypto.spec.IvParameterSpec;

import java.security.SecureRandom;

import java.util.Base64;

public class supp {

  

public static SecretKey generateDESKey() throws Exception {

KeyGenerator kg = KeyGenerator.getInstance("DES");

kg.init(56); // DES key size

return kg.generateKey();

}

  

public static String encrypt(String plaintext, SecretKey key) throws Exception {

Cipher cipher = Cipher.getInstance("DES/CBC/PKCS5Padding");

byte[] iv = new byte[8];

new SecureRandom().nextBytes(iv);

IvParameterSpec ivSpec = new IvParameterSpec(iv);

cipher.init(Cipher.ENCRYPT_MODE, key, ivSpec);

byte[] ciphertext = cipher.doFinal(plaintext.getBytes("UTF-8"));

  

byte[] ivPlusCipher = new byte[iv.length + ciphertext.length];

System.arraycopy(iv, 0, ivPlusCipher, 0, iv.length);

System.arraycopy(ciphertext, 0, ivPlusCipher, iv.length, ciphertext.length);

return Base64.getEncoder().encodeToString(ivPlusCipher);

}

  

public static String decrypt(String base64IvPlusCipher, SecretKey key) throws

Exception {

byte[] ivPlusCipher = Base64.getDecoder().decode(base64IvPlusCipher);

if (ivPlusCipher.length < 9) {

throw new IllegalArgumentException("Input too short to contain IV and ciphertext.");

}

byte[] iv = new byte[8];

byte[] ciphertext = new byte[ivPlusCipher.length - 8];

System.arraycopy(ivPlusCipher, 0, iv, 0, 8);

System.arraycopy(ivPlusCipher, 8, ciphertext, 0, ciphertext.length);

Cipher cipher = Cipher.getInstance("DES/CBC/PKCS5Padding");

cipher.init(Cipher.DECRYPT_MODE, key, new IvParameterSpec(iv));

byte[] plaintextBytes = cipher.doFinal(ciphertext);

return new String(plaintextBytes, "UTF-8");

}

// Demo

public static void main(String[] args) {

    System.out.println("Ishad Pande, B2, 25");

try {

SecretKey key = generateDESKey();

String message = "Hello, DES in Java!";

String encrypted = encrypt(message, key);

String decrypted = decrypt(encrypted, key);

System.out.println("Algorithm: " + key.getAlgorithm());

System.out.println("Original : " + message);

System.out.println("Encrypted: " + encrypted);

System.out.println("Decrypted: " + decrypted);

} catch (Exception e) {

e.printStackTrace();

}

}

}
```

![[image-21.png]]