Implementace vlastního hostingu pro GIT
Veronika Šustková, Veronika Straňáková
Obchodní akademie Uherské Hradiště 
20.5.2026

Úvod
Cílem projektu je vytvořit prostor ve webovém prostředí pro vytváření a spravování repositářů. K tomu využijeme program Gitea, kteroý nainstalujeme pomocí příkazového řádku. Tento úkol si uděláme a zdokumentujeme s postupem pro dva operační systémy.

Projekt Implementace vlastního hostingu pro Git je vhodný pro nastavení vlastního lokálního Gitu. Gitea nám rozšíří Git o webové rozhraní. Je vhodná pro jedince, kteří potřebují aby Git běžel na jejich serveru. Umožňuje více lidem pracovat na jednom projektu a vidět tak historii změn, popisky. Můžeme zde i přiřazovat sobě a ostatním úkoly.

Plánujeme využít jako návod oficiální dokumentaci Gitei, případně youtube návody ale nebráníme se ani konverzaci o výsledku s umělou inteligencí.

Výsledek si ověříme tím, že otevřeme na počítači prohlížeč, kde zadáme IP adresu nebo localhost:3000 a uvidíme, zda se Git načte a jestli v něm zůstanou naše data.



Postup řešení
1.	Otevřeme aplikaci Terminál. 
2.	Zadáme příkaz pro instalaci Gitea pomocí BREW INSTALL GITEA
3.	Dále se program nainstaluje a spustíme Giteu příkazem BREW SERVICES START GITEA
4.	Do libovolného prohlížeče v počítači napíšeme localhost:3000
5.	Otevře se stránka našeho Gitu, kde si upravíme výchozí konfiguraci
6.	Nainstalujeme Giteu
7.	Pokud jsme ještě nevytvořili administrátora, tak si teď založíme 1. účet
8.	Jsme přesunuti na stránku našeho samotného Gitu, kde si můžeme vytvořit nový repozitář

1.	V příkazovém řádku zadáme příkazy 
-	Sudo apt update && sudo apt install -y docker.io docker-compose
-	Sudo systemctl enable –now docker
-	Sudo usermod -aG docker $USER && newgrp docker
2. Vytvoříme složku gitea a přesuneme se do ní příkazy mkdir ~/gitea && cd ~/gitea
3.  Zapíšeme pomocí příkazu nano docker-compose.yml do souboru tyto údaje:
version: „3“
servives:
 gitea:
  image: gitea/gitea:latest
  container_name: gitea
  restart: always
  ports:
    - "3000:3000"
    - "2222:22"
  volumes: 
    - ./data:/data
4. Následuje příkaz docker-compose up -d pro spuštění
5. Otevřeme si na stroji localhost:3000 nebo pokud máme na virtuálním stroji spuštěný síťový most nebo nastavený NAT, tak si zjistíme IP adresu virtuálky pomocí příkazu IP A.
6. Zkontrolujeme jestli se nám líbí výchozí konfigurace a sjedeme dolů pro nastavení účtu správce
7. Klikneme NAINSTALOVAT GITEA a po chvíli se dostaneme na hlavní stránku našeho Gitu

Ověření cílů
Stránka se opakovaně správně načetla a data v ní zůstaly bez jakýchkoliv chyb.
Rozdělení práce
Dokumentace, návody – Veronika Šustková
Plánování projektu – Veronika Straňáková, Veronika Šustková

Závěr
Všechny zvolené části projektu se za nás povedly. Je tady více variant, jak využít Gitu ale tahle je za nás nejvíce uživatelsky přívětivá.

Pokud by někdo použil tento návod, tak by si měl dát pozor na zapisování do souboru docker-compose.yml. Dají se zde použít jenom mezery pro odsazení a uživatel si musí pohlídat úroveň řádků.

Bylo by vhodné prozkoumat práci vícero uživatelů na jednom projektu a přidělování úkolů.
Zdroje:
Návod Gitea : Dostupné z: https://docs.gitea.com/installation/install-with-docker Citováno dne [2026-05-20]

Návod videa : Dostupné z: https://www.youtube.com/watch?v=jWN8wCNuyec Citováno dne [2026-05-20]

Ověření u Clauda : Dostupné z: https://claude.ai/share/f1959d02-fc2e-4687-98f0-9b43a280f898 Citováno dne [2026-05-20]
