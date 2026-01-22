# AutoAccept - Auto Accept CS2 Match Finder

Automatyczne akceptowanie zaproszeń do meczów w Counter-Strike 2. Program wykrywa przycisk "Akceptuj" i automatycznie go klika, oszczędzając Ci czasu.

## 🎯 Funkcjonalności

- ✅ **Automatyczne akceptowanie meczy** - Program sam klika "Akceptuj" gdy pojawi się dialog
- 📊 **Statystyki sesji** - Licznik zaakceptowanych meczy i czas pracy
- ⚙️ **Regulacja pewności** - Dostosuj procentowo pewność detekcji przycisku (50-95%)
- 🎮 **Interwał skanowania** - Ustaw częstość skanowania ekranu (0.3-2.0s)
- 💾 **Automatyczny zapis konfiguracji** - Program pamięta Twoje ustawienia
- 🔄 **Aktualizacje** - Wbudowana funkcja sprawdzania i pobierania nowych wersji
- 🔝 **Zawsze na wierzchu** - Opcja aby okno programu zawsze pozostawało widoczne
- 📝 **Logi zdarzeń** - Pełny dziennik działania programu

## 📋 Wymagania

- **System operacyjny:** Windows 10/11
- **Monitor:** 1920x1080 lub wyższe rozdzielczenie
- **Obrazy szablonów:**
  - `akceptuj.png` - zrzut ekranu przycisku "Akceptuj"
  - `csgame.png` - zrzut ekranu ekranu głównego CS2

## 🚀 Instalacja

### Opcja 1: Instalator (Zalecane)
1. Pobierz `AutoAccept-Setup.exe` z [Releases](https://github.com/DoginGG/autoaccept/releases)
2. Uruchom instalator
3. Program zainstaluje się do `C:\Users\[Twoja nazwa]\AppData\Local\AutoAccept\`

### Opcja 2: Portable (bez instalacji)
1. Pobierz `AutoAccept-Update.zip` z [Releases](https://github.com/DoginGG/autoaccept/releases)
2. Rozpakuj gdzie chcesz
3. Uruchom `AutoAccept.exe`

### Opcja 3: Z źródeł (Dla developerów)
```powershell
git clone https://github.com/DoginGG/autoaccept.git
cd autoaccept
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
python autoaccept.py
```

## 📖 Jak używać

1. **Przygotuj obrazy szablonów:**
   - Zrób zrzut ekranu przycisku "Akceptuj" i zapisz jako `akceptuj.png`
   - Zrób zrzut ekranu tła gry i zapisz jako `csgame.png`
   - Umieść oba pliki w folderze z programem

2. **Konfiguracja (opcjonalnie):**
   - **Pewność Akceptuj** (50-95%) - Jak pewny program ma być że znalazł przycisk
   - **Pewność Ekran Gry** (50-95%) - Jak pewny program ma być że znalazł tło gry
   - **Interwał skanowania** (0.3-2.0s) - Jak często skanować ekran
   - **Zawsze na wierzchu** - Checkbox aby okno było zawsze widoczne
   - **Wyłącz po znalezieniu** - Auto-stop gdy gra się uruchomi

3. **Uruchom:**
   - Kliknij przycisk **Start**
   - Program będzie monitorować ekran w poszukiwaniu przycisku
   - Statystyki będą aktualizowane w czasie rzeczywistym

4. **Zatrzymaj:**
   - Kliknij przycisk **Stop** aby wstrzymać skanowanie

## 🔧 Kalibracja

Jeśli program nie znajduje przycisku:

1. **Zmniejsz pewność** - Ustaw na 50-60% zamiast 70%
2. **Zmień rozmiar obrazu** - Upewnij się że zrzut ekranu ma odpowiedni rozmiar
3. **Dodaj więcej tła** - Na zrzęcie ekranu powinno być więcej otoczenia wokół przycisku
4. **Oświetlenie** - Zrób zrzut w warunkach zbliżonych do rzeczywistych

## 🔄 Aktualizacje

Program posiada wbudowany system aktualizacji:

1. Kliknij przycisk **Sprawdź Aktualizacje**
2. Program porówna wersję lokalną z GitHub
3. Jeśli dostępna jest nowa wersja, program zaproponuje pobranie
4. Po zatwierdzeniu automatycznie pobierze, zainstaluje i restartuje się

## ⚠️ Troubleshooting

**Program nie znajduje przycisku:**
- Upewnij się że obrazy są w folderze z programem
- Zmniejsz pewność do 50%
- Zrób nowe zrzuty ekranu

**Program się wysypuje:**
- Sprawdź logi w polu "Logi" w programie
- Upewnij się że monitor ma rozdzielczość 1920x1080+

**Aktualizacja nie działa:**
- Sprawdź połączenie internetowe
- Spróbuj ręcznie pobrać z GitHub Releases

## 📝 Changelog

### v1.0.0 (2026-01-22)
- Pierwsza publiczna wersja
- Automatyczne akceptowanie meczy
- Statystyki sesji
- System aktualizacji
- Zapis konfiguracji

## 📄 Licencja

MIT License - Możesz używać, modyfikować i rozpowszechniać ten program

## 🤝 Wsparcie

Jeśli napotkasz problem:
1. Sprawdź [Issues](https://github.com/DoginGG/autoaccept/issues) czy ktoś już o tym wspomniał
2. Otwórz nowe Issue z opisem problemu
3. Dołącz zrzuty ekranu lub logi z programu

## ⚖️ Disclaimer

Ten program jest narzędziem automatyzacji dla Twojej wygody. Używaj go odpowiedzialnie. Autor nie ponosi odpowiedzialności za ewentualne konsekwencje.

---

**Wersja:** 1.0.0  
**Autor:** DoginGG  
**GitHub:** https://github.com/DoginGG/autoaccept

## Wskazówki
- Jeśli wykrywanie jest zbyt czułe lub zbyt słabe, dostosuj suwakiem próg pewności (oddzielnie dla przycisku i ekranu gry).
- Zmniejszenie interwału skanowania przyspiesza reakcję kosztem obciążenia CPU.
- Upewnij się, że obrazy `akceptuj.png` i `csgame.png` pasują do Twojej rozdzielczości/DPI.
- `ESC` lub przesunięcie myszy w lewy górny róg ekranu zatrzymuje kliknięcia (PyAutoGUI FAILSAFE).

## Pakowanie do EXE (opcjonalnie)
```powershell
pip install pyinstaller
pyinstaller --onefile --add-data "akceptuj.png;." --add-data "csgame.png;." autoaccept.py
```

Po zbudowaniu exe umieść obrazy w pakiecie (dystrybucji) lub korzystaj z dołączonych zasobów PyInstaller.
