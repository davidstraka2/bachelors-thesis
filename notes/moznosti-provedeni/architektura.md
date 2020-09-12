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
    - přidají ovládací prvky pro práci s určitými typy prvků dokumentu
    - nějaké základní překladové moduly (např. zvýraznění, citace, seznam,
        tabulka) mohou být poskytovány spolu se základním modulem, další mohou
        být poskytovány ve formě volitelných rozšíření (např. LaTeX matematika,
        [TikZ](https://texample.net/tikz/examples/) diagramy, [MusicXML](
        https://www.w3.org/2017/12/musicxml31/))
- šablonové moduly
    - určí, kterého typu je který prvek dokumentu
    - v podstatě takové "lepidlo" mezi základním modulem a překladovými moduly
    - #todo zvýrazňování syntaxe?

Tato architektura by umožnila jednoduché rozšíření v podobě různých šablon a
syntaktických prvků.
