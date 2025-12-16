# Dispensa – Concetti di base di Sicurezza Informatica  
*(Information Security – Cybersecurity Basics)*

---

## 0. Introduzione
Nel mondo digitale, dati e sistemi sono diventati fondamentali: documenti di lavoro, foto personali,
credenziali di accesso, servizi online.  
La **sicurezza informatica (Cybersecurity)** ha l’obiettivo di proteggere informazioni e sistemi da:
- accessi non autorizzati  
- modifiche indesiderate  
- interruzioni del servizio  

### Termini chiave
- **Information Security (InfoSec)**: sicurezza delle informazioni su qualsiasi supporto (digitale, cartaceo, ecc.).
- **Cybersecurity**: sicurezza di reti, sistemi, applicazioni e servizi digitali.

---

## 1. La CIA Triad: Confidentiality, Integrity, Availability
La base teorica della sicurezza informatica è la **CIA Triad**.

### 1.1 Confidentiality (Confidenzialità)
Le informazioni devono essere accessibili solo a chi è autorizzato.

**Esempi di controlli:**
- Access control (controlli di accesso)
- Encryption (cifratura dei dati)
- Gestione corretta di username e password

### 1.2 Integrity (Integrità)
I dati devono essere corretti e non alterati in modo non autorizzato.

**Esempi:**
- Checksums
- Digital signatures (firme digitali)
- Controlli sui log e sulle modifiche

### 1.3 Availability (Disponibilità)
I sistemi e i servizi devono essere disponibili quando servono agli utenti autorizzati.

**Esempi:**
- Backup
- Redundancy (ridondanza di server, dischi, link)
- Protezione da DoS/DDoS attacks

### Altri concetti chiave
- **Asset**: qualunque cosa abbia valore (dati clienti, server, database, reputazione aziendale).
- **Threat (Minaccia)**: evento o attore che può causare danno (attacker, incendio, guasto, errore umano).
- **Vulnerability (Vulnerabilità)**: debolezza sfruttabile da una minaccia.
- **Risk (Rischio)**: combinazione di:
  - probabilità che una threat sfrutti una vulnerability
  - impatto del danno sugli asset
- **Authenticity (Autenticità)**: certezza sull’identità di chi comunica.
- **Non-repudiation (Non ripudio)**: impossibilità di negare un’azione svolta.

---

## 2. Tipologie di attaccanti e di attacchi

### 2.1 Threat Actors (Tipi di attaccanti)
- **Script kiddies**
- **Cyber criminals**
- **Insiders**
- **Hacktivists**
- **Nation-state actors**

**Motivazioni tipiche:**
- Financial gain
- Espionage
- Ideology
- Reputation / sfida personale

### 2.2 Attacchi verso la CIA Triad

**Contro la Confidentiality:**
- Furto credenziali
- Sniffing del traffico di rete
- Data breach

**Contro l’Integrity:**
- Manomissione di database
- Alterazione dei log
- Modifica non autorizzata di file di configurazione

**Contro l’Availability:**
- DoS/DDoS attacks
- Cancellazione di dati senza backup
- Sabotaggio di infrastrutture

---

## 3. Malware: Virus, Worm, Trojan, Ransomware…
**Malware** = *malicious software*, creato per causare danni o ottenere vantaggi illeciti.

### Principali tipologie
- **Virus**: si aggancia a file o programmi legittimi.
- **Worm**: si autoreplica e si diffonde via rete.
- **Trojan horse**: software apparentemente legittimo con funzioni malevole.
- **Ransomware**: cifra i dati e chiede un riscatto.
- **Spyware**: raccoglie informazioni sull’utente.
- **Keylogger**: registra i tasti premuti.
- **Adware**: mostra pubblicità invasive.

### Payload e Infection Vector
- **Payload**: cosa fa il malware (cifrare, spiare, cancellare dati).
- **Infection vector**: come entra nel sistema:
  - allegati email
  - chiavette USB
  - download da siti non affidabili
  - exploit di vulnerabilità

---

## 4. AAA: Authentication, Authorization, Accounting

### Authentication – *Who are you?*
Verifica dell’identità dell’utente.  
**Esempi:** username/password, badge, smart card, biometria.

### Authorization – *What can you do?*
Definisce cosa può fare un utente autenticato.  
**Esempi:** permessi, ruoli, gruppi, ACL.

### Accounting – *What did you do?*
Tracciamento delle attività.  
**Esempi:** log di accesso, log applicativi.

### Fattori di autenticazione
- Something you know
- Something you have
- Something you are  

**MFA**: uso di almeno due fattori diversi.

### Password Security
**Problemi comuni:**
- Password deboli
- Riutilizzo delle password
- Condivisione delle credenziali

**Buone pratiche:**
- Passphrase ≥ 12 caratteri
- Evitare dati personali
- Password manager
- MFA attiva

**Attacchi comuni:**
- Brute-force
- Dictionary attack
- Credential stuffing

---

## 5. Network Security – Firewall, NAT, HTTPS, VPN

### 5.1 Concetti di rete
- IP address
- Port
- Protocol  

**Porte comuni:**
- HTTP → 80  
- HTTPS → 443  
- SSH → 22  
- RDP → 3389  

### 5.2 Firewall
Filtra il traffico in base a regole.
- Packet filtering
- Stateful firewall

**Politiche:**
- Default deny (più sicura)
- Default allow (meno sicura)

### 5.3 NAT e rete domestica
- **NAT**: più dispositivi con un solo IP pubblico.
- **Port forwarding**: da usare solo se necessario.

### 5.4 HTTPS e TLS
- HTTP non cifrato
- HTTPS = HTTP + TLS:
  - Encryption
  - Integrity
  - Server authentication

### 5.5 VPN
Crea un tunnel cifrato tra dispositivo e rete remota.
- Protezione su Wi-Fi pubblici
- Remote work

---

## 6. Crittografia

### 6.1 Obiettivi
- Confidentiality
- Integrity
- Authentication
- Non-repudiation

### 6.2 Symmetric Encryption
- Stessa chiave per cifrare/decifrare
- Veloce
- Problema: distribuzione della chiave

### 6.3 Asymmetric Encryption
- Coppia di chiavi: public / private
- Usata in TLS, email cifrate, firme digitali

### 6.4 Hash Functions
- Output a lunghezza fissa
- One-way
- Collision resistant  

**Usi:**
- Password hashing
- Verifica integrità file

### 6.5 Digital Signature e Certificates
- **Digital signature**: integrità, autenticità, non ripudio
- **Digital certificate (X.509)**: lega una public key a un’identità
- Emesso da una **Certificate Authority (CA)**

---

## 7. Human Factor, Social Engineering e Incident Response

### 7.1 Human Factor
L’utente è spesso l’anello più debole:
- click su link malevoli
- allegati sospetti
- USB sconosciute
- aggiornamenti ignorati

### 7.2 Social Engineering
Tecniche basate sulla psicologia:
- Phishing
- Spear phishing
- Smishing
- Vishing
- Pretexting

**Segnali di allarme:**
- urgenza
- richieste di dati sensibili
- errori grammaticali
- mittente sospetto

### 7.3 Security Best Practices
- Sistemi aggiornati
- Antivirus aggiornati
- Backup regolari
- MFA
- Uso limitato di account admin
- Lock screen

### 7.4 Incident Response
**Fasi:**
1. Identification
2. Containment
3. Eradication & Recovery
4. Lessons learned

**Regola per l’utente:**
- segnalare subito
- non cancellare prove
- non improvvisare

---

## 8. Mini Glossario IT/EN
- Information Security (InfoSec)
- Cybersecurity
- CIA Triad
- Asset
- Threat
- Vulnerability
- Risk
- Malware
- Ransomware
- Phishing
- Firewall
- VPN
- Encryption
- Hash function
- Digital signature
- Certificate Authority (CA)
- Multi-Factor Authentication (MFA)
