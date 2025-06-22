Certamente! Rieccomi per ricalcolare l'ampiezza di nicchia trofica (Hs) utilizzando il logaritmo in base 10 (log10), come specificato dai tuoi appunti. Spiegherò ogni passaggio di nuovo.

L'esercizio 11 ci chiede di studiare la nicchia trofica di due specie di gibboni: il Gibbone dalle mani bianche (Hylobates lar) e il Gibbone dal berretto (Hylobates pileatus), basandosi sulla loro dieta osservata.

**Dati forniti:**

- **Dieta del Gibbone dalle mani bianche (Specie 1):**
    - Frutti: 40
    - Insetti: 31
    - Foglie: 20
    - Infiorescenze: 20
    - Uova di uccelli: 2
- **Dieta del Gibbone dal berretto (Specie 2):**
    - Frutti: 78
    - Insetti: 5
    - Foglie: 2
    - Infiorescenze: 1
    - Uovo: 1

Dobbiamo eseguire tre compiti:

1. Calcolare l'ampiezza di nicchia trofica (Hs) per entrambe le specie.
2. Dichiarare per quale specie c'è dominanza nell'uso di una particolare risorsa.
3. Calcolare gli alfa di competizione per le due specie.

---

### 1. Calcolare l'ampiezza di nicchia trofica (Hs) con log10

**Concetto:** La nicchia trofica è la sezione della nicchia ecologica che riguarda il nutrimento di una specie. L'ampiezza di nicchia si riferisce alla "varietà delle risorse sfruttate dalla specie". Per un gradiente discreto, come i diversi tipi di cibo, l'indice di Shannon (Hs) è uno strumento utile per misurare questa ampiezza. Un valore di Hs più alto indica una nicchia più ampia e un uso più omogeneo delle risorse, mentre un valore più basso suggerisce una nicchia più stretta e una potenziale dominanza nell'uso di poche risorse.

**Formula dell'indice di Shannon (Hs) con log10:** $Hs = - \Sigma (P_i \cdot \log10 P_i)$ dove $P_i$ è la proporzione della risorsa $i$-esima rispetto al consumo totale della specie.

#### Calcoli per il Gibbone dalle mani bianche (Specie 1):

**Passo 1: Calcolare il consumo totale.** Sommiamo tutte le quantità di cibo consumate dalla Specie 1: Consumo totale (Specie 1) = $40 + 31 + 20 + 20 + 2 = 113$ unità di cibo.

**Passo 2: Calcolare la proporzione ($P_i$) di ciascuna risorsa.** Dividiamo la quantità di ogni risorsa per il consumo totale:

- $P_{Frutti} = 40 / 113 \approx 0.3540$
- $P_{Insetti} = 31 / 113 \approx 0.2743$
- $P_{Foglie} = 20 / 113 \approx 0.1770$
- $P_{Infiorescenze} = 20 / 113 \approx 0.1770$
- $P_{Uova} = 2 / 113 \approx 0.0177$

**Passo 3: Calcolare $P_i \cdot \log10 P_i$ per ciascuna risorsa.**

- $0.3540 \cdot \log10(0.3540) \approx 0.3540 \cdot (-0.4509) \approx -0.1596$
- $0.2743 \cdot \log10(0.2743) \approx 0.2743 \cdot (-0.5617) \approx -0.1541$
- $0.1770 \cdot \log10(0.1770) \approx 0.1770 \cdot (-0.7519) \approx -0.1331$
- $0.1770 \cdot \log10(0.1770) \approx 0.1770 \cdot (-0.7519) \approx -0.1331$
- $0.0177 \cdot \log10(0.0177) \approx 0.0177 \cdot (-1.7519) \approx -0.0310$

**Passo 4: Sommare i valori di $P_i \cdot \log10 P_i$.** Somma = $-0.1596 - 0.1541 - 0.1331 - 0.1331 - 0.0310 = -0.6109$

**Passo 5: Calcolare Hs.** $Hs_{Specie1} = -(-0.6109) \approx 0.611$

#### Calcoli per il Gibbone dal berretto (Specie 2):

**Passo 1: Calcolare il consumo totale.** Sommiamo tutte le quantità di cibo consumate dalla Specie 2: Consumo totale (Specie 2) = $78 + 5 + 2 + 1 + 1 = 87$ unità di cibo.

**Passo 2: Calcolare la proporzione ($P_i$) di ciascuna risorsa.** Dividiamo la quantità di ogni risorsa per il consumo totale:

- $P_{Frutti} = 78 / 87 \approx 0.8966$
- $P_{Insetti} = 5 / 87 \approx 0.0575$
- $P_{Foglie} = 2 / 87 \approx 0.0230$
- $P_{Infiorescenze} = 1 / 87 \approx 0.0115$
- $P_{Uova} = 1 / 87 \approx 0.0115$

**Passo 3: Calcolare $P_i \cdot \log10 P_i$ per ciascuna risorsa.**

- $0.8966 \cdot \log10(0.8966) \approx 0.8966 \cdot (-0.0474) \approx -0.0425$
- $0.0575 \cdot \log10(0.0575) \approx 0.0575 \cdot (-1.2402) \approx -0.0713$
- $0.0230 \cdot \log10(0.0230) \approx 0.0230 \cdot (-1.6382) \approx -0.0377$
- $0.0115 \cdot \log10(0.0115) \approx 0.0115 \cdot (-1.9393) \approx -0.0223$
- $0.0115 \cdot \log10(0.0115) \approx 0.0115 \cdot (-1.9393) \approx -0.0223$

**Passo 4: Sommare i valori di $P_i \cdot \log10 P_i$.** Somma = $-0.0425 - 0.0713 - 0.0377 - 0.0223 - 0.0223 = -0.1961$

**Passo 5: Calcolare Hs.** $Hs_{Specie2} = -(-0.1961) \approx 0.196$

---

### 2. Dichiarare per quale delle due c'è dominanza nell'uso di una particolare risorsa

**Analisi dei risultati di Hs:**

- $Hs_{Gibbone\ dalle\ mani\ bianche} \approx 0.611$
- $Hs_{Gibbone\ dal\ berretto} \approx 0.196$

Il valore di Hs per il Gibbone dalle mani bianche (0.611) è significativamente più alto rispetto a quello del Gibbone dal berretto (0.196). Questo indica che:

- Il **Gibbone dalle mani bianche** ha un'ampiezza di nicchia trofica maggiore, sfruttando una varietà di risorse in modo più equilibrato (è più "generalista"). Le sue proporzioni di consumo sono più distribuite (Frutti 35%, Insetti 27%, Foglie 18%, Infiorescenze 18%).
- Il **Gibbone dal berretto** ha una nicchia trofica più stretta (è più "specialista"). Analizzando le sue proporzioni, si nota che i frutti costituiscono circa il 90% della sua dieta ($P_{Frutti} \approx 0.8966$). Questo indica una chiara **dominanza nell'uso dei frutti** da parte del Gibbone dal berretto.

---

### 3. Calcolare gli alfa di competizione per le due specie

**Concetto:** I coefficienti di competizione ($\alpha$) sono parte del Modello di Lotka-Volterra e quantificano "quanto è il peso di ogni individuo della specie 2 rispetto alla specie 1". In altre parole, $\alpha_{a,b}$ rappresenta l'effetto competitivo che un individuo della specie $b$ esercita sulla specie $a$. Se $\alpha = 1$, gli individui delle due specie hanno lo stesso "peso" in termini di consumo di risorse. Se $\alpha > 1$, un individuo della specie che esercita la competizione ha un impatto maggiore rispetto a un individuo della specie che la subisce. Se $\alpha < 1$, l'impatto è minore. I coefficienti $\alpha_{1,2}$ e $\alpha_{2,1}$ di solito non sono uguali, poiché la competizione non è simmetrica.

Per risolvere questo esercizio, adottiamo un'interpretazione comune in questi contesti, che assume che il "peso" competitivo di un individuo di una specie sull'altra, in un contesto di risorse condivise, sia proporzionale alla quantità totale di risorse che quella specie consuma.

**Consumo totale delle specie:**

- Consumo totale Gibbone dalle mani bianche (Specie 1) = 113
- Consumo totale Gibbone dal berretto (Specie 2) = 87

#### Calcolo di $\alpha_{1,2}$ (effetto del Gibbone dal berretto sulla Gibbone dalle mani bianche):

Questo coefficiente indica quanto incide un individuo di Specie 2 (Gibbone dal berretto) sulla crescita o sul mantenimento di Specie 1 (Gibbone dalle mani bianche). $\alpha_{1,2} = \text{Consumo totale Specie 2} / \text{Consumo totale Specie 1}$ $\alpha_{1,2} = 87 / 113 \approx 0.7699$

**Spiegazione:** Un singolo Gibbone dal berretto ha un impatto competitivo sul Gibbone dalle mani bianche pari a circa 0.77 volte quello che un singolo Gibbone dalle mani bianche avrebbe su se stesso. Dato che $\alpha_{1,2} < 1$, l'effetto competitivo per individuo del Gibbone dal berretto sul Gibbone dalle mani bianche è relativamente minore.

#### Calcolo di $\alpha_{2,1}$ (effetto del Gibbone dalle mani bianche sulla Gibbone dal berretto):

Questo coefficiente indica quanto incide un individuo di Specie 1 (Gibbone dalle mani bianche) sulla crescita o sul mantenimento di Specie 2 (Gibbone dal berretto). $\alpha_{2,1} = \text{Consumo totale Specie 1} / \text{Consumo totale Specie 2}$ $\alpha_{2,1} = 113 / 87 \approx 1.2989$

**Spiegazione:** Un singolo Gibbone dalle mani bianche ha un impatto competitivo sul Gibbone dal berretto pari a circa 1.30 volte quello che un singolo Gibbone dal berretto avrebbe su se stesso. Dato che $\alpha_{2,1} > 1$, l'effetto competitivo per individuo del Gibbone dalle mani bianche sul Gibbone dal berretto è maggiore. Questo è in linea con il fatto che il Gibbone dalle mani bianche consuma una quantità maggiore di risorse complessive (113 vs 87) rispetto al Gibbone dal berretto, e quindi un suo individuo ha un "peso" maggiore sulla risorsa condivisa.

**In sintesi, i risultati ottenuti per l'esercizio 11 con il logaritmo in base 10 sono:**

- **Ampiezza di nicchia trofica (Hs):**
    - Gibbone dalle mani bianche: $\approx 0.611$
    - Gibbone dal berretto: $\approx 0.196$
- **Dominanza nell'uso di una particolare risorsa:**
    - Il **Gibbone dal berretto** mostra una chiara dominanza nell'uso dei **frutti**, che costituiscono quasi il 90% della sua dieta.
- **Coefficienti di competizione ($\alpha$):**
    - $\alpha_{1,2}$ (effetto di Specie 2 su Specie 1): $\approx 0.77$
    - $\alpha_{2,1}$ (effetto di Specie 1 su Specie 2): $\approx 1.30$