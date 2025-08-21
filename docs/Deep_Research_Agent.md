# Agent głębokiego researchu (internetowy detektyw)

## Co to jest?
Gdy potrzebujesz odpowiedzi na trudne pytania, ten agent działa jak
dociekliwy detektyw. Potrafi przeszukiwać internet i zbierać informacje z
różnych źródeł, po czym streszcza je w prosty sposób.

## Jak wygląda śledztwo
1. **Wiadomość z Telegrama** – pytasz np. „Jak działa energia słoneczna?”.
2. **Filter** – upewnia się, że masz dostęp do agenta.
3. **AI Agent** – decyduje, czy wystarczy szybkie wyszukiwanie (Sonar) czy
   potrzebne jest głębsze kopanie (Sonar Pro).
4. **Streszczenie** – agent zbiera znalezione informacje i odsyła zwięzłą
   odpowiedź.

## Jak uruchomić
1. Zaimportuj `Deep_Research_Agent.json` do n8n.
2. W węźle z modelem ustaw lokalny LLM (np. `qwen2-7b`) według
   [Local_LLM_Setup.md](Local_LLM_Setup.md).
3. Jeśli nie chcesz korzystać z usług Perplexity, podłącz własne źródło danych
   lub prosty RAG.
4. Kliknij **Execute Workflow** i zadawaj pytania w okienku czatu.

## Podpowiedź
Możesz rozszerzyć agenta, aby zapisywał najciekawsze znaleziska w notatniku lub
wysyłał je e‑mailem do ciebie.

