# Cryptography Fundamentals and OpenSSL Practical

## 1. Encryption types

- **Symmetric encryption:** The same secret key is used to encrypt and decrypt data. It is efficient for bulk data, but the key must be shared securely.
- **Asymmetric cryptography:** Uses a mathematically related public/private key pair. It supports tasks such as key exchange and digital signatures, depending on the algorithm and protocol.
- **Hashing:** Produces a fixed-length digest from input data. A cryptographic hash is not intended to be decrypted.
- **Digital certificates:** Bind an identity to a public key, typically through a certificate authority and a chain of trust.
- **TLS:** Protects network communications and authenticates a server using certificates in common HTTPS deployments.

## 2. OpenSSL encryption/decryption practical

Run in Kali. This creates local demonstration files only.

```bash
mkdir -p ~/apexplanet-task1/crypto
cd ~/apexplanet-task1/crypto
printf 'ApexPlanet Task 1 demonstration' > message.txt
openssl enc -aes-256-cbc -salt -pbkdf2 -in message.txt -out message.enc
```

OpenSSL prompts for a password. Use a temporary lab password; do not save it in this repository or in screenshots.

Decrypt:

```bash
openssl enc -d -aes-256-cbc -pbkdf2 -in message.enc -out decrypted.txt
cat decrypted.txt
```

Enter the same password when prompted. Compare the recovered plaintext with the original file. If the command fails, record the actual error and troubleshoot rather than claiming success.

**Record results**
- Encryption completed: `[YES/NO — based on actual test]`
- Decryption completed: `[YES/NO — based on actual test]`
- Plaintext matched: `[YES/NO — based on actual comparison]`
- Screenshot filenames: `[FILL IN]`

AES-CBC does not itself provide authenticated encryption. This is a learning demonstration, not a recommendation for designing a production encryption system.

## 3. Hashing practical

```bash
printf 'ApexPlanet Task 1' > hash-demo.txt
md5sum hash-demo.txt
sha256sum hash-demo.txt
```

Record the actual outputs in your private notes or report if they contain no sensitive data.

- **MD5:** Has known collision weaknesses and should not be used for security-sensitive integrity protection or password storage.
- **SHA-256:** A widely used cryptographic hash for general-purpose integrity checks.
- Neither command encrypts the file; there is no decryption step for a hash.

## 4. Inspect a TLS certificate

If your Kali VM has Internet connectivity:

```bash
openssl s_client -connect example.com:443 -servername example.com </dev/null
```

Look for certificate details and verification output. Results depend on connectivity, system time and certificate configuration. Do not claim verification succeeded unless the output supports it.

## 5. Key terms

- **Key:** Secret or public/private cryptographic material used by an algorithm.
- **Salt:** Random or unique input used in operations such as password-based key derivation or password hashing.
- **Certificate chain:** Certificates used to connect a server certificate to a trusted root.
- **TLS:** A protocol that protects data in transit.
- **Password hashing:** Use a purpose-built, salted password-hashing scheme rather than a fast general-purpose hash such as plain SHA-256.

## 6. Evidence checklist

- [ ] Encryption command run and result recorded.
- [ ] Decryption command run and plaintext compared.
- [ ] MD5 and SHA-256 commands run and explained.
- [ ] TLS certificate inspection attempted, or connectivity limitation recorded.
- [ ] No password, private key or secret committed to GitHub.
