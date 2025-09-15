# 🔐 TryHackMe — Section 5: Cryptography

## 🔎 Overview
This section covers **how we secure data**: encryption (symmetric & asymmetric), **public-key crypto** (RSA, Diffie-Hellman, SSH, certificates), **hashing** (integrity, passwords, HMAC), and hands-on **password cracking** with **John the Ripper**.

---

## 🧱 Cryptography Basics

### 🌟 Importance
- Ensures **confidentiality, integrity, authenticity** in hostile environments.
- Compliance examples: **PCI DSS** (payments), **HIPAA/HITECH** (US health), **GDPR** (EU), **DPA** (UK).
- Encrypt **at rest** and **in transit**.

### 🔁 Plaintext ➜ Ciphertext (Core Terms)
- **Plaintext** → (cipher + **key**) → **Ciphertext**; reverse = **Decryption**.
- **Cipher** = public algorithm; **key** stays secret (except public key in PKI).
- Goal: infeasible to recover plaintext **without the key**.

### 🕰️ Historical Ciphers
- **Caesar**, **Vigenère**, **Enigma**, **One-Time Pad** (perfect secrecy if used correctly).

### 🗝️ Types of Encryption
- **Symmetric (one key)**: fast; key exchange is hard.
  - **DES (56-bit)** → broken (1999) → **3DES (deprecated, 2019)** → **AES (128/192/256)** = modern standard.
- **Asymmetric (keypair)**: **public key** encrypts / verifies; **private key** decrypts / signs.
  - **RSA** (≥2048-bit recommended), **Diffie-Hellman** (≥2048-bit), **ECC** (e.g., 256-bit ≈ RSA-3072).
  - Slower; based on one-way math problems.

### ➕ Bitwise & Number Theory (Crypto Math)
- **XOR (⊕)**: different → 1, same → 0; self-inverse; commutative & associative.
- **Modulo (mod)**: remainder; not reversible; output in `[0, divisor)`.

---

## 🛡️ Public Key Cryptography

### 🎯 Security Properties
- **Authentication & Authenticity**, **Integrity**, **Confidentiality**.

### 🔗 Hybrid Crypto
- Use **asymmetric** to agree on **symmetric** keys (performance + security).

### 🧮 RSA (High-Level)
- Public-key encryption based on **factoring** hardness.  
- **Public key** encrypts / verifies; **private key** decrypts / signs.

### 🤝 Diffie-Hellman (DH)
- Establishes a **shared secret** over an **insecure channel** using public parameters (prime `p`, generator `g`) and private exponents.  
- Commonly paired with RSA (e.g., for auth/signatures).

### 🖧 SSH (Secure Shell)
- **Server auth** via known host key fingerprints (MitM warning on changes).
- **Client auth**: passwords or keys (**RSA**, **ECDSA**, **Ed25519**, plus `-SK` hardware key variants).
- **Key hygiene**: keep private keys secret, protect with a **passphrase**, generate locally, copy **public** key (`ssh-copy-id`), use `~/.ssh/authorized_keys`.
- `ssh -i <key> user@host` to specify a key.
- Note: a lingering authorized key can act as a **backdoor**.

### ✍️ Digital Signatures & Certificates
- **Sign with private key**, **verify with public key** (authenticity + integrity).
- **PKI certificates** (HTTPS): chain of trust from **Root CA**; trust is anchored in CAs.

### 📧 PGP/GPG
- **GPG** (OpenPGP) for **email encryption** & **signing**; verify senders and message integrity.

### 🧪 Crypto Attacks (Big Picture)
- **Cryptanalysis**, **Brute Force**, **Dictionary** attacks—choose strong, modern algorithms & keys.

---

## #️⃣ Hashing Basics

### 🧰 What Is a Hash?
- **Fixed-length digest** of arbitrary input; **one-way** (not reversible).  
- Examples: **MD5**, **SHA-1**, **SHA-256** (newer SHA-2/3 preferred).  
- Tools output **hex** (e.g., `md5sum`, `sha256sum`).

### 🎯 Why Hash?
- **Integrity** checks; **password storage** (store **hashes**, not plaintext).

### ⚠️ Collisions
- Different inputs → **same hash**.  
- **MD5/SHA-1**: collision-prone → **insecure** for integrity/PKI uses.

### 🔒 Password Storage (Bad vs Good)
- **Insecure**: plaintext, deprecated encryption, weak hash.  
- **Better**: **salted** hashes; slow KDFs (**bcrypt**, **scrypt**, **Argon2**).  
- **Salt**: random, per-user, **stored alongside** hash; defeats rainbow tables.

### 🧩 Recognizing Hashes
- Format/prefixes help (Linux `/etc/shadow` uses `$prefix$options$salt$hash`):  
  - `$y$` yescrypt (modern default), `$7$` scrypt, `$2b$/$2y$` bcrypt, `$6$` sha512crypt, `$1$` md5crypt, etc.  
- **Windows**: NTLM; stored in **SAM**.

### 🧾 Integrity & HMAC
- Hash files to detect tampering/duplicates.  
- **HMAC** = hash + secret key for **authenticity + integrity**.  
- Formula: `HMAC(K, M) = H((K ⊕ opad) || H((K ⊕ ipad) || M))`.

---

## 🧨 John the Ripper (JtR) — Basics

### 📖 Terms
- One-way hashes (MD4/MD5/SHA1/NTLM) mask original data.

### ⚙️ Basic Use
- **Syntax:** `john [options] [file]`  
- **Wordlist mode:** `john --wordlist=<path> <hashfile>`  
- **Identify hash:** use hash-id tools (best for prefixed formats).  
- **Format-specific:** `john --format=<fmt> --wordlist=<path> <hashfile>`

### 🪟 Windows & 🐧 Linux Targets
- **Windows**: crack **NTLM/NThash** from **SAM**.  
- **Linux**: combine `/etc/passwd` + `/etc/shadow` via `unshadow passwd shadow > combo` then run `john combo`.

### 🧠 Single Crack Mode
- `john --single --format=<fmt> <file>` uses **username/GECOS** heuristics + **mangling rules**.

### 🧪 Custom Rules
- Define in `john.conf`:  
  - `Az` append, `A0` prepend, `c` capitalize; character classes like `[0-9]`, `[A-Z]`, `[a-z]`, `[!£$%@]`.

### 🗜️ Archives & Keys
- **zip2john**, **rar2john** → convert archives to crackable hashes.  
- **ssh2john** → convert `id_rsa` private keys for passphrase cracking.

---

## 🧠 What I Learned
- Can explain **confidentiality, integrity, authenticity** and map them to crypto tools.  
- Know when to use **symmetric vs asymmetric** and why hybrid schemes dominate.  
- Understand **RSA**, **Diffie-Hellman**, and **SSH** key management & risks.  
- Can describe **PKI**, certificate trust chains, and **digital signatures**.  
- Can choose safe **hash/KDFs** and implement **salting** to defeat rainbow tables.  
- Recognize common **hash formats** (Linux `/etc/shadow` prefixes, Windows NTLM).  
- Use **HMAC** to provide integrity + authenticity.  
- Operate **John the Ripper** to crack hashes/archives/SSH keys with proper modes, formats, and rules—ethically and legally.

---
