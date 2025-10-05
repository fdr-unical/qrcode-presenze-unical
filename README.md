# QR Code Presenze in Aula - UnICal

Sistema di rilevamento presenze con QR Code dinamico standalone per aule universitarie.

## 📋 Descrizione

Questo strumento è una versione **HTML standalone** del sistema di rilevamento presenze per l'Università della Calabria. Funziona completamente nel browser senza necessità di server, utilizzando QR code dinamici con token temporali per prevenire frodi.

Il sistema genera un QR code che si aggiorna automaticamente ogni 60 secondi, impedendo agli studenti di condividere il link con colleghi assenti.

## 🎯 Caratteristiche

- **QR Code Dinamico**: Si aggiorna automaticamente ogni 60 secondi con un token temporale unico
- **Anti-frode**: L'URL del form Microsoft è nascosto (campo password) e non visibile agli studenti
- **Finestra temporale**: Il QR code è valido solo per i primi 30 secondi di ogni minuto
- **Contatore visivo**: Gli studenti vedono quando scansionare il codice
- **Interfaccia semplice**: Basta incollare l'URL del form Microsoft e cliccare "Avvia"
- **Zero dipendenze server**: Funziona completamente nel browser

## 🚀 Come usare

### Opzione 1: GitHub Pages (Consigliata)

1. Vai su **https://fdr-unical.github.io/qrcode-presenze-unical/**
2. Incolla l'URL del tuo form Microsoft Forms nel campo (apparirà come puntini •••)
3. Clicca su "Avvia QR Code"
4. Proietta lo schermo in aula
5. Gli studenti scansionano il QR code ogni minuto durante la lezione

### Opzione 2: Download locale

1. Scarica il file `index.html`
2. Aprilo con un browser moderno
3. Segui i passaggi dell'Opzione 1

## 🔒 Sicurezza

- **URL nascosto**: L'URL del form è in un campo password e non appare sullo schermo proiettato
- **Token temporale**: Ogni QR code contiene un parametro `?t=timestamp` che cambia ogni 60 secondi
- **Validità limitata**: Gli studenti possono scansionare solo nei primi 60 secondi del minuto
- **Anti-condivisione**: Il link diventa invalido dopo 60 secondi, impedendo la condivisione

## 📝 Requisiti

- Browser moderno (Chrome, Firefox, Edge, Safari)
- Connessione internet per caricare la libreria QRCode.js
- Form Microsoft Forms con URL pubblico

## 🛠️ Tecnologie utilizzate

- HTML5
- JavaScript (Vanilla)
- [QRCode.js](https://davidshimjs.github.io/qrcodejs/) - Libreria per generare QR code
- CSS3 per l'interfaccia

## 📱 Compatibilità

Funziona su tutti i dispositivi e browser moderni. Gli studenti possono scansionare il QR code con qualsiasi smartphone.

## 👨‍🏫 Caso d'uso

Sistema sviluppato presso l'Università della Calabria (UnICal) per la gestione delle presenze in aule universitarie. Ideale per:
- Lezioni frontali in grandi aule
- Seminari e workshop
- Esami e verifiche  
- Qualsiasi contesto didattico che richieda rilevamento presenze anti-frode

## 📄 Licenza

MIT License - Vedi file LICENSE per dettagli

## 🤝 Contributi

Contributi, segnalazioni di bug e richieste di funzionalità sono benvenuti!

Apri una Issue su: https://github.com/fdr-unical/qrcode-presenze-unical/issues

## 👤 Autore

**Francesco De Rango**  
📧 Email: francesco.derango@unical.it  
🏛️ Università della Calabria  
🔗 GitHub: [@fdr-unical](https://github.com/fdr-unical)

## 📧 Contatti

Per domande, supporto o collaborazioni:

- **Issues**: https://github.com/fdr-unical/qrcode-presenze-unical/issues
- **Email**: francesco.derango@unical.it

---

**Nota**: Questo strumento è progettato per integrarsi con Microsoft Forms. Assicurati di avere un form attivo e accessibile prima di utilizzare il sistema.

Sviluppato da Francesco De Rango  
In uso presso l'Università della Calabria
