# Smart Office Plan

## Sicurezza e Backup Dati

L'ufficio necessità di un Server + NAS per la gestione e la protezione dei dati

---
### Hardware
---

L'hardware potrebbe essere recuperato dal deposito, ci possono essere varie alternative:

#### 1. PC Fisso con Dischi di Backup
![](/src/img/PC.jpg)

- Un PC Fisso con CPU abbastanza potente da usare come server
- Vari Hard Disk o SSD per poter creare un RAID ("rete" di hard disk duplicati) così da poter avere riserve di altri hard disk in caso di guasti
- Un SSD principale per il sistema operativo

<b>Vantaggi:</b>
- Permette di cambiare i componenti facilmente in caso di guasti o necessità di upgrade
- Permette di inserire tanti hard disk in modo da avere un "NAS"

<b>Svantaggi:</b>
- Può essere ingombrante
- Potrebbe non essere efficiente energeticamente

---
#### 2. TV Box/Magbox
![](/src/img/Box.jpeg)


- Uno o più Box
- Una scheda SD per ogni Box

<b>Vantaggi:</b>
- Soluzione compatta, silenziosa ed efficiente energeticamente
- Potenza x Prezzo Decente

<b>Svantaggi:</b>
- Non ha le connessioni di un computer fisso, quindi per collegare gli hard disk serverebbe una serie di lettori da comprare a parte

- Non permette il collegamento di Hard Disk senza

<br></br>


### <b>Che soluzione propongo?</b>
### Server + Box

Il server può essere sfruttato per il backup e protezione dei dati,
mentre le box possono essere sfruttate per la protezione in rete 

in alternativa, si potrebbe far fare tutto al server a discapito di un pò di performance



---

## Sicurezza Rete
### Bitwarden - Sistema per le password
Bitwarden è un software per conservare in maniera sicura le password, mantenedole sul nostro server e all'interno della nostra rete aziendale, senza farle uscire al di fuori

### "Buone abitudini"
Alcune buone abitudini possono migliorare la sicurezza:
- Inserire SEMPRE verifiche a più passaggi e/o Passkey
- Usare una mail separata per il lavoro, o crearla al momento per alcuni servizi (magari creare una mail lavorativa col nostro dominio @universalbet.it)
- Cambiare le password con alcune più sicure e non ripetitive

### Protezioni Locali

#### Dispositivi singoli
- IP Fisso
- Cloudflare WARP per Protezione


#### Impostazioni router

<b>Il router potrebbe non supportare alcune impostazioni di sicurezza, quindi potrebbe essere utile comprare un [Fritz Box](https://amzn.eu/d/8XDmUz0)</b>

- Sistema a rete interna doppia :
    - WiFi-Enterprise - Accesso WiFi non solo con Password ma anche con nome utente, in modo che ognuno può accedere al wifi con le proprie credenziali, stessa rete dei dispositivi collegati via cavo
    - WiFi Classico per Dispositivi ospiti o esterni ai PC, in rete separata dai dispositivi dell'ufficio

- Connessione che passa per il Server Locale, in modo da proteggere l'intera rete via WARP
- Firewall Aggressivo, con regola "Zero-Trust", comunicazione solo quando strettamente necessario

#### Software del Server Locale

<b>Il server sarà isolato, i dati e la comunicazione potranno essere gestiti solo ed unicamente nella rete locale, ad eccezione di eventuali software singoli (es. Grabber o software di sistema per gli aggiornamenti di sicurezza)</b>
- Sistema Operativo Linux - Debian
- Pihole - Blocco Annunci e domini pericolosi a livello di rete, quindi per tutti i dispositivi
- Samba - Software per la condivisione dei file del NAS in rete, protetto da semplice password da inserire una singola volta
- VS-Code Server - Software per programmare sul server, utile per Hosting di vari software dalla nostra rete interna

#### Server Secondario/Magbox

- Sistema Operativo Linux
- Cloudflare WARP
- VSFTPD - Condivisione File anche via internet via protocollo SFTP (Sicuro) per File non importanti, protetto da accesso 2FA

## Altro da poter aggiungere
- UPS, per la protezione dei PC e dei Dati da cali o sovraccarichi di corrente
- RPD, Accesso ai desktop da remoto senza Software se non quelli integrati con Windows e Linux
