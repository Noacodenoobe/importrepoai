# Agent głębokiego researchu V2 + RAG

## Przegląd
- Zaawansowany agent researchowy łączący wyszukiwanie w sieci z Retrieval-Augmented Generation.
- Wykorzystuje Supabase jako wektorową bazę wiedzy.
- Zawiera węzły do wczytywania plików PDF i dzielenia tekstu, aby zasilać bazę.
- Wykorzystuje modele DeepSeek do rozumowania.

## Przepływ
1. Wyzwalacz Telegrama przekazuje wiadomości do `Switch`, który wybiera odpowiedni tryb agenta.
2. Dokumenty można przesłać, podzielić i zembedować w Supabase, aby później je wyszukiwać.
3. `AI Agent` odpyta wektorową bazę i narzędzia zewnętrzne, aby przygotować wyczerpującą odpowiedź.

## Przełączenie na modele lokalne
1. Zamień węzły DeepSeek na lokalne modele działające na endpointzie zgodnym z OpenAI.
2. Do embeddingów użyj lokalnego modelu lub usługi offline współpracującej z Supabase.
3. Upewnij się, że wszystkie poświadczenia wskazują na lokalne usługi i nie zawierają zdalnych kluczy.
