# Demo podagentów (jak zespół piszący bloga)

## O co chodzi?
Wyobraź sobie redakcję. Redaktor naczelny prosi kilku reporterów o pomoc:
jednego o research, innego o napisanie tytułów, kolejnego o napisanie
paragrafów, a jeszcze innego o znalezienie obrazka. Ten workflow pokazuje, jak
taka współpraca wygląda w n8n.

## Kto tu pracuje
- **Blog Writer Agent** – redaktor naczelny, który scala wszystko w jedną całość.
- **Research Agent** – reporter zbierający informacje z internetu.
- **Titles and Structure Tool** – pomaga ułożyć tytuł i plan artykułu.
- **Write Section Tool** – pisze każdy akapit.
- **Generate Image Tool** – dobiera grafikę pasującą do tekstu.

## Jak przetestować
1. Zaimportuj w n8n plik `AI Sub Agent Demo.json`.
2. Ustaw lokalny model zgodnie z poradnikiem
   [Local_LLM_Setup.md](Local_LLM_Setup.md) – w każdym węźle wybierz `Local
   OpenAI` i odpowiedni model.
3. Kliknij **Execute Workflow** i w czacie poproś: „Napisz artykuł o zdrowym
   śnie”. Zobaczysz, jak kolejne narzędzia kolejno się uruchamiają.

## Co możesz zmienić
- Zamień modele na inne (np. `mixtral-8x7b` zamiast `llama3-8b`).
- Podłącz własne źródła danych do Research Agenta.
- Dodaj dodatkowy krok, np. korektę języka przez **Bielika**.

