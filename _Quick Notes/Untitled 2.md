Here are all the *unique questions* extracted from the text you provided, organized by topic and numbered for clarity:

---

### *1. Cryptographic Attacks and Concepts*

1. What is cryptography? Explain Encryption and Decryption with the help of a diagram.
2. Explain cryptographic attacks with example.
3. What do you mean by network security? Explain the model of network security in detail.
4. What are different types of attack? Explain all categories and its subtypes in detail.
5. Explain the model of symmetric encryption.
6. Define the following cryptosystem terms:
   a) Confidentiality
   b) Authentication
   c) Integrity

---

### *2. Cipher Techniques*

7. Explain monoalphabetic cipher in detail and generate ciphertext for the text: "HAVE A GOOD DAY".
8. Explain polyalphabetic cipher with a suitable example.
9. Distinguish between monoalphabetic and polyalphabetic ciphers.
10. Explain addition and multiplication ciphers with example.
11. Encrypt the message "Money helps to build infrastructure" using Hill Cipher with the key \[5 7]. Show your calculations and results in detail.

---

### *3. Algorithms and Cipher Systems*

12. Explain extended Euclidean algorithm with example. **TBD**
13. Explain block cipher and its components.
14. Explain Blowfish algorithm in detail.
15. Explain RC algorithm in detail.
16. Explain in detail DES, Double DES, and Triple DES with diagram.
17. Describe the process of key generation in AES.
18. Describe key generation of AES algorithm.
19. Explain key distribution scenario in detail.

---

### *4. Cipher Types and Modes*

20. Differentiate between DES and AES algorithms.
21. Differentiate between Block and Stream ciphers.
22. Differentiate Block ciphers and Stream ciphers in detail.
23. Explain block cipher modes of operation

---

A **block cipher** is a symmetric encryption algorithm that encrypts data in fixed-size blocks, typically 64 or 128 bits, using a shared secret key. Unlike stream ciphers that process data bit by bit, block ciphers work on entire blocks at once, making them suitable for encrypting large amounts of structured data. Widely used block ciphers include AES (Advanced Encryption Standard), DES (Data Encryption Standard), and Blowfish. These ciphers are fundamental to modern cryptography, securing everything from internet traffic to file encryption.

The core components of a block cipher include the **plaintext block**, which is the original data to be encrypted, and the **ciphertext block**, which is the encrypted output. A **secret key** is used for both encryption and decryption, making the cipher symmetric. The **encryption algorithm** applies a series of complex transformations known as rounds, each involving substitution, permutation, and mixing operations, often aided by smaller subkeys called **round keys**. These subkeys are generated from the main key using a process called a **key schedule**.

Since block ciphers work on fixed-size blocks, **modes of operation** are used to handle messages longer than one block. These modes define how blocks are linked together and help achieve additional security properties like randomness and integrity. Common modes include ECB (Electronic Codebook), which encrypts each block independently; CBC (Cipher Block Chaining), which chains blocks together for better security; and CTR (Counter Mode), which turns the block cipher into a stream cipher. Together, these components and techniques make block ciphers versatile and secure tools in the field of cryptography.