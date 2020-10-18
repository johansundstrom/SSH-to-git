# SSH-to-github

## BASH

1. Skapa och CD'a till ~/.ssh
2. Lista innehållet ```ls -la```
1. Skapa nycklar ```ssh-keygen -t rsa -b 4096 -C your-email```
1. Kontrollera att filerna ```ìd_rsa``` (privat) och ```id_rsa.pub``` (publik) skapades
1. Kontrollera att ssh-agenten körs med ```eval "$(ssh-agent -s)"``` svar med PID ges
1. Lägg till privata nyckeln till ssh-agent ```ssh-add id_rsa```
1. Kopiera innehållet i publika nyckeln ```pbcopy < id_rsa.pub```
1. Klistra in innehållet i clipboard till GITHUB > settings > ssh and gpg settings
1. Testar autentifikation mot GITHUB ```ssh -T git@github.com``` Detta lägger också till i filen ```known_hosts```
1. Vid clone använd ```SSH copy URL``` istället för ```HTTPS copy URL```
1. Gå till shell och toucha, add, commit och push. Detta kräver inte inlogg

## VS CODE

* Klicka på "Source Control"
* Klicka på "Open Repository"
* Klistra in ```git@github.com:xxxxxx.git```
* Open

## Windows

* I Apps and Features, se till att ```Open SSH Server``` är startad, annars lägg till
* Kontrollera att servicen är startad med ```ssh-agent -s```
* Se Bash instruktion p. 6

### Problem

* "Could not open a connection to your authentication agent"
* ```"C:\Program Files\Git\cmd\start-ssh-agent.cmd"``` 
* Skriv lösenordet som kombinerades vid skapandet av nyckel

## Förlorad publik nyckel

* Kör ```ssh-keygen -y -f {privat-nyckel} > publik-nyckel```
* Vid password kommer prompt
