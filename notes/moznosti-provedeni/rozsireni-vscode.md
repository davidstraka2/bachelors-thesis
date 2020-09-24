<sub>[Poznámky](../README.md)
| [Možnosti provedení](README.md)
| Rozšíření existujícího editoru: VS Code
<sub>

---

# Rozšíření existujícího editoru: VS Code

[Web](https://code.visualstudio.com)
| [Repozitář](https://github.com/Microsoft/vscode)
| [Dokumentace](https://code.visualstudio.com/docs)
| [API reference rozšíření](https://code.visualstudio.com/api)

- open source (MIT)
- aktivně vyvýjen Microsoftem
- postaven na [Electronu](electron.md), napsán v TypeScriptu
- Windows, OS X, Linux
- existuje také jakýsi webový port Monaco Editor
    - (respektive Monaco je nějaká menší část VS Code a jako samostatný webový
        editor se pak generuje ze zdroje VS Code)
    - [Web](https://microsoft.github.io/monaco-editor/)
        | [Repozitář](https://github.com/Microsoft/monaco-editor)
        | [API reference](
        https://microsoft.github.io/monaco-editor/api/index.html)
    - open source (MIT)
    - aktivně vyvýjen Microsoftem
    - podporuje ale jen velice omezenou podmnožinu funkcí
    - *(také - stejně jako Electron aplikace - nepodporuje mobilní zařízení)*

## Funkcionalita

*Následuje seznam klíčové funkcionality nad rámec základní funkcionality
obsažené ve většině populárních editorů kódu.*

- podpora rozšíření
    - [oficiální repozitář/obchod s rozšířeními](
        https://marketplace.visualstudio.com/vscode)
    - zabudovaný správce rozšíření
    - chybí API pro nástrojovou lištu (viz [issue](
        https://github.com/microsoft/vscode/issues/41309)) a VS Code narozdíl
        od [Atomu](rozsireni-atom.md#funkcionalita) nepodporuje manipulaci s
        jeho DOM ve jménu lepšího výkonu (viz [dokumentace](
        https://code.visualstudio.com/api/extension-capabilities/overview#restrictions
        ) nebo [Stack Overflow](https://stackoverflow.com/q/45891428/8302708))
        - nejblíže se k tomu dá dostat zneužitím jiných UI prvků (viz např.
            rozšíření [Shortcut Menu Bar](
            https://marketplace.visualstudio.com/items?itemName=jerrygoyal.shortcut-menu-bar
            ) nebo [Shortcuts](
            https://marketplace.visualstudio.com/items?itemName=gizak.shortcuts))
        - [seznam](
            https://code.visualstudio.com/api/extension-capabilities/extending-workbench
            ) UI komponent, se kterými mohou rozšíření pracovat
    - zabudovaný systém testování (viz [dokumentace](
        https://code.visualstudio.com/api/working-with-extensions/testing-extension
        ))
        - nezávyslý na testovacím frameworku
- zvýrazňování syntaxe
    - [TextMate](https://macromates.com/manual/en/language_grammars) gramatiky
- přizpůsobitelný vzhled
    - [oficiální repozitář/obchod s tématy](
        https://marketplace.visualstudio.com/vscode)
- přizpůsobitelné klávesové zkratky
- prohlížeč souborů v projektu
- otevření více souborů vedle sebe
- Git integrace
- sdílená real-time editace díky oficiálnímu rozšíření [Live Share](
    https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)
- vzdálený vývoj (viz [dokumentace](
    https://code.visualstudio.com/docs/remote/remote-overview))
    - umožnuje pohodlný vývoj za použití kontejneru, vzdáleného počítače nebo
        [WSL](https://docs.microsoft.com/cs-cz/windows/wsl/)
