# Cryptography & Network Security

[![Markdown](https://img.shields.io/badge/Format-Markdown-blue.svg)](#)
[![Status](https://img.shields.io/badge/Status-Maintained-success.svg)](#)

> Raccolta di appunti, schemi e riassunti relativi ai concetti fondamentali della crittografia moderna e della sicurezza delle reti. 
> Questo repository contiene materiale di studio strutturato per semplificare e rendere accessibili concetti complessi, partendo dai fondamenti matematici fino ad arrivare ai protocolli applicativi utilizzati su Internet.

<p align="center">
  <img width="800" height="559" alt="image" src="https://github.com/user-attachments/assets/3edce1cf-e016-4763-99a5-88076f285b04" />
</p>

## Indice Analitico (CRITTOGRAFIA)

### 1. Fondamenti e Introduzione
* **Teoria dei Numeri:** Analisi dei concetti algebrici necessari per la crittografia.
* **Sintesi Logica:** Connessioni tra le strutture algebriche e la loro applicazione pratica.

### 2. Crittografia Simmetrica e PRG
* **Primitive Simmetriche:** Principi di riservatezza e gestione delle chiavi.
* **Pseudo Random Generators (PRG):** Definizione ed espansione del seed.
* **Operatore XOR:** Proprietà fondamentali e il One-Time Pad.
* **Cifratura a Blocchi:** Architetture e modalità operative per la gestione di flussi di dati.
* **Sintesi Logica:** Evoluzione dai generatori deterministici alla cifratura di blocco sicura.

### 3. Sicurezza Formale dei PRG
* **Teorema di Yao:** Il criterio di sicurezza basato sul *Next-bit Test*.
* **Hard-Core Predicate (HCP):** L'atomo di imprevedibilità legato a funzioni unidirezionali.
* **Generatore di Goldwasser-Micali (BBS):** Costruzione di stringhe sicure basata sulla fattorizzazione e sui residui quadratici (Falsi Quadrati).
* **Sintesi Logica:** Dimostrazione della sicurezza computazionale tramite riduzione.

### 4. Integrità del Testo Cifrato
* **Pseudo Random Functions (PRF):** Differenze con i PRG e capacità di accesso casuale.
* **Message Authentication Code (MAC):** Protocolli per garantire l'integrità e l'autenticità dei dati.
* **Sintesi Logica:** Transizione dalla protezione della riservatezza (Privacy) alla protezione della manomissione (Authenticity).

### 5. Crittografia Asimmetrica
* **Modello a Chiave Pubblica:** Fondamenti della crittografia asimmetrica.
* **One Way Trapdoor Functions:** Funzioni unidirezionali con "botola" segreta.
* **Diffie-Hellman (PKDH):** Protocollo di scambio delle chiavi su canali non sicuri.
* **RSA:** Implementazione basata sulla difficoltà di fattorizzazione di interi.
* **Firma Digitale e Funzioni Hash:** Meccanismi di autenticazione e verifica dell'integrità del messaggio.
* **Sintesi Logica:** Il legame tra complessità computazionale e distribuzione delle chiavi.

### 6. Protocolli Avanzati e Applicazioni
* **Oblivious Transfer:** Trasferimento di informazione con limitazione della conoscenza.
* **Bit Commitment:** Protocolli per l'impegno di un valore senza rivelarlo anticipatamente.
* **Secret Sharing (Shamir):** Distribuzione del segreto basata sull'interpolazione polinomiale.
* **Dining Cryptographers:** Protocolli per l'anonimato in reti condivise.
* **Zero Knowledge Proofs (ZKP):** Dimostrazioni di conoscenza senza rivelazione di segreti.

---
## Indice Analitico (NETWORK SECURITY) (TODO)
