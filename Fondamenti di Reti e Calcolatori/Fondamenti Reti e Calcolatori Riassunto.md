# Introduzione ai fondamenti di reti di calcolatori  
*(Introduction to Computer Networks)*

---

## 1. Cos’è una rete di calcolatori

### 1.1 Definizione
Una **rete di calcolatori (computer network)** è un insieme di dispositivi (*hosts* o *nodes*), come:
- PC e laptop  
- server  
- smartphone e tablet  
- stampanti di rete  
- dispositivi IoT (smart TV, smart speaker, ecc.)

collegati tra loro tramite un **mezzo di comunicazione (transmission medium)**, ad esempio:
- cavo in rame (*twisted pair*)  
- fibra ottica  
- collegamenti radio (Wi-Fi, 4G/5G, Bluetooth)

con lo scopo di:
- **condividere risorse (resource sharing)**: file, stampanti, applicazioni  
- **scambiarsi dati (data communication)**  
- **fornire servizi di rete (network services)**: web, email, cloud, VoIP  

**Idea chiave:** una rete permette a un dispositivo A di inviare un *data packet* a un dispositivo B,
anche se si trova dall’altra parte del mondo.

### 1.2 Vantaggi delle reti
- **Condivisione delle risorse**
  - una sola stampante di rete per più PC  
  - file server centralizzato  
- **Comunicazione rapida**
  - email  
  - instant messaging  
  - videoconferenze (*video conferencing*)  
- **Affidabilità (reliability)**
  - server ridondanti  
  - percorsi alternativi (*redundant paths*)  
- **Scalabilità (scalability)**
  - possibilità di aggiungere rapidamente nuovi dispositivi (*nodes*)

### 1.3 Esempi di reti nella vita quotidiana
- rete Wi-Fi di casa (*home network*)  
- rete dell’ufficio o della scuola (*enterprise network*)  
- reti dei provider Internet (*ISP networks*)  
- **Internet**: la rete delle reti (*network of networks*)

---

## 2. Tipologie di reti e network topologies

### 2.1 Tipologie in base all’estensione geografica

#### PAN – Personal Area Network
Piccola rete personale (pochi metri).  
**Esempi:**
- smartphone ↔ smartwatch via Bluetooth  
- laptop ↔ cuffie wireless  

#### LAN – Local Area Network
Rete locale (casa, ufficio, laboratorio, aula).

**Caratteristiche:**
- proprietà di una singola organizzazione  
- alta velocità (*high data rate*)  
- tecnologie tipiche: Ethernet, Wi-Fi  

#### MAN – Metropolitan Area Network
Rete che copre un’area metropolitana o una città.  
Spesso gestita da un *service provider*.

#### WAN – Wide Area Network
Rete su scala geografica ampia (paesi, continenti).
- collega sedi aziendali distanti  
- tecnologie: fibra, radio, collegamenti dedicati, MPLS, VPN  

**Internet è una global WAN.**

---

### 2.2 Topologie di rete (*network topologies*)
La **topologia** descrive come i nodi sono collegati tra loro.

#### Bus topology
- tutti i dispositivi collegati a un unico cavo condiviso  
- semplice ma poco robusta  
- oggi quasi solo storica  

#### Star topology
- ogni dispositivo collegato a un nodo centrale (switch)  
- molto usata nelle LAN moderne  
- un guasto a un cavo colpisce solo un dispositivo  

#### Ring topology
- dispositivi collegati ad anello  
- i dati passano da un nodo al successivo  
- usata in reti storiche (es. Token Ring)  

#### Mesh topology (parziale o totale)
- molti collegamenti ridondanti  
- alta affidabilità  
- Internet spesso modellata come una mesh  

**Nota:**  
- *Physical topology* ≠ *Logical topology*  
- logicamente una rete può comportarsi come una stella anche se fisicamente diversa

---

## 3. Modelli a strati: OSI e TCP/IP
Per gestire la complessità, i protocolli di rete sono organizzati in **strati (layers)**.
Ogni layer comunica con:
- il layer superiore (*upper layer*)  
- il layer inferiore (*lower layer*)

### 3.1 OSI Reference Model – 7 layers
Modello teorico a 7 livelli:

1. **Physical Layer**
   - trasmissione di bit  
   - segnali elettrici, ottici, radio  
   - cavi, connettori, hub  

2. **Data Link Layer**
   - unità di dati: *frame*  
   - indirizzi MAC  
   - rilevazione errori locali, controllo accesso al mezzo (MAC)

