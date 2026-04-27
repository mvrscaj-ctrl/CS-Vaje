short answers:

1. Difference between encryption and signing
While both use the same key pair, they serve two completely different security goals: Confidentiality and Authenticity.

Encryption (Privacy): Its purpose is to hide the content. You use the recipient's public key to scramble the data. Only the recipient’s private key can unscramble it.
It’s like putting a letter in a safe that only the recipient can open.Signing 

(Identity): Its purpose is to prove who sent the file and that it hasn't been changed. You use your own private key to create a digital fingerprint (hash) of the file. 
Anyone with your public key can verify that the "seal" is yours. It’s like an unbreakable wax seal on an envelope.

2.Role of public and private keys
In asymmetric cryptography (like PGP/GPG), the keys work in a "one-way" relationship.

Public Key can be used by everyone. It encrypts data or verifies a signature.	It is like an open padlock or a public phone number.

Private Key is used only by you and it decrypts data or is used to sign something.	It is like the physical key to the padlock or a secret PIN.

3. What happens when an encrypted file is modified?
If an attacker or if you change the content even a single bit after it has been encrypted and signed, the process will fail during decryption.

Integrity check failure: When you sign a file, GPG calculates a cryptographic hash (a unique string of characters) of the original data.

The "Corrupted" alert: When the recipient tries to decrypt the modified file, GPG will recalculate the hash. Because the file was changed, the hashes won't match.

Result: GPG will issue a loud warning: gpg: WARNING: message was tampered with! or gpg: BAD signature.