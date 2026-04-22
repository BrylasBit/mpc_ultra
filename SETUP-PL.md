# 🎙️ INSTALACJA I PRZEWODNIK - MPC ULTRA v8

> Kompletny przewodnik po instalacji i konfiguracji dla użytkowników polskich

---

## 📋 Wymagania Systemowe

✅ **System operacyjny**: Windows, macOS, Linux
✅ **Przeglądarka**: Chrome, Edge, Firefox, Safari (aktualnie wersje)
✅ **Audio**: Głośniki lub słuchawki
✅ **Internet**: Nie wymagane (działa lokalnie)

---

## 🚀 SZYBKA INSTALACJA

### Opcja 1: Najprostsza (Rekomendowana)
1. Pobierz plik `index.html`
2. Kliknij dwa razy na plik
3. Aplikacja otworzy się w przeglądarce
4. Gotowe! ✓

### Opcja 2: Z Gita
```bash
# Pobierz projekt
git clone https://github.com/BrylasBit/mpc_ultra.git
cd mpc_ultra

# Otwórz w przeglądarce (macOS)
open index.html

# Lub na Linuxie
xdg-open index.html

# Lub na Windowsie (PowerShell)
start index.html
```

### Opcja 3: Z Serwera HTTP
```bash
# Jeśli masz Python zainstalowany
python -m http.server 8000
# Potem otwórz: http://localhost:8000/index.html

# Lub z Node.js
npx http-server
```

---

## 🎵 KROK 1: WGRYWANIE SAMPLI

### Przygotuj pliki WAV

**Kategorie sampli:**
- 🥚 **KOPNIĘCIA (KICKSY)**: `WKK1.wav`, `WKK2.wav`, `WKK3.wav`, `WKK4.wav`
- 🔊 **BEBUNY (SNARES)**: `WSP1.wav`, `WSP2.wav`, `WSP3.wav`, `WSP5.wav`
- 🎩 **TALERZE (HI-HATS)**: `WHT1.wav`, `WHT2.wav`, `WHT3.wav`, `WHT4.wav`, `WHT5.wav`

### Technika wgrywania - Wybierz jedną:

#### ⚡ Metoda A - DRAG & DROP (NAJSZYBSZA)
```
1. Zaznacz wszystkie pliki .wav
2. Przeciągnij na pole "DRAG WAV FILES HERE"
3. Gotowe! ✓
```

#### 🎯 Metoda B - BEZPOŚREDNIO NA PADY
```
1. Weź plik WKK1.wav
2. Przeciągnij na PAD 01
3. Weź plik WKK2.wav
4. Przeciągnij na PAD 02
5. Powtórz dla wszystkich sampli...
```

#### 🎛️ Metoda C - SAMPLE MANAGER
```
1. Kliknij przycisk "Sample Manager"
2. Przeglądaj i wybierz sample
3. Kliknij na sample
4. Kliknij na pad, aby przypisać
5. Gotowe! ✓
```

---

## ⌨️ KROK 2: NAUKA STEROWANIA

### Klawiatura
| Klawisz | Funkcja |
|---------|---------|
| **1-8** | Trig pady (bęby) |
| **Q-W-E-R-T-Y-U-I** | Klawiatura górna (syntezator) |
| **Z-X-C-V-B-N-M-,** | Klawiatura dolna (syntezator) |
| **SPACJA** | Play/Pause |
| **M** | Metronom ON/OFF |
| **ESC** | PANIC (zabij wszystkie dźwięki) |

### Przyciski Panel Sterowania
- 🟠 **PLAY** - Uruchom sekwenser
- ⏸️ **PAUSE** - Wstrzymaj beat
- 🔴 **STOP** - Zatrzymaj (reset)
- 🎵 **BPM** - Zmień tempo (drag slider)
- 🎛️ **KIT** - Wybierz zestaw bębnów

---

## 🎮 KROK 3: TWORZENIE BEATU

### Podstawowa sesja
```
1. Kliknij na KIT aby wybrać zestaw bębnów (808, 909, TRAP, etc.)

2. Zobacz SEQUENCER - to siatka 16 kroków

3. Programuj beat:
   • Rząd 1 (KICK)    → kliknij kroki: 1, 5, 9, 13
   • Rząd 2 (SNARE)   → kliknij kroki: 5, 13
   • Rząd 3 (HI-HAT)  → kliknij co drugi krok (1,3,5,7...)

4. Ustaw BPM (tempo) - slider po lewej

5. Naciśnij SPACJA aby Play

6. Obserwuj! Metrykę pokazuje gdzie jesteś w beacie
```

### Przykład prostego beatu
```
KICK:    ■ . . . ■ . . . ■ . . . ■ . . .
SNARE:   . . . . ■ . . . . . . . ■ . . .
HI-HAT:  ■ . ■ . ■ . ■ . ■ . ■ . ■ . ■ .
```
= klasyczny 4/4 beat hip-hopowy 90s

---

## 🎹 KROK 4: SYNTEZATOR (DODATKOWE)

### Granie na Pianinu
```
Dolny rząd (Q-U):    Oktawa górna
Górny rząd (Z-M):    Oktawa dolna

Przykład:
Q = Do (C)
W = Re (D)
E = Mi (E)
R = Fa (F)
T = Sol (G)
Y = La (A)
U = Si (B)
```

### Syntezator Moog
- Zastosowany oscylator typu Moog
- Polyphonic - graj wiele nut jednocześnie
- Niskie opóźnienie (low latency)
- Idealny do basów i melodii

---

## 🎛️ KROK 5: MIDI (ZAAWANSOWANE)

### Podłączenie Kontrolera MIDI

**Jeśli masz kontroler MIDI (np. Launchkey Mini MK2):**

```
1. Podłącz kontroler USB do komputera
2. Kliknij przycisk "MIDI" (prawy górny róg)
3. Wybierz swój kontroler z listy
4. Padziki → PADY MPC (1-8)
5. Klawisze → Syntezator
6. Gotowe! 🎉
```

### Zalecane Kontrolery
- ✅ Akai Launchkey Mini MK2 (testowany & rekomendowany)
- ✅ Native Instruments Komplete Kontrol
- ✅ Any standard USB MIDI device

---

## 🔧 ROZWIĄZYWANIE PROBLEMÓW

### ❌ Problem: Dźwięki się zapętlają / skaczą

**Przyczyny:**
- Plik WAV jest uszkodzony
- Zbyt wiele próbek grających jednocześnie
- Zbyt duży plik audio

**Rozwiązanie:**
```
1. Naciśnij ESC (Panic Button) - zabija ALL dźwięki
2. Odśwież stronę (F5)
3. Wczytaj mniejsze pliki WAV (<5MB)
```

---

### ❌ Problem: Sampli nie grają

**Przyczyny:**
- Pliki WAV nie wgrane
- Sample nie przypisane do padów
- Zły format pliku

**Rozwiązanie:**
```
1. Sprawdź czy pliki to rzeczywiście .wav
2. Połóż je w poprawnej kategorii
3. Użyj Sample Manager aby przypisać pady
4. Test: Kliknij pad - powinno zagrać
```

---

### ❌ Problem: Klawiatura nie działa

**Przyczyny:**
- Focus jest w polu tekstowym INPUT
- Javascript wyłączony
- Zła klawiatura (non-standard layout)

**Rozwiązanie:**
```
1. Kliknij gdzieś poza polem tekstowym
2. Spróbuj ponownie nacisnąć klawisz
3. Upewnij się że masz angielskie ustawienia klawiatury
```

---

### ❌ Problem: MIDI nie działa

**Przyczyny:**
- Kontroler nie podłączony
- Brak sterowników MIDI
- Brak obsługi Web MIDI w przeglądarce

**Rozwiązanie:**
```
1. Sprawdź USB connection
2. Zainstaluj sterowniki producenta
3. Otwórz inną przeglądarkę (Chrome/Edge)
4. Restart przeglądarki
5. Spróbuj innego urządzenia MIDI
```

---

### ❌ Problem: Brak dźwięku / cicho

**Przyczyny:**
- System wyciszony
- Głośnik/słuchawki nie podłączone
- Web Audio API wyłączony

**Rozwiązanie:**
```
1. Sprawdzić głośność systemu
2. Klapki hałasu włączyć
3. Wkopać inny plik (inne słuchawki/głośnik)
4. Refresh strony i pozwól dostępu do Audio
```

---

## 🎓 PORADY I TRIKI

### 💡 Porada 1: Layering dźwięków
```
• Warstwuj više sampli na jednym padzie dla grubszego dźwięku
• Każdy PAD może grać wiele nut naraz
• Eksperymentuj z BPM aby znaleźć groove
```

### 💡 Porada 2: Budowanie Groove'u
```
• Zacznij od kicku/beatu fundamentu
• Dodaj snare'a w syncopacji
• Napełniaj hi-hatami i inne elementy
• Powtarzaj i iteruj
```

### 💡 Porada 3: Struktura Beatu
```
INTRO     (8 kroków)
VERSE 1   (16 kroków)
CHORUS    (16 kroków)
VERSE 2   (16 kroków)
CHORUS    (16 kroków)
OUTRO     (8 kroków)

Tip: Zmień beat co 16 kroków aby to było bardziej interesujące
```

### 💡 Porada 4: BPM Selection
```
🎵 Hip-Hop:     85-95 BPM
🎵 Trap:        140-160 BPM (ale half-time = 70-80)
🎵 Dubstep:     140 BPM
🎵 House/Techno: 120-130 BPM
🎵 Drill:       160-180 BPM
```

---

## 📚 PRZYDATNE LINKI

- 📖 [Official README (English)](README.md)
- 🐛 [Report Issues](https://github.com/BrylasBit/mpc_ultra/issues)
- 💬 [Discussions](https://github.com/BrylasBit/mpc_ultra/discussions)
- 🎹 [Music Production Tips](https://en.wikipedia.org/wiki/Music_production)
- 🎵 [Beat Making Guide](https://en.wikipedia.org/wiki/Beat_(music))

---

## 🎯 NEXT STEPS

Po opanowaniu podstaw:

1. **Eksperymentuj** - spróbuj różnych soundów i BPMów
2. **Twoż** - zrób swój własny beat od zera
3. **Uczyń się** - z Youtube tutoriali o produkcji muzyki
4. **Ulepszaj** - kontrybuuj do projektu jeśli znaleźć bugs

---

## ❓ FAQ

**P: Czy mogę używać to komercyjnie?**
O: Tak! Licencja MIT pozwala na komercyjne użycie.

**P: Czy moja praca zostaje zapisana?**
O: Nie. Aktualnie nie ma funkcji SAVE/LOAD.  (planuowane w przyszłości)

**P: Ile sampli mogę wgrać?**
O: Teoretycznie tysiące - zależy od RAM przeglądarki (zwykle 100-500)

**P: Czy działa offline?**
O: Tak! Wszystko działa lokalnie w przeglądarce.

**P: Czy mogę eksportować beat do MP3?**
O: Aktualnie nie. (funkcja planowana)

---

## 🎉 POWODZENIA W TWORZENIU MUZYKI!

Masz pytania? Stwórz ISSUE na GitHubie lub zaproś mnie do dyskusji.

**Happy Beat Making! 🎵🔥**

