# Agent głębokiego researchu

## Przegląd
- Specjalizuje się w głębokim researchu z użyciem modeli Sonar i Sonar Pro od Perplexity.
- Centralny `AI Agent` (OpenAI GPT-4o-mini) decyduje, kiedy wywołać odpowiednie narzędzie Perplexity.
- Zawiera węzeł `Window Buffer Memory`, który przechowuje niedawny kontekst rozmowy.
- Zaprojektowany z myślą o integracji z Telegramem i filtrem dostępu.

## Przepływ
1. Wiadomość użytkownika dociera przez Telegram i przechodzi przez `Filter`, który sprawdza uprawnienia.
2. `AI Agent` analizuje zapytanie i wybiera narzędzie Sonar lub Sonar Pro.
3. Wybrane narzędzie zwraca dane, które agent streszcza dla użytkownika.

## Przełączenie na modele lokalne
1. Zamień główny model OpenAI na lokalny LLM, korzystając z węzła kompatybilnego z OpenAI.
2. Jeśli nie chcesz używać Perplexity, zastąp narzędzia Sonar lokalnym wyszukiwaniem internetowym lub RAG.
3. Zaktualizuj poświadczenia tak, aby wskazywały na lokalny endpoint i usuń klucze API.
