# 🛒 Lista Spesa per la Cici

**Lista Spesa per la Cici** è una web app ultra-leggera "serverless" (senza database) progettata per semplificare la gestione della spesa familiare. Funziona interamente tramite browser e sfrutta la condivisione dei link per passare la lista da chi la scrive a chi va al supermercato.

> **Il concetto:** Una persona seleziona i prodotti ("Cosa serve oggi?"), genera un link e lo invia su WhatsApp. L'altra persona apre il link e si trova la lista ordinata per reparti, pronta per essere spuntata.

## ✨ Funzionalità Principali

* **Zero Backend:** I dati della spesa viaggiano nell'URL. Non serve registrazione, login o database.
* **Doppia Modalità:**
    * **Modalità Selezione (Chi compila/Utente 1):** Interfaccia per scegliere i prodotti, divisa per categorie, con salvataggio automatico (LocalStorage) per non perdere la bozza se si chiude la pagina.
    * **Modalità Spesa (Chi acquista/Utente 2):** Interfaccia di lettura ottimizzata, con ordinamento automatico per reparti e funzione "spunta" (tap per barrare l'acquisto).
* **Categorie Intelligenti:** Anche se selezioni i prodotti in ordine sparso, la lista finale viene riordinata automaticamente (es. tutta la Frutta insieme, tutti i Freschi insieme).
* **Aggiunta Manuale:** Possibilità di aggiungere prodotti non presenti in lista ("Altro / Mancanti").
* **Condivisione Rapida:** Tasto diretto per inviare la lista su WhatsApp o copiare il link.
* **Mobile First:** Design responsivo, ottimizzato per l'uso da smartphone con pulsanti grandi e interfaccia pulita.

## 🚀 Come si usa

### 1. Per chi prepara la lista
1.  Apri la pagina web.
2.  Il titolo mostrerà un emoji casuale ogni volta (🌙, ☀️, 👹, etc.) per rendere l'esperienza più simpatica.
3.  Scorri le categorie e tocca i prodotti per selezionarli (apparirà una spunta verde).
4.  Se manca qualcosa, scrivilo nel campo "Scrivi qui cosa manca..." e premi `+`.
5.  In basso, premi **WhatsApp 💚** per inviare la lista o **Copia Link 📋**.

### 2. Per chi fa la spesa
1.  Clicca sul link ricevuto.
2.  Vedrai la lista già divisa per reparti (Verdura, Macelleria, Casa, ecc.).
3.  Mentre cammini tra le corsie, tocca i prodotti presi: diventeranno grigi e barrati.
4.  A fine spesa, puoi cliccare su "Nuova Lista ✨" per ricominciare da capo (torna alla home pulita).

## 🛠 Installazione e Deploy

Poiché il progetto è un singolo file HTML (`index.html`), non richiede installazioni complesse.

### Opzione A: Uso Locale
Basta scaricare il file `index.html` e aprirlo con qualsiasi browser (Chrome, Safari) sul tuo telefono o PC.

### Opzione B: Hosting Gratuito (Consigliato)
Per poter condividere il link su WhatsApp in modo efficace, la pagina deve essere online. Puoi caricarla gratuitamente su:
* **GitHub Pages:** Crea un repository, carica il file e attiva Pages nelle impostazioni.
* **Netlify / Vercel:** Trascina semplicemente il file nella loro dashboard.
* **Altervista / Spazio Web personale:** Carica il file via FTP.

## ⚙️ Personalizzazione Prodotti

Vuoi cambiare i prodotti predefiniti? È facilissimo.
Apri il file `index.html` con un editor di testo (Notepad, VS Code) e cerca la variabile `const products`:

```javascript
// Cerca questa parte nel codice verso la riga 200
const products = {
    "Verdura & Odori 🥦": [
        "🧄 Aglio", "🥬 Carciofi", "🥕 Carote"
    ],
    // Puoi aggiungere le tue categorie qui sotto:
    "Birre & Aperitivo 🍺": [
        "Birra bionda", "Patatine", "Arachidi"
    ]
};
```

Puoi aggiungere nuove categorie o modificare gli array di prodotti a tuo piacimento. L'app si adatterà automaticamente e creerà i nuovi gruppi nella lista finale.

## 🎨 Struttura del Codice

* **CSS:** Stile pulito e moderno, con variabili CSS per i colori (`--primary: #2ecc71`). Include animazioni per le checkbox e un design "card" per i prodotti.
* **JavaScript:**
    * Gestisce la logica di codifica/decodifica URL (`encodeURIComponent` e `decodeURIComponent`).
    * Usa `localStorage` per salvare la bozza della selezione nel browser di chi scrive la lista.
    * Logica di smistamento (sorting) che mappa i prodotti scelti alle rispettive categorie originali.

## 📄 Licenza

Progetto open source. Sentiti libero di modificarlo, migliorarlo e usarlo per la tua spesa!

---

**Autore:** [YIN Renlong](https://github.com/YIN-Renlong)
*Creato per semplificare la vita domestica.*
