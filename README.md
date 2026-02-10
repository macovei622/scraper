# n8n Lead Generation Workflows

Три автоматизированных воркфлоу для генерации лидов в сфере медицинских AI устройств и клинических исследований.

## Workflows

| Файл | Целевая персона | Описание |
|------|-----------------|----------|
| `n8n_workflow_panic_cto.json` | CTO/VP Eng в AI-медевайс | Поиск технических лидеров в компаниях с FDA фокусом |
| `n8n_workflow_helperless_clinician.json` | Principal Investigators | Поиск PI по AI/ECG trials из ClinicalTrials.gov |
| `n8n_workflow_clinical_ops_manager.json` | Clinical Ops Managers | Поиск менеджеров в компаниях с diversity pressure |

## Требуемые API

- **SerpAPI** ($50/мес) — для LinkedIn поиска через Google
- **ScraperAPI** ($49/мес) — для обхода защиты сайтов компаний
- **OpenAI** — для генерации персонализированных сообщений
- **Google Sheets** — для хранения лидов

## Бесплатные API

- ClinicalTrials.gov API
- PubMed E-utilities API

## Установка

1. Импортировать JSON в n8n
2. Настроить credentials (SerpAPI, Google Sheets OAuth, OpenAI)
3. Заменить `YOUR_GOOGLE_SHEET_ID` на ID таблицы
4. Активировать workflow

## Архитектура

```
Cron Trigger → Поиск компаний/людей → Фильтрация → Обогащение → Google Sheets → OpenAI → Сохранение сообщения
```
