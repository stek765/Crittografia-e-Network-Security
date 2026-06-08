# Appunti di Crittografia (2025/26)

Stefano Zanolli - Magistrale di Ingegneria e Scienze Informatiche

---

## Argomenti:

---

1. INTRODUZIONE

---

- Teoria dei numeri
- COLLEGA GLI ARGOMENTI

---

1. CRITTOGRAFIA ASIMMETRICA

---

- Crittografia Asimmetrica
- One Way Trapdoor Functions
- Diffie-Hellman - asimmetrico (PKDH)
- RSA
- COLLEGA GLI ARGOMENTI
- Firma digitale e Hash

---

1. PRG e CRITTOGRAFIA SIMMETRICA

---

- crittografia simmetrica
- PRG (Pseudo Random Generators)
- XOR
- Cifratura simmetrica a blocchi
- COLLEGA GLI ARGOMENTI

---

1. SICUREZZA di una PRG

---

- Teorema di Yao (Next-bit test)
- HCP (Hard-Core predicate)
- Generatore di Goldwasser-Micali (BSS)
- COLLEGA GLI ARGOMENTI

---

1.  INTEGRITY del CIPHERTEXT

---

- PRF (Pseudo Random Functions) e MAC
- COLLEGA GLI ARGOMENTI

---

1. USI “CREATIVI” E UTILI DELLA CRITTOGRAFIA

---

- Oblivious transfer
- Bit commitment
- Secret sharing (Shamir)
- Dining cryptographers
- ZKP (Zero knowledge proofs )

---

## 1. INTRODUZIONE:

### Teoria dei numeri (parte 1)

![1.JPG](Appunti%20di%20Crittografia%20(2025%2026)/1.jpg)

![2.JPG](Appunti%20di%20Crittografia%20(2025%2026)/2.jpg)

---

## COLLEGA GLI ARGOMENTI (Preview completa)

![IMMAGINE DEFINITIVA.png](Appunti%20di%20Crittografia%20(2025%2026)/IMMAGINE_DEFINITIVA.png)

È prematuro mostrare quest’immagine, ma è utile per dare contesto.
Utilizzerò quest’immagine componendola durante gli appunti un blocchetto alla volta in modo da non perdere mai di vista come ogni argomento si collega al suo successivo. 

---

---

### Teoria dei numeri (parte 2)

Introduzione teorica prima di affrontare la Crittografia Asimmetrica:

![3.JPG](Appunti%20di%20Crittografia%20(2025%2026)/3.jpg)

![4.JPG](Appunti%20di%20Crittografia%20(2025%2026)/4.jpg)

![5.JPG](Appunti%20di%20Crittografia%20(2025%2026)/5.jpg)

---

## 2. CRITTOGRAFIA ASIMMETRICA

Invece di affrontare gli argomenti in blocco unendo crittografia Simmetrica e poi Asimmetrica, ho scelto di andare seguendo uno schema un pò più logico, facendomi la seguente domanda: 

*” Se la crittografia si basa su una chiave, a prescindere da come venga usata, il PRIMO ostacolo vero è capire come questa chiave può essere scambiata tra 2 o più persone su internet no? “*

La risposta  ci conduce al primo argomento vero del corso:  La Crittografia Asimmetrica.

---

### DEFINIZIONE PRO E CONTRO:

La Crittografia Asimmetrica funziona con 2 chiavi che hanno ruoli distinti:
- una chiave PUBBLICA viene usata dagli altri per **cifrare** nei miei confronti, 
- l’altra è PRIVATA (segreta) e serve ad invertire il processo, ovvero **decifrare** i messaggi che mi arrivano.

PRO: 

- Risolvono il problema dello scambio della chiave su internet (Tutti utilizzano le chiavi pubbliche per cifrare e private per decifrare i propri messaggi senza bisogno di scambi).
- Introducono altri vantaggi che poi vedremo come la Firma Digitale per garantire proprietà fondamentali della sicurezza come “AUTHENTICITY” e “INTEGRITY”.

CONTRO:

- Il difetto più grande è la loro lentezza computazionale, se dovessimo usarle per cifrare e decifrare ogni messaggio, Internet si pianterebbe.  Per questo il loro utilizzo si limita quasi sempre a creare un tunnel sicuro in cui scambiare la VERA chiave di cifratura, la chiave simmetrica.
- Inoltre algoritmi come RSA hanno problemi di padding e prevedibilità su messagi brevi, e problemi di malleabilità (Malleability attack).

