<sub>[Poznámky](../README.md)
| [Možnosti provedení](README.md)
| Rozšíření existujícího editoru: Atom
<sub>

---

# Rozšíření existujícího editoru: Atom

[Web](https://atom.io)
| [Repozitář](https://github.com/atom/atom)
| [Dokumentace](https://atom.io/docs)<sup>[1](#note-1)</sup>

- open source (MIT)
- aktivně vyvýjen GitHubem (jejž koupil Microsoft)
- postaven na [Electronu](electron.md), napsán převážně v JavaScriptu (z části
    také v CoffeeScriptu, především starší části)
- x64 / Windows, OS X, Linux
- modulární rozšiřitelná architektura
    - jednotlivá rozšíření mohou také jednoduše komunikovat mezi sebou (viz
        [dokumentace](
        https://flight-manual.atom.io/behind-atom/sections/interacting-with-other-packages-via-services/))

## Funkcionalita

*Následuje seznam klíčové funkcionality nad rámec základní funkcionality
obsažené ve většině populárních editorů kódu.*

- podpora rozšíření (okolo kterých je postavená architektura Atomu a která spolu
    mohou jednoduše komunikovat, viz výše)
    - [oficiální repozitář/obchod s rozšířeními](https://atom.io/packages)
    - zabudovaný package manager
    - zabudovaný systém testování (viz [dokumentace](
        https://flight-manual.atom.io/hacking-atom/sections/writing-specs/))
        - používá framework [Jasmine](
            https://jasmine.github.io/1.3/introduction.html) (byť starší verzi)
        - umožnuje psát integrační testy díky přístupu k DOM
        - #todo bude to fungovat i s webview pro živý náhled?
- zvýrazňování syntaxe
    - vlastní [formát](
        https://flight-manual.atom.io/hacking-atom/sections/creating-a-grammar/)
        postavený na práci se syntaktickými stromy z [Tree-sitter](
        http://tree-sitter.github.io/tree-sitter/) parseru
    - dále jsou v [legacy režimu](
        https://flight-manual.atom.io/hacking-atom/sections/creating-a-legacy-textmate-grammar/)
        podporovány [TextMate](
        https://macromates.com/manual/en/language_grammars) gramatiky
- přizpůsobitelný vzhled
    - [oficiální repozitář/obchod s tématy](https://atom.io/themes)
- přizpůsobitelné klávesové zkratky
- prohlížeč souborů v projektu
- otevření více souborů vedle sebe
- Git integrace
- sdílená real-time editace díky oficiálnímu rozšíření [Teletype](https://teletype.atom.io)

## Relevantní rozšíření

*Následuje seznam vybraných existujících rozšířeních pro Atom, která do něj
přidávají funkcionalitu nějakým způsobem relevantní našim požadavkům.*

### Atom Tool Bar

[Atom Packages](https://atom.io/packages/tool-bar)
| [Repozitář](https://github.com/suda/tool-bar)

- přidává nástrojovou lištu
- je možno přepnout mezi svislým a vodorovným režimem, měnit polohu lišty a
    velikost ikon položek
- sama o sobě je lišta prázdná, položky do ní přidávájí až další pluginy
    - např. [Toolbar for Atom](https://atom.io/packages/tool-bar-atom)
- [API](https://github.com/suda/tool-bar#integrating-instructions) pro přidání
    položek dalšími rozšířeními Atomu
- open source (MIT)
- napsán v JavaScriptu

### Atom HTML Preview

[Atom Packages](https://atom.io/packages/atom-html-preview)
| [Repozitář](https://github.com/harmsk/atom-html-preview)

- zobrazuje živý náhled HTML dokumentů
- open source (MIT)
- napsán v CoffeeScriptu
- hodně otevřených issues, ale vývoj zdá se není zrovna aktivní

### Preview for Atom

[Atom Packages](https://atom.io/packages/preview)
| [Repozitář](https://github.com/Glavin001/atom-preview)

- zobrazuje živý náhled transpilovaného kódu pro řadu různých jazyků
    - např. CoffeeScript, TypeScript, LESS, SASS/SCSS, ...
- open source (MIT)
- napsán v CoffeeScriptu
- není již udržován

### TikZ-Preview

[Atom Packages](https://atom.io/packages/tikz-preview)
| [Repozitář](https://github.com/PhilippImhof/tikz-preview)

- inline náhled [TikZ](https://texample.net/tikz/examples/) diagramů v LaTeX
    dokumentech
- vyžaduje LaTeX instalaci
- open source (MIT)
- napsán v JavaScriptu

### Juno

[Web](https://junolab.org)
| [Atom Packages](https://atom.io/packages/uber-juno)
| [Repozitář](https://github.com/JunoLab/atom-julia-client)
| [Dokumentace](http://docs.junolab.org/latest/)

- prostředí pro práci s jazykem Julia
- živá zpětná vazba, zvýrazňování syntaxe, grafy, integrace s Julia debuggerem
- open source (MIT)
- napsán v JavaScriptu, CoffeeScriptu a Julii
- od léta 2020 je již pouze "udržován" a vývojáři Juno spojili síly s vývojáři
    rozšíření pro VS Code ([Visual Studio Marketplace](
    https://marketplace.visualstudio.com/items?itemName=julialang.language-julia
    ), [repozitář](https://github.com/julia-vscode/julia-vscode))

## Relevantní základní rozšíření

*Následuje seznam vybraných základních rozšířeních pro Atom, která do něj
přidávají funkcionalitu nějakým způsobem relevantní našim požadavkům.*

*Základní rozšíření jsou vyvýjena přímo vývojáři Atomu a jsou s ním standardně
instalována. Jedná se tedy vzhledem k modulární architektuře editoru prakticky o
volitelnou součást samotného editoru.*

### Markdown Preview

[Atom Packages](https://atom.io/packages/markdown-preview)
| [Repozitář](https://github.com/atom/markdown-preview)

- zobrazuje živý náhled Markdown dokumentů
- open source (MIT)
- napsán v JavaScriptu

---

*<a href="#note-1" name="note-1"><sup>1</sup></a> Včetně API reference
rozšíření*
