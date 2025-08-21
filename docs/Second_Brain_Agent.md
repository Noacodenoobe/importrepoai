# Agent Drugiego Mózgu

## Przegląd
- Działa jako osobista baza wiedzy, wykorzystując Supabase do przechowywania wektorów.
- `Vector Store Agent` oparty na OpenAI GPT-4o-mini dodaje i wyszukuje informacje.
- Kontekst rozmowy przechowywany jest w Postgresie przez `Postgres Chat Memory`.
- Integracje obejmują Telegram oraz transkrypcję YouTube do wprowadzania treści.

## Przepływ
1. Napływające dane są embedowane i zapisywane w Supabase.
2. Zapytania użytkownika uruchamiają wyszukiwanie wektorowe.
3. Agent tworzy odpowiedź na podstawie znalezionych fragmentów i odsyła ją użytkownikowi.

## Przełączenie na modele lokalne
1. Zamień GPT-4o-mini na lokalny LLM (np. `llama3-8b`), aktualizując model i `baseUrl` w węźle.
2. Wymień embeddingi OpenAI na lokalny model, np. `text-embedding-nomic`.
3. Zaktualizuj poświadczenia, aby usuwały zdalne klucze API i kierowały zapytania na lokalne endpointy.
