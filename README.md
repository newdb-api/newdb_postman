# NEWDB Postman Collection Repository

Официальная коллекция [Postman](https://www.postman.com/) для работы с **NEWDB REST API** (версия 2.0).

[![Run in Postman](https://run.pstmn.io/button.svg)](https://newdb.net/docs)

---

## Структура репозитория

```
postman/
├── collections/
│   └── collection.json       # Основная коллекция Postman v2.1.0 (все методы API + формат ZB)
├── environments/
│   ├── newdb_prod.json       # Окружение Production (base_url, test_base_url, api_token)
│   └── newdb_sandbox.json    # Окружение Sandbox (тестовый контур, test_base_url, format: zb)
├── globals/                  # Глобальные переменные Postman
└── README.md
```

---

## Быстрый импорт в Postman Desktop

1. Откройте **Postman Desktop**.
2. Нажмите кнопку **Import** (в левом верхнем углу).
3. Выберите файл `postman/collections/collection.json`.
4. Также импортируйте файлы окружения:
   - `postman/environments/newdb_sandbox.json` (для бесплатного тестирования без расхода баланса).
   - `postman/environments/newdb_prod.json` (для боевых запросов).
5. В правом верхнем углу Postman выберите нужное окружение:
   - **NEWDB Sandbox (Test)**: преднастроен с тестовым токеном `test_token_newdb_sandbox` и URL `https://api.newdb.net/test/v2`.
   - **NEWDB Production**: укажите ваш рабочий токен в переменной окружения `api_token`.

---

## Переменные окружения

| Переменная | Значение Sandbox | Значение Production | Описание |
| :--- | :--- | :--- | :--- |
| `test_base_url` | `https://api.newdb.net/test/v2` | `https://api.newdb.net/test/v2` | URL тестового контура Sandbox |
| `base_url` | `https://api.newdb.net/v2` | `https://api.newdb.net/v2` | Базовый URL боевого сервиса |
| `api_token` | `test_token_newdb_sandbox` | `your_api_token_here` | Токен доступа (`X-API-KEY`) |
| `format` | `zb` | `zb` | Формат ответа (по умолчанию `zb` для совместимости) |
| `request_id` | `{{$guid}}` | `{{$guid}}` | Автоматически сохраняемый UUID запроса |

---

## Группы запросов в коллекции

* **`00. Service & Auth`** — проверка баланса токена (`GET /v2/balance`), получение результатов по `requestId`.
* **`01. Физические лица`** — `complex_by_passport`, `passport_mvd`, `passport_fns`, `fssp_person`, `bankrot_person`, `pledge_person`, `arbitr_person`, `nalog_debt`, `fns_block_person`, `egrul_ip`, `terrorist`, `elmk_registry`.
* **`02. Юридические лица`** — `complex_by_inn`, `egrul`, `fns_block`, `bankrot_legal`, `arbitr_legal`, `fssp_legal`.
* **`03. Иностранные граждане`** — `rkl` (Реестр контролируемых лиц МВД), `patent_msk`, `foreign_vng`.
* **`04. Имущество и залоги`** — `pledge_vin` (проверка авто по VIN на залоги в ФНП), `rosreestr`.
* **`05. ГАС Правосудие и суды`** — `pravo_search` (судебные дела в СОЮ), `kad_event_monitor` (процессуальный контроль конкретного дела КАД).
* **`06. Формат ЗАПРАВИЛЬНЫЙБИЗНЕС (ZB)`** — полная совместимость с форматом ZB:
  - **`01. Тестовый контур Sandbox (GET запросы)`**: 18 методов с параметром `format=zb` на `{{test_base_url}}/run`.
  - **`02. Тестовый контур Sandbox (POST запросы)`**: 18 методов на `{{test_base_url}}` с телом `{"method": "...", "params": {...}, "format": "zb"}`.
  - **`03. Боевой контур Production (ZB формат)`**: 18 методов на `{{base_url}}` в формате ZB.
* **`07. Формат КОНТУР.ПОКУС (Pokus)`** — полная совместимость со схемами Контур.Покус (Focus API v3):
  - **`01. Тестовый контур Sandbox (GET запросы)`**: 10 ключевых методов (`/api3/req`, `/api3/smzGetStatus`, `/api3/fssp`, `/api3/fnsBlockedBankAccounts`, `/api3/companyBankruptcy`, `/api3/trademarks`, `/api3/checkPassport` и др.) с параметром `format=pokus` или `format=kontur` на `{{test_base_url}}/run`.
  - **`02. Тестовый контур Sandbox (POST запросы)`**: 10 методов на `{{test_base_url}}` с телом `{"method": "...", "params": {...}, "format": "pokus"}`.
  - **`03. Боевой контур Production (Pokus формат)`**: 10 методов на `{{base_url}}` в формате Контур.Покус.

---

## Синхронизация с GitHub

Для синхронизации коллекции между Postman Desktop и данным репозиторием используйте skill `postman-github-sync`:
```bash
git add postman/collections/collection.json postman/environments/
git commit -m "Sync Postman collection"
git push origin main
```
