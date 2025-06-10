# 🚀 SG Job Creator

**Pokročilý systém pro správu jobů v FiveM ESX frameworku**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![FiveM](https://img.shields.io/badge/FiveM-Compatible-blue.svg)](https://fivem.net/)
[![ESX](https://img.shields.io/badge/ESX-Legacy-green.svg)](https://github.com/esx-framework/esx-legacy)

## 📋 Obsah

- [Funkce](#-funkce)
- [Požadavky](#-požadavky)
- [Instalace](#-instalace)
- [Konfigurace](#-konfigurace)
- [Použití](#-použití)
- [API](#-api)
- [Screenshoty](#-screenshoty)
- [Podpora](#-podpora)
- [Licence](#-licence)

## ✨ Funkce

### 🎯 Základní funkce
- **Vytváření jobů** - Jednoduché vytváření nových pracovních pozic
- **Správa gradů** - Kompletní systém pro správu pozic v rámci jobu
- **Whitelisted joby** - Podpora pro joby vyžadující povolení
- **Real-time aktualizace** - Okamžité zobrazení změn bez restartu
- **Vyhledávání** - Rychlé vyhledávání v seznamu jobů

### 🎨 Moderní UI
- **Responzivní design** - Funguje na všech rozlišeních
- **Dark theme** - Moderní tmavý vzhled
- **Animace** - Plynulé přechody a efekty
- **Toast notifikace** - Elegantní zpětná vazba
- **Modal dialogy** - Intuitivní editační rozhraní

### 🔧 Pokročilé funkce
- **Konfigurovatelné notifikace** - ox_lib, ESX, QB-Core nebo vlastní UI
- **Flexibilní oprávnění** - Nastavitelné skupiny s přístupem
- **Debug mód** - Podrobné logování pro vývojáře
- **Automatické zavření** - UI se zavře po kritických operacích
- **Confirm dialogy** - Potvrzovací dialogy pro bezpečnost

### 📊 Statistiky
- **Dashboard** - Přehled všech jobů a statistik
- **Počítadla** - Celkový počet jobů, gradů a whitelisted pozic
- **Přehled jobů** - Rychlý náhled všech existujících jobů

## 📋 Požadavky

### Povinné
- **FiveM Server** (nejnovější verze)
- **ESX Legacy** nebo **ESX 1.2+**
- **oxmysql** (MySQL databáze)

### Volitelné
- **ox_lib** (pro pokročilé notifikace)
- **QB-Core** (experimentální podpora)

## 🚀 Instalace

### 1. Stažení
\`\`\`bash
git clone https://github.com/your-username/sg_jobcreator.git
\`\`\`

### 2. Umístění
Zkopírujte složku `sg_jobcreator` do vašeho `resources` adresáře.

### 3. Databáze
Spusťte SQL script pro vytvoření potřebných tabulek:
\`\`\`sql
-- Spusťte scripts/install.sql ve vaší MySQL databázi
\`\`\`

### 4. Server.cfg
Přidejte do vašeho `server.cfg`:
\`\`\`cfg
ensure sg_jobcreator
\`\`\`

### 5. Restart
Restartujte server nebo použijte:
\`\`\`
refresh
start sg_jobcreator
\`\`\`

## ⚙️ Konfigurace

### Config.lua
\`\`\`lua
Config = {}

-- Framework nastavení
Config.Framework = 'esx' -- 'esx' nebo 'qb-core'

-- Příkaz pro otevření UI
Config.Command = 'jobcreator'

-- Oprávnění
Config.Permissions = {
    'admin',
    'superadmin'
}

-- UI nastavení
Config.UI = {
    AutoCloseAfterRestart = true,
    AutoCloseDelay = 2000,
    ShowConfirmDialogs = true,
    EnableAnimations = true
}

-- Debug režim
Config.Debug = false
\`\`\`

### Notifikační systémy

#### Vlastní UI
\`\`\`lua
- Toast notifikace v UI
- Plně přizpůsobitelné

## 🎮 Použití

### Otevření UI
\`\`\`
/jobcreator
\`\`\`
*Vyžaduje admin oprávnění*

### Vytvoření jobu
1. Otevřete UI pomocí `/jobcreator`
2. Přejděte na záložku "Creator"
3. Vyplňte formulář:
   - **Název jobu**: Interní název (např. `police`)
   - **Zobrazovaný název**: Název pro hráče (např. `Policie`)
   - **Základní plat**: Výchozí plat pro grade 0
   - **Whitelisted**: Zaškrtněte pro whitelisted job
4. Klikněte "Vytvořit Job"

### Správa gradů
1. V seznamu jobů klikněte na "Grady"
2. Přidejte nový grade:
   - **Level**: Číslo gradu (0-10)
   - **Název**: Interní název gradu
   - **Zobrazovaný název**: Název pro hráče
   - **Plat**: Plat pro tento grade
3. Klikněte "Přidat Grade"

### Editace a mazání
- **Edit**: Upravte existující job nebo grade
- **Smazat**: Odstraňte job (pouze pokud ho nikdo nemá)
- **Restart ESX Jobs**: Restartuje ESX job systém

## 📸 Screenshoty

### Dashboard
![Dashboard](https://via.placeholder.com/800x400/1e293b/f1f5f9?text=Dashboard+View)

### Job Creator
![Creator](https://via.placeholder.com/800x400/1e293b/f1f5f9?text=Job+Creator)

### Grade Management
![Grades](https://via.placeholder.com/800x400/1e293b/f1f5f9?text=Grade+Management)

## 🛠️ Vývoj

### Struktura projektu
\`\`\`
sg_jobcreator/
├── client/
│   └── main.lua          # Client-side logika
├── server/
│   └── main.lua          # Server-side logika
├── html/
│   ├── index.html        # UI struktura
│   ├── script.js         # UI logika
│   └── style.css         # UI styly
├── config.lua            # Konfigurace
├── fxmanifest.lua        # Resource manifest
\`\`\`

### Přispívání
1. Forkněte repository
2. Vytvořte feature branch (`git checkout -b feature/AmazingFeature`)
3. Commitněte změny (`git commit -m 'Add some AmazingFeature'`)
4. Pushněte do branch (`git push origin feature/AmazingFeature`)
5. Otevřete Pull Request

## 🐛 Známé problémy

### Časté problémy a řešení

#### UI se neotevírá
- Zkontrolujte oprávnění v `Config.Permissions`
- Ověřte, že máte admin práva
- Zkontrolujte F8 konzoli pro chyby

## 📞 Podpora

### Discord
Připojte se na náš Discord username: pleonshit.cz

### GitHub Issues
Pro bug reporty a feature requesty použijte [GitHub Issues](https://github.com/Merodicoexe/sg_jobcreator/issues)

### Dokumentace
Kompletní dokumentace je dostupná na [Wiki](https://github.com/Merodicoexe/sg_jobcreator/wiki)

## 🔄 Changelog

### v2.0.0 (Aktuální)
- ✨ Přidán config.lua s flexibilními nastaveními
- 🎨 Nové moderní UI s dark theme
- 🔔 Podpora pro ox_lib, ESX a QB-Core notifikace
- 🛡️ Vlastní confirm dialogy místo browser alertů
- 📊 Dashboard s statistikami
- 🐛 Opraveny všechny známé bugy

### v1.0.0
- 🎉 Počáteční release
- ⚡ Základní CRUD operace pro joby
- 👥 Správa gradů
- 🎯 ESX kompatibilita

## 📄 Licence

Tento projekt je licencován pod MIT licencí - viz [LICENSE](LICENSE) soubor pro detaily.

## 🙏 Poděkování

- **ESX Framework** - Za skvělý framework
- **ox_lib** - Za moderní UI komponenty
- **FiveM Community** - Za podporu a feedback

## 🌟 Podpořte projekt

Pokud se vám projekt líbí, dejte mu ⭐ na GitHubu!

---

**Vytvořeno s ❤️ týmem SG Scripts**

*Pro více scriptů navštivte náš [GitHub](https://github.com/Merodicoexe)*
