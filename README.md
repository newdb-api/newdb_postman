# NEWDB Postman Collection Repository

Официальная коллекция [Postman](https://www.postman.com/) для работы с **NEWDB REST API** (версия 2.0).

[![Run in Postman](https://run.pstmn.io/button.svg)](https://newdb.net/docs)

---

## Структура репозитория

```
postman/
├── collections/
│   └── collection.json       # Основная коллекция Postman v2.1.0 (все методы API)
├── environments/
│   └── newdb_prod.json       # Окружение Production (base_url, api_token)
├── globals/                  # Глобальные переменные Postman
└── README.md
```

---

## Быстрый импорт в Postman Desktop

1. Откройте **Postman Desktop**.
2. Нажмите кнопку **Import** (в левом верхнем углу).
3. Выберите файл `postman/collections/collection.json`.
4. Также импортируйте файл окружения `postman/environments/newdb_prod.json`.
5. В правом верхнем углу Postman выберите окружение **NEWDB Production**.
6. Укажите ваш рабочий токен в переменной окружения `api_token`.

---

## Переменные окружения

| Переменная | Значение по умолчанию | Описание |
| :--- | :--- | :--- |
| `base_url` | `https://api.newdb.net/v2` | Базовый URL сервиса |
| `api_token` | `your_api_token_here` | Ваш токен доступа (`X-API-KEY`) |
| `request_id` | `{{$guid}}` | Автоматически сохраняемый UUID запроса |

---

## Группы запросов в коллекции

* **`00. Service & Auth`** — проверка баланса токена (`GET /v2/balance`), получение результатов по `requestId`.
* **`01. Физические лица`** — `complex_by_passport`, `passport_mvd`, `passport_fns`, `fssp_person`, `bankrot_person`, `pledge_person`, `arbitr_person`, `nalog_debt`, `fns_block_person`, `egrul_ip`, `terrorist`, `elmk_registry`.
* **`02. Юридические лица`** — `complex_by_inn`, `egrul`, `fns_block`, `bankrot_legal`, `arbitr_legal`, `fssp_legal`.
* **`03. Иностранные граждане`** — `rkl` (Реестр контролируемых лиц МВД), `patent_msk`, `foreign_vng`.
* **`04. Имущество и залоги`** — `pledge_vin` (проверка авто по VIN на залоги в ФНП), `rosreestr`.
* **`05. ГАС Правосудие`** — `pravo_search` (судебные дела в СОЮ).

---

## Синхронизация с GitHub

Для синхронизации коллекции между Postman Desktop и данным репозиторием используйте skill `postman-github-sync`:
```bash
git add postman/collections/collection.json postman/environments/
git commit -m "Sync Postman collection"
git push origin main
```
