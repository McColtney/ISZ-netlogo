# Tutorial NetLogo

## Instalacja programu

- [download NetLogo 5.3.1 (Mac/Win/Linux)](https://ccl.northwestern.edu/netlogo/5.3.1/)

## Czym jest NetLogo?

![Przykładowa symulacja w NetLogo](/images/screen01.png)

**NetLogo** to programowalne wieloagentowe środowisko do modelowania i symulacji naturalnych i społecznych zjawisk.

**NetLogo** jest szczególnie dobrze przystosowane do modelowania złożonych systemów rozwijających się z czasem. Daje możliwość wydania instrukcji dużej ilości niezależnych agentów osadzonych w środowisku, dzięki czemu możliwe jest odkrywanie związków pomiędzy mikroskopowym zachowaniem indywiduów a makroskopowym wzorcem, który wyłania się z ich interakcji.

**NetLogo** pozwala otwierać symulacje i eksperymentować z ich parametrami, jak i tworzyć własne modele. Jest wystarczająco proste dla uczniów szkół, a zaawansowane na tyle, by służyć jako potężne narzędzie dla badaczy w wielu dziedzinach.

**NetLogo** ma rozległą dokumentację oraz bibliotekę modeli — ogromną kolekcję gotowych symulacji adresujących zjawiska z dziedzin takich jak biologia i medycyna, fizyka i chemia, matematyka i informatyka, ekonomia czy socjologia.

**NetLogo** jest kolejną generacją w serii wieloagentowych języków modelowania, takich jak [StarLogo](http://education.mit.edu/portfolio_page/starlogo-tng/) i StarLogoT. NetLogo działa na maszynie wirtualnej Javy, dlatego obsługuje wszystkie ważne systemy operacyjne. Jest uruchamiane jako aplikacja desktopowa; wspierane jest również używanie go z linii komend.

## Otwieranie i korzystanie z modułów

## Programowanie modułów

### Materiały

- [Dokumentacja NetLogo](https://ccl.northwestern.edu/netlogo/docs/)

### Tworzenie własnego modułu od zera

1. Po otwarciu nowego pustego modelu w NetLogo, utwórz w widoku interfejsu nowy przycisk.
1. Zmień jego właściwość _Commands_ na `setup`. Przycisk będzie wywoływał procedurę o takim identyfikatorze.
1. Otwórz zakładkę z kodem. Wprowadź szkielet funkcji `setup` wg wzoru:
```NetLogo
to setup
;;; komentarz
end
```
