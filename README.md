# SSH-to-git

* CD'a över till ~/.ssh

* ```ls -la```

* ```ssh-keygen -t rsa -b 4096 -C your-email```

* Filerna ``ìd_rsa```och ```id_rsa.pub``` skapades

* Kontrollera att ssh-agenten körs med ```eval "$(ssh-agent -s)"```

* Lägg till privata nyckeln till ssh-agent ```ssh-add id_rsa```

* Kopiera innehållet i publika nyckeln ```pbcopy < id_rsa.pub```

* Klistra in innehållet i clipboard till GITHUB > settings > ssh and gpg settings

* Testar autentifikation mot GITHUB ```ssh -T git@github.com``` Detta lägger också till i filen ```known_hosts

* 
