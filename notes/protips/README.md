<sub>[Poznámky](../README.md)
| Užitečné informace a tipy k tvorbě BP
<sub>

---

# Užitečné informace a tipy k tvorbě BP

- [Státní závěrečná zkouška - Závěrečná práce (Course Pages)](
    https://courses.fit.cvut.cz/SZZ/tema-prace.html)
- [FIT ČVUT thesis tips (GitHub)](https://github.com/hroncok/fit-thesis-tips)
- [ProjectsFIT]
- [Jak uspět s bakalářkou na FIT (časopis Buď FIT)](
    https://casopis.fit.cvut.cz/obecne/ak-uspet-s-bakalarkou-na-fit/)
- [Digitální knihovna ČVUT (DSpace)](https://dspace.cvut.cz)
- [Jak psát závěrečnou práci (Ústřední knihovna ČVUT)](
    http://knihovna.cvut.cz/seminare-a-vyuka/jak-psat/jak-psat-zaverecnou-praci)
- [Google Scholar](https://scholar.google.com)
- ~~[Odevzdané závěrečné práce (Systém závěrečné práce)](
    https://is.fit.cvut.cz/group/intranet/zp/list)~~ (starý systém, nahrazen od
    letního semestru B202 systémem [ProjectsFIT])

[ProjectsFIT]: https://projects.fit.cvut.cz

## Snímky editoru

Do LaTeX zdroje lze vložit vektorové obrázky v PDF a rastrové obrázky ve
formátech PNG a JPEG. Pro snímky editoru bude lepší použít vektorovou variantu,
namísto prostého rastrového screenshotu.

Jednou možností, jak získat z Atomu PDF, je zavolat v konzoli Atomu funkci
`print()`. Po zavolání se zobrazí dialogové okno s výběrem tiskárny a možnostmi
tisku; pro vytvoření PDF je zde potřeba zvolit virtuální PDF tiskárnu - jedna
taková je i defaultně ve Windows 10. Jedním problémem tohoto přístupu je, že
je zde jediná volba tisku, a tou je volba horizontální, respektive vertikální
orientace. Druhým problémem je, že vzniklé PDF obsahuje rasterizovaný obrázek.
Navíc se obsah zdá nějak uřízlý. Tyto problémy možná budou závislé na OS a
konkrétní virtuální PDF tiskárně, ale existuje další řešení.

Lepším, byť trochu komplikovanějším řešením, je využít Chrome DevTools Protocol.
Nejprve je potřeba v libovolném Chromium-based prohlížeči otevřít stránku
<chrome://inspect/#devices> (nefunguje to v soukromém okně). Následně otevřeme
Atom ve speciálním debugovacím režimu s pomocí příkazu `atom --inspect`. Na
otevřené stránce v prohlížeči by měl být vidět seznam "Remote Target #LOCALHOST"
a v něm položka Node.js. Otevřeme odkaz "inspect" této položky a otevře se okno
s konzolí. Do této konzole vložíme následující script (a upravíme cestu výstupu,
případně [možnosti tisku](
https://www.electronjs.org/docs/api/web-contents#contentsprinttopdfoptions) dle
libosti):

```js
const fs = require('fs').promises;
const path = require('path');

async function printPDF(
    filepath = 'printPDF-output.pdf',
    options = {
        landscape: true,
        marginsType: 1,
        printBackground: true,
        printSelectionOnly: false,
}) {
    const browserWindow = atomApplication.getAllWindows()[0].browserWindow;
    const webContents = browserWindow.webContents;
    const data = await webContents.printToPDF(options);
    await fs.writeFile(filepath, data);
    const resFilepath = path.resolve(process.cwd(), filepath);
    return `Writing PDF to "${resFilepath}".`; // console.log doesn't work here
}

await printPDF('cesta/k/výslednému.pdf');
```

Výsledné PDF pak můžeme případně různě oříznout dle potřeby (např. [tento online
nástroj](https://pdf.online/crop-pdf) se zdá dobře použitelný) a poté jej přímo
vložit do LaTeX zdroje.

---

Reference:
- <https://www.electronjs.org/docs/tutorial/application-debugging>
- <https://www.electronjs.org/docs/tutorial/debugging-main-process>
- <https://chromedevtools.github.io/devtools-protocol/>
- <https://nodejs.org/en/docs/guides/debugging-getting-started/>
- <https://www.geeksforgeeks.org/generate-pdf-in-electronjs/>
- <https://stackoverflow.com/questions/63016984/electron-print-to-pdf-selection-only>
