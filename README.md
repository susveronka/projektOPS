# Vytvoření vlastního gitu pomocí instalace Gitea na MacOS a Debian.

## pro MacOS

1) Otevřeme aplikaci Terminál.
   
2) Zadáme příkaz pro instalaci gitea pomocí BREW INSTALL GITEA.

   <img width="1470" height="956" alt="Snímek obrazovky 2026-05-01 v 9 52 30" src="https://github.com/user-attachments/assets/f7d0ef8f-c014-4baa-940f-16d2aa49bc00" />

3) Dále se program nainstaluje a spustíme giteu příkazem BREW SERVICES START GITEA.

<img width="1470" height="956" alt="Snímek obrazovky 2026-05-01 v 9 52 43" src="https://github.com/user-attachments/assets/92f1fb25-3318-4297-9b36-205652ba6c84" />

4) Do libovolného prohlížeče v počítači napíšeme localhost:3000.


5) Otevře se stránka našeho gitu, kde si navolíme nastavení.

     <img width="1470" height="956" alt="Snímek obrazovky 2026-05-01 v 9 37 51" src="https://github.com/user-attachments/assets/cc0c1867-73ff-4231-be54-df224dccd2fa" />
     
6) Nainstalujeme giteu

   <img width="1470" height="956" alt="Snímek obrazovky 2026-05-01 v 9 40 51" src="https://github.com/user-attachments/assets/19ac47cb-3c12-459d-97a6-b70a1e713403" />

7) Pokud jsme ještě nevytvořili administrátora, tak si teď založíme 1. účet.

   <img width="1470" height="956" alt="Snímek obrazovky 2026-05-01 v 9 40 46" src="https://github.com/user-attachments/assets/52997e1b-67a4-4325-9e20-a1c13f9b15fe" />


8) Jsme přesunuti na stránku našeho samotného gitu, kde si můžeme vytvořit nový repozitář.

  <img width="1470" height="956" alt="Snímek obrazovky 2026-05-01 v 9 41 47" src="https://github.com/user-attachments/assets/c75fd96a-59e1-4be4-825f-f3cf20c9b06f" />



## Návod pro Debian

1) V příkazovém řádku zadáme příkazy
   - sudo apt update && sudo apt install -y docker.io docker-compose
   - sudo systemctl enable --now docker
   - sudo usermod -aG docker $USER && newgrp docker
     
   <img width="652" height="436" alt="Snímek obrazovky 2026-06-08 v 5 26 20" src="https://github.com/user-attachments/assets/d30eca73-8c08-4ba1-9b60-03d21c049991" />
<img width="652" height="436" alt="Snímek obrazovky 2026-06-08 v 5 32 48" src="https://github.com/user-attachments/assets/504cbe60-6c2f-4e51-9a48-4a6e6a07002b" />

2) Vytvoříme složku gitea a přesuneme se do ní

   <img width="652" height="436" alt="Snímek obrazovky 2026-06-08 v 8 33 23" src="https://github.com/user-attachments/assets/d0897915-40f3-440d-b813-ececbb1acf14" />

3) Zapíšeme pomocí příkazu nano docker-compose.yml

version: "3"

services:

  gitea:
  
    image: gitea/gitea:latest
    
    container_name: gitea
    
    restart: always
    
    ports:
    
      - "3000:3000"
      
      - "2222:22"
      
    volumes:
    
      - ./data:/data

4) Následuje příkaz docker-compose up -d

<img width="652" height="436" alt="Snímek obrazovky 2026-06-08 v 15 40 25" src="https://github.com/user-attachments/assets/18c27a27-fbde-4f6c-bb47-83586fbf1937" />

5) Otevřeme si na stroji localhost:3000 nebo pokud máme na virtuálním stroji spuštěný síťový most nebo nastavený NAT, tak si zjistíme IP adresu virtuálky pomocí IP A

<img width="1119" height="672" alt="Snímek obrazovky 2026-06-08 v 15 41 20" src="https://github.com/user-attachments/assets/4a701288-8ece-46fa-b91f-a9f0293bf68b" />

6) Zkontrolujeme jestli se nám líbí výchozí konfigurace a sjedeme dolů pro nastavení účtu správce

<img width="1119" height="672" alt="Snímek obrazovky 2026-06-08 v 15 41 53" src="https://github.com/user-attachments/assets/4927157b-bc5c-4f73-93df-c80349a7e69e" />

7) Klikneme NAINSTALOVAT GITEA a po chvíli se dostaneme na hlavní stránku našeho gitu

<img width="1119" height="672" alt="Snímek obrazovky 2026-06-08 v 15 42 14" src="https://github.com/user-attachments/assets/73357498-687e-4778-9640-519edc55f9d4" />

<img width="1119" height="672" alt="Snímek obrazovky 2026-06-08 v 15 42 26" src="https://github.com/user-attachments/assets/fd2ca75a-6afd-4190-86dc-290db0f45a7c" />


