# Conversione tra Decimale e Binario

La conversione tra numeri **decimali** (base 10) e **binari** (base 2) è fondamentale in informatica, perché i computer lavorano internamente con valori binari.

---

## 🔢 Conversione da Decimale a Binario

Per convertire un numero decimale in binario si usa il metodo delle **divisioni successive per 2**.

### ✔️ Procedura
1. Dividi il numero per 2.
2. Annota il **resto** (0 o 1).
3. Prendi il **quoziente** e dividilo nuovamente per 2.
4. Ripeti finché il quoziente diventa 0.
5. Il numero binario è la sequenza dei resti **letta dal basso verso l’alto**.

### 📘 Esempio: convertiamo 13 in binario

| Divisione | Quoziente | Resto |
|-----------|-----------|--------|
| 13 / 2    | 6         | 1      |
| 6 / 2     | 3         | 0      |
| 3 / 2     | 1         | 1      |
| 1 / 2     | 0         | 1      |

Leggendo i resti al contrario:  
**13 → 1101₂**

---

## 🔁 Conversione da Binario a Decimale

Per convertire un numero binario in decimale si usa il metodo delle **potenze di 2**.

### ✔️ Procedura
1. Scrivi il numero binario.
2. Assegna un valore di potenza di 2 a ciascuna cifra, partendo da 0 a destra.
3. Moltiplica ogni cifra (0 o 1) per la potenza di 2 corrispondente.
4. Somma tutti i risultati.

### 📘 Esempio: convertiamo 1101₂ in decimale

Posizioni (da destra a sinistra):  
- 1 × 2⁰ = 1  
- 0 × 2¹ = 0  
- 1 × 2² = 4  
- 1 × 2³ = 8  

Somma:  
**8 + 4 + 0 + 1 = 13**

Quindi:  
**1101₂ → 13**

---

## 🎯 Riassunto veloce

- **Decimale → Binario**: dividi per 2, prendi i resti, leggi al contrario.  
- **Binario → Decimale**: somma delle potenze di 2 corrispondenti alle cifre a 1.

