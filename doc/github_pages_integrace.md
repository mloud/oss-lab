# Integrace GitHub Pages

Tento projekt je čistě statický web (HTML, CSS, JS bez frameworků jako byl Vite). 
Je nastaven tak, aby se automaticky nasazoval na GitHub Pages pomocí GitHub Actions, jakmile dojde k odeslání (push) kódu na hlavní větev `main`.

## Jak to celé funguje

1. **Commit a Push**: 
   Jakmile upravíš kód, provedeš commit a pushneš změny na vzdálený repozitář na GitHubu do větve `main`.

2. **Spuštění Action (Workflow)**: 
   GitHub zaznamená změnu ve větvi `main` a podívá se do složky `.github/workflows/static.yml`. Tento soubor obsahuje návod pro GitHub, co má v takovém případě udělat.

3. **Nasazení (Deploy) na GitHub Pages**: 
   Jelikož jde o statický web, není potřeba nic složitě kompilovat nebo sestavovat přes NPM.
   GitHub Action vezme tvé stávající soubory v repozitáři a rovnou je zkopíruje a vystaví na webovém serveru GitHub Pages.

## Důležité nastavení na GitHubu

Aby tento proces fungoval, je třeba mít v repozitáři na GitHubu zapnuté nasazování přes GitHub Actions (což je moderní a doporučovaný způsob):
- Běž do repozitáře na webu GitHub.
- Přejdi do záložky **Settings** -> vlevo v menu vyber **Pages**.
- V sekci **Build and deployment** nastav položku **Source** na volbu **GitHub Actions**.

*(Pozn.: Žádné složité nastavování Vite a `base` cest zde už není potřeba. GitHub Action z `static.yml` se o vše postará sama.)*
