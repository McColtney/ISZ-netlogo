# Tutorial NetLogo

## Spis treści
- [Instalacja programu](#)
- [Czym jest NetLogo?](#)
- [Modele](#)
- [Programowanie modułów](#)

## Instalacja programu

- [download NetLogo 5.3.1 (Mac/Win/Linux)](https://ccl.northwestern.edu/netlogo/5.3.1/)

## Czym jest NetLogo?

![Przykładowa symulacja w NetLogo](/images/screen01.png)

**NetLogo** to programowalne wieloagentowe środowisko do modelowania i symulacji naturalnych i społecznych zjawisk.

**NetLogo** jest szczególnie dobrze przystosowane do modelowania złożonych systemów rozwijających się z czasem. Daje możliwość wydania instrukcji dużej ilości niezależnych agentów osadzonych w środowisku, dzięki czemu możliwe jest odkrywanie związków pomiędzy mikroskopowym zachowaniem indywiduów a makroskopowym wzorcem, który wyłania się z ich interakcji.

**NetLogo** pozwala otwierać symulacje i eksperymentować z ich parametrami, jak i tworzyć własne modele. Jest wystarczająco proste dla uczniów szkół, a zaawansowane na tyle, by służyć jako potężne narzędzie dla badaczy w wielu dziedzinach.

**NetLogo** ma rozległą dokumentację oraz bibliotekę modeli — ogromną kolekcję gotowych symulacji adresujących zjawiska z dziedzin takich jak biologia i medycyna, fizyka i chemia, matematyka i informatyka, ekonomia czy socjologia.

**NetLogo** jest kolejną generacją w serii wieloagentowych języków modelowania, takich jak [StarLogo](http://education.mit.edu/portfolio_page/starlogo-tng/) i StarLogoT. NetLogo działa na maszynie wirtualnej Javy, dlatego obsługuje wszystkie ważne systemy operacyjne. Jest uruchamiane jako aplikacja desktopowa; wspierane jest również używanie go z linii komend.

## Modele

### Otwieranie i korzystanie z modeli

Gotowe modele dostarczone z programem można otworzyć przez `File > Models Library`.

W oknie NetLogo można wymienić następujące istotne obszary, podzielone na 3 zakładki, `Inteface | Info | Code`:
- `Interface` pokazuje kontrolki służące do manipulacji i wyświetlania wyników symulacji.
- `Info` zawiera istotne informacje dostarczone przez autora modułu, m.in. propozycje manipulowania modelem, jego tło naukowe albo sugestie rozbudowy czy zmian.
- `Code` zawiera definicje zmiennych (część zmiennych zdefiniowana jest przez samo umieszczenie i nazwanie kontrolki w karcie `Interface`) oraz procedur, napisane w języku NetLogo.

Gdy zostanie wczytany jakiś moduł, w karcie `Interface` mogą ukazać się różne kontrolki:
- **Przyciski** służące do uruchomiania procedur, w szczególności `setup` i `go`
- **Suwaki** pozwalające manipulować parametrami modelu
- **Wykresy** oraz **monitory** wyświetlające aktualne i historyczne dane

Zazwyczaj sposobem na rozpoczęcie symulacji jest zainicjowanie lub zresetowanie stanu środowiska przyciskiem `setup`, a następnie uruchomienie go przyciskiem `go`. Proszę zwrócić uwagę na symbol cyklicznych strzałek, który może pojawić się na przycisku `go`, sugerujący że symulacja będzie trwała dopóki nie osiągnie warunków końcowych, bądź zostanie przerwana ponownym wciśnięciem `go`. Przyciski `go` lub `go once` bez symbolu cyklu uruchomią tylko jedno przejście, _tick_ symulacji.

Zmiana parametrów układu przy pomocy suwaków może wymagać ponownego wykonania `setup`, aby symulacja przebiegła poprawnie.

Prędkością wykonywania symulacji można manipulować suwakiem znajdującym się w górnej części karty `Interface`. Zmieniając karty warto pamiętać, że symulacja nie jest zawieszana podczas pobytu na karcie innej niż `Interface`.
  
### Przykładowe modele

#### Tumor

Model znajduje się bibliotece pod `Sample Models/Biology/Tumor`.

- `SETUP`: Czyści obraz. Tworzy dwie niebieskie rakowe komórki macierzyste. Jedna pozostaje statyczna. Druga będzie poruszać się w prawo.
- `GO`: Uruchamia symulację.
- `KILL TRANSITORY CELLS`: Zabija komórki przejściowe, które są młodsze niż 10 kroków czasowych.
- `KILL STEM CELL`: Zabija komórkę macierzystą statyczną. 
- `KILL MOVING CELL`: Zabija komórkę macierzystą przesuniętą w prawo.
- `LEAVE-TRAIL`: Śledzenie drogi komórki.
- `CELL-COUNT`: Wyświetla całkowitą liczbę żywych komórek.
- `LIVING CELLS PLOT`: wykres wszystkich żywych komórek

1. Kliknij na `KILL TRANSISTORY CELLS` kiedy model jest uruchomiony. Jest to symulacja chemicznego leczenia. Środek eliminuje młode (czerwone) komórki które się dzielą, ale za to pozostawia stare komórki. Zauważ, że guz kurczy się i wzrasta ponownie. Kliknij kilka razy ponownie. Większość znanych leków stosowanych w chemioterapii hamuje podział nowych komórek lecz nie powoduje śmierci tych starszych. Tak więc pozostają one nienaruszone. Problem polega na tym, że komórki macierzyste utrzymują guza, a to powoduje przerzuty. Komórki macierzyste są na ogół odporne na chemioterapię. Można je usunąć jedynie dużymi dawkami substancji chemicznych, które zagrażają zdrowym komórkom macierzystym. 

1. Kiedy nowotwór znów urośnie, kliknij na `KILL MOVING STEM CELL`. Prawa komórka macierzysta zniknęła. Jej potomkowie żyją nieco dłużej, a potem umierają.

1. Kliknij na `KILL ORIGINAL STEM CELL` i obserwuj stopniowy zanik guza. Żadne nowe komórki nie są tworzone. Starsze starzeją się aż do śmierci i zanikają. 

#### Muscle Development

Model znajduje się w bibliotece pod `Sample Models/Biology/Muscle Development`.

- `SETUP`: Ustawia model.
- `GO`: Uruchamia model.
- `INTENSITY`: Im większa siła, tym większa ilość włókien mięśniowych, które będą zmęczone po sesji treningowej.
- `HOURS-OF-SLEEP`: Ilość snu wpływa na to jak szybko organizm rozbija hormony.
- `DAYS-BETWEEN-WORKOUTS`: Ilość dni pomiędzy treningami.
- `%-SLOW-TWITCH-FIBERS`: Prawdopodobieństwo posiadania cech wolnych skurczy.
- `MUSCLE DEVELOPMENT VS. TIME`: Rozmiar masy mięśniowej wraz z upływem czasu.
- `HORMONES VS. TIME`: Średnia zawartość hormonów w każdym z włókien.

1. Uruchom model z ustawieniami domyślnymi. Co się dzieje z ilością masy mięśniowej?
2. Przetrenowanie występuje wtedy gdy organizm nie jest w stanie całkowicie się odbudować po ostatnim treningu. To powoduje stagnację rozwoju mięśni, a w skrajnych wypadkach ich utratę. Jaki jest najlepszy sposób aby uniknąć przetrenowania organizmu?

### Wybrane interesujące modele
- Sample Models
  - Art
    - Diffusion Graphics
	- Sound Machines
  - Biology
    - Ants
	- Autumn
	- Evolution
	  - Cooperation
	  - Sunflower Biomorphs
	- Flocking
	- Fur
	- Honeycomb
	- Wolf Sheep Predation
  - Chemistry & Physics
    - Crystallization
	  - Crystallization Moving
	- Waves
	  - Wave Machine
  - Computer Science
    - Cellular Automata
	  - Life
	- Dining Philosophers
	- Particle Systems
	  - Particle System Flame
	- Vants
	- Wandering Letters
  - Earth Science
    - Grand Canyon
  - Mathematics
    - Fractals
	  - Mandelbrot
	  - Sierpinski Simple
	- Probability
	  - Galton Box
	- Vector Fields
  - Social Science
    - Segregation
	- Traffic Bacis
	- Traffic Grid
	- Wealth Distribution
- Curricular Models
  - BEAGLE Evolution
    - DNA Replication Fork
  - NIELS
    - Current in a Wire
	
## Programowanie modułów

### Materiały

- [Dokumentacja NetLogo](https://ccl.northwestern.edu/netlogo/docs/)

### Podstawy składni NetLogo

Przepływ sterowania w NetLogo dokonuje się poprzez wywoływanie procedur. Pierwsze poruszenie dokonuje się poprzez kontrolkę interfejsu `setup`. Wywołuje ona procedurę o zazwyczaj tej samej nazwie, której zadaniem jest wprowadzenie układu w stan początkowy.

Warto zauważyć, że część zmiennych tworzona jest nie w sekcji `Code`, ale `Interface`, gdyż samo utworzenie kontrolki suwaka równoważne jest z deklaracją zmiennej globalnej.

Ponadto zmienne mogą żyć tylko w określonych przestrzeniach, m.in.: globalnej, jako cechy żółwi lub jako cechy pól siatki. Procedury nie posiadają zmiennych lokalnych ani nie mogą zwracać, czy przyjmować wartości.

Definicja procedury:

```
to do-something
  ;;; comment
end
```

Definicja dodatkowych zmiennych globalnych, cech żółwi oraz cech pól siatki:

```
globals ;;; słowo kluczowe
  [ lifespan             ;;; deklaracje zmiennych
    chance-reproduce ]   ;;; deklaracje zmiennych
	
turtles-own
  [ something ]
  
patches-own
  [ something ]
```