3. **Network Layer**
   - unità di dati: *packet*  
   - routing tra reti  
   - protocollo principale: IP  

4. **Transport Layer**
   - unità di dati: *segment* (TCP), *datagram* (UDP)  
   - comunicazione end-to-end  
   - protocolli: TCP, UDP  

5. **Session Layer**
   - gestione delle sessioni di comunicazione  

6. **Presentation Layer**
   - data translation  
   - compression  
   - encryption  

7. **Application Layer**
   - servizi applicativi: HTTP, FTP, SMTP, DNS, ecc.

> Il modello OSI è soprattutto didattico, ma molto utile per comprendere le funzioni di rete.

---

### 3.2 TCP/IP Protocol Suite – 4 layers
Modello reale usato in Internet:

1. **Link Layer**
   - Physical + Data Link OSI  
   - Ethernet, Wi-Fi  

2. **Internet Layer**
   - equivalente al Network Layer OSI  
   - protocollo: IP  

3. **Transport Layer**
   - TCP, UDP  

4. **Application Layer**
   - HTTP/HTTPS, DNS, SMTP, FTP, ecc.

### 3.3 Metafora della lettera
- Application → contenuto della lettera  
- Transport → tipo di spedizione  
- Internet/Network → strade e città  
- Link → postino e infrastruttura fisica  

---

## 4. Indirizzamento IP – IP Addressing

### 4.1 Perché serve un indirizzo IP?
L’**IP address** identifica in modo univoco:
- la **rete**  
- l’**host** all’interno della rete  

### 4.2 IPv4 – struttura di base
- 32 bit  
- *dotted decimal notation*: `192.168.1.10`  
- 4 ottetti (0–255)

**Subnet mask e CIDR:**
- Subnet mask: `255.255.255.0`  
- CIDR: `192.168.1.10/24`

### 4.3 Indirizzi privati e pubblici
**Range privati IPv4 (RFC 1918):**
- 10.0.0.0 – 10.255.255.255  
- 172.16.0.0 – 172.31.255.255  
- 192.168.0.0 – 192.168.255.255  

**Indirizzi speciali:**
- loopback: `127.0.0.1`  
- default gateway: IP del router (es. `192.168.1.1`)

### 4.4 Cenni su IPv6
- 128 bit  
- notazione esadecimale  
- spazio di indirizzi enorme  
- migliore supporto a sicurezza e autoconfigurazione  

---

## 5. Protocolli fondamentali

### 5.1 MAC address ed Ethernet
- indirizzo fisico della NIC  
- 48 bit, esadecimale  
- usato nel Data Link Layer  

**Ethernet:**
- tecnologia LAN più diffusa  
- unità di dati: *Ethernet frame*

### 5.2 ARP – Address Resolution Protocol
Traduce IP → MAC all’interno della LAN.

**Esempio:**
- ARP Request: “Who has 192.168.1.20?”  
- ARP Reply: “192.168.1.20 is at 00:1A:2B:3C:4D:5E”

### 5.3 IP e ICMP
**IP**
- instrada pacchetti  
- servizio *best-effort*  

**ICMP**
- messaggi di controllo ed errore  
- usato da `ping` e `traceroute`

### 5.4 TCP vs UDP

**TCP**
- connection-oriented  
- affidabile  
- controllo flusso e congestione  
- usato da HTTP, email, FTP  

**UDP**
- connectionless  
- più veloce, meno overhead  
- usato da DNS, streaming, VoIP, gaming  

**Metafora:**
- TCP = pacco tracciato  
- UDP = cartolina  

### 5.5 DNS e HTTP/HTTPS
- **DNS**: nome → IP  
- **HTTP**: protocollo del web  
- **HTTPS**: HTTP + TLS  
  - confidentiality  
  - integrity  
  - server authentication  

---

## 6. Cenni di Network Security

### 6.1 Firewall
Filtra il traffico in base a regole:
- porte  
- IP  
- protocolli  

### 6.2 NAT – Network Address Translation
- private IP → public IP  
- uso di PAT (porte)  
- tipico delle reti domestiche  

### 6.3 Segmentazione e VLAN
Divisione della rete in subnet/VLAN per:
- migliori performance  
- maggiore sicurezza  
- isolamento dei problemi  

---

## 7. Strumenti di diagnostica di base

### 7.1 ping
Verifica la raggiungibilità di un host e la latenza.
```bash
ping www.google.com
