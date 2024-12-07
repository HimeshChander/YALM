# RSA Cryptographic Exploitation: Cube Root Attack

## Overview
This project demonstrates a vulnerability in RSA encryption with a small public exponent (`e = 3`). It includes a server that encrypts a secret and scripts to exploit the weakness using a **cube root attack**.

## Files
### 1. **Server-Side**
- `server.py`: RSA server encrypting a flag with public key `(n, e)`.
- `Modified_server.py`: A test version of the server with placeholder values for `n` and the flag.

### 2. **Attack Scripts**
- `Flag.py`: Performs the full attack:
  - Finds `n` using binary search.
  - Recovers the plaintext (flag) with a **Stereotyped Message Attack** using SageMath.
- `Cube_root_attack.py`: Standalone script to decode ciphertext using cube root calculations.

## Tools Used
- **Pwntools**: For server interaction.
- **PyCryptodome**: For cryptographic number conversions.
- **SageMath**: For polynomial and small root calculations.
- **SymPy/mpmath**: For cube root computations.

## How to Run
1. Run the server:
   ```bash
   python3 server.py
   ```
2. Run the attack:
   ```bash
   python3 Flag.py
   ```
3. Test cube root decoding:
   ```bash
   python3 Cube_root_attack.py
   ```

## Key Concepts
- **Stereotyped Message Attack**: Exploits RSA's weakness with small exponents.
- **Cube Root Attack**: Recovers plaintext if \( m^3 < n \).

This project highlights RSA vulnerabilities for educational purposes.
