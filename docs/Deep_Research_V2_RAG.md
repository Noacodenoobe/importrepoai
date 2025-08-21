# Agent researchu V2 z własnym notesem (RAG)

## Co go wyróżnia?
To jak detektyw, który oprócz internetu ma własny uporządkowany notes. Notesem
jest baza Supabase, gdzie można wrzucać dokumenty (np. PDF) i później szybko je
odnajdywać.

## Jak przebiega praca
1. **Telegram Trigger** – odbiera pytania lub dokumenty.
2. **Split & Embed** – jeśli wyślesz plik, agent dzieli go na małe kawałki i
   zapisuje w bazie Supabase.
3. **AI Agent** – gdy zadasz pytanie, agent sięga do internetu i do swojego
   „notesu”, aby skleić pełną odpowiedź.

## Uruchomienie krok po kroku
1. W n8n zaimportuj plik `Deep_Research_V2___RAG.json`.
2. Zgodnie z [Local_LLM_Setup.md](Local_LLM_Setup.md) ustaw lokalny model (np.
   `qwen2-7b`) we wszystkich węzłach LLM.
3. Ustaw połączenie z bazą Supabase (adres, klucz API). W tutorialach Supabase
   znajdziesz darmową wersję do testów.
4. Kliknij **Execute Workflow** i spróbuj wysłać plik PDF oraz pytanie na jego
   temat.

## Dalsze pomysły
- Możesz dodać przeszukiwanie własnego folderu z notatkami.
- Zastąp Supabase inną bazą wektorową, jeśli wolisz (np. Chroma).

