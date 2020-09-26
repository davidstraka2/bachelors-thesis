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

Webové aplikace umožňují intuitivnější tvorbu UI oproti mnohým dalším
alternativám. Poskytují rozsáhlé JavaScriptové API a existuje pro ně obrovské
množství otevřených knihoven pokrývajících nejrůznější funkcionalitu. Také pro
ně existuje velké množství kvalitních debugovacích a testovacích nástrojů.

Technologie jako PWA sice nabízí možnost vytvořit webovou aplikaci, která bude
fungovat plně offline, ale se všemi výhodami webových aplikací přinášejí i
stejná omezení, jako např. velice omezenou práci se souborovým systémem nebo
nemožnost práce s procesy systému.

Electron v sobě spojuje výhody Node.js a webových aplikací. UI je tak možno
vytvořit stejně jako jakoukoli jinou webovou stránku, je možno využít Chrome Dev
Tools atd. Zároveň je zde ale plný přístup k souborovému systému, možnost
spouštět podprocesy a komunikovat s nimi prostřednictvím standardního
vstupu/výstupu, dokonce díky [native addons](https://nodejs.org/api/addons.html)
lze pracovat s C/C++ knihovnami přímo jako s JavaScript knihovnami (bohužel
tvorba bindings je docela složitý proces).

Nejlepším řešením se ale zdá, pokud možno rozšířit jeden z populárních
otevřených editorů, které již poskytují mnoho základních funkcí, za nimiž stojí
velké množství práce. Zároveň většinou poskytují i nespočet funkcí navíc, které
sice nejsou nutné pro náš projekt, ale dále zvyšují uživatelský komfort (např.
integrovaná práce s gitem, živá kolaborativní editace, existence mnoha různých
témat atd.).

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

Architekturu bude nejlepší koncipovat tak, aby byl výsledný editor/rozšíření co
nejlépe dále rozšiřitelné při tvorbě dalších WooWoo šablon. Zároveň by bylo
dobré oddělit rozšíření přidávající funkcionalitu od těch, která pouze řeknou,
které prvky šablona podporuje a jak je pojmenovává - takový přístup umožní
pohodlné znovuužutí funkcionality více šablonami.

Nejlepším řešením se tedy zdá realizace formou rozšíření nebo skupiny
rozšířeních pro Atom. Jako následující krok se nabízí ověřit, že takto půjde
realizovat klíčové požadavky, u kterých to není nutně zřejmé (živý náhled,
nástrojová lišta, případně prověřit) a architekturu (jak dobře funguje
komunikace/spolupráce mezi více rozšířeními). Také bude dobré ověřit funkčnost
některých důležitých knihoven pro podporu LaTeX matematiky nebo TikZ diagramů
(případně využití nativního software v podobě komunikace přes stdio).
