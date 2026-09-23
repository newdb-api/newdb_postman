# Покрытие 57 пауков

Сверка: 2026-09-23. На Scrapyd 34 и 38 зарегистрирован одинаковый набор из 57 пауков. Маршруты и обязательные параметры сверены с `spiders_yandex`. Отсутствие маршрута не означает неисправность паука. Запросы не исполнялись.

| Паук Scrapyd | Активные API-методы | Покрытие |
| --- | --- | --- |
| `1c_diadok` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `bankrot` | `bankrot_legal`, `bankrot_person` | Покрыт API-запросами коллекции. |
| `disqual` | `disqual` | Покрыт API-запросами коллекции. |
| `driver_license` | `driver_license` | Покрыт API-запросами коллекции. |
| `egrul_untrusted` | `egrul_untrusted` | Покрыт API-запросами коллекции. |
| `elmk_registry` | `elmk_registry` | Покрыт API-запросами коллекции. |
| `fedresurs_zalog` | `pledge_legal`, `pledge_person`, `pledge_property`, `pledge_vin` | Покрыт API-запросами коллекции. |
| `fedsfm_terrorist` | `terrorist` | Покрыт API-запросами коллекции. |
| `fnp_dover` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `fns_block` | `fns_block`, `fns_block_person` | Покрыт API-запросами коллекции. |
| `fns_bo` | `fns_bo` | Покрыт API-запросами коллекции. |
| `fns_mass_founders` | `fns_mass_founders` | Покрыт API-запросами коллекции. |
| `fns_mass_leaders` | `fns_mass_leaders` | Покрыт API-запросами коллекции. |
| `fns_msp` | `msp` | Покрыт API-запросами коллекции. |
| `foreign` | `foreign_patent`, `foreign_rnr`, `foreign_rvp_blank`, `foreign_rvp_stamp`, `foreign_vng` | Покрыт API-запросами коллекции. |
| `fsin` | `fsin_wanted` | Покрыт API-запросами коллекции. |
| `fssp_company` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `fssp_fizik` | `fssp_person` | Покрыт API-запросами коллекции. |
| `fssp_legal` | `fssp_legal` | Покрыт API-запросами коллекции. |
| `gas_pravo` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `gas_pravo_sing` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `getinn` | `passport_fns` | Покрыт API-запросами коллекции. |
| `gosuslugi_pass` | `passport_mvd` | Покрыт API-запросами коллекции. |
| `intellectual_property` | `intellectual_property` | Покрыт API-запросами коллекции. |
| `kad_arbitr_case` | `arbitr_case` | Покрыт API-запросами коллекции. |
| `kad_arbitr_debt_sum` | `arbitr_debt_sum` | Покрыт API-запросами коллекции. |
| `kad_arbitr_inn` | `arbitr_legal`, `arbitr_person` | Покрыт API-запросами коллекции. |
| `kad_processual_control` | `kad_event_monitor` | Покрыт API-запросами коллекции. |
| `leasing_fedresurs` | `leasing_fedresurs` | Покрыт API-запросами коллекции. |
| `minjust_foreign_agent` | `inoagent` | Покрыт API-запросами коллекции. |
| `mos_gorsud` | `mos_gorsud` | Сборщик → raw.court_cases. Исключён из публичных примеров; поиск через pravo_search. |
| `mos_gorsud_sing` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `mvd_wanted` | `mvd_wanted` | Покрыт API-запросами коллекции. |
| `nalog` | `egrul`, `egrul_ip` | Покрыт API-запросами коллекции. |
| `nalog_debt` | `nalog_debt` | Покрыт API-запросами коллекции. |
| `nspd_cadastr` | `nspd_cadastr` | Покрыт API-запросами коллекции. |
| `ods_case_details` | `pravo_cases_details` | Покрыт API-запросами коллекции. |
| `ods_case_search` | `act_text_search`, `pravo_search` | Покрыт API-запросами коллекции. |
| `opensanctions` | `opensanctions` | Покрыт API-запросами коллекции. |
| `ozon_main_page` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `ozon_products` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `patent_mo` | `patent_mo` | Покрыт API-запросами коллекции. |
| `patent_msk` | `patent_msk` | Покрыт API-запросами коллекции. |
| `pravo_event_monitor` | `pravo_event_monitor` | Покрыт API-запросами коллекции. |
| `pravo_judge_analytics` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `pravo_judge_cases` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `pravo_judge_profile` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `pravo_judge_search` | — | Нет активного маршрута в spiders_yandex; публичный запрос не добавлен. |
| `proverki_gov` | `proverki_gov`, `proverki_knm` | Покрыт API-запросами коллекции. |
| `proverki_knm` | — | В реестре API `proverki_knm` направлен на `proverki_gov`; отдельного маршрута на этот класс нет. |
| `realty_object` | `realty_price` | Покрыт API-запросами коллекции. |
| `rkl` | `rkl` | Покрыт API-запросами коллекции. |
| `rnp` | `rnp` | Покрыт API-запросами коллекции. |
| `rosreestr` | `rosreestr` | Покрыт API-запросами коллекции. |
| `self_employed` | `self_employed` | Покрыт API-запросами коллекции. |
| `vin_check` | `vin_check` | Покрыт API-запросами коллекции. |
| `zakupki_contracts` | `contracts`, `contracts_person` | Покрыт API-запросами коллекции. |

`complex_by_passport`, `complex_by_inn`, `complex_by_innfiz` и `court_arbitration` выполняются оркестратором, а не отдельным пауком.

Из старой коллекции удалён запрос `fssp_company`: паук развёрнут, но активного API-маршрута в реестре нет. Неподтверждённые алиасы `disqualified_person` и `corporate_restrictions_person` заменены зарегистрированными `disqual` и `egrul_untrusted`.
