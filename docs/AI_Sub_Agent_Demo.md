# Demonstracja podagentów

## Przegląd
- Pokazuje hierarchię podagentów używaną do tworzenia wpisów na blog.
- Główny **Blog Writer Agent** koordynuje research, tworzenie konspektu, pisanie i generowanie obrazów.
- Wykorzystuje narzędzia: wyszukiwanie Perplexity, tworzenie tytułu i struktury, pisanie sekcji oraz generowanie grafiki.
- Opiera się na kilku węzłach z modelami OpenAI.

## Przepływ
1. **Research Agent** zbiera informacje z Perplexity i innych źródeł.
2. **Titles and Structure Tool** proponuje tytuły i konspekt.
3. **Write Section Tool** pisze każdą sekcję wpisu.
4. **Generate Image Tool** tworzy pasującą grafikę.
5. Wyniki łączy i zwraca **Blog Writer Agent**.

## Przełączenie na modele lokalne
1. Uruchom lokalny endpoint LLM zgodny z API OpenAI.
2. Zamień każdy węzeł OpenAI na lokalny model (np. `llama3-8b` lub `mixtral-8x7b`).
3. Ustaw opcję `baseUrl` w węźle na adres lokalnego serwera i usuń klucze API.
4. Do generowania obrazów możesz użyć lokalnego modelu dyfuzyjnego albo pozostawić węzeł korzystający z zewnętrznego API.
