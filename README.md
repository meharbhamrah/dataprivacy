# **Data Privacy – Detailed Notes**

Data privacy focuses on protecting personal and sensitive information from unauthorized access, misuse, or disclosure, while ensuring individuals have control over how their data is used and shared.

---

## **Notion of Data Privacy**

- **Definition:** Protecting sensitive data from unauthorized access, while giving people control over how their information is collected, processed, and shared.  
- **Importance:**  
  - Protects individuals from fraud, identity theft, and exploitation.  
  - Builds trust between organizations and users.  
  - Ensures compliance with global and local regulations.

---

## **Historical Context**

- **1970s–1990s:** Growth of digital systems and early data protection laws (e.g., in Germany, USA, EU).  
- **2000s:** The internet boom led to widespread collection and sharing of user data.  
- **2010s–Present:**  
  - Rise of Big Data, AI, and targeted advertising.  
  - Stricter global regulations like GDPR (EU), CCPA (California), and the Indian DPDP Act 2023.

---

## **Types of Sensitive Data**

- **Personally Identifiable Information (PII):** Name, address, phone number, email, government IDs.  
- **Financial Data:** Bank details, credit card numbers, transaction history.  
- **Health Data:** Medical history, prescriptions, genetic or biometric data.  
- **Behavioral Data:** Search patterns, location history, online activity.  
- **Special Categories:** Religion, race, political opinions, or sexual orientation.

---

## **Privacy Laws and Regulations**

### **GDPR (General Data Protection Regulation - EU)**  
- Emphasizes user consent, transparency, and accountability.  
- Provides rights like data portability and the right to be forgotten.  
- Requires organizations to report breaches within 72 hours.

### **CCPA (California Consumer Privacy Act)**  
- Grants users the right to access, delete, or opt out of selling their data.  
- Focused on transparency and consumer control.

### **DPDP Act (Digital Personal Data Protection Act, India, 2023)**  
- Introduces a legal framework for personal data processing.  
- Mandates explicit consent for collection and processing.  
- Includes penalties for non-compliance.

---

## **Data Privacy Attacks and Risks**

- **Phishing:** Fake emails or links to trick users into sharing credentials.  
- **Malware/Ransomware:** Malicious software that steals or locks data.  
- **Insider Threats:** Misuse of data by employees or trusted individuals.  
- **SQL Injection and Hacking:** Exploiting vulnerabilities to access databases.  
- **Social Engineering:** Manipulating individuals to obtain confidential data.

---

## **Impact of Data Breaches**

- **For Individuals:**  
  - Identity theft  
  - Financial loss  
  - Emotional stress or reputational harm  

- **For Organizations:**  
  - Heavy financial penalties and legal consequences  
  - Loss of customer trust and credibility  
  - Possible operational disruptions

---

## **Cryptography and Data Protection**

**Cryptography** is the practice of securing data through encoding and mathematical techniques.  

### **Key Goals**  
- Confidentiality  
- Integrity  
- Authentication  
- Non-repudiation

### **Symmetric Encryption**  
- Uses the same key for both encryption and decryption.  
- **Examples:** AES, DES  
- **Use Case:** Fast encryption for large amounts of data.

### **Asymmetric Encryption**  
- Uses two keys: a **public key** (encrypt) and a **private key** (decrypt).  
- **Examples:** RSA, ECC  
- **Use Case:** Digital certificates, secure communications.

### **Hashing and Digital Signatures**  
- **Hashing:** Converts data into a fixed-length string (e.g., SHA-256). Used for integrity verification.  
- **Digital Signatures:** Ensure authenticity and verify that data hasn’t been tampered with.

---

## **Data Collection, Use, and Reuse**

- Over-collection or irresponsible reuse of data can lead to profiling, manipulation, or unethical targeting.  
- Examples include targeted ads, credit scoring, or political manipulation.

---

## **Data Anonymization**

Removing personally identifiable details while retaining the utility of the data.  

**Techniques:**  
- **Masking:** Partially hiding data.  
- **Generalization:** Reducing precision, such as sharing a city instead of an exact address.  
- **Noise Addition:** Slight random changes to make re-identification harder.  
- **Tokenization:** Replacing real data with random tokens.

**Challenges:**  
- Advanced analytics can still re-identify anonymized data.  
- Balancing privacy with data usefulness is difficult.

---

## **Ethical Considerations**

### **Privacy vs. Surveillance**  
- Organizations and governments often justify mass data collection for safety or security, but excessive surveillance threatens individual freedoms.

### **Ethics of Data Collection and Use**  
- Consent must be **clear, informed, and voluntary**.  
- Organizations must ensure **transparency** and **purpose limitation**.

### **Bias and Discrimination**  
- AI systems can inherit or amplify biases present in historical data.  
- Impacts include discrimination in hiring, loans, policing, and advertising.  
- **Solution:** Fairness audits, ethical AI development, and bias testing.

---
