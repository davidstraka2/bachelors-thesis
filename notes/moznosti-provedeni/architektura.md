<sub>[Poznámky](../README.md)
| [Možnosti provedení](README.md)
| Architektura
<sub>

---

# Architektura

- základní modul
    - rozparsuje WooWoo dokument
        - vzhledem k jednoduchosti syntaxe by mohl stačit relativně jednoduchý
            systém využívající regulární výrazy
    - zobrazí živý náhled
    - zobrazí ovládací prvky
        - *(nebo je nějak zprostředkuje)*
        - např. nástrojová lišta
- překladové moduly
    - poskytnou základnímu modulu funkce pro překlad jednotlivých typů prvků
        dokumentu tak, aby je bylo možno zobrazit v živém náhledu
        - funkce mohou mít podobu jednoduché modifikace textu, případně by šlo
            využít React komponent (nebo něčeho podobného)
    - přidají ovládací prvky pro práci s určitými typy prvků dokumentu
    - mohou případně přidat i další chování specifické pro své typy prvků
        dokumentu (např. nějaké speciální našeptávání)
    - nějaké základní překladové moduly (např. zvýraznění, citace, seznam,
        tabulka) mohou být poskytovány spolu se základním modulem, další mohou
        být poskytovány ve formě volitelných rozšíření (např. LaTeX matematika,
        [TikZ](https://texample.net/tikz/examples/) diagramy, [MusicXML](
        https://www.w3.org/2017/12/musicxml31/))
    - také by mohl být jeden či více modulů pro překlad neznámých/
        nepodporovaných typů prvků dokumentu (pro případ, že by se vyskytly)
        - kdyby takových modulů bylo více, mohl by si uživatel zvolit jeden
            aktivní
- šablonové moduly
    - určí, kterého typu je který prvek dokumentu
    - v podstatě takové "lepidlo" mezi základním modulem a překladovými moduly
    - aktivní šablonu by pak mělo jít zvolit pomocí jednoduchého nastavení (v
        nastaveních editoru nebo konfiguračním souborem apod.)
    - #todo zvýrazňování syntaxe?

Tato architektura by umožnila jednoduché rozšíření v podobě různých šablon a
syntaktických prvků.
