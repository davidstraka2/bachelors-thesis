<sub>[Poznámky](../README.md)
| [Možnosti provedení](README.md)
| Rozšíření existujícího editoru: Atom
<sub>

---

# Rozšíření existujícího editoru: Atom

[Web](https://atom.io)
| [Repozitář](https://github.com/atom/atom)
| [Dokumentace](https://atom.io/docs)<sup>1</sup>

- open source (MIT)
- aktivně vyvýjen GitHubem (jejž koupil Microsoft)
- postaven na Electronu, napsán převážně v JavaScriptu (z části také v
    CoffeeScriptu, především starší části)
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

*Následuje seznam existujících rozšířeních pro Atom, která do něj přidávají
funkcionalitu nějakým způsobem relevantní našim požadavkům.*

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

---

*<sup>1</sup> Včetně API reference rozšíření*
