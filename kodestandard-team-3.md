
# Team 3's Kodestandarder :rocket:

Det er nemmere at arbejde sammen, når vi er enige om et par standarder. Når vi lærer mere, så opdaterer vi standarden.

## Versioner 
- Python ≥ 3.5, < 3.6 [[Nyeste er 3.5.10]](https://docs.python.org/3.5/)
- C ≥ C99
- C++ ≥ C++11 

## Kodestandarder
Det giver mest mening at følge typiske standarder for de sprog, vi bruger [med hjælp fra vores IDE](https://github.com/AUTeam2/standards/blob/master/PyCharm.md#kodestandard).

### Python
- De fleste skriver Python efter [PEP8](https://www.python.org/dev/peps/pep-0008/). Så det prøver vi også.
- Det er en lang kodestandard, vi kan slå op i efter behov.
- Væsentligst til at komme i gang:
	* Benyt 4 mellemrum til hver indrykning.
		> Use 4 spaces per indentation level.
		> Spaces are the preferred indentation method.
		> Python 3 disallows mixing the use of tabs and spaces for indentation.
	* Linjelænger, prøv at holde dem under 80 tegn
		> Limit all lines to a maximum of 79 characters.
		> ...makes it possible to have several files open side-by-side, and works well when using code review tools that present the two versions in adjacent columns.
	* Filer gemmes i UTF-8, men lad være med at bruge ikke-ascii-tegn i koden
		> Code in the core Python distribution should always use UTF-8.
		> All identifiers in the Python standard library MUST use ASCII-only identifiers, and SHOULD use English words wherever feasible.
	* Slå op i standarden for at se, hvordan man navngiver en funktion, en klasse, en variabel, osv...
		> Class names should normally use the CapWords convention.
		> Always use self for the first argument to instance methods.
		> Always use cls for the first argument to class methods.
		> Function names should be lowercase, with words separated by underscores as necessary to improve readability.
		> Variable names follow the same convention as function names.

- Benyt Exception handling, hvor fejl ellers kan få programmet til at stoppe, eller resultere i krævet genstart af Gateway. Se bl.a. [Py 3.5 Tutorial on Errors](https://docs.python.org/3.5/tutorial/errors.html).
	* Specificér den/de exception(s), som du vil fange, fx `except ValueError`. Skriv ikke bare en "blankocheck".
	* Dokumentér tydeligt rationalet i koden; Fx hvad du forventer skal ske, og hvilke fejl der kan opstå.

### C/C++
- Vi benytter [AU's kodestandard](https://blackboard.au.dk/bbcswebdav/pid-1817350-dt-content-rid-5205395_1/courses/BB-Cou-UUVA-78333/BB-Cou-UUVA-54474_ImportedContent_20170612103145/BB-Cou-UUVA-62537_ImportedContent_20160606015213/Programmeringsstandard_UK.pdf).

## Dokumentation

- Vi dokumenterer vores kode, mens vi skriver koden.
- Der er forskel på at kommentere og dokumentere. Det er godt at kommentere, og det er _krævet_ at dokumentere.
- Vi brug de værktøjer, der er naturlige til det sprog, vi skriver i.
	* **Python**:
		- Vi bruger docstrings til at dokumentere alle moduler, klasser og funktioner. Se fx [Documenting Python code](https://realpython.com/documenting-python-code/). 
		- Vi bruger Sphinx til at samle dokumentation senere (__to be decided__).
		- Hvis vi har lyst, kan vi derfor skrive formattere dokumentationen med [ReStructuredText](https://en.wikipedia.org/wiki/ReStructuredText).
	* **C/C++**:
		- Vi benytter Doxygen til at dokumentere C/C++-kode. 

## Testing
- Vi tester så meget, vi kan.
- Vi benytter de testværktøjer, der er naturlige for de sprog, vi skriver i.
	* **Python**:
		- Vi skriver unit tests med `unittest` (__to be decided__)[som er den foretrukne måde](https://docs.djangoproject.com/en/2.2/topics/testing/).
	* **C/C++**: 
		- Vi må evaluere behovet... `Catch2`, `GoogleTest`?

## Versionsstyring
- Vi benytter **Git** og **Github** til versionsstyring og kodedeling (på nær fortroligt materiale og kode fra ReMoni, medmindre dette kan lægges i et Private repo).
- Vi lægger vores fælles kode på [https://github.com/E5PRO5-2020](https://github.com/E5PRO5-2020).
- Vi benytter Github til bug-tracking (issues).
- Vi linker med Jira, så vidt muligt.

### Master branch
- Master branch (mainline) skal altid kunne deployes til Gateway.
- Kode skal være testet og peer-reviewed inden vi merger til master.
- Vi merger kun til master på baggrund af pull requests. Se en god video om det [her](https://www.youtube.com/watch?v=oFYyTZwMyAg).

### Branches
- Vi benytter branches til fastfrysning af releases, featureudvikling og fix af issues. Vi har beskrevet workflowet [her](https://github.com/AUTeam2/standards/blob/master/branch-workflow.md).
- Vi navngiver branches som fx ”release/2.0”, ”feature/opgaveId” og ”issue/bugId”.
- Release-nummerering følger timebox-nummerering. Kode released i timebox 2 fastfryses i en branch med navn ”release/2.0”.
- Det er scrum-masters ansvar, at en releaseversion fastfryses.

### Commit-beskeder
- Vi skriver gode og commit-beskeder, der hjælper hinanden med at forstå ændringer.
- Vi overholder følgende punkter for gode beskeder [[hvorfor?]](https://chris.beams.io/posts/git-commit/):
	> - Skriv commit-beskeder på engelsk.
	> - Separér emnelinje og indholdsfelt med tom linje.
	> - Skriv emnelinje på maks. 50 tegn.
	> - Skriv med stort begyndelsesbogstav i emnelinje.
	> - Benyt ikke punktum i emnelinje.
	> - Skriv i bydeform i emnelinjen.
	> - Hold indholdsfeltet inden for en kolonnebredde på 72 tegn.
	> - Brug indholdsfeltet til at forklare hvad og hvorfor (ikke hvordan).

## Navne på filer, mapper
- Vi laver versionsstyring af kodefiler med **Github**... _Ikke_ med mange kopier af filer eller versionsnummerering i filnavne :smile:
- Læsbare mellemrum laves med bindestreg (-) eller underscore (_). Undlad at bruge mellemrum i fil- og mappenavne, det er bare for svært at håndtere i terminalen og i kode. 
- Brug kun tegnene a-z, A-Z, 0-9, -, _. Undlad at bruge ikke-ascii-tegn og specialtegn.
- Vi fortrækker at bruge små bogstaver, medmindre et stort tegn signalerer noget _helt_ specifikt.
- Vi bruger kun ét punktum i et filnavn. Dette punktum markerer filtypen (medmindre der er en standard, vi skal overholde, fx til `yaml`).


That's all folks! :rabbit:
