# Come funzionano le Desktop Entries su NixOS

Qua come funzionano le Desktop Entries su Linux e come costruirle: https://specifications.freedesktop.org/desktop-entry-spec/latest/

Anche su NixOS le Desktop Entries sono salvate in file `.desktop`. [Qua](https://developer.gnome.org/documentation/guidelines/maintainer/integrating.html#desktop-files) ho trovato che, in GNOME, solitamente sono salvate nei path `/usr/share/applications` oppure `$HOME/.local/share/applications` (dipende dall'impostazione del sistema),
%%
scrivere nella pagina di Linux la differenza tra "system installations" e "user installations": le variabili d'ambiente `XDG_DATA_DIRS` e `XDG_DATA_HOME` che dipendono dal tipo di installazione: per le "system installations", il primo tipicamente indica `/usr/share/applications`; per le "user installations", il secondo tipicamente è `$HOME/.local/share/applications`.
%%
ma [in NixOS non sono presenti tutti lì](https://discourse.nixos.org/t/where-are-desktop-files-located/17391/4). Per vedere in che cartelle sono contenuti, eseguire il comando:
```bash
ls -l /run/current-system/sw/share/applications
```
E uscirà tutta la lista delle applicazioni installate con le relative Desktop Entries.

Secondo [questo commento sul forum di NixOS](https://discourse.nixos.org/t/partly-overriding-a-desktop-entry/20743/2), ogni Desktop Entry viene generata automaticamente a ogni rebuild del sistema dal proprio package e l'unico modo per modificarle è modificare il package in sé, tenendo anche conto del fatto che ogni package è diverso e può costruire la sua Desktop Entry in modo diverso (quindi c'è bisogno di documentarsi leggendo il codice sorgente del package).

Home Manager mette anche a disposizione l'opzione [`xdg.desktopEntries`](https://nix-community.github.io/home-manager/options.xhtml#opt-xdg.desktopEntries) per poter creare nuove Desktop Entries: tuttavia, queste non riconoscono eventuali Entries già esistenti, quindi non sono in grado di sovrascriverle.

Come si fa:
```
exec = "obsidian obsidian://vault/GiardinoDigitale";
```

Per le icone: https://obsidian.md/blog/new-obsidian-icon/

Problema: lo apre in un'altra istanza di Obsidian, qua soluzione https://askubuntu.com/a/648467 ma infattibile su NixOS
%%
Forum: https://forum.obsidian.md/t/can-i-create-a-desktop-shortcut-to-a-specific-obsidian-vault/11734

Guida ufficiale di Obsidian: https://help.obsidian.md/Extending+Obsidian/Obsidian+URI
In particolare, qua per Linux: https://developer.gnome.org/documentation/guidelines/maintainer/integrating.html#desktop-files
- Parla anche di `desktop-file-utils`: https://www.freedesktop.org/wiki/Software/desktop-file-utils/ che poi offre 3 comandi:
	- `desktop-file-edit`
	- `desktop-file-install`
	- `desktop-file-validate`
%%