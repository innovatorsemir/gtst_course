# Day 5 – Cryptography

## 1. Introduction to Cryptography

### What is Cryptography?

Cryptography is the science of secret or hidden writing. It is used to protect information by transforming readable data into a form that unauthorized people cannot understand.

The word *Cryptography* comes from:
- **Crypto:** Hidden or secret
- **Graphy:** Writing

Cryptography helps secure data and communications.

### Main Components of Cryptography

1. **Encryption:** The process of hiding messages so that they cannot be read by anyone other than the intended recipient.
2. **Integrity:** Ensuring that data or resources have not been altered without authorization.

## 2. Important Cryptography Terms

### Plaintext
The original readable message or data before encryption.

### Ciphertext
The unreadable or transformed message produced after encryption.

### Cipher
A method or algorithm used to encrypt and decrypt messages.

### Key
A string of numbers or characters used as an input to a cryptographic algorithm.

Cryptographic algorithms are generally standardized and published. The security of the encryption depends on keeping the key secret, rather than hiding the algorithm.

### Encryption and Decryption

- **Encryption:** Converts plaintext into ciphertext.
- **Decryption:** Converts ciphertext back into plaintext.

There are two major categories of encryption:

- Symmetric encryption
- Asymmetric encryption

## 3. Symmetric Encryption

Symmetric encryption is a type of encryption in which the same secret key is used for both encryption and decryption.

Examples:
- Caesar Cipher
- DES
- AES

### Types of Symmetric Ciphers

**1. Block Cipher**

A block cipher encrypts data in fixed-size blocks, commonly 64-bit or 128-bit blocks.

**2. Stream Cipher**

A stream cipher encrypts data one bit or one byte at a time. It is useful when data is received as a continuous stream of information.

## 4. Substitution Ciphers

A substitution cipher replaces each letter or character in plaintext with another character according to a specific mapping.

### 4.1 Caesar Cipher

The Caesar Cipher is a simple substitution cipher in which every letter in the alphabet is shifted by a fixed number of positions.

The traditional Caesar Cipher uses a shift of three positions.

Example:

| Plaintext | Ciphertext |
|---|---|
| A | D |
| B | E |
| C | F |
| D | G |

The same shifting process is applied throughout the alphabet.

### 4.2 Substitution Cipher Using a Key

A keyed substitution cipher uses a keyword to create a different alphabet mapping.

For example, if the keyword is `WORD`, the letters W, O, R, and D are placed first, and the remaining unused letters are added afterward.

The mapping must be one-to-one:
- One plaintext letter must not map to multiple ciphertext letters.
- One ciphertext letter must not represent multiple plaintext letters in the same mapping.

### 4.3 ROT13

ROT13 is a simple substitution cipher that replaces each letter with the letter 13 positions after it in the Latin alphabet.

It is a special case of the Caesar Cipher.

Example website:

https://rot13.com/

ROT13 is not suitable for protecting sensitive information because it is easy to reverse.

## 5. Data Encryption Standard (DES)

### What is DES?

The Data Encryption Standard (DES) is a symmetric-key encryption algorithm that was once widely used to protect data.

- Developed by IBM in the early 1970s.
- Adopted as a U.S. federal standard in 1977.
- Uses a 64-bit block size.
- Uses an effective key length of 56 bits.
- The remaining 8 bits of its 64-bit key representation are used for parity.

DES is no longer considered secure for protecting sensitive information. It has been withdrawn as a standard, and modern systems have transitioned to stronger algorithms such as AES.

### How DES Works

DES takes a 64-bit plaintext block and processes it through three main stages:

1. Initial Permutation
2. Feistel Rounds
3. Final Permutation

Decryption follows the same general process using the same secret key, with the round keys applied in reverse order.

### 5.1 Initial and Final Permutation

The initial and final permutations are performed using permutation boxes (P-boxes).

They are inverses of each other.

For example, an input sequence:

`1, 2, 3, 4, 5`

could be rearranged into:

`3, 4, 2, 1, 5`

The values remain the same, but their positions change.

These permutations do not provide the main cryptographic security of DES.

### 5.2 Feistel Structure and Rounds

The Feistel structure divides the 64-bit block into two equal halves:

- Left half (L)
- Right half (R)

DES performs 16 rounds of processing.

The round operations involve:
- Expansion
- XOR with a subkey
- Substitution
- Permutation
- Swapping the halves

These operations are repeated across the rounds to transform the plaintext into ciphertext.

## 6. Advanced Encryption Standard (AES)

### What is AES?

