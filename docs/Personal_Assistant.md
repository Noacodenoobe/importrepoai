# Asystent osobisty

## Przegląd
- Asystent działający przez Telegram, który koordynuje wiele wyspecjalizowanych agentów.
- Obsługuje tekst i głos, research, śledzenie wydatków, zarządzanie e‑mailami, pogodę/wiadomości oraz pisanie treści.
- Utrzymuje długoterminowy kontekst dzięki pamięci czatu opartej na Postgresie.

## Przepływ
1. **Telegram Trigger** odbiera wiadomości lub nagrania.
2. Nagrania są transkrybowane i łączone z tekstem w `Combine fields`.
3. **Orchestrator Agent** wybiera podagentów, takich jak Research, Finance Tracker, Email Manager czy Write Section Tool.
4. Odpowiedzi wracają do użytkownika przez Telegram.

## Integracja z modelami lokalnymi
- Zastąpiono zdalne modele lokalnymi odpowiednikami:
  - **GPT-4.1** → `mixtral-8x7b` działający pod `http://localhost:8080/v1`.
  - **Anthropic Chat Model** → `qwen2-7b-instruct` pod tym samym adresem.
  - **GPT-5-Nano** → `phi-3-mini` do lekkich zadań.
  - **OpenAI** (transkrypcja) → lokalny `faster-whisper`.
- Wszystkie węzły LLM korzystają z poświadczeń **Local OpenAI** wskazujących na lokalny serwer.
- Dzięki temu cały workflow asystenta działa bez zewnętrznych wywołań API.

## Dalsze usprawnienia
- Można dodać warstwę tłumaczenia z użyciem modelu **Bielik 11B**, aby zadbać o naturalną polszczyznę.
- W razie potrzeby zastąp pozostałe węzły OpenAI odpowiednikami hostowanymi lokalnie.
