# Agent zarządzania projektami

## Przegląd
- Zbudowany w n8n i LangChain do obsługi projektów w Asanie.
- Główny model LLM to Anthropic Claude.
- Kontekst rozmowy przechowywany jest w **Simple Memory**, a narzędzie **Think** pomaga w rozumowaniu.
- Zawiera dedykowane węzły Asany do tworzenia projektów, zadań, podzadań oraz wyszukiwania użytkowników.

## Przepływ
1. Wyzwalacz czatu przekazuje wiadomość do agenta **Project Manager**.
2. Agent decyduje, którego narzędzia Asany użyć: utworzyć projekt, zadanie, podzadanie czy wyszukać użytkownika.
3. Historia rozmowy zapisywana jest w **Simple Memory**, aby agent miał kontekst.

## Przełączenie na modele lokalne
1. Uruchom lokalny serwer LLM (np. LocalAI, Ollama) udostępniający endpoint zgodny z OpenAI `/v1`.
2. Zamień węzeł Anthropic Claude na węzeł typu OpenAI, wskazujący na lokalny serwer.
3. Ustaw parametr `model` na nazwę lokalnego modelu (np. `llama3-8b-instruct`) oraz `baseUrl` na adres serwera.
4. W n8n zaktualizuj poświadczenia tak, aby nie używać kluczy API i kierować zapytania na lokalny serwer.
