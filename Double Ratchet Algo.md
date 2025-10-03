# Double Ratchet Algorithm

## Introduction
The **Double Ratchet Algorithm** is a cryptographic protocol that powers modern end-to-end encrypted messaging systems such as **Signal** and **WhatsApp**. Its design ensures that even if some keys are compromised, conversations remain secure.  

The algorithm combines:
- A **Diffie–Hellman (DH) ratchet** for asynchronous key agreement  
- A **symmetric-key ratchet** for continuous key updates  

Together, these provide **forward secrecy** and **post-compromise security**, making private communication resilient against long-term attacks.

---

## Core Principles

- **Forward Secrecy** → Previously sent messages remain safe even if current keys are stolen.  
- **Post-Compromise Security** → If a device is compromised, future communications recover automatically.  
- **Ratchet Mechanism** → Keys evolve in one direction only; old keys cannot be regenerated.  

---

## Components

### 1. Diffie–Hellman Ratchet
- Parties generate short-lived DH key pairs.  
- When a new public key is received, both sides compute a new DH shared secret.  
- This shared secret refreshes the **root key**, ensuring ongoing protection.  

### 2. Symmetric-Key Ratchet
- Uses a **Key Derivation Function (KDF)**.  
- With each new message, the chain key is advanced to produce a unique **message key**.  
- Message keys are used once and discarded.  

---

## Workflow

### Initialization
- A session begins with a shared secret (often via **X3DH**, the Extended Triple Diffie–Hellman handshake).  
- Both parties maintain a **root key (RK)** and two **chain keys (CKs)**: one for sending and one for receiving.  

### Sending a Message
1. The sending chain key derives a new **message key (MK)**.  
2. The message is encrypted using this MK.  
3. Optionally, a new DH public key is attached to trigger a ratchet step.  

### Receiving a Message
1. If the sender’s DH public key has changed:  
   - Perform a **DH ratchet step**.  
   - Update the root key and reset the chain keys.  
2. Advance the receiving chain key to derive the correct message key.  
3. Decrypt the message.  

### DH Ratchet Step
- Performed when new DH keys are exchanged.  
- Combines the new DH shared secret with the current root key via a KDF.  
- Resets sending/receiving chain keys.  
- Guarantees both **forward secrecy** and **post-compromise security**.  

---

## Terminology

| Term             | Description |
|------------------|-------------|
| **Root Key (RK)**    | Master evolving secret, refreshed during DH ratchets |
| **Chain Key (CK)**   | Evolves forward to generate message keys |
| **Message Key (MK)** | One-time key for encrypting/decrypting a single message |
| **DH Key Pair**      | Temporary public/private key pair for ratchet steps |
| **KDF**              | Key Derivation Function used to evolve secrets |

---

## WhatsApp and the Double Ratchet

WhatsApp integrates the Double Ratchet as part of the **Signal Protocol**. Here’s how it applies:

- **Session Setup** → Performed via **X3DH** to establish the initial shared secret.  
- **Unique Message Keys** → Every message is encrypted with a one-time key.  
- **Offline Support** → DH ratchets allow asynchronous updates when users come back online.  
- **Group Chats** → Each participant maintains a separate ratchet, ensuring group secrecy.  
- **Security Outcomes**:  
  - Forward secrecy (past messages remain private)  
  - Post-compromise security (sessions recover automatically)  
  - Replay prevention (message keys are never reused)  

---

## Security Properties

- **Confidentiality** → Each message uses a fresh encryption key.  
- **Forward Secrecy** → Past communications are secure even if current keys are leaked.  
- **Post-Compromise Security** → Security is restored after compromise.  
- **Asynchronous Messaging** → Works seamlessly when users are not online at the same time.  
- **Integrity & Authenticity** → Messages are authenticated and protected against tampering.  

---

## References

- [Signal Protocol: Double Ratchet Specification](https://signal.org/docs/specifications/doubleratchet/)  
- [Signal Blog – The Double Ratchet Algorithm](https://signal.org/blog/the-double-ratchet-algorithm/)  
- [WhatsApp Security Whitepaper](https://www.whatsapp.com/security/)  
- [Cryptography Engineering Blog: Double Ratchet Explained](https://blog.cryptographyengineering.com/2016/03/17/double-ratchet-algorithm/)  

---

## Further Resources

- [Signal Protocol GitHub](https://github.com/signalapp/libsignal-protocol-c)  
- [Wikipedia – Double Ratchet Algorithm](https://en.wikipedia.org/wiki/Double_Ratchet_Algorithm)  
