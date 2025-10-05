# QR Code Presenze in Aula - UniCal

Sistema di rilevamento presenze con **QR Code dinamico anti-frode** per aule universitarie.

## 📋 Descrizione

Sistema standalone per la gestione delle presenze sviluppato per l'Università della Calabria. Utilizza QR code dinamici con **validazione timestamp lato client** per prevenire condivisioni fraudolente.

Il sistema genera un QR code che si rinnova automaticamente ogni 60 secondi. I QR scaduti vengono **bloccati automaticamente** dal sistema di validazione integrato.

## 🎯 Caratteristiche

- **QR Code Dinamico**: Si rinnova automaticamente ogni 60 secondi (configurabile 30-180s)
- **Validazione Timestamp**: Blocca automaticamente QR code vecchi (oltre 2 minuti con tolleranza default)
- **Sicurezza Tripla**: 
  - URL form nascosto (campo password)
  - Token temporale nel QR
  - Login Microsoft/UniCal obbligatorio per compilare il form
- **Countdown Visivo**: Mostra agli studenti i secondi rimanenti con animazione
- **Design Moderno**: Interfaccia professionale con gradiente viola
- **Zero Dipendenze Server**: Funziona completamente nel browser

## 🚀 Come usare

### GitHub Pages (Consigliato)

1. Vai su **https://fdr-unical.github.io/qrcode-presenze-unical/**
2. Inserisci l'URL del form Microsoft Forms (apparirà nascosto come •••)
3. (Opzionale) Modifica l'intervallo di validità (default: 60s)
4. Clicca "🚀 Avvia Sistema"
5. Proietta il QR in aula
6. Gli studenti scansionano il QR che cambia ogni minuto

### Download locale

1. Scarica `index.html`
2. Apri con browser moderno (Chrome, Firefox, Edge, Safari)
3. Segui i passaggi sopra

## 🔒 Sistema di Sicurezza

### Validazione QR Code
Quando uno studente scansiona il QR:

1. **Controllo Timestamp**: Il sistema calcola se il QR è nella finestra temporale valida
2. **Tolleranza**: Default ±1 finestra (circa 2 minuti totali)
3. **Blocco Automatico**: QR oltre la finestra mostrano "⛔ QR Code Scaduto"
4. **Redirect Condizionale**: Solo QR validi vengono reindirizzati al form

### Parametri URL
Ogni QR contiene:
- `t`: Bin temporale (timestamp / period)
- `p`: Period in secondi (es. 60)
- `f`: URL form Microsoft (encoded)

Esempio: `?t=29328079&p=60&f=https%3A%2F%2Fforms.microsoft.com%2F...`

### Sicurezza Form Microsoft
- Il form richiede login Microsoft/UniCal
- Solo utenti autenticati dell'organizzazione possono compilare
- Tracciabilità completa via email istituzionale

## ⚙️ Configurazione

### Modifica Tolleranza

Nel file `index.html`, cerca:

```javascript
const TOLERANCE = 1; // Finestre di tolleranza (±1)
```

Opzioni:
- `TOLERANCE = 0`: Solo bin corrente valido (~60s)
- `TOLERANCE = 1`: ±1 finestra (~2 minuti) **[DEFAULT]**
- `TOLERANCE = 2`: ±2 finestre (~3 minuti)

### Modifica Period Default

Nel codice HTML:

```html
<input type="number" id="period" value="60" min="30" max="180" step="15" />
```

Cambia `value="60"` con il valore desiderato (30-180 secondi).

## 📝 Requisiti

- Browser moderno con JavaScript abilitato
- Connessione internet per libreria QRCode.js
- Form Microsoft Forms configurato per l'organizzazione UnICal

## 🛠️ Tecnologie utilizzate

- HTML5 + CSS3 (gradiente moderno)
- JavaScript Vanilla (ES6+)
- [QRCode.js v0.7.0](https://davidshimjs.github.io/qrcodejs/) - Generazione QR
- GitHub Pages per hosting

## 📱 Compatibilità

- ✅ Chrome, Firefox, Edge, Safari (desktop e mobile)
- ✅ Tutti gli smartphone moderni con fotocamera
- ✅ Funziona offline per il docente (dopo primo caricamento)
- ⚠️ Studenti necessitano connessione per validazione e form

## 🔧 Troubleshooting

### QR non appare
- Verifica che JavaScript sia abilitato
- Controlla Console (F12) per errori libreria QRCode
- Prova a ricaricare la pagina (Ctrl+F5)

### QR vecchi non vengono bloccati
- Verifica tolleranza: con `TOLERANCE=1` accetta ±60s
- Aspetta almeno 2-3 minuti prima di testare QR "vecchio"
- Controlla Console per log validazione

### Studenti non riescono ad accedere al form
- Verifica che il form Microsoft accetti login UnICal
- Controlla che URL form sia corretto
- Assicurati che studenti usino account @studenti.unical.it

## 👨‍🏫 Caso d'uso

Ideale per:
- Lezioni frontali in grandi aule (200+ studenti)
- Seminari e convegni
- Esami e verifiche intermedie
- Qualsiasi contesto che richieda presenza fisica certificata

**Note**: Con period 60s e TOLERANCE 1, finestra totale ~2 minuti. Per aule molto grandi (300+ studenti) considerare period 90-120s.

## 📄 Licenza

MIT License - Libero per uso educativo e commerciale.

## 🤝 Contributi

Contributi benvenuti! Per bug o feature:

- Apri Issue: https://github.com/fdr-unical/qrcode-presenze-unical/issues
- Pull Request benvenute

## 👤 Autore

**Francesco De Rango**  
📧 francesco.derango@unical.it  
🏛️ Dipartimento di Biologia, Ecologia e Scienze della Terra (DIBEST)   
🎓 Università della Calabria  
🔗 GitHub: [@fdr-unical](https://github.com/fdr-unical)

## 📧 Supporto

- **Issues GitHub**: https://github.com/fdr-unical/qrcode-presenze-unical/issues
- **Email**: francesco.derango@unical.it

---

**Sistema Anti-Frode Certificato** ✅  
QR dinamici + Validazione timestamp + Autenticazione Microsoft

Sviluppato e testato presso l'Università della Calabria  
Versione 2.0 - Ottobre 2025
