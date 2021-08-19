# SSH-to-github

## GIT-BASH

1. (Skapa mappen och) CD'a till ~/.ssh
2. Lista innehållet ```ls -la```

### Skapa nycklar

3. Skapa nycklar ```ssh-keygen -t rsa -b 4096 -C <your-email>```
4. Kontrollera att filerna ```id_rsa``` (privat) och ```id_rsa.pub``` (publik) skapades
5. Kontrollera att ssh-agenten körs med ```eval "$(ssh-agent -s)"``` svar med PID ges

### Lägg till nyckeln till agenten

6. Lägg till privata nyckeln till ssh-agent ```ssh-add ~/.ssh/id_rsa```

### Kopiera publik nyckel i t.ex. GitHub

7. Kopiera innehållet i publika nyckeln ```pbcopy < ~/.ssh/id_rsa.pub``` eller ```clip < ~/.ssh/id_rsa.pub```
8. Klistra in innehållet i clipboard till GITHUB > settings > ssh and gpg settings

### Testa autentifiering

9.  Testar autentifikation mot GITHUB ```ssh -T git@github.com``` Detta lägger också till i filen ```known_hosts```

### Annat förfarande i Github

10. Vid clone repo - använd ```SSH copy URL``` istället för ```HTTPS copy URL```

### Testa

11. Gå till shell och toucha, add, commit och push. Detta kräver inte inlogg

## VS CODE

* Klicka på "Source Control"
* Klicka på "Open Repository"
* Klistra in ```git@github.com:<ditt repo>.git```
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
