%%
TODO:
- Dividere tutto in moduli (più file)
- Aggiungere il collect-garbage: o comando `sudo nix-collect-garbage —delete-older-than 15d` oppure
```
nix.gc = {
    automatic = true;
    dates = "weekly";
    options = "--delete-older-than 30d";
};
```
- Impostare programmi di default con cui aprire i file (es. aprire i PDF con Firefox)
- Aggiornare NixOS e i package in automatico (rivedere tra i video salvati come fare)
- Tilde facilmente copiabile
- Aggiungere i metadati in automatico quando scarico file con yt-dlp

(aggiungere icona di NixOS alla pagina Obsidian)

Per aggiornare:
```bash
sudo nix-channel --update
```
e
```bash
nix-env -u
```
Per vedere modifiche:
```bash
nvd diff /nix/var/nix/profiles/system-{<NUMERO PENULTIMA>,<NUMERO ULTIMA>}-link
```
Esempio:
```bash
nvd diff /nix/var/nix/profiles/system-{176,177}-link
```

Da vedere:
- https://github.com/the-nix-way/dev-templates?tab=readme-ov-file
- https://nixos.org/guides/nix-pills/00-preface
- https://github.com/willmcpherson2/willos/tree/a6fe74f71886c18a08de16a348e66b08f4e0debf
- https://starship.rs/
- https://www.youtube.com/watch?v=KsDYul3J3Dc
- https://nix-community.github.io/home-manager/index.xhtml
- https://aulab.it/guide-avanzate/3/guida-git-in-italiano
- https://hoverbear.org/blog/declarative-gnome-configuration-in-nixos/#getting-home-manager-set-up
- https://www.reddit.com/r/NixOS/comments/18559ik/new_to_nixos_should_i_do_home_manager/
- https://nixos-and-flakes.thiscute.world/preface
- https://github.com/NixOS/nixpkgs/issues/9682
- https://nixos.wiki/wiki/Ubuntu_vs._NixOS