The Advanced Encryption Standard (AES) is a widely used symmetric encryption algorithm designed to protect sensitive information.

- Developed by Belgian cryptographers Vincent Rijmen and Joan Daemen.
- Adopted by NIST in 2001.
- Replaced DES as the U.S. encryption standard.
- Uses a fixed block size of 128 bits (16 bytes).
- Performs operations on bytes rather than individual bits.

### AES Key Sizes

AES supports three key lengths:

| Algorithm | Key Length | Number of Rounds |
|---|---:|---:|
| AES-128 | 128 bits | 10 |
| AES-192 | 192 bits | 12 |
| AES-256 | 256 bits | 14 |

Longer keys provide a larger key space, although they may require more processing resources.

### How AES Works

AES uses a series of transformations involving substitution, shifting, mixing, and round-key addition.

The main operations are:

**1. SubBytes**

Each byte is replaced with another byte using a predefined substitution table called the S-box.

**2. ShiftRows**

The rows of the state are shifted cyclically to the left.

**3. MixColumns**

Each column is transformed using matrix multiplication. This changes the arrangement and values of the bytes in each column.

**4. AddRoundKey**

The current state is combined with a round key using the bitwise XOR operation.

The final encryption round does not include the MixColumns operation.

Decryption uses the corresponding inverse transformations to recover the original plaintext.

### 6.1 Substitution Box (S-box)

The S-box is a substitution table used in AES.

It performs nonlinear substitution by replacing each input byte with another byte according to a fixed lookup table.

This contributes to the confusion and diffusion properties of the encryption algorithm.

### 6.2 ShiftRows

The ShiftRows operation moves the bytes in each row by a particular number of positions:

- First row: No shift.
- Second row: Shift one position to the left.
- Third row: Shift two positions to the left.
- Fourth row: Shift three positions to the left.

### Applications of AES

AES is used in many areas, including:

1. **Data Encryption:** Protecting files, folders, and storage devices.
2. **Secure Communications:** Protecting network traffic, VPN connections, wireless communications, and VoIP.
3. **Cryptographic Protocols:** Used in protocols such as TLS and IPsec.
4. **Government and Military:** Used to protect sensitive and classified information.

## 7. Common Terms in Symmetric Encryption

### Secret Key

The secret key is the key used by the encryption and decryption algorithm.

The lecture refers to a 56-bit key in its discussion of DES.

### Initialization Vector (IV)

An Initialization Vector is a random or pseudorandom value used by certain encryption modes to help ensure that encryption produces different results when encrypting the same plaintext with the same key.

An IV is not necessarily secret, but it must be used according to the requirements of the encryption mode.

### Encryption Modes

**1. ECB (Electronic Codebook)**

Each plaintext block is encrypted independently.

**2. CBC (Cipher Block Chaining)**

Each plaintext block is XORed with the previous ciphertext block before encryption. The first block uses an Initialization Vector.

## 8. Limitations of Symmetric Encryption

Symmetric encryption has some important limitations:

- If the secret key is exposed, the confidentiality of the encrypted data may be compromised.
- The secret key must be securely delivered to the intended recipient.
- If an attacker obtains the key, they may be able to decrypt the protected information.

This key-distribution problem is one reason asymmetric encryption is useful.

## 9. Asymmetric Encryption

### What is Asymmetric Encryption?

Asymmetric encryption uses a pair of mathematically related keys:

1. **Public Key:** Can be shared with other people.
2. **Private Key:** Must be kept secret by its owner.

In a basic public-key encryption process:

1. The sender obtains the recipient's public key.
2. The sender encrypts the message using that public key.
3. The recipient receives the ciphertext.
4. The recipient decrypts it using the corresponding private key.

A message encrypted with the recipient's public key can only be decrypted using the corresponding private key, assuming a secure and correctly implemented algorithm.

Unlike symmetric encryption, the secret decryption key does not need to be transmitted to the sender.

### Types of Asymmetric Encryption Algorithms

Two algorithms discussed in the lecture are RSA and ElGamal.

### 9.1 RSA

RSA is a widely known public-key cryptographic algorithm.

Its name comes from its developers:

- Ron Rivest
- Adi Shamir
- Leonard Adleman

Important characteristics:
- Uses a public and private key pair.
- Supports different key sizes.
- The lecture mentions 512-, 1024-, and 2048-bit keys.
- It is one of the most widely recognized public-key algorithms.

RSA security depends on appropriate key sizes and secure implementation. Older, shorter key sizes are not suitable for modern security.

### 9.2 ElGamal

ElGamal is an asymmetric encryption algorithm developed by Taher ElGamal.

Important characteristics:
- Uses mathematical operations to generate public and private keys.
- Supports different key sizes.
- The lecture mentions 512- and 1024-bit keys.
- It is less commonly encountered than RSA in many introductory examples.

### Applications of Asymmetric Encryption

Asymmetric cryptography is used in secure communication systems, including SSH.

### SSH Keys

When configuring SSH, a user can generate a public and private key pair.

Command:

```bash
ssh-keygen
```

- The public key can be shared with the remote system.
- The private key remains on the user's computer.
- The remote system uses the public key to verify authentication involving the corresponding private key.

SSH also maintains information about previously contacted hosts in a file called `known_hosts`.

**Important:** If a private key is leaked, an attacker may be able to impersonate its owner or gain unauthorized access to systems that trust that key. Private keys should be protected with appropriate file permissions and, where possible, a passphrase.

## 10. Three Important Cryptography Concepts

The lecture introduces three concepts that should not be confused with one another.

### 10.1 Encoding and Decoding

Encoding transforms data into another representation without using a secret cryptographic key.

It is commonly used to represent or transmit data in a particular format.

Examples:
- Base64
- Base32
- ROT13

Encoding is not encryption. It does not provide confidentiality because it can generally be reversed without a secret key.

### 10.2 Encryption and Decryption

Encryption transforms plaintext into ciphertext using a cryptographic algorithm and a key.

Decryption reverses the process using the appropriate key.

Examples:
- DES
- AES
- RSA

### 10.3 Hash Functions

A hash function takes input data of any length and produces a fixed-length output called a hash or digest.

Important characteristics:
- A cryptographic hash function is designed to be one-way.
- The output is commonly represented as a hexadecimal string.
- A hash is not decrypted like ciphertext.
- Different input data should produce different outputs, although collisions are mathematically possible.

If someone wants to find the original input corresponding to a hash, they may try candidate inputs and compare their resulting hashes. This is called hash matching or password cracking, depending on the context.

### Salt

A salt is a random value added to a password before it is processed by a password-hashing function.

Its purpose is to make identical passwords produce different stored hash values when different salts are used.

Salts are normally stored alongside the resulting password hash. Password-storage systems should use dedicated password-hashing algorithms such as bcrypt, scrypt, or Argon2.

### Examples of Hash Algorithms

- MD5
- SHA-256
- bcrypt

## 11. MD5 (Message-Digest Algorithm 5)

MD5 is a cryptographic hash function that produces a 128-bit hash value.

Important characteristics:
- Produces a 128-bit digest.
- Its hexadecimal representation contains 32 characters.
- Each hexadecimal character represents four bits.
- It was originally designed for cryptographic applications.

However, MD5 is no longer considered secure for cryptographic purposes because weaknesses allow collisions.

It may still be encountered in older systems and non-security checksum applications, but it should not be used to protect passwords or provide modern cryptographic integrity.

### Purpose of Hashing

Hashing is commonly used for:

1. **Integrity:** Comparing hashes can help determine whether data has changed.
2. **Password Verification:** Secure password-hashing algorithms store password-derived hashes rather than plaintext passwords.

A hash function does not provide confidentiality by itself.

## 12. Common Encoding and Hash Representations

The lecture provides the following representations and examples:

| Method | Example |
|---|---|
| Base2 | `01100010 01110010 01100101 01100001 01101011 01101001 01110100` |
| Base8 | `142 162 145 141 153 151 164` |
| Base16 | `62 72 65 61 6b 69 74` |
| Base32 | `MJZGKYLLNF2A====` |
| Base58 | `4jP4KDubX1` |
| Base62 | `22udqyscMu` |
| Base64 | `YnJlYWtpdA==` |
| Base85 | `@WH$gCM@k` |
| Base91 | `%zmfv;:YH` |
| URL Encoding | `hello%20there%20%3F` |

The lecture also provides these hash examples:

**MD5:**
```text
5d41402abc4b2a76b9719d911017c592
```

**SHA-1:**
```text
aaf4c61ddcc5e8a2dabede0f3b482cd9aea9434d
```

**ROT example:**
```text
Uryyb, Frphevgl Grfgref
```

Encoding formats and hash functions serve different purposes. Base64 and URL encoding can be reversed directly, while a cryptographic hash is not designed to be reversed.

## 13. Tools of the Trade

There are many encoding, encryption, and hashing algorithms. Identifying an unknown value manually can be difficult, so security professionals use analysis tools.