---

### ONE-WAY TRAPDOOR FUNCIONTS

Le One-Way Trapdoor Functions sono operazioni semplicissime nell’andare in una direzione, 
one-way, ma computazionalmente impossibili nel tornare indietro, così impossibili da basare la maggior parte della nostra sicurezza oggi giorno su di esse.

Le abbiamo gia viste ma le rielencherò qui sotto in modo schematico: 

|                   **Problema** |            **Formula / Definizione** |                        **Intrattabilità (Difficoltà)** |
| --- | --- | --- |
| **1. LOGARITMO DISCRETO** | $g^x \equiv h \pmod{p}$ | Conoscendo la base $g$ $$ e il risultato $h$, è impossibile trovare l'esponente $x$ se  $p$ ha centinaia di cifre. |
| **2. FATTORIZZAZIONE** | $n = p \times q$ | Dato un numero enorme $n$, è impossibile risalire ai due fattori primi $p$ e $q$ che lo hanno generato. |
| **3. RADICE QUADRATA** | $x^2 \equiv a \pmod{n}$ | Dato $a$, stabilire se esiste un $x$ tale che elevato al quadrato dia $a$ È difficile quanto fattorizzare $n$. |
| **4. INDISTINGUIBILITÀ (QRP)** | $Vero \times Falso = Falso$  | Senza conoscere i fattori di $n$, è impossibile distinguere un "vero quadrato" da un "falso quadrato" (pseudo-residuo). |

---

### DIFFIE-HELLMAN (PKDH)

![6.JPG](Appunti%20di%20Crittografia%20(2025%2026)/6.jpg)

*Note*: I **gruppi Diffie-Hellman** sono set di parametri matematici ($q, \alpha$) standardizzati e testati per garantire la massima robustezza contro il calcolo dei logaritmi discreti. Usare parametri fissi assicura l'interoperabilità tra dispositivi e permette ai **firewall** di convalidare istantaneamente il livello di sicurezza della connessione senza bloccarla. 

---

### RSA

![7.JPG](Appunti%20di%20Crittografia%20(2025%2026)/7.jpg)

---

## COLLEGA GLI ARGOMENTI

![COLLEGAMENTO_1.png](Appunti%20di%20Crittografia%20(2025%2026)/COLLEGAMENTO_1.png)

Ecco che piazziamo il primo blocco, quello dello Scambio della chiave da cui partiremo per fare la vera cifratura di un messaggio e molto altro ancora. 

Aggiungo qui sotto altri 2 argomenti importanti, la Firma Digitale e la funzione di Hash.

---

### FIRMA DIGITALE e HASH

![8.JPG](Appunti%20di%20Crittografia%20(2025%2026)/8.jpg)

### DSS (Digital Signature Standard)

**Cos'è**: È lo standard NIST (FIPS 186) per la firma digitale. È un documento/manuale delle regole.

**A cosa serve**: Serve solo a "firmare" i messaggi, non a cifrarli o a scambiare chiavi (a differenza di RSA).  

**Cosa garantisce**:
    1. **Autenticità**: Sei sicuro di chi ha firmato.  

    2. **Integrità**: Il messaggio non è stato alterato.  

    3. **Non ripudio**: Chi firma non può negare di averlo fatto.  

**Algoritmi inclusi**: Supporta principalmente **DSA**, **RSA** e **ECDSA** (Curve Ellittiche).  

---

In breve: Il DSS è il "regolamento" ufficiale che dice come mettere una firma digitale valida su un documento.

---

---

### COLLEGA GLI ARGOMENTI

![COLLEGAMENTO_4.png](Appunti%20di%20Crittografia%20(2025%2026)/COLLEGAMENTO_4.png)

---

---

## 4.  PRG e CRITTOGRAFIA SIMMETRICA

Ora entriamo nel cuore della crittografia, parlando dell’idea Teorica dei generatori PRG e della loro traduzione nel mondo reale in algoritmi diventati fondamentali nella vita di tutto i giorni per proteggere i nostri dati, come l’AES. 

---

### CRITTOGRAFIA SIMMETRICA (storia)

Partiamo da un pò di storia, parleremo di cosa sta alla base di ogni algoritmo di cifratura simmetrico e per cosa viene utilizzato, iniziamo.

