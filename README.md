# Skilly na hledání klientů a osobní oslovení

Sada skillů pro AI asistenta, který vám pomůže najít vhodné firmy, ověřit kontakt, napsat osobní e-mail se dvěma follow-upy a připravit odpovědi a schůzky. Inspirací byly postupy open source projektu Sellbird, text je napsaný nově a česky.

**Nejdůležitější pravidlo:** asistent nikdy nic neodešle sám. Připraví koncept, vy ho zkontrolujete a odešlete. Odeslat smí jen na váš výslovný pokyn ke konkrétnímu e-mailu.

## Co je ve složce

| Soubor | K čemu |
|---|---|
| `onboarding-firmy/SKILL.md` | Asistent se vyptá na vaši firmu, nabídku, zákazníka, region, důkazy, tón a tabu a uloží z toho profil firmy. |
| `research-leadu/SKILL.md` | Najde firmy a rozhodující lidi ve veřejných zdrojích, ověří e-mail, dá skóre 0 až 10. |
| `psani-osloveni/SKILL.md` | Napíše osobní první e-mail a 2 follow-upy. |
| `odpovedi-a-schuzky/SKILL.md` | Roztřídí odpovědi, navrhne reakci a termín schůzky. |
| `pravidla-osloveni/SKILL.md` | Pevná pravidla, GDPR a obchodní sdělení v ČR a EU, doručitelnost. |
| `chatgpt-instrukce.md` | Vše v jednom textu pro ChatGPT (vejde se do limitu 8000 znaků). |
| `zip/` | Každý skill zabalený zvlášť pro nahrání do Clauda. |

Pořadí práce: onboarding-firmy, research-leadu, psani-osloveni, odpovedi-a-schuzky. Skill pravidla-osloveni platí pořád.

## Jak to vložit do Clauda

**Varianta A: Skills** (doporučeno, pokud je máte k dispozici)
1. V Claudovi otevřete nastavení a sekci Skills (podle verze aplikace bývá pod Capabilities).
2. Nahrajte postupně ZIP soubory ze složky `zip/`. Každý obsahuje jednu složku se souborem SKILL.md.
3. Zapněte webové vyhledávání.
4. Napište: "Chci začít hledat klienty." Claude sám použije onboarding-firmy.

**Varianta B: Projects**
1. Založte nový projekt, třeba "Hledání klientů".
2. Do znalostí projektu nahrajte všech pět souborů SKILL.md.
3. Do instrukcí projektu napište: "Řiď se soubory SKILL.md v projektu. Začni onboardingem firmy. Nikdy nic neodesílej sám."
4. Až vznikne profil firmy, uložte ho do projektu jako `profil-firmy.md`. Stejně tak tabulku oslovených.

## Jak to vložit do ChatGPT

1. Otevřete Prozkoumat GPT a Vytvořit, pak záložku Konfigurace.
2. Do pole Pokyny vložte celý obsah souboru `chatgpt-instrukce.md`.
3. V Možnostech zapněte vyhledávání na webu.
4. Až vznikne profil firmy, nahrajte ho jako soubor do Znalostí GPT, ať ho nemusíte pokaždé opakovat.
5. GPT si nechte soukromý, profil obsahuje vaše obchodní informace.

Pokud nechcete vlastní GPT, můžete text vložit i na začátek běžné konverzace nebo do projektu v ChatGPT.

## Jak to vložit do Grok Bota

1. Pošlete Grok Botovi soubory SKILL.md (nebo je vložte do chatu) a napište: "Ulož si tyhle skilly."
2. Formát SKILL.md s hlavičkou name a description Grok Bot čte přímo.
3. Napište: "Chci začít hledat klienty." Profil firmy si uloží do paměti.
4. Pokud máte připojený Gmail, nechte asistenta připravovat koncepty, ne odesílat.

## S jakými nástroji to funguje nejlépe

- **Webové vyhledávání a čtení webů.** Bez něj asistent firmy nenajde. Zapněte ho vždy.
- **Tabulka na evidenci oslovených** (Google Sheets, Excel, nebo soubor v projektu). Hlídá, aby se nikdo neoslovil dvakrát.
- **E-mail jen v režimu konceptů.** Pokud asistenta připojíte ke Gmailu nebo Outlooku, ať jen vytváří koncepty. Odesílejte sami.
- **Kalendář nebo rezervační odkaz.** Termíny schůzek pak asistent bere z reality, ne z hlavy.
- **Oddělená doména a schránka pro oslovení** s nastaveným SPF, DKIM a DMARC, ať neriskujete pověst hlavní adresy.

## Co skilly záměrně nedělají
- Neodesílají e-maily a nespouštějí žádný autopilot.
- Nepřihlašují se na LinkedIn ani jinam vaším heslem a nestahují data za přihlášením.
- Nevymýšlejí kontakty, reference ani čísla.
- Nedělají hromadné rozesílky.

## Pozor na zákon
V ČR zákon č. 480/2004 Sb. vyžaduje pro obchodní sdělení e-mailem předchozí souhlas, a Úřad pro ochranu osobních údajů to vztahuje i na firmy a adresy typu info@. Skill vás na riziko upozorní a doporučí přednostně teplé kontakty, ale odpovědnost za odeslání nesete vy. Podrobnosti jsou v `pravidla-osloveni/SKILL.md`. Nejde o právní radu.

## Licence a původ
Postupy jsou inspirované open source projektem Sellbird (github.com/ethanplusai/sellbird, licence AGPL-3.0). Žádný text ani kód z něj není převzatý doslova.
