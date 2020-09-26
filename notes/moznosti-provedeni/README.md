<sub>[Poznámky](../README.md)
| Možnosti provedení
<sub>

---

# Možnosti provedení

## [PWA](pwa.md)

## [Electron](electron.md)

## Rozšíření existujícího editoru

### [Ace](rozsireni-ace.md)
### [Atom](rozsireni-atom.md)
### [Light Table](rozsireni-lighttable.md)
### [VS Code](rozsireni-vscode.md)

## [Knihovny](knihovny.md)

## [Architektura](architektura.md)

## Souhrn a diskuze

#todo Ace, PWA

Light Table není aktivně udržován/vyvýjen (a není ani ve stabilní verzi), má
pouze menší komunitu uživatelů, existuje pro něj méně rozšíření, jeho
dokumentace mi přijde nedostatečná a je napsán v pro mě zcela neznámém jazyku.

VS Code je pro mě z pohledu uživatele nejlepší editor pro obecné použití, má
skvělou dokumentaci a největší komunitu kolem, ale neumožňuje rozšířením
manipulaci s jeho DOM a zároveň mu chybí funkcionalita nástrojové lišty s
odpovídajícím API.

Atom pokrývá všechnu nutnou funkcionalitu a poskytuje rozšířením největší
svobodu co do manipulace s ním, ostatně jeho slogan je "A hackable text editor
for the 21st Century". Má přehlednou dokumentaci (byť na VS Code v tomhle ohledu
nemá), rozumně aktivní komunitu a spoustu rozšíření. Nabízí systém pro tvorbu
integračních testů rozšířeních. Jediná hezká funkcionalita, která by mi z
pohledu uživatele oproti Atomu chyběla, je podpora vzdáleného vývoje s
kontejnery nebo WSL, to ale není nic nutného pro potřeby našeho rozšíření.

Nejlepším řešením se tedy zdá realizace formou rozšíření nebo skupiny
rozšířeních pro Atom. Jako následující krok se nabízí ověřit, že takto půjde
realizovat klíčové požadavky, u kterých to není nutně zřejmé (živý náhled,
nástrojová lišta, případně prověřit, jak dobře funguje komunikace/spolupráce
mezi více rozšířeními).
