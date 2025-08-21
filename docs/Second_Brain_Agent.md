# Agent Drugiego Mózgu (twój osobisty bibliotekarz)

## Idea
Zamiast trzymać ważne informacje w głowie, możesz je odkładać do „drugiego
mózgu”. Agent zapisuje notatki w bazie Supabase i potrafi je później znaleźć,
gdy o coś zapytasz.

## Jak to działa
1. **Dodawanie informacji** – wysyłasz wiadomość lub plik. Agent tworzy z niego
   wektor i zapisuje w bazie (jak spis treści w bibliotece).
2. **Pytanie** – prosisz: „Przypomnij mi ciekawostki o Marsie”.
3. **Wyszukiwanie** – agent przeszukuje bazę i zwraca pasujące fragmenty.
4. **Odpowiedź** – z odnalezionych notatek tworzy krótkie podsumowanie.

## Uruchomienie krok po kroku
1. Zaimportuj w n8n `Second_Brain_Agent.json`.
2. Skonfiguruj połączenie z Supabase (adres i klucz). Możesz użyć darmowego
   konta.
3. Ustaw lokalny model LLM oraz embeddings zgodnie z
   [Local_LLM_Setup.md](Local_LLM_Setup.md) – np. `llama3-8b` i
   `text-embedding-nomic`.
4. Kliknij **Execute Workflow**. Dodaj kilka notatek i spróbuj o nie zapytać.

## Pomysły na rozwój
- Połącz agenta z YouTube lub podcastami, aby automatycznie zapisywać
  transkrypcje.
- Dodaj funkcję przypomnień wysyłanych na e‑mail.

