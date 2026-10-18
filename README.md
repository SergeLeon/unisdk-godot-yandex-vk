# UniSDK — SDK для Яндекс.Игр и ВК Игр на Godot 4 · Yandex Games & VK Games SDK for Godot

<p align="center">
  <a href="https://store.godotengine.org/asset/sergeleon/unisdk/"><img alt="Godot Asset Store" src="https://img.shields.io/badge/Godot%20Asset%20Store-UniSDK-478cbf"></a>
  <a href="https://sergeleon.github.io/unisdk-godot-yandex-vk/"><img alt="Website" src="https://img.shields.io/badge/website-landing%20page-478cbf"></a>
  <a href="https://godotengine.org"><img alt="Godot 4.3+" src="https://img.shields.io/badge/Godot-4.3%2B-478cbf"></a>
  <a href="LICENSE"><img alt="MIT License" src="https://img.shields.io/badge/license-MIT-green"></a>
</p>

> **English summary.** UniSDK is a Godot 4.3+ editor plugin that provides a single GDScript API
> (`UniSDK.ads`, `.payments`, `.leaderboards`, `.storage`, …) for the **Yandex Games**, **VK Games**
> and **OK Games** web platforms. One HTML5 build runs everywhere: the adapter is detected at
> runtime, a mock bridge keeps the game playable in the editor, and the export dialog generates
> ready-to-upload web presets.

**SDK для Яндекс.Игр на Godot 4 · Yandex Games SDK for Godot · VK Games SDK · VK Bridge для Godot · ВК Игры SDK.**
Установка из [Godot Asset Store](https://store.godotengine.org/asset/sergeleon/unisdk/) или копированием `addons/uni_sdk`.

## Что внутри

- **Реклама** — rewarded, interstitial с кулдауном, баннеры; состояние форматов, лимиты ожидания, причина отказа.
- **Покупки** — каталог, покупка, восстановление неиспользованных платежей.
- **Лидерборды** — отправка очков, чтение таблицы, проверка доступности полной таблицы.
- **Облачные сохранения** — Yandex Player Data и VK Storage: локальный кэш, diff-записи, повторы, сохранение при сворачивании вкладки.
- **Отзывы и «в избранное»** — запрос оценки, ярлык на добавление игры в закладки.
- **Автодетект платформы** — одна Web-сборка на Яндекс, VK и ОК.
- **Mock-режим** — игра, сохранения и «показ рекламы» работают в редакторе без аккаунта платформы.
- **Экспорт** — диалог создаёт Web-пресеты, HTML-оболочки Яндекса и VK, cache-busting, ZIP; опционально hosting config для VK.

## Установка

1. Поставь аддон из [Godot Asset Store](https://store.godotengine.org/asset/sergeleon/unisdk/) либо скопируй папку `addons/uni_sdk` в проект.
2. **Project → Project Settings → Plugins** → включи **UniSDK**.
3. Autoload `UniSDK` зарегистрируется сам, профили платформ создадутся при первом запуске.

## Быстрый старт

```gdscript
func _ready() -> void:
	await UniSDK.ensure_initialized()
	var result: Dictionary = await UniSDK.ads.show_rewarded()
	if result.get("rewarded", false):
		grant_coins()
```

## Требования

- Godot **4.3+**, экспорт Web (HTML5). На десктопе и мобилках работает mock-мост.
- Реклама, покупки и облако в проде требуют опубликованной игры и ключей Яндекс.Игр / VK Игр.

## Документация

- **[addons/uni_sdk/DOCUMENTATION.md](addons/uni_sdk/DOCUMENTATION.md)** — полный справочник: все модули и методы, настройки проекта, различия платформ, лимиты и лимиты ожидания рекламы, внутреннее устройство JS-мостов, патч Emscripten, mock-режим, миграция с Yandex-only SDK, troubleshooting, changelog.
- **[Лендинг](https://sergeleon.github.io/unisdk-godot-yandex-vk/)** — то же описание на одной странице.

<details>
<summary><b>По каким запросам находится этот репозиторий / Search terms</b></summary>

`sdk для яндекса` · `sdk для яндекса godot` · `sdk для вк` · `sdk для вк игр` · `яндекс игры sdk` · `яндекс игры godot 4` ·
`яндекс игры плагин godot` · `вк игры sdk` · `вк игры godot` · `yandex games sdk godot 4` · `yandex games godot plugin` ·
`yagames sdk gdscript` · `yandex player data godot` · `яндекс реклама rewarded godot` ·
`vkontakte games sdk godot` · `vk bridge godot 4` · `vk bridge gdscript` ·
`vk storage godot` · `vk web app godot` · `одноклассники sdk godot` · `ok.ru games godot` ·
`godot web export html5` · `godot web export preset` · `godot rewarded video` · `godot interstitial ad` ·
`godot cloud saves` · `godot leaderboard` · `godot in-app purchases web` · `godot html5 mobile game` ·
`универсальный sdk для игровых платформ godot` · `unified sdk godot web platforms`

Синонимы и торговые названия: **Яндекс.Игры**, **Yandex Games**, **YaGames**, **Yandex Player**, **Yandex SDK**,
**ВК Игры**, **VK Games**, **VK Play**, **VK Bridge**, **VK Storage**, **Одноклассники**, **OK.ru**, **OK Games**.

</details>

## Лицензия

[MIT](LICENSE) — используй свободно, включая коммерческие игры.
