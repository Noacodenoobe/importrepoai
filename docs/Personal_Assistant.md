# Asystent osobisty (jak przyjaciel, który pamięta wszystko)

## Co robi?
Wyobraź sobie, że masz drużynę małych pomocników. Jeden zna się na pogodzie,
drugi pilnuje wydatków, a trzeci potrafi pisać maile. Nad nimi czuwa
**Dyrygent** – Orchestrator. Kiedy wysyłasz wiadomość, Dyrygent decyduje, którego
pomocnika poprosić o działanie i łączy odpowiedzi w jedną wiadomość.

## Jak działa w środku
1. **Wiadomość z Telegrama** – piszesz tekst albo nagrywasz głos.
2. **Transkrypcja** – jeśli to nagranie, „maszyna do pisania” (Whisper) zamienia
   głos na tekst.
3. **Dyrygent** – Orchestrator czyta tekst i wybiera odpowiedniego pomocnika:
   - *Badacz* szuka informacji w sieci,
   - *Księgowy* zapisuje wydatki,
   - *Sekretarz* tworzy lub streszcza e‑maile,
   - *Pisarz* tworzy dłuższe teksty.
4. **Powrót odpowiedzi** – wynik wraca do ciebie na Telegramie.

## Jak uruchomić agenta krok po kroku
1. **Przygotuj modele** – postępuj według poradnika
   [Local_LLM_Setup.md](Local_LLM_Setup.md). Pobierz np. `mixtral-8x7b` i
   `phi-3-mini`, uruchom serwer w LM Studio.
2. **Włącz n8n** – pobierz wersję Desktop, włącz i kliknij **Import**, aby
   wczytać plik `Personal Assistant.json`.
3. **Połącz z modelami**
   - Wejdź w **Credentials → OpenAI → Add** i nazwij połączenie `Local OpenAI`.
   - W polu **Base URL** wpisz adres serwera z LM Studio, np.
     `http://localhost:8080/v1`. Pole z kluczem pozostaw puste.
   - Otwórz każdy węzeł LLM (np. `GPT‑4.1`) i wybierz połączenie `Local OpenAI`,
     a w polu model wpisz nazwę pobranego modelu.
4. **Skonfiguruj Telegram** – w aplikacji Telegram napisz do `@BotFather`,
   utwórz nowego bota i skopiuj token. W n8n w węźle `Telegram Trigger` wklej
   ten token.
5. **Start** – kliknij **Execute Workflow** i napisz do swojego bota na
   Telegramie. Powinieneś otrzymać odpowiedź od Asystenta.

## Przykładowa rozmowa
```
Ty: "Dodaj wydatek 15 zł na kawę"
Asystent: "Zapisano: kawa – 15 zł"

Ty: "A jaka jutro będzie pogoda w Warszawie?"
Asystent: "Jutro 12 °C i deszcz, nie zapomnij parasola!"
```

## Jak rozwijać dalej
- Dodaj tłumacza **Bielik**, aby odpowiedzi brzmiały jeszcze naturalniej po
  polsku.
- Napisz własnego pomocnika, np. do planowania diety – Dyrygent zajmie się jego
  włączeniem w rozmowę.