### 13.1 Hashid

Hashid helps identify possible hash algorithms based on a supplied hash format.

Basic syntax:

```bash
hashid <hash>
```

It provides possible matches, not guaranteed identification.

### 13.2 CyberChef

CyberChef is a web-based tool for working with encoding, decoding, encryption, hashing, and data transformations.

Website:

https://gchq.github.io/CyberChef/

The lecture introduces the **Magic** operation.

General workflow:

1. Open CyberChef.
2. Search for `Magic`.
3. Add the Magic operation to the recipe.
4. Enter the input data.
5. Examine the output and possible interpretations.

CyberChef can help identify common encodings and transformations.

### 13.3 TunnelsUp Hash Analyzer

TunnelsUp provides a hash-analysis tool that helps identify possible hash types using characteristics such as length and format.

Website:

https://www.tunnelsup.com/hash-analyzer/

### 13.4 CrackStation

CrackStation is an online service that can compare certain hashes against known password and hash databases.

Website:

https://crackstation.net/

Its effectiveness depends on whether the hash is supported and whether a matching value exists in its databases. Salted or modern password hashes may not be recoverable through simple database lookup.

### Decoding and Decryption Tools

CyberChef can help with encoding and decoding operations. Other online tools may provide encryption and decryption demonstrations.

Examples mentioned in the lecture:

- DES: https://anycript.com/crypto/des
- AES: https://anycript.com/crypto

Use encryption tools only with data you are authorized to process. Avoid entering real passwords, private keys, or confidential information into public websites.

## 14. Identifying Unknown Hashes

During penetration testing and security assessments, an analyst may encounter hashes generated by a particular platform or application.

The lecture recommends the following general approach:

1. Identify the software or platform that generated the hash.
2. Research the hash format used by that software.
3. Identify the relevant hashing algorithm.
4. Look for documentation or analysis tools that support the format.
5. Perform authorized testing using appropriate methods.

For example, a hash may have been generated by software such as Openfire.

Identifying the originating application can help narrow down the possible hash format.

## 15. Wordlists

### What is a Wordlist?

A wordlist is a normal text file containing different words or candidate strings.

In security testing, wordlists can be used to:
- Test password strength.
- Check candidate passwords against password hashes.
- Perform authorized dictionary-based password audits.
- Supply repeated inputs to security-testing tools.

### Custom Wordlists

A custom wordlist contains terms selected for a particular authorized test.

It can be created manually using a text editor or generated using tools such as:
- CeWL
- CUPP
- Crunch

Wordlists should only be used for systems and accounts that the tester is authorized to assess.

## 16. Wordlist Generation Tools

### 16.1 CeWL

CeWL is a Ruby program that crawls a website to a specified depth and generates a list of words found in the website's content.

The lecture introduces it as a way to create custom wordlists based on website content.

### 16.2 CUPP

CUPP (Common User Passwords Profiler) is a tool for generating custom password lists based on information provided for an authorized security assessment.

### 16.3 Crunch

Crunch is an open-source tool used to generate custom wordlists based on specified character sets and lengths.

General syntax:

```bash
crunch <min_length> <max_length> [options]
```

### Crunch Character-Set Symbols

| Symbol | Meaning |
|---|---|
| `,` | Uppercase letters |
| `@` | Lowercase letters |
| `%` | Numeric characters |
| `^` | Special characters |

The lecture also introduces:

- `-t`: Uses a specified pattern.
- `-p`: Generates permutations of supplied words or characters.

When using a pattern, its length must match the required output length.

## 17. John the Ripper

John the Ripper is a widely known password-auditing and password-recovery tool.

It supports many hash formats and can use wordlists to test candidate passwords against hashes.

General syntax:

```bash
john [options] [path_to_file]
```

### Important Options

**1. Specify a Wordlist**

```bash
--wordlist=<path>
```

This option specifies the wordlist used for testing candidate passwords.

**2. Specify a Hash Format**

```bash
--format=<hashType>
```

This option specifies the hash format when it is known.

Example format mentioned in the lecture:

```text
raw-md5
```

John the Ripper should only be used for authorized password auditing and recovery.

## 18. Python for Cryptography

Python can be used to build programs that perform encryption, encoding, decoding, and hashing operations.

Understanding the mathematical operations behind cryptographic algorithms helps developers implement and analyze them.

The lecture introduces:
- XOR operations.
- Base64 encoding and decoding.
- Basic cryptographic programming concepts.

### 18.1 XOR Operation

XOR stands for **Exclusive OR**.

It is a bitwise logical operation that compares two bits.

The output is `1` when the input bits are different and `0` when they are the same.

| A | B | A XOR B |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

XOR is used in many cryptographic operations.

An important property is that applying the same XOR value twice restores the original value:

```text
A XOR K XOR K = A
```

This property makes XOR useful in simple demonstrations of reversible transformations. XOR alone, however, is not a secure encryption system.

### 18.2 Base64 Encoding and Decoding

Python provides the built-in `base64` module for Base64 encoding and decoding.

Example:

```python
import base64

message = "Hello, Security Testers"

# Encode
encoded = base64.b64encode(message.encode("utf-8"))
print("Encoded:", encoded.decode("utf-8"))

# Decode
decoded = base64.b64decode(encoded).decode("utf-8")
print("Decoded:", decoded)
```

Base64 is an encoding method, not encryption. It does not protect sensitive information.

## 19. Obfuscation

### What is Obfuscation?

In software development, obfuscation is the process of transforming source code or machine code into a form that is difficult for humans to understand.

High-level programming languages are generally readable. If someone obtains the source code, they may be able to understand its logic and structure.

Developers use obfuscation to make code analysis more difficult and protect intellectual property.

### Why is Obfuscation Used?

- Makes source code harder to understand.
- Makes reverse engineering more difficult.
- Helps protect proprietary implementation details.
- Can make it harder to identify the program's internal logic.

Obfuscation does not replace encryption or secure software design.

### 19.1 Python Code Obfuscation

Python code can be transformed into a less readable form using code-obfuscation tools.

Website mentioned in the lecture:

https://pyobfuscate.com/pyd

### 19.2 Website Code Obfuscation

Website code may be bundled, minified, or transformed to make it less readable.

The lecture mentions:

**Webpack**

Webpack is a JavaScript module bundler commonly used to combine and process application resources.

### 19.3 Android Code Obfuscation

The lecture mentions:

**ProGuard**

ProGuard is a tool used in Android and Java development for code shrinking and optimization, and it can also obfuscate code by renaming classes, methods, and fields.

Obfuscation can make code analysis more difficult, but it does not guarantee that an application cannot be reverse-engineered.

## 20. Key Differences to Remember

| Concept | Purpose | Uses a Secret Key? | Reversible? |
|---|---|---|---|
| Encoding | Changes data representation | No | Yes |
| Encryption | Protects data confidentiality | Yes, or a key pair | Yes, with the appropriate key |
| Hashing | Produces a fixed-length digest | Not normally | Not designed to be reversed |
| Obfuscation | Makes code harder to understand | Not necessarily | Not necessarily |

## 21. Important Tools and Websites

| Tool | Main Purpose |
|---|---|
| ROT13 | Simple letter substitution |
| CyberChef | Encoding, decoding, hashing, and data transformation |
| Hashid | Identifying possible hash algorithms |
| TunnelsUp | Hash analysis |
| CrackStation | Searching supported hashes against known databases |
| CeWL | Generating wordlists from website content |
| CUPP | Generating custom password lists |
| Crunch | Generating wordlists using patterns and character sets |
| John the Ripper | Authorized password auditing and recovery |
| `ssh-keygen` | Generating SSH key pairs |
| Webpack | Bundling and processing web application resources |
| ProGuard | Android/Java code optimization and obfuscation |

## 22. Quick Summary

- **Cryptography:** Protecting information through secret writing.
- **Symmetric Encryption:** Uses the same key for encryption and decryption.
- **Substitution Ciphers:** Replacing letters using a fixed or keyed mapping.
- **DES:** An older symmetric block cipher.
- **AES:** A modern symmetric block cipher.
- **Asymmetric Encryption:** Uses public and private key pairs.
- **RSA & ElGamal:** Examples of asymmetric algorithms.
- **Encoding & Decoding:** Changing data representation without a secret key.
- **Hashing:** Producing a fixed-length, one-way digest.
- **MD5:** A 128-bit hash algorithm.
- **Cryptography Tools:** CyberChef, Hashid, and TunnelsUp.
- **Wordlists:** Collections of words used in authorized security testing.
- **CeWL, CUPP & Crunch:** Tools for generating custom wordlists.
- **John the Ripper:** A password-auditing and recovery tool.
- **Python for Cryptography:** Using Python for XOR and Base64 operations.
- **Obfuscation:** Making source code harder to understand.

**Key lesson:** Understand the difference between encoding, encryption, hashing, and obfuscation. They have different purposes and should not be treated as interchangeable.

---

@innovatorsemir