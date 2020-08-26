# SSH-to-github

## BASH

1. CD'a över till ~/.ssh
2. Visa innehållet i katalogen med ```ls -la```
1. Skapa nyckalr med ```ssh-keygen -t rsa -b 4096 -C your-email```
1. Kontrollera att filerna ```ìd_rsa```och ```id_rsa.pub``` skapades
1. Kontrollera att ssh-agenten körs med ```eval "$(ssh-agent -s)"``` svar med PID ges
1. Lägg till privata nyckeln till ssh-agent ```ssh-add id_rsa```
1. Kopiera innehållet i publika nyckeln ```pbcopy < id_rsa.pub```
1. Klistra in innehållet i clipboard till GITHUB > settings > ssh and gpg settings
1. Testar autentifikation mot GITHUB ```ssh -T git@github.com``` Detta lägger också till i filen ```known_hosts```
1. Vid clone använd SSH copy URL istället för HTTPS copy URL
1. Gå till shell och toucha, add, commit och push. Detta kräver inte inlogg

## VS CODE

* Klicka på "Source Control"
* Klicka på "Open Repository"
* Klistra in ```git@github.com:xxxxxx.git```
* Open

## Windows

* I Apps and Features, se till att Open SSH Server är startad, annars lägg till
* Kontrollera att servicen är startad med ```ssh-agent -s```
* Se Bash instruktion p. 6