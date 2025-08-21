# Przewodnik konfiguracji lokalnych modeli LLM

## 1. Co będziemy robić
Ten poradnik pokazuje, jak uruchomić agentów z tego repozytorium na własnym komputerze
bez internetu. Wszystko opisane jest prostym językiem, aby nawet początkujący mogli
spróbować swoich sił.

## 2. Czego potrzebujemy
1. **Komputer z mocną kartą graficzną** – Twój sprzęt z RTX 5080 i 32 GB RAM świetnie się nadaje.
2. **Program do uruchamiania modeli** – użyjemy [LM Studio](https://lmstudio.ai) (łatwy interfejs) lub [Ollama](https://ollama.com) (działa z terminala).
3. **n8n** – tutaj działają wszystkie agentowe "przepisy". Możesz skorzystać z wersji Desktop [z tej strony](https://n8n.io).

## 3. Pobieranie modeli
### 3.1 Otwórz LM Studio
1. Uruchom LM Studio i przejdź do zakładki **Models**.
2. Wpisz nazwę modelu w wyszukiwarkę i kliknij **Download**.

### 3.2 Jakie modele pobrać
| Zastosowanie | Nazwa modelu w LM Studio | Do czego służy |
|-------------|-------------------------|---------------|
| Główny mózg asystenta | `mixtral-8x7b-instruct` | rozumienie pytań i sterowanie innymi agentami |
| Szybkie zadania (np. pogoda) | `phi-3-mini` | krótkie odpowiedzi, działa błyskawicznie |
| Głęboki research | `qwen2-7b-instruct` | analizuje i łączy informacje |
| Piękny język polski | `bielik-11b` | tłumaczenia i poprawa stylu |
| Transkrypcja audio | `faster-whisper-large-v3` | zamienia mowę na tekst |

> Jeśli model jest zbyt duży, w LM Studio wybierz opcję **Quantized** (np. 4-bit), wtedy zmieści się w pamięci karty graficznej.

## 4. Uruchomienie lokalnego serwera modeli
1. W LM Studio przejdź do zakładki **Server**.
2. Kliknij **Start** – pojawi się adres, np. `http://localhost:8080`.
3. Zanotuj ten adres; w n8n ustawimy go jako "OpenAI Base URL".

## 5. Podłączenie modeli w n8n
1. Uruchom n8n i zaimportuj workflow, np. `Personal Assistant.json`.
2. Wejdź w zakładkę **Credentials** → **OpenAI** → dodaj nowe i nazwij je `Local OpenAI`.
3. W polu **Base URL** wpisz `http://localhost:8080/v1`, a pole z kluczem API zostaw puste.
4. Otwórz węzeł z modelem (np. `GPT-4.1`) i wybierz w nim poświadczenia `Local OpenAI`. Zmień nazwę modelu na taką, jak w LM Studio (np. `mixtral-8x7b-instruct`).
5. Powtórz dla pozostałych węzłów: research (`qwen2-7b-instruct`), szybkie zadania (`phi-3-mini`), tłumaczenia (`bielik-11b`).
6. Dla transkrypcji głosu dodaj węzeł **HTTP Request** kierujący na `faster-whisper`.

## 6. Korzystanie z agentów
1. W n8n kliknij **Execute Workflow**.
2. Otwórz Telegram i wyślij wiadomość do bota powiązanego z `Personal Assistant`.
3. Zadawaj pytania po polsku. Asystent sam dobierze model i odpowie.
4. Spróbuj też innych agentów z folderu `docs/` – każdy działa podobnie, tylko ma inne zadania (np. zarządzanie projektami, tworzenie blogów).

## 7. Co dalej
- Testuj różne modele. Jeśli odpowiedzi są wolne, wybierz mniejszy model.
- Zajrzyj do plików `docs/*.md` aby dowiedzieć się, co robi każdy agent.
- Ucz się poprzez zabawę – modyfikuj workflowy i zobacz, co się stanie!

Powodzenia i miłej nauki!