La Crittografia Simmetrica è una crittografia basato su un’unica chiave che deve essere condivisa tra 2 o più persone, orientata alla performance. Algoritmi come dicevo prima l’AES opera in modo meccanico a velocità elevatissime ma il difetto è proprio il problema del passarsi una chiave in modo sicuro, ed è il motivo per cui esiste la crittografia asimmetrica.

Tutto si basa su 2 regole inviolabili dettate da uno dei padri della crittografia, Claude Shannon:

- CONFUSIONE: l’algoritmo deve distruggere ogni legame logico tra la chiave segreta e il testo                            cifrato, solitamente tramite sostituzione (usando delle tabelle dette S-Box).
- DIFFUSIONE:    l’algoritmo deve garantire che cambiando anche un solo bit di entrata,                                         l’output dovrà propagare questa modifica in modo che almeno la metà dei bit                            di uscita cambi completamente.

Algoritmi  Storici: 

![9.JPG](Appunti%20di%20Crittografia%20(2025%2026)/9.jpg)

---

## APPROFONDIMENTO: DES vs AES

Ripartiamo dai concetti iniziali, ripartiamo da Claude Shannon e Feistel, PRG e HCP.

![                                       **FEISTEL (DES)**](Appunti%20di%20Crittografia%20(2025%2026)/Screenshot_2026-05-02_alle_16.44.27.png)

                                       **FEISTEL (DES)**

![                             SP - NETWORK (AES)](Appunti%20di%20Crittografia%20(2025%2026)/Screenshot_2026-05-02_alle_16.44.39.png)

                             SP - NETWORK (AES)

### 1. FEISTEL (a sinistra)

È quella che abbiamo visto finora (usata da algoritmi come  DES o Camellia (TLS lo usa spesso)).

- **Come lavora:** la funzione **F** prende la metà destra, usa la chiave come istruzione e le **S-Box** per creare confusione. Quando il risultato "caotico" esce dalla funzione e colpisce la metà sinistra tramite lo **XOR**, l'operazione propaga quel cambiamento bit per bit: ogni singolo bit alterato dalla S-Box forza il bit corrispondente della metà sinistra a invertirsi, "infettandola" matematicamente. (usa n sottochiavi quante i round)
- **Il vantaggio:** È molto comoda perché per decifrare basta fare i passaggi al contrario, usando la stessa identica struttura.

### 2. SPN (a destra - usata da AES)

Invece di dividere a metà, la SPN lavora su **tutto il blocco contemporaneamente**. Le lettere che vedi nell'immagine (S e P) sono esattamente quello che abbiamo spiegato prima:

- **S (Substitution):** È la **Confusione**. Prende i bit a pezzetti (S1, S2, S3, S4) e li sostituisce usando le S-Box.
- **P (Permutation):** È la **Diffusione**. Prende tutti i bit usciti dalle S-Box e li incrocia (quelle linee che si intrecciano nell'immagine), spalmandoli su tutto il blocco.

### Qual è la differenza fondamentale?

- **In Feistel:** In ogni round modifichi solo **metà** del messaggio. Serve quindi un numero maggiore di round (giri) per raggiungere l'effetto valanga su tutto il blocco.
- **In SPN:** In ogni round modifichi **tutto** il messaggio in un colpo solo. Questo la rende potenzialmente più veloce e aggressiva nel creare confusione, ma richiede componenti matematiche più complesse per poter tornare indietro (decifrare).

---

### PRG (Pseudo Random Generators)

Partiamo dal rispondere ad una domanda: Che cos’è una PRG??

Una PRG non è altro che una funzione che prende in ingresso una chiave (denominata SEED), che non è altro che la nostra chiave simmetrica Master Key che ci siamo passati prima tramite Diffie-Hellman per esempio, per generare una stringa di bit pseudo-casuali infinita.

In realtà non è esattamente quella la chiave utilizzata, di fatto per comodità si derivano chiavi secondarie per i vari compiti partendo dalla Master Key. 
Tramite una KDF (Key Derivation Functions), vengono generate dalle corrispettive parti (quindi sia da Alice che da Bob) delle chiavi derivate.

Dicevamo, la PRG, che segue l’idea del ‘One-Time Pad’ , prende in ingresso questa chiave derivata (seed) e lo frulla attraverso una formula matematica per sputare fuori una sequenza chilometrica di numeri (stringa).
Questa lunghissima sequenza è "pseudo-casuale": per un hacker sembra totalmente imprevedibile (come una cascata di dadi lanciati a caso), ma in realtà se conoscesse il *seme* iniziale potrebbe ricreare l'esatta sequenza.

**A cosa serve in pratica?** Per i computer generare il caso "vero" (tipo misurare le variazioni di temperatura del processore) è un processo lentissimo. Il PRG risolve il problema: prende un pizzico di vera casualità e lo espande istantaneamente per creare tonnellate di numeri sicuri.

⇒ La traduzione nel mondo reale della PRG è per esempio l’AES visto prima che però ha dei limiti.

---

### XOR - $\oplus$

| **Input A** | **Input B** | **Risultato (A ⊕ B)** |
| --- | --- | --- |
| 0 | 0 | **0** |
| 0 | 1 | **1** |
| 1 | 0 | **1** |
| 1 | 1 | **0** |

In crittografia lo XOR è l’unica operazione che garantisce la Perfect Secrecy se combinato con un bit casuale, ovvero il risultato finale avrà sempre probabilità $\frac{1}{2}$ di essere 1 e probabilità $\frac{1}{2}$ di essere 0. 

                         **Testo ⊕ Chiave = Cifrato    →      Cifrato ⊕ Chiave = Testo**

---

### CIFRATURA SIMMETRICA A BLOCCHI

Fino a questo momento, ho omesso un particolare intenzionalmente perchè rendeva più intuitivo tutto il processo: ovvero che questa stringa infinita generata dalla PRG, va tagliata a blocchi ed eseguito lo XOR con il messaggio in chiaro anche lui diviso in blocchi della stessa dimensione.(Proprio per rispettare l’algoritmo di One-Time-Pad).

Questo ci porta ad un problema non indifferente della crittografia simmetrica, ovvero che è a blocchi! 
Non esiste una funzione che macini tutto quanto il messaggio in un colpo solo, ed è proprio questo il limite dell’AES a cui mi riferivo prima, ovvero che l’algoritmo lavora su blocchi di bit molto piccoli alla volta e questo crea dei problemi di sicurezza.

![10.png](Appunti%20di%20Crittografia%20(2025%2026)/10.png)

### QUINDI:  l’algoritmo spezza il messaggio in blocchi, spezza la stringa generata casuale (PRG) in blocchi e fa lo XOR tra blocchi usando ECB/CBC/CTR. 

Alla fine ricompatta tutto in un unico blocco cifrato finale!

---

### APPROFONDIMENTO (CURIOSITÀ):

Esiste un cifrario a blocchi moderno usato comunemente con l'**AES-XTS** (XEX Tweakable Block Cipher with Ciphertext Stealing).

### AES-XTS (Full Disk Encryption)

L'**AES-XTS** è lo standard industriale per la crittografia degli interi dischi rigidi (usato da BitLocker, FileVault, LUKS). Nasce per risolvere due vincoli fisici insormontabili degli hard disk:

1. **Dimensione Fissa:** I settori del disco (es. 4 KB) non hanno spazio extra. Se entrano 4 KB in chiaro, devono uscire 4 KB cifrati. Non si possono aggiungere metadati (come IV o Nonce).
2. **Accesso Casuale Rapido:** Il processore deve poter decifrare istantaneamente il settore 1.000.000 senza dover scorrere i precedenti.

***Il Rischio:*** Senza metadati, usare un AES standard produrrebbe un difetto fatale: salvare lo stesso identico file (es. blocchi di zeri) in settori diversi genererebbe lo stesso output cifrato, rivelando la struttura del disco agli hacker.

***La Soluzione:* La Doppia Chiave e il "Tweak"**
L'AES-XTS risolve il problema ancorando la crittografia alla *posizione fisica* del dato. Divide la chiave principale in due sotto-chiavi:

- **Chiave 1 (Generazione del Tweak):** Prende l'indirizzo fisico del settore sul disco (LBA) e lo cifra. Il risultato è il **Tweak**, una variabile matematica unica per quel preciso settore.
- **Chiave 2 (Cifratura Dati):** Esegue l'algoritmo AES standard.

***Il Meccanismo (XOR-Encrypt-XOR)***
Il processo avviene in tre micro-fasi esatte:

1. Il dato in chiaro viene fuso matematicamente (XOR) con il Tweak.
2. Il blocco risultante subisce la cifratura AES tramite la Chiave 2.
3. L'output cifrato viene fuso nuovamente (XOR) con il Tweak.

***Risultato Architetturale:***
Poiché l'equazione include l'indirizzo fisico, scrivere lo stesso identico file sul Settore 10 e sul Settore 500 produrrà due ciphertext **radicalmente diversi**. Il sistema garantisce accesso casuale istantaneo e azzera i pattern visibili, senza aggiungere un singolo byte di peso.

---

### COLLEGA GLI ARGOMENTI

![COLLEGAMENT_2.png](Appunti%20di%20Crittografia%20(2025%2026)/COLLEGAMENT_2.png)

Abbiamo visto come scambiarsi una master key, che dopo una KDF diventa il nostro seme (SEED) con cui attivare l’algoritmo di cifratura simmetrico, ovvero una PRG come AES che per ovviare al problema di cifrare un pezzo alla volta utilizza il CTR durante il processo e ottiene come risultato un unico blocco finale che è propri il nostro messaggio CIFRATO!

C’è un problema ora: come sappiamo se la nostra PRG è sicura?

---

---

## 5. SICUREZZA DI UNA PRG

Ecco la spiegazione rigorosa di come tre concetti più teorici si legano per  provare che un Generatore Pseudo-Casuale (PRG) è sicuro.

---

### 1) TEOREMA DI YAO (NEXT-BIT TEST)

Nella crittografia moderna, non possiamo accontentarci di numeri che "sembrano" casuali. Ci serve una prova formale. Il Teorema di Yao fornisce esattamente questo: una definizione matematica di cosa renda un PRG crittograficamente sicuro.

**Il concetto:**
Yao introduce il Next-Bit Test (Test del bit successivo). Immagina che un avversario (un algoritmo con una potenza di calcolo realistica) osservi i primi $n$ bit generati da uno PRG. 
Il test stabilisce che il generatore è sicuro se e solo se l'avversario non ha alcun metodo per prevedere il bit $n+1$, con una probabilità significativamente superiore al 50%.

**La validità pratica:**
Yao ha dimostrato matematicamente che se una sequenza supera questo test, è "computazionalmente indistinguibile" da una sequenza veramente casuale. 

**In pratica:** se non puoi prevedere il bit successivo, l'intera stringa è crittograficamente solida. 

La sfida ingegneristica diventa quindi una sola: come generiamo una serie di bit dove il successivo è sempre imprevedibile?

---

### **2) HCP (HARD-CORE PREDICATE)**

Per superare il test di Yao, ci serve una fonte di imprevedibilità garantita. Qui entra in gioco l'HCP (Hard-Core Predicate).

**Il concetto:**
In crittografia lavoriamo con le **Funzioni One-Way** (funzioni unidirezionali), operazioni matematiche facilissime da calcolare in un senso, ma impossibili da invertire (es. la moltiplicazione di due numeri primi giganti è facile, la fattorizzazione del risultato è difficilissima).
L'HCP è **un singolo bit di informazione** associato all'input di questa funzione.

**La proprietà fondamentale:**
La teoria dell'HCP dimostra che, conoscendo solo l'output della funzione, indovinare il valore di quello specifico bit (l'HCP) è matematicamente complesso **esattamente quanto lo è invertire l'intera funzione unidirezionale**.

**L'impatto pratico:**
Abbiamo appena trovato la nostra "ancora di sicurezza". Se basiamo la sicurezza del nostro sistema su un problema matematico che richiede milioni di anni per essere risolto, l'HCP ci garantisce che indovinare quel singolo bit richiederà lo stesso identico tempo e sforzo computazionale.

---

### 3) GENERATORE DI GOLDWASSER-MICALI (BBS)

Ora abbiamo la regola (Yao) e il materiale grezzo (l'HCP). L'architettura logica che li unisce serve a costruire un PRG dove la sicurezza non è un'opinione, ma una certezza matematica legata alla **difficoltà della fattorizzazione**.

**Il concetto:**
Blum e Micali hanno progettato un sistema iterativo. Il loro algoritmo utilizza il problema dei Residui Quadratici per generare il bit HCP successivo da mettere nella stringa.

**Come opera l'algoritmo:**
1. **Inizializzazione:** Si parte da un valore segreto iniziale (il *seed* o seme), che chiamiamo $x_0$.
2. **Estrazione e Iterazione:** Il sistema calcola il valore successivo $x_1$ applicando la funzione unidirezionale a  $x_0$. Contemporaneamente, **estrae l'HCP** del valore corrente. Questo HCP diventa il primo bit ufficiale della stringa in output.
3. **Il Loop:** Il processo si ripete. $x_1$ viene usato per calcolare $x_2$, estraendo un nuovo HCP (il secondo bit dell'output). E così via.

**La sintesi logica:**
Poiché ogni singolo bit generato è un Hard-Core Predicate protetto dalla difficoltà di fattorizzare numeri giganti, la sua imprevedibilità è garantita. Nessun hacker può indovinare se il bit successivo sarà 0 o 1 con una probabilità migliore del lancio di una moneta.

Essendo ogni bit singolarmente imprevedibile, la stringa infinita generata **soddisfa rigorosamente il Next-Bit Test di Yao**. Abbiamo così ottenuto un PRG di cui possiamo dimostrare l'assoluta sicurezza computazionale.

**(Nota):** Il meccanismo è identico per il Blum-Micali classico (Logaritmo Discreto) e per il Blum-Blum-Shub/Goldwasser-Micali (Falsi Quadrati). Cambia solo il la funzione unidirezionale usata.

Nella sua teoria Micali utilizza la figura del Distinguisher per dimostrare per assurdo che un attaccante  vedendo cambiare da un messaggio1 cifrato a un messaggio2 cifrato un bit alla volta, non potrebbe che avere il 50% di probabilità di indovinare e non un punto in più.
Se avesse anche solo il  51%, utilizzando il limite di Chernoff raggiungerebbe il 100% di accuratezza facendo saltare la sicurezza della stringa.

---

### COLLEGA GLI ARGOMENTI

![COLLEGAMENTO_3.png](Appunti%20di%20Crittografia%20(2025%2026)/COLLEGAMENTO_3.png)

Con questo capitolo  ci siamo fermati e abbiamo realizzato una cosa  importante: 
Possiamo AFFERMARE che la nostra PRG è sicura e sappiamo il perchè grazie a Yao e Micali.

Ora il passo successivo è un altro: garantire che nessuno manometta il pacchetto durante il viaggio!

---

---

## **Approfondimento: Dalla Teoria alla Realtà (CSPRNG)**

Per comprendere come i sistemi informatici generino numeri casuali sicuri (alla base di chiavi RSA, Wi-Fi o TLS), è necessario distinguere tra il modello matematico teorico (perfetto ma lento) e l'ingegneria del mondo reale (veloce e sicura).

Questi sistemi prendono il nome di **CSPRNG** (***Cryptographically Secure Pseudo-Random Number Generators***).

---

### **BASE TEORICA (ripasso pre-spiegazione)**

Come gia visto nella parte di Crittografia, l'idea teorica alla base della generazione casuale sicura sfrutta problemi matematici complessi (come la fattorizzazione di grandi numeri o il logaritmo discreto) abbinati al concetto di **HCP (Hard-Core Predicate)**.

Come prima, l'algoritmo teorico più celebre basato su questa idea è il **Blum Blum Shub (BBS)**. 

*Funziona così:*

1. **Inizializzazione:** Si sceglie un grande numero $N$ (prodotto di due numeri primi, come in RSA) e un valore segreto di partenza (*Seed*).

---

2. **La Funzione Unidirezionale:** Ad ogni ciclo, il sistema esegue un calcolo facile in una direzione ma impossibile da invertire senza conoscere i fattori (es. l'elevamento al quadrato modulo $N$).

---

3. **Estrazione del Bit (HCP):** Dal risultato di questo calcolo, il sistema estrae un solo bit (ad esempio, l'ultimo bit, o bit meno significativo). La matematica dimostra che indovinare questo singolo bit estratto equivale a risolvere l'intero problema della fattorizzazione.

---

4. **Iterazione:** Il risultato viene re-inserito nella funzione per estrarre il bit successivo, creando una stringa infinita.

---

**Il problema:** Questo approccio offre una sicurezza matematica assoluta (dimostrabile), ma è computazionalmente insostenibile. Richiede calcoli su numeri di migliaia di bit solo per produrre un singolo "1" o "0". Se un server dovesse generare megabyte di chiavi al secondo usando il BBS, collasserebbe.

---

### **1. SOLUZIONE REALE (Architettura dei CSPRNG moderni)**

L'obiettivo di un CSPRNG è trasformare una piccola quantità di rumore fisico (entropia) in un flusso infinito e matematicamente imprevedibile di bit. Da questo flusso, il sistema si limiterà a “tagliare” dei blocchi della lunghezza che gli servono, ogni volta che un protocollo richiederà la creazione di una nuova chiave.

**Fase A: La Raccolta dell'Entropia (Il Seme Iniziale)**
Poiché il computer non può generare casualità dal nulla, il Sistema Operativo utilizza un "raccoglitore di entropia" che campiona eventi fisici misurabili ma crittograficamente imprevedibili dell'hardware:

• I millisecondi di latenza tra gli input della tastiera o i movimenti del mouse.
• Il rumore termico e le fluttuazioni microscopiche di voltaggio della CPU.
• I tempi esatti di accesso ai settori dei dischi di memoria.

Questi dati ambientali vengono processati (tipicamente tramite funzioni di Hash) per generare un **Seme (Seed)** iniziale denso e puramente casuale (es. 256 bit).

**Fase B: L'Espansione tramite AES-CTR**
Il Seme fisico iniziale si genera lentamente. Per fornire ai protocolli di rete gigabyte di numeri casuali senza latenza, il sistema utilizza l'algoritmo AES.
 In questo contesto, l'AES non viene usato per garantire la riservatezza di un messaggio, ma come Funzione Pseudo-Casuale (PRF):

1. **Inizializzazione:** Il sistema usa il Seme fisico appena raccolto come Chiave Segreta dell'algoritmo AES.

2. **Input Sequenziale:** Prende un contatore numerico standard (il numero `1`) e applica un padding di zeri per raggiungere la dimensione di blocco fissa di 128 bit richiesta dall'AES (`0000...00000001`).

3. **L'Elaborazione:** L'AES elabora questo blocco fondendolo con la chiave segreta attraverso 14 round di sostituzioni e permutazioni non lineari (tramite le S-Box). L'output risultante è un blocco di 128 bit crittograficamente non correlato all'input.

4. **L'Effetto Valanga:** Il sistema inserisce nel calcolo il contatore successivo, il `2` (`0000...00000010`). Sebbene differisca dal precedente per un singolo bit, l'architettura matematica dell'AES innesca un "effetto valanga": l'output a 128 bit sarà radicalmente diverso e imprevedibile rispetto al blocco precedente.

5. **Velocità Hardware:** Iterando il contatore (`3, 4, 5...`), il processore genera un flusso continuo di bit pseudo-casuali. Sfruttando i set di istruzioni hardware dedicati all'AES presenti nelle CPU moderne (AES-NI), il sistema produce miliardi di bit sicuri al secondo senza saturare le risorse di calcolo.

---

### 2. APPLICAZIONE (Generazione delle chiavi RSA)

Questo flusso continuo di bit pseudo-casuali viene utilizzato dai protocolli di sicurezza per istanziare parametri crittografici. Nel caso dell'RSA, l'obiettivo iniziale è individuare due numeri primi sufficientemente grandi ($p$ e $q$).

1. **Estrazione:** Il sistema preleva dal flusso generato dal CSPRNG un blocco di bit della lunghezza necessaria (es. 2048 bit continui).

2. **Formattazione del Candidato:** Per ottimizzare i tempi di calcolo, il sistema manipola i margini del blocco estratto: forza l'ultimo bit a `1` (garantendo che il numero sia dispari, poiché un numero pari non può essere primo) e forza il primo bit a `1` (garantendo che il numero abbia effettivamente una magnitudo di 2048 bit). Si ottiene così il "Candidato P".

**3. Test di Miller-Rabin e Loop di Scarto**
Per la legge matematica della densità dei numeri primi, a grandezze crittografiche (es. 2048 bit) la probabilità di estrarre casualmente un numero primo è bassissima (circa 1 su 700). Poiché il fallimento è l'esito statisticamente quasi certo, l'ingegneria informatica non cerca una formula magica per generare il numero perfetto al primo colpo, ma compensa questa rarità matematica con la pura velocità hardware, procedendo per scarti rapidissimi.

Il sistema agisce in tandem:

- **Il Filtro (Test di Miller-Rabin):** Il "Candidato P" subisce il test probabilistico di Miller-Rabin. Invece di tentare una lentissima fattorizzazione, questo algoritmo esegue prove statistiche mirate a "bocciare" i numeri composti in pochi microsecondi. Alla prima iterazione fallita, il candidato è scartato. Solo se le supera tutte, la probabilità che sia primo sfiora il 100% (es. 99,9999%).
- **Il Loop (Forza Bruta):** Nel millisecondo esatto in cui un candidato viene bocciato, il sistema taglia istantaneamente un nuovo segmento di 2048 bit dal flusso inesauribile del CSPRNG, lo formatta e riavvia il test.

Grazie a questo ciclo continuo, il processore testa e scarta migliaia di candidati al secondo finché non "fa centro". Il numero validato diventa ufficialmente il parametro **P**. A quel punto, il loop si azzera e la spietata selezione riparte da capo per individuare **Q**, fornendo infine i due pilastri per generare l'intera chiave RSA.

---

### PRF (Pseudo Random Functions)

la fase di applicazione di cui parlavamo prima tagliando la stringa generata, si traduce nell’utilizzo dei PRF. 
A differenza del PRNG (che genera un flusso continuo e generico), il PRF prende il Seed e lo fonde con dei valori di contesto, quali possono essere un User ID o un App ID.

![               le 3 fasi del CSPRNG (entropia-PRG-applicazione)](Appunti%20di%20Crittografia%20(2025%2026)/Screenshot_2026-05-03_alle_19.43.56.png)

               le 3 fasi del CSPRNG (entropia-PRG-applicazione)

---

## 6. INTEGRITY DEL CIPHERTEXT

---

Per garantire che il nostro messaggio cifrato (ciphertext) non venga manomesso durante il suo viaggio verso Bob, utilizziamo le Pseudo Random Functions, un concetto simile alle PRG di prima.

### PRF (PSEUDO RANDOM FUNCTIONS) e  MAC

![11.JPG](Appunti%20di%20Crittografia%20(2025%2026)/11.jpg)

![12.JPG](Appunti%20di%20Crittografia%20(2025%2026)/12.jpg)

### La differenza strutturale: PRNG vs. PRF

Per capire la PRF, dobbiamo contrapporla al PRNG che abbiamo studiato finora.

- **Il PRNG ha una "memoria" (Stateful):** Come abbiamo visto con l'AES-CTR, il PRNG si avvia con un Seme e poi mantiene un contatore interno (1, 2, 3...). Ogni volta che gli chiedi dei bit, lui avanza e ti dà bit nuovi. Se perdi il conto di dove è arrivato, non puoi ricostruire il flusso. Serve per generare materiale *nuovo e indipendente*.
- **La PRF è "senza memoria" (Stateless):** Non ha contatori che avanzano da soli. Non genera nulla finché non le dai i parametri. Serve per generare materiale *riproducibile e mirato*. Se due computer diversi (es. il tuo PC e il server di Google) inseriscono gli stessi dati nella stessa PRF, ottengono lo stesso risultato.

A differenza del PRNG (che genera un flusso continuo e generico), il PRF prende il Seed e lo fonde con dei valori di contesto, quali possono essere un User ID o un App ID.

---

### COLLEGA GLI ARGOMENTI

![IMMAGINE DEFINITIVA.png](Appunti%20di%20Crittografia%20(2025%2026)/IMMAGINE_DEFINITIVA%201.png)

Siamo arrivati alla fine del percorso, abbiamo visto come la crittografia asimmetrica ci permette di scambiare una chiave master key, da cui deriviamo una chiave che utilizziamo per cifrare i nostri dati tramite una PRG (AES-CTR per esempio) sicura grazie alle fondamenta teoriche di Yao e Micali. 
La stringa a blocchi viene XORata al Plaintext per ottenere il Ciphertext a cui aggiungiamo il timbro inserendo nel messaggio un MAC finale (CBC-MAC per esempio). 

Finalmente abbiamo un messaggio sicuro e impossibile da manomettere pronto per essere spedito a Bob!

---

## 7. USI “CREATIVI” E UTILI DELLA CRITTOGRAFIA

![IMG_4753.JPG](Appunti%20di%20Crittografia%20(2025%2026)/IMG_4753.jpg)

(aggiunta al perchè se Bob conosce 2 radici diverse allora vince: Perché la differenza matematica tra queste due radici ($x-y$) condivide un divisore in comune con $n$. 
Calcolando un semplice Massimo Comune Divisore (MCD) tra questa differenza e $n$, estrai all'istante il fattore segreto $p$!)

---

![IMG_4754.JPG](Appunti%20di%20Crittografia%20(2025%2026)/IMG_4754.jpg)

![IMG_4755.JPG](Appunti%20di%20Crittografia%20(2025%2026)/IMG_4755.jpg)

![IMG_4756.JPG](Appunti%20di%20Crittografia%20(2025%2026)/IMG_4756.jpg)

![IMG_4757.JPG](Appunti%20di%20Crittografia%20(2025%2026)/IMG_4757.jpg)

---