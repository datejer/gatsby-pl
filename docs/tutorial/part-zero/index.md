---
title: Skonfiguruj środowisko programistyczne
typora-copy-images-to: ./
disableTableOfContents: true
---

Zanim zaczniesz budować swoją pierwszą strone Gatsby, musisz zapoznać się z niektórymi podstawowymi technologiami internetowymi i upewnić się, że zainstalowałeś wszystkie wymagane narzędzia oraz programy.

## Zapoznaj się z wierszem poleceń

Wiersz poleceń to interfejs tekstowy służący do uruchamiania poleceń na komputerze. Często występuje pod nazwą terminal. W tym samouczku będziemy używać obu określeń zamiennie. Uźywanie terminala przypomina używanie Findera na komputerach Mac lub Eksploratora w systemie Windows. Finder i Explorer to przykłady graficznych interfejsów użytkownika (GUI). Wiersz poleceń to potężne, tekstowe narzędzie do interakcji z komputerem.

Poświęć chwilę, aby zlokalizować i otworzyć interfejs wiersza poleceń (CLI) dla swojego komputera. W zależności od używanego systemu operacyjnego sprawdź [**instrukcje dla komputerów Mac**](https://www.imymac.com/pl/mac-cleaner/how-to-open-terminal-on-mac.html), [**instrukcje dla systemu Windows**](https://www.download.net.pl/10-sposobow-na-uruchomienie-wiersza-polecenia-w-windows-10/n/7949/) lub [**instrukcje dla systemu Linux**](https://pl.wikibooks.org/wiki/Ubuntu/Podstawowe_polecenia).

_Uwaga: Jeśli dopiero zaczynasz korzystać z wiersza poleceń, „uruchomienie” polecenia oznacza wprowadzenie określonego zestawu instrukcji w wierszu polecenia i naciśnięcie klawisza Enter. Polecenia będą wyświetlane w podświetlonym polu, coś w rodzaju `node --version`, ale nie każde podświetlone pole jest poleceniem! Jeśli coś jest poleceniem, zostanie wspomniane jako coś, co musisz uruchomić/wykonać._

## Zainstaluj Node.js dla Twojego systemu operacyjnego

Node.js to środowisko, które może uruchamiać kod JavaScript poza przeglądarką internetową. Gatsby jest zbudowany w Node.js. Aby rozpocząć pracę z Gatsby, musisz posiadać aktualną wersję zainstalowaną na komputerze. npm jest dostarczany w pakiecie z Node.js, więc jeśli nie masz npm, istnieje prawdopodobieństwo, że nie masz także Node.js.

### Instrukcja dla Mac

Aby zainstalować Gatsby i Node.js na komputerze Mac, zaleca się użycie [Homebrew](https://brew.sh/). Trochę konfiguracji na początku może uchronić Cię przed wieloma problamami w przyszłości!

#### Jak zainstalować lub zweryfikować Homebrew na swoim komputerze:

1. Otwórz Terminal.
2. Sprawdź czy Homebrew jest zainstalowane. Powinieneś zobaczyć "Homebrew" oraz numer wersji.

```shell
brew -v
```

3. Jeśli nie, pobierz i zainstaluj [Homebrew wraz z instrukcją](https://docs.brew.sh/Installation).
4. Po zainstalowaniu Homebrew powtórz krok 2, aby zweryfikować.

#### Zainstaluj Xcode Command Line Tools:

1. Otwórz Terminal.
2. Zainstaluj Xcode Command Line Tools uruchamiając komendę:

```shell
xcode-select --install
```

> 💡 Jeśli to zawiedzie, pobierz narzędzie [bezpośrednio ze strony Apple](https://developer.apple.com/download/more/), po zalogowaniu się za pomocą konta programisty Apple.

3. Po wyświetleniu okna zezwolenia na rozpoczęcie instalacji, pojawi się ponownie okno z prośbą o zaakceptowanie licencji pobieranych narzędzi.

#### Zainstaluj Node

1. Otwórz Terminal.
2. Zainstaluj Node przy pomocy Homebrew:

```shell
brew install node
```

> 💡 Jeśli nie chcesz instalować go przez Homebrew, pobierz najnowszą wersję Node.js z [oficjalnej strony Node.js](https://nodejs.org/en/), kliknij dwukrotnie pobrany plik i przejdź przez proces instalacji

### Instrukcja dla Windows

- Pobierz i zainstaluj najnowszą wersję Node.js z [oficjalnej strony Node.js](https://nodejs.org/en/)

### Instrukcja dla Linuks

Zainstaluj nvm (Node Version Manager) i potrzebne zależności. nvm służy do zarządzania Node.js i wszystkimi powiązanymi wersjami.

> 💡 Jeśli podczas instalacji pakietu system poprosi o potwierdzenie, wpisz `y` i naciśnij enter.

Wybierz swoje distro:

- [Ubuntu, Debian, i inne distro oparte na apt](#ubuntu-debian-and-other-apt-based-distros)
- [Arch, Manjaro i inne distro oparte na pacman](#arch-manjaro-and-other-pacman-based-distros)
- [Fedora, RedHat, i inne distro oparte na dnf](#fedora-redhat-and-other-dnf-based-distros)

> 💡 Jeśli dystrybucji Linuxa z której korzystasz nie ma na liście, poszukaj instrukcji w internecie.

#### Ubuntu, Debian i inne dystrybucje oparte na `apt`:

1. Upewnij się, że dystrybucja Linuksa jest gotowa do działania uruchamiając aktualizacje:

```shell
sudo apt update
sudo apt -y upgrade
```

2. Zainstaluj curl, który pozwoli Ci przesyłać dane i pobierać dodatkowe zależności:

```shell
sudo apt-get install curl
```

3. Po zakończeniu instalacji pobierz najnowszą wersję NVM:

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.1/install.sh | bash
```

4. Potwierdź, że zadziałało. Dane wyjściowe powinny zawierać numer wersji.

```shell
nvm --version
```

5. Przejdź do sekcji: [Ustaw domyślną wersję Node.js](#set-default-nodejs-version)

#### Arch, Manjaro i inne dystrybucje oparte na `pacman`:

1. Upewnij się, że dystrybucja jest gotowa do działania:

```shell
sudo pacman -Sy
```

2. Te dystrybucje już posiadają zaisntalowany curl, więc możesz użyć tego polecenia do pobrania NVM:

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.1/install.sh | bash
```

3. Przed użyciem NVM musisz zainstalować dodatkowe zależności, uruchamiając:

```shell
sudo pacman -S grep awk tar
```

4. Potwierdź, że zadziałało. Powinieneś zobaczyć numer wersji.

```shell
nvm --version
```

5. Przejdź do sekcji: [Ustaw domyślną wersję Node.js](#set-default-nodejs-version)

#### Fedora, RedHat i inne dystrybucje oparte na `dnf`:

1. Te dystrybucje już posiadają zaisntalowany curl, więc możesz użyć tego polecenia do pobrania NVM:

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.1/install.sh | bash
```

2. Potwierdź, że zadziałało. Powinieneś zobaczyć numer wersji.

```shell
nvm --version
```

3. Przejdź do sekcji: [Ustaw domyślną wersję Node.js](#set-default-nodejs-version)

Jeśli dystrybucji Linuksa, której używasz, nie ma na liście, znajdź instrukcje w Internecie.

#### Ustaw domyślną wersję Node.js

Gdy nvm jest zainstalowany, domyślnie nie ma określonej wersji Node. Musisz zainstalować żądaną wersję i poinstruować NVM aby z niej korzystał. W tym przykładzie użyto najnowszego wydania wersji 10, ale zamiast niej można użyć nowszej wersji.

```shell
nvm install 10
nvm use 10
```

Aby potwierdzić, że zadziałało:

```shell
npm --version
node --version
```

Wynik powinien wyglądać podobnie do poniższego zrzutu ekranu, pokazując numery wersji w odpowiedzi na polecenia.

![Sprawdź wersje node i npm w terminalu](01-node-npm-versions.png)

Po wykonaniu instalacji i sprawdzeniu, czy wszystko jest poprawnie zainstalowane, możesz przejść do następnego kroku.

## Zainstaluj Git

Git to darmowy i open-source'owy system kontroli wersji. Przeznaczony jest on do szybkiej i wydajnej obsługi wszelkiego rodzaju projektów - od małych po bardzo duże. Podczas instalowania startera Gatsby, wykorzystuje on Git, aby pobrać i zainstalować wymagane pliki projektu startowego. Aby skonfigurować pierwszą stronę Gatsby, musisz zainstalować Git.

Procesy pobierania i instalacji Git zależą od Twojego systemu operacyjnego. Postępuj zgodnie z instrukcjami dla swojego systemu:

- [Zainstaluj Git na macOS](https://www.atlassian.com/git/tutorials/install-git#mac-os-x)
- [Zainstaluj Git na Windows](https://www.atlassian.com/git/tutorials/install-git#windows)
- [Zainstaluj Git na Linux](https://www.atlassian.com/git/tutorials/install-git#linux)

## Interfejs Gatsby CLI

Interfejs Gatsby CLI pozwala szybko tworzyć nowe strony oparte na Gatsby i uruchamiać komendy potrzebne do tworzenia stron w Gatsby. Gatsby CLI jest paczką npm.

Gatsby CLI jest dostępny za pośrednictwem npm i powinien zostać zainstalowany globalnie, uruchamiając komendę:

```shell
npm install -g gatsby-cli
```

_**Uwaga**: po zainstalowaniu Gatsby i uruchomieniu go po raz pierwszy zobaczysz krótki komunikat informujący o gromadzeniu anonimowych danych dotyczących użytkowania komend Gatsby CLI, możesz przeczytać więcej o tym, jak te dane są pobierane i wykorzystywane w [dokumencie o telemetrii](/docs/telemetry)._

Zobacz dostępne komendy:

```shell
gatsby --help
```

![Sprawdź dostępne komendy w terminalu](05-gatsby-help.png)

> 💡 Jeśli nie możesz pomyślnie uruchomić interfejsu Gatsby CLI przez problemy z uprawnieniami, możesz sprawdzić [dokoumentację npm na temat rozwiązywania problemów z uprawnieniami](https://docs.npmjs.com/getting-started/fixing-npm-permissions), lub [ten poradnik](https://github.com/sindresorhus/guides/blob/master/npm-global-without-sudo.md).

## Utwórz witrynę Gatsby

Teraz możesz zacząć korzystać z Gatsby CLI i utworzyć swoją pierwszą stronę Gatsby. Przy pomocy interfejsu możesz pobrać „startery” (częściowo zbudowane strony z domyślną konfiguracją), aby szybciej zacząć tworzyć określony typ strony. Starter „Hello World”, którego będziesz tutaj używać, to starter z elementami niezbędnymi do stworzenia witryny Gatsby.

1.  Otwórz terminal.
2.  Utwórz nową stronę korzystając ze startera:

```shell
gatsby new hello-world https://github.com/gatsbyjs/gatsby-starter-hello-world
```

> 💡 Co tu się właściwie wydarzyło?
>
> - `new` to komenda, która tworzy nowy projekt Gatsby.
> - W tym wypadku, `hello-world` to tytuł projektu - możesz wybrać dowolną nazwę. Narzędzie CLI umieści kod strony w nowym folderze o nazwie „hello-world”.
> - Ostatnia część komendy, czyli adres URL, wskazuje repozytorium kodu na GitHubie, w którym znajduje się kod startowy, którego chcesz użyć.

> 💡 W zależności od Twojej prędkości pobierania ilość czasu będzie się różnić. Dla zwięzłości poniższy gif został wstrzymany podczas części instalacji

3.  Przejdź do katalogu roboczego:

```shell
cd hello-world
```

> 💡 Oznacza to _'Chcę zmienić folder (`cd`) na subfolder “hello-world”'_. Kiedy chcesz uruchomić jakąś komendę dla swojej witryny, musisz znajdować się w jej kontekście (innymi słowy, terminal musi być skierowany na folder, w którym znajduje się kod strony).

4.  Uruchom tryb deweloperski:

```shell
gatsby develop
```

> 💡 To polecenie uruchamia serwer developerski. Dzięki temu będziesz mógł zobaczyć i przetestować nową witryną w lokalnym środowisku programistycznym - (na twoim komputerze, niepublikowaną w Internecie).

<video controls="controls" autoplay="true" loop="true">
  <source type="video/mp4" src="./03-create-site.mp4"></source>
  <p>Twoja przeglądarka nie obsługuje tego elementu wideo.</p>
</video>

### Wyświetl swoją witrynę lokalnie

Otwórz nową kartę w przeglądarce i przejdź do `http://localhost:8000/`

![Sprawdź stronę główną](04-home-page.png)

Gratulacje! Właśnie zacząłęś budować swoją pierwszą stronę z Gatsby! 🎉

Możesz zobaczyć stronę lokalnie, pod adresem `http://localhost:8000/` tak długo jak długo będzie uruchomiony serwer deweloperski. Ten proces rozpoczął się gdy uruchomiłeś komendę `gatsby develop`. Aby go zatrzymać (lub “zatrzymać serwer deweloperski"), wróć do terminala i przyciskając klaiwsz "control" wciśnij klawisz "c" (ctrl+c). By uruchomić serwer ponownie, uruchom ponownie komendę `gatsby develop`!

_**Uwaga:** Jeśli używasz wirtualnej maszyny takiej jak `vagrant` i/lub chcesz nasłuchiwać na lokalny adres IP, uruchom komendę `gatsby develop -- --host=0.0.0.0`. Serwer programistyczny będzie teraz nasłuchiwał zarówno na `http://localhost` jak i na Twoim lokalnym adresie IP._

## Skonfiguruj edytor kodu

Edytor kodu to program zaprojektowany specjalnie do edycji kodu. Wybór jest ogromny, istnieje wiele świetnych edytorów.

### Pobierz VS Code

Dokumentacja Gatsby czasami zawiera zrzuty ekranu wykonane w VS Code, więc jeśli nie masz jeszcze preferowanego edytora, możesz wybrać właśnie ten. Dzięki temu Twój ekran będzie wyglądał jak zdjęcia z samouczka i dokumentacji. Jeli zdecydujesz się na VS Code, odwiedź [stronę VS Code](https://code.visualstudio.com/#alt-downloads) i pobierz wersję odpowiednią dla Twojego systemu.

### Zainstaluj wtyczkę Prettier

Polecamy również wtyczkę [Prettier](https://github.com/prettier/prettier). Jest to narzędzie, które pomaga sformatować kod, tak aby uniknąć błędów.

Możesz użyć Prettier bezpośrednio w edytorze, używając [wtyczki Prettier VS Code](https://github.com/prettier/prettier-vscode):

1.  Otwórz zakładkę rozszerzeń w VS Code (View => Extensions).
2.  Wyszukaj "Prettier - Code formatter".
3.  Kliknij "Install". (Po instalacji pojawi się komunikat z prośbą o ponowne uruchomienie VS Code, aby włączyć rozszerzenie. Nowsze wersje VS Code automatycznie włączą rozszerzenie po pobraniu.)

> 💡 Jeśli nie używasz VS Code, sprawdź dokumentacje Prettier opisującą [proces instalacji](https://prettier.io/docs/en/install.html) lub [integrację z innymi edytorami](https://prettier.io/docs/en/editors.html).

## ➡️ Co dalej?

Podsumowując, w tej sekcji:

- Nauczyłeś/aś się o wierszu polecenia i o tym jak go używać
- Zainstalowałeś/aś i poznałeś/aś Node.js, npm CLI, system kontroli wersji Git oraz interfejs Gatsby CLI
- Stowrzyłeś/aś nową stronę w Gatsby przy użyciu interfejsu Gatsby CLI
- Uruchomiłeś/aś serwer deweloperski Gatsby oraz odwiedziłeś/aś swoją stronę lokalnie
- Pobrałeś/aś edytor kodu
- Zainstalowałeś/aś narzędzie do formatowania kodu Prettier

Teraz możesz przejść do [**zapoznaj się z blokami konstrukcyjnymi Gatsby**](/tutorial/part-one/).

## Adnotacja

### Przegląd podstawowych technologii

Nie trzeba być ekspertem w tych dziedzinach - jeśli nie jesteś, nie martw się! Podczas tej serii samouczków, wiele się nauczysz. Oto niektóre z głównych technologii internetowych, których będziesz używać podczas tworzenia stron w Gatsby:

- **HTML**: Język znaczników, który jest w stanie zrozumieć każda przeglądarka internetowa. HTML nadaje treści internetowej uniwersalną strukturę, definiując elementy takie jak nagłówki, akapity i inne. Skrót HTML oznacza HyperText Markup Language.
- **CSS**: Język służący do opisu formy prezentacji treści internetowych (czcionek, kolorów, układu itp.). Skrót CSS oznacza Cascading Style Sheets (kaskadowe arkusze stylów).
- **JavaScript**: Język programowania, który pomaga budować dynamiczne i interaktywne strony internetowe.
- **React**: Biblioteka (napisana w JavaScript) używana do budowania interfejsów użytkownika. Jest to framework używany przez Gatsby do tworzenia stron i struktury treści.
- **GraphQL**: Język zapytań, który pozwala pobierać dane do witryny. Jest to interfejs używany przez Gatsby do zarządzania danymi witryny.

### Co to jest strona internetowa?

Jeśli potrzebujesz pełnego wprowadzenia do tego, czym jest strona internetowa - w tym wprowadzenie do HTML i CSS - sprawdź “[**Tworzenie swojej pierwszej strony internetowej**](https://learn.shayhowe.com/html-css/building-your-first-web-page/)”. Jest to świetne miejsce do rozpoczęcią nauki o sieci. Aby uzyskać bardziej praktyczne wprowadzenie do [**HTML**](https://www.codecademy.com/learn/learn-html), [**CSS**](https://www.codecademy.com/learn/learn-css), oraz [**JavaScript**](https://www.codecademy.com/learn/introduction-to-javascript), sprawdź samouczki na Codecademy. [**React**](https://reactjs.org/tutorial/tutorial.html) i [**GraphQL**](http://graphql.org/graphql-js/) również mają własne poradniki wprowadzające.

### Naucz się więcej o wierszu poleceń

Dla świetnego wprowadzenia do korzystania z terminala, sprawdź [**samouczek Codecademy o wierszu poleceń**](https://www.codecademy.com/courses/learn-the-command-line/lessons/navigation/exercises/your-first-command) jeśli używasz Maca lub Linuxa, lub [**ten samouczek**](https://www.computerhope.com/issues/chusedos.htm) jeśli jesteś użytkownikiem Windowsa. Nawet jeśli posiadasz Windowsa, warto zobaczyć pierwszą stronę samouczka od Codecademy--znajdziesz tam wiele interesujących informacji. Dowiesz się m.in. czym jest wiersz poleceń, a nie tylko jak z niego korzystać.

### Naucz się więcej na temat npm

npm to manager paczek dla Javascript. Paczka to kod w formie modułu, którego możesz użyć w swoim projekcie. Jeśli pobrałeś i zainstalowałeś Node.js, npm również został zainstalowany na Twoim komputerze!

npm składa się z trzech odrębnych części: strona npm, rejestr npm, oraz interfejs wiersza polceń npm.

- Na stronie możesz przejrzeć jakie paczki Javascript są dostępne w rejestrze npm.
- Rejestr npm to ogromna baza danych, która zawiera informacje na temat dostępnych paczek.
- Kiedy znajdziesz paczkę, która Cię interesuje, możesz użyć interfejsu npm aby zainstalować ją w swoim projekcie lub globalnie (tak jak inne interfejsy wiersza poleceń). Interfejs npm odpowiada za komunikację z rejestrem - zazwyczaj interakcja odbywa się tylko ze stroną internetową npm lub interfejsem npm.

> 💡 Sprawdź wprowadzenie do npm, “[**Czym jest npm?**](https://docs.npmjs.com/getting-started/what-is-npm)”.

### Naucz się więcej na temat Git

Nie musisz wiedzieć jak działa Git, aby ukończyć ten samouczek, jednakże jest to bardzo użyteczne narzędzie. Jeśli chcesz dowiedzieć się więcej na temat systemów kontroli wersji, Git oraz Githuba, sprawdź ten [Podręcznik Git](https://guides.github.com/introduction/git-handbook/) stworzony przez Githuba.