Altra roba da vedere:
https://www.reddit.com/r/NixOS/comments/113ondu/rice_nixos/:
currently active are, in alphabetical order:
- Bluetooth Quick Connect (Bluetooth Toggle in quick settings)
- **Blur my Shell** (my absolute favorite. makes shell look 10X better)
- caffeine (keep it from sleeping)
- Extensions List (toggle extensions and open their settings from the Top Bar)
- Focus Indicator (gnome devs beta; windows jump when alt-tabbing into them)
- **GSConnnect** (another favorite of mine. Apple Ecosystem on Steroids, integrates Phone to Linux) **(please don't actually install it, instead use programs.kdeconnect and programs.kdeconnect.package)**
- Night Theme Switcher (automatically switch dark and light mode)
- Task Widget (display Tasks next to the Calendar in the notification Area)
- user Themes (allows you to use your own Themes)
- Weather O' Clock (shows weather next to time in Top Bar)
- **Workspace Indicator** (another favorite, shows your Workspaces in Top Bar in a pretty cool way. helps a lot with orientation)
since this List got pretty large, i decided to **Bold** my 3 favorite extensions. i hope this doesn't destroy the esthetics too much

Vedere da [Ubuntu 22.04](Ubuntu%2022.04.md) roba da aggiungere

Creare pacchetti Nix di:
- Doom Emacs
- Moises

scrivere poi in questa pagina tutte le cose che si possono personalizzare es. anche MIMEtypes ecc.

https://www.reddit.com/r/NixOS/comments/119l576/nixos_immutability_and_ease_of_use/

https://nixos.org/explore/
%%

Questa guida è stata scritta interamente da me per coloro che hanno già conoscenze di base su Linux e sono interessati al mondo di NixOS. Qua troverete tutto quel che ho imparato su questo sistema operativo. Su GitHub ho una [repo pubblica](https://github.com/Rexus752/NixOS) in cui è caricata la mia configurazione di NixOS e che tengo aggiornata di pari passo col mio sistema.

# Cos'è NixOS e perché dovrei usarlo?

NixOS è una distribuzione Linux basata sul [[package manager Nix]] che ruota intorno a 3 concetti fondamentali:
1. [Dichiaratività](#Dichiaratività): NixOS usa un approccio dichiarativo nella configurazione del sistema, salvando tutto in file scritti in linguaggio Nix;
2. [Riproducibilità](#Riproducibilità): ogni configurazione di NixOS si può facilmente riprodurre su altri computer senza doverla replicare manualmente;
3. [Indistruttibilità](#Indistruttibilità): in NixOS è praticamente impossibile ritrovarsi nella condizione di avere un sistema operativo non funzionante.

## Dichiaratività

La maggioranza dei sistemi operativi è basato su un approccio di tipo _imperativo_: per apportare modifiche alla propria configurazione (che comprende le impostazioni di base del sistema operativo stesso, le applicazioni installate o i pacchetti nel caso delle distribuzioni Linux, le impostazioni delle applicazioni, ecc.), eseguendo operazioni come l'installazione di un nuovo programma, si eseguono istruzioni che, una dopo l'altra, ne alterano lo stato.

NixOS, invece, usa un approccio di tipo _dichiarativo_ (simile a quello dei dotfile in Linux): la configurazione del sistema operativo è tutta contenuta (_dichiarata_) in uno o più file di configurazione scritti in linguaggio Nix e, a ogni avvio, il sistema viene letteralmente _costruito_ esattamente come dichiarato nei file. Ciò permette di tenere traccia facilmente di tutto ciò che contribuisce alla configurazione del sistema, proprio perché è tutto scritto in dei semplici file modificabili.

## Riproducibilità

Proprio grazie alla [dichiaratività](#Dichiaratività), essendo tutta la configurazione del sistema salvata in file, basta semplicemente copiare questi file su altri computer su cui è installato NixOS per riprodurre perfettamente la stessa identica configurazione del sistema; ovviamente, tutto ciò che non è parte della configurazione del sistema, quindi tutti i dati come documenti, salvataggi di giochi, ecc. non saranno trasferiti (per fare ciò, esiste `restic`).

La caratteristica della riproducibilità può tornare molto utile nel caso in cui ci sia bisogno di configurare multipli computer nello stesso modo, per esempio in un laboratorio scolastico o universitario in cui tutti i computer devono avere installati gli stessi programmi. In questo modo, per effettuare delle nuove modifiche al sistema (come l'installazione di un nuovo programma) basta lavorare su un solo computer e, in automatico, propagarle a tutti gli altri, senza dover mettere mani su ogni singolo computer.

Inoltre, grazie a ciò, ognuno può facilmente condividere la propria configurazione a chiunque possa essere interessato nella community di NixOS (la mia la trovate sul [mio profilo GitHub](https://github.com/Rexus752/NixOS)).

## Indistruttibilità

Ogni aggiornamento della propria configurazione di NixOS (anche detto _rebuild_) viene salvato in memoria e ciò permette all'utente, durante la fase di avvio del sistema (nel GRUB), di accedere a qualsiasi configurazione salvata precedentemente (chiamate _generazioni_).

In questo modo, se si effettua un _rebuild_ che in qualche modo "rompe" il sistema operativo e ne impedisce perfino l'avvio, basta tornare all'ultima generazione ancora funzionante salvata in memoria e ripartire da lì aggiustando gli errori. Con altri sistemi operativi invece, se ne viene compromesso perfino l'avvio, bisogna necessariamente trovare l'origine del problema e provare a ripararlo, altrimenti l'alternativa è reinstallare il sistema operativo da zero e ripartire da capo.

Attenzione però: bisogna ricordarsi di impostare (preferibilmente subito dopo l'installazione di NixOS) un controllo di versione%%link%% sui file di configurazione, in quanto ogni generazione con salva con sé anche i file che l'hanno generata.

# Installazione

Ecco un mini-tutorial su come installare e impostare le parti fondamentali di NixOS (più qualche mio consiglio personale). È una guida fatta a prova di scemo (tipo me), esposta nei minimi dettagli e pensata proprio per coloro che sono ancora alle prime armi con il mondo di Linux (è preferibile però avere almeno una conoscenza di base del suo funzionamento e un minimo di esperienza pregressa con qualche altra distribuzione). In ogni caso non c'è da preoccuparsi, non è stato dato nulla per scontato proprio per evitare incomprensioni e permettere a tutti di capire  

La versione che ho installato io di NixOS e sulla base di cui ho scritto questa guida è la `24.05.2411.706eef542dec`; con versioni future potrebbero cambiare alcune cose o addirittura smettere di funzionare, in quel caso siete pregati di [[contattarmi]] così posso aggiornare la guida di conseguenza.

Ci tengo a precisare che, ovviamente, esiste anche il [manuale ufficiale di NixOS](https://nixos.org/manual/nixos/stable/) che comprende anche una [guida sull'installazione](https://nixos.org/manual/nixos/stable/#ch-installation). Se siete già abbastanza esperti nel campo, seguite quello (anche perché sarà costantemente aggiornato man mano che usciranno versioni future di NixOS). Questa guida l'ho voluta ugualmente scrivere proprio per coloro che hanno bisogno di avere il lavoro facilitato, non dando nulla per scontato e, soprattutto, per avere una guida di riferimento in **italiano**.

## Preparazione per l'installazione

Prima di eseguire l'installazione vera e propria di NixOS, c'è bisogno di un po' di preparazione.

Innanzitutto, andando a cambiare il sistema operativo, sarà necessario fare una **formattazione** del disco fisso, quindi prima di procedere consiglio vivamente di salvarsi **TUTTO** ciò che non volete perdere su spazi di archiviazione esterni come chiavette, HDD esterni o anche sul cloud con Google Drive o Dropbox.

Se avete un po' di pazienza e preferite fare le cose in sicurezza per evitare di avere in futuro rimpianti su dati che avete permanentemente perso, vi consiglio di continuare a usare il vostro computer per almeno una settimana, esattamente come avete fatto finora e, nel frattempo, salvarvi tutto quello di cui vi ricordate (io consiglio una settimana di "attesa" perché credo che in una settimana ci si riesca a ricordare di tutto ciò che può essere utile salvarsi, ma ovviamente più si "temporeggia" e meglio è). Questo è il mio consiglio, sentitevi liberi di non seguirlo a vostro rischio e pericolo (ma ricordatevi, fatelo per il vostro bene, meglio "perdere" una settimana di tempo che perdere qualcosa che può esservi essenziale e che potenzialmente non potreste recuperare mai più).

Bene, una volta terminato il trasferimento di tutti i dati utili, si può procedere con l'installazione vera e propria. L'occorrente è il seguente:
- Una chiavetta USB da almeno 2GB che sarà formattata (per diventare una chiavetta USB avviabile o, detto in parole povere, per essere "flashata") e, di conseguenza, perderà ogni dato salvato su di essa (anche in questo caso bisogna trasferire da qualche altra parte tutto il contenuto della chiavetta, altrimenti si rischia di perderlo per sempre); 
- Una connessione a Internet che può essere effettuata in uno dei seguenti modi:
	- Tramite Ethernet, cioè tramite cavo LAN collegato al computer;
	- Tramite tethering, cioè collegando il telefono al computer tramite un cavo USB e attivando l'impostazione del tethering sul telefono stesso;
	- La connessione tramite Wi-Fi è altamente sconsigliata (ho provato durante la mia installazione a impostare il collegamento alla rete Wi-Fi ma non ci sono riuscito, quindi non so neanche dirvi come si faccia lol);
- Ovviamente, un dispositivo da cui seguire queste istruzioni diverso da quello su cui si installerà il sistema operativo (va bene anche il telefono stesso da cui si fa tethering oppure un altro computer).

## Installazione dell'immagine sulla chiavetta

Nella [pagina dei download sul sito ufficiale di NixOS](https://nixos.org/download/), scorrendo in basso alla sezione _NixOS: the Linux distribution_ si trovano le immagini ISO di NixOS. In questa guida uso la _Minimal ISO image_ (cioè quella da riga di comando) anziché quella grafica perché, pur seguendo l'installazione guidata sul manuale ufficiale, la versione della _Graphical ISO image_ che ho provato ad usare non mi salvava correttamente in memoria le vecchie generazioni.

Scaricata l'immagine ISO, si deve rendere la chiavetta USB avviabile come si fa solitamente con l'installazione da chiavetta di qualsiasi altra distribuzione Linux (in ogni caso, c'è una [guida sul manuale ufficiale di NixOS](https://nixos.org/manual/nixos/stable/#sec-booting-from-usb)).

Una volta avviata l'installazione manuale dalla chiavetta USB, si aprirà l'interfaccia a riga di comando: l'utente con cui viene effettuato l'accesso automaticamente si chiama `nixos` e non ha una password, quindi si può usare direttamente il comando `sudo` senza una password:

```bash
sudo -i
```


## Partizionamento

```
lsblk
```
lista partizioni

nel mio caso risultato è
```
nvme0n1
- nvme0n1p1
- nvme0n1p2
```

### Eliminazione delle partizioni

```
fdisk /dev/nomedisco
fdisk /dev/nvme0n1
```
per formattare le partizioni `nvme0n1`

```
d
```
e poi
```
1
```
per eliminare la prima partizione

```
d
```
e poi
```
invio
```
(seleziona in automatico la partizione rimanente, oppure numero delle altre partizioni)

```
w
```
per confermare

altri comandi utili:
- `m` per l'help di fdisk

```
lsblk
```
ulteriore conferma delle partizioni eliminate

### Creazione delle partizioni

```bash
fdisk /dev/nomedisco
```

inserire un comando per volta:
```bash
g
n
1
2048
+512M # (se tastiera italiana presa come quella italiana, premere shift+ì (il + è al posto del ^))
(inserire schema tastiera inglese)
Y # se chiede se rimuovere la signature
t
1
n
2
invio
invio
Y # se chiede se rimuovere la signature
w
```

vedere con
```
lsblk
```
ora ci sono due partizioni, una da 512M e l'altra con tutto il resto della memoria

```
mkfs.fat -F 32 /dev/nvme0n1p1 
```

```
fatlabel /dev/nvme0n1p1 NIXBOOT
```

```
mkfs.ext4 /dev/nvme0n1p2 -L NIXROOT
```

```
mount /dev/disk/by-label/NIXROOT /mnt
```

```
mkdir -p /mnt/boot
```

```
mount -o umask=077 /dev/disk/by-label/NIXBOOT /mnt/boot
```

### Creazione dello swapfile

```
dd if=/dev/NOMEDISCOCHIAVETTA (if=/dev/sda) of=/mnt/.swapfile bs=1024 count=2097152 # 2GB size
```

aspettare che finisca

```
chmod 600 /mnt/.swapfile
```

```
mkswap /mnt/.swapfile
```

```
swapon /mnt/.swapfile
```

## File di config

### Creazione file

```
nixos-generate-config --root /mnt
```

### Modifica file

```
cd /mnt/etc/nixos
```

```
nano configuration.nix
```

Nel file:
```
networking.hostName = "manuel"
```

```
networking.networkmanager.enable = true
```

```
timezone Europe/Rome
```

```
services xserver enable

services xserver xkb {
layout = "it"
options??? 
}

hardware.pulseaudio.enable = true

libinput true

users.users.manuel = {
   isNormalUser = true;
   home = "/home/manuel";
   initialPassword = "PASSWORD";
   extraGroups = ["wheel" "networkmanager"];
};

services.openssh.enable = "true";
```
abilitare cups con `services.printing.enable = true;`

aggiungere poi
```
# Bootloader
boot.loader.grub.device = "nodev";
boot.loader.grub.efiSupport = "true";
boot.loader.grub.useOSProber = "true";
```

per salvare le modifiche:
```
ctrl+x
y
invio
```

se qualcosa si rompe nel configuration.nix:
1. `cd /mnt/etc/nixos`
2. `nano configuration.nix`
poi inserire password per root (solitamente stessa password dell'utente principale)
e infine `reboot`

## Installazione di NixOS

```
cd /mnt

nixos-install
```

fare reboot

dopo reboot, fare accesso inserendo come password `PASSWORD`, aprire il terminale ed eseguire

```
passwd
NUOVAPW
NUOVAPW
```

## Flakes e home-manager

per creare i flakes e home-manager seguire https://www.youtube.com/watch?v=a67Sv4Mbxmc

# Setup veloce

Aggiungere gli alias per il rebuild

# Repo su GitHub del config di NixOS

## Setup della repo

Se permessi negati di `/home/manuel/nixos`, eseguire:
```
sudo chown manuel nixos -R
```

installare `gh`, fare login con:

```
gh auth login
```

- Github.com
- SSH
- Yes
- Invio (no passphrase)
- Invio (GitHub CLI)
- Paste an authentication token
- Generate new token (classic)
- Note: `GitHub CLI`
- Expiration: `30 days`
- Select scopes: `repo`, `admin:org`, `admin:public_key`

Nella directory `/home/manuel/nixos`:
```
git init
git add .
git status
git commit -m "Initial commit"
```

Nella directory `/home/manuel/nixos`:
```
gh repo create
```

- `Push an existing local repository to GitHub`
- Invio
- `NixOS` (nome repo)
- Owner: `Rexus752`
- Descrizione: `My personal NixOS setup`
- Visibilità: `Public`
- Add a remote: Invio (`Yes`)
- Remote name: Invio (`origin`)
- Push?: Invio (`Yes`)

## Aggiornamento della repo

### Verifica dell'`origin`

%%
- Sistemare poi quello che c'è scritto, es. non so se è giusto dire "lista dei remote" al punto 2
- Scegliere se mettere in markdown-code i nomi tipo `origin`, `remote` ecc.
- Aggiungere eventualmente a origin, remote ecc. i collegamenti alle loro definizioni nella Obsidian note su GitHub che poi creerò
%%

Prima di aggiornare la repo, bisogna verificare che l'URL dell'origin sia di tipo SSH e non HTTPS:

1. Navigare nella cartella della repo:
	```bash
	cd ~/nixos
	```

2. Ottenere la lista dei remote con:
	```bash
	git remote -v
	```

3. Se la lista dei remote è del tipo HTTPS, cioè nel formato `https://github.com/USER/REPO.git` (dove `USER` è il vostro nome utente su GitHub, mentre `REPO` è il nome della repo) anziché del tipo SSH, cioè `git@github.com:USER/REPO.git`, bisogna aggiornare l'URL (dato che l'HTTPS non è più supportato):
	```bash
	git remote set-url origin git@github.com:USER/REPO.git
	```
	(ovviamente nel comando vanno sostituiti `USER` col proprio nome utente e `REPO` col nome della propria repo)

4. Se l'URL è già di tipo SSH, potete dormire sonni tranquilli e saltare il passaggio 3. Anche oggi avete ottenuto una piccola vittoria in questo mondo marcio.

### Creazione del commit e push

1. Aggiorna file tracciati da Git %%corretto dire così?%%:
	```bash
	git add .
	```
2. Verifica le modifiche dei file:
	```bash
	git status
	```
3. Crea il commit:
	```bash
	git commit -m "<messaggio>"
	```
	dove al posto di `<messaggio>` ci va il messaggio da associare al commit %%aggiungere poi una nota sulle convenzioni: https://www.conventionalcommits.org/en/v1.0.0/ %%;
4. Fai un _push_ delle modifiche verso il branch `master`:
	```bash
	sudo git push -u origin master
	```

# Backups su Google Drive con `restic` e `rclone`

https://francis.begyn.be/blog/nixos-restic-backups

## Setup `rclone`

1. Avviare il config di `rclone`:
	```bash
	rclone config
	```
2. A meno che non siano già state fatte altre operazioni con `rclone`, la CLI non troverà alcun un file di configurazione e, di conseguenza, nessun _remote_ già creato. Per crearne uno nuovo, scrivere `n` e premere invio;
3. Come nome del nuovo _remote_, inserire `gdrive`;
4. Come tipo di storage da configurare, inserire il numero corrispondente a quello di Google Drive (nel mio caso è il `17`);
5. Come _Client ID_ da inserire, crearne uno nuovo seguendo la guida disponibile al [link](https://rclone.org/drive/#making-your-own-client-id) che è stato stampato nella console;
6. Finito il setup dell'applicazione, dopo aver preso nota del _Client ID_ dell'applicazione, inserirlo nel terminale;
7. Come _Client Secret_, inserire quello dell'applicazione di cui avete appena preso nota;
8. Come _scope_ dell'applicazione, inserire il numero corrispondente a quello con accesso completo (generalmente l'`1`);
9. Per il file di Service Account Credentials JSON, lasciare vuoto e premere invio;
10. Per una configurazione avanzata, lasciare vuoto e premere invio;
11. Premere invio per aprire l'interfaccia di accesso nel browser;
12. Selezionare l'account Google sul cui Drive fare il backup;
13. Anche se si viene reindirizzati a un messaggio di avvertimento che dice che l'app non è stata ancora verificata da Google, cliccare su `Advanced` in basso a sinistra e poi su `Go to rclone (unsafe)` (che poi, "`unsafe`" mica tanto lol, l'app è nostra e sappiamo perfettamente ciò che fa e se è pericolosa);
14. Confermare l'accesso dell'app `rclone` al nostro account Google;
15. Tornare sul terminale e premere invio per non impostare il servizio come un Team Drive;
16. Uscito il riepilogo dei dati del _remote_, premere invio per confermare;
17. Scrivere `q` e premere invio per terminare la configurazione di `rclone`.

## Setup `restic`

1. Creare una nuova repository di `restic`:
	```bash
	restic -r rclone:gdrive:/backups init
	```
2. Nel `configuration.nix`, scrivere il seguente blocco di codice:
	```nix
	services.restic.backups = {
		gdrive = {
			user = "<user>";
			repository = "rclone:gdrive:/backups";
			initialize = true;
			passwordFile = "<password>";
			paths = [
				<paths>
			];
		};
	};
	```
	dove:
	- al posto di `<user>` ci va il nome dell'utente di NixOS su cui eseguire le operazioni;
	- al posto di `<password>` ci va il percorso di un file (anche un semplice file `.txt`) contenente la password che vogliamo usare per accedere alla repository dei backup;
	- al posto di `<paths>` metterci un array di stringhe di percorsi di cartelle che vogliamo salvare;
3. Se ci sono sottocartelle da escludere o se si vogliono utilizzare altre opzioni (per vederle tutte, andare sul [sito di NixOS](https://search.nixos.org/options?channel=unstable&show=services.restic.backups.%3Cname%3E.extraBackupArgs&from=0&size=15&sort=relevance&type=packages&query=services.restic.backups.%3Cname%3E)), includerle nell'opzione `extraBackupArgs`:
	```nix
	services.restic.backups = {
		gdrive = {
			...
			extraBackupArgs = [];
		};
	};
	```
4. Se si vuole impostare un backup automatico, usare l'opzione `timerConfig` come nel seguente esempio in cui viene effettuato un backup su base settimanale:
	```nix
	services.restic.backups = {
		gdrive = {
			...
			timerConfig = {
				OnCalendar = "daily";
				Persistent = true;
			};
		};
	};
	```
	(la sintassi per questa opzione può essere trovata eseguendo nel terminale i comandi `man systemd.timer` e `man systemd.time` oppure [qui](https://www.freedesktop.org/software/systemd/man/latest/systemd.timer.html))

## Altre opzioni

- Use `restic ls` to list the files contained in a snapshot.
- Use `restic restore` to restore some or all files contained in a snapshot.
- Use `restic mount` (on supported platforms) to get a browsable file structure with the files in your snapshots.

```bash
restic -r rclone:gdrive:/backups snapshots
```
(password: `PASSWORD`)

# GNOME

```bash
dconf watch /
```

```
dconf2nix -i /home/manuel/Desktop/dconf.settings -o /home/manuel/Desktop/dconf.nix
```

Quando si fanno modifiche alle impostazioni dell'estensione, se non è cambiato nulla, per sicurezza chiudere e riaprire le impostazioni dell'estensione perché alcuni elementi es. slider, toggle buttons ecc. non si aggiornano automaticamente.

ATTENZIONE: deve sempre uscire
```
restarting the following units: home-manager-manuel.service
```
ALTRIMENTI VUOL DIRE CHE NON STA AGGIORNANDO LE MODIFICHE DI HOME-MANAGER
Se non restarta, fare
```
systemctl restart home-manager-manuel.service
```

Ogni volta che si fanno modifiche alla barra delle `favorite-apps` di `"org/gnome/shell"` riavviare il sistema per applicare le modifiche.

# Fonti

- [Vimjoyer - NixOS beginner guide](https://www.youtube.com/watch?v=bjTxiFLSNFA)