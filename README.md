<p align="center">
  <img src="preview.png" alt="ZAPRET CORE" width="100%" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/build-private-black?style=flat-square" />
  <img src="https://img.shields.io/badge/signed-signtool-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/engine-DirectX%2011-purple?style=flat-square" />
  <img src="https://img.shields.io/badge/version-2.7.0-white?style=flat-square" />
</p>

<h3 align="center">Приватная система обхода DPI нового поколения</h3>
<p align="center">Закрытый исходный код · Подписанные бинарные файлы · Нулевая задержка</p>

<p align="center">
  <a href="https://zapretcore.ru/index.html"><b>zapretcore.ru</b></a> &nbsp;│&nbsp; 
  <a href="https://github.com/dysonbehind/zapret-discord-youtube/releases"><b>Releases</b></a> &nbsp;│&nbsp; 
  <a href="https://t.me/wokeupinthemorning"><b>Telegram</b></a>
</p>

---

> **ZAPRET CORE** работает на уровне ядра ОС. Пакеты фрагментируются и модифицируются локально через WinDivert — трафик никогда не покидает вашу машину. Это не VPN. Нет удалённых серверов. Нет потери скорости. Нет логов.

---

### Что внутри

```
28 PROFILES        Стратегии DPI-desync под каждого провайдера
24 THEMES          12 dark · 12 light · полная адаптация UI
MTPROTO PROXY      Telegram через WebSocket + Cloudflare CDN fallback
HTTP PROXY         Раздача обхода на телефон по Wi-Fi (порт 8080)
ADAPTIVE SCANNER   Автоматический подбор рабочего профиля
HOSTS MANAGER      Управление доменами и IP из интерфейса
DNS TOOLS          DoH через Cloudflare 1.1.1.1 · SNI spoofing
WARP 1.1.1.1       Интеграция с Cloudflare WARP
OTA UPDATES        Обновление без переустановки
WINDOWS SERVICE    Фоновая работа · автозапуск · без окна
```

### Архитектура

```
C++20 / MSVC 2022 / DirectX 11 / Dear ImGui
Ядро:    winws.exe + WinDivert64.sys (kernel-level packet interception)
Крипто:  Windows CNG — BCrypt AES-CTR (MTProto handshake)
Сеть:    WinHTTP WebSocket · raw TCP · Cloudflare CDN pool
Рендер:  Direct3D 11 · аппаратное ускорение · 0% CPU в простое
```

### Запуск

```
1. Скачать релиз → запустить от администратора
2. Выбрать профиль → «Запустить обход»
3. Telegram / YouTube / Discord — работают
```

**Мобильные устройства:**  
Включить TG Proxy → открыть `http://<IP>:8081` на телефоне → Setup Node сделает остальное

---

> [!CAUTION]
> **Единственные официальные источники:**  
> GitHub — [zapretcore/zapret-core](https://github.com/dysonbehind/zapret-discord-youtube)
> Сайт — [zapretcore.ru](https://zapretcore.ru)  
> Telegram — [@zapretcore](https://t.me/wokeupinthemorning)
> Всё остальное — **подделка**. Не скачивайте файлы из других источников.

> [!IMPORTANT]
> **Все релизы подписаны** через `signtool` с верифицированным сертификатом. Бинарный файл защищён от модификации. Если подпись не совпадает — файл скомпрометирован.

> [!WARNING]
> **WinDivert** — легитимный open-source драйвер для перехвата сетевого трафика на уровне ядра. Детектируется как `RiskTool.Multi.WinDivert` — это штатное поведение. Добавьте директорию утилиты в исключения антивируса.

---

<table>
<tr>
<td width="50%">

**Zero Latency**  
Обход на уровне ядра. 100% пропускной способности канала сохраняется.

**Local Only**  
Весь процесс происходит на вашей машине. Без серверов, без подписок, без логов.

</td>
<td width="50%">

**One Click**  
Сложные параметры `--dpi-desync` в одном GUI. Консоль не нужна.

**Cross-Device**  
Один ПК раздаёт обход на все устройства в сети через HTTP/MTProto прокси.

</td>
</tr>
</table>

---

## ZAPRET CORE v2.7.0 — «Полный обход»

> Twitch исправлен. WARP больше не нужен. Профили пересобраны с нуля.

### 🎮 Apex Legends — профили P10–P14

Профили 10–14 полностью пересобраны из кастомных `.bat` конфигураций:

- **P10** — Apex / Multisplit AutoTTL
- **P11** — Fuck DPI / Multisplit + Syndata
- **P12** — Real / Apex FakedSplit *(лучший для Apex)*
- **P13** — General ALT 7.1 (расширенные игровые порты + STUN)
- **P14** — General ALT 7.2 (расширенные игровые порты + STUN)

Все используют `quic_initial_dbankcloud_ru.bin` для UDP bypass. Для Apex рекомендуется **P12**.

### 🎨 24 темы — 12 dark + 12 light

Полная переработка палитры:
- **Dark:** Midnight, Void, Slate, Emerald, Neon, Toxic, Phantom, Crimson, Obsidian, Carbon, Abyss, Ember
- **Light:** Snow, Cloud, Sakura, Pearl, Latte, Glacier, Mint, Lavender, Cream, Rose, Frost, Ivory

Все элементы UI адаптированы под каждую тему: трей, роли, Routing Engine, Adaptive Scanner, логи, сетка.

### 🔧 Остальное

- **THROUGHPUT** — чистый стиль, палка убрана, скорость через accent color
- **Color picker** — hue + saturation bars, hex chip, drag
- **Settings popup** — точно под контент, без скролла
- **Light theme fixes** — полный скан: mesh, grid, домены, статистика, separator — всё видно
- **Атмосфера** — Snow / Bypass / FCK RKN (Petals удалён)

### Из v2.6.5

- **Встроенный терминал** — cmd.exe прямо в LOGS, переключатель «Логи / Терминал»
- **Hot-swap профилей** — смена профиля на лету без остановки обхода
- **Адаптивный сканер** — реалистичный пинг через `time_connect` (TCP RTT)
- **Чат** — текст больше не выходит за границы, окно 420×500, счётчик символов
- **Hosts** — файл закрывается сразу после записи
- **Автозапуск** — программа всегда стартует с системой + трей
- **OTA** — пользовательские списки `*-user` сохраняются при обновлении

---

> **Тестируйте после обновления.** Результаты зависят от провайдера и региона. Пишите в [@zapretcore](https://t.me/zapretcore).

---

> [!NOTE]
> **Исходный код не публикуется.** Распространяются только подписанные скомпилированные бинарные файлы через [Releases](https://github.com/dysonbehind/zapret-discord-youtube). Проект разрабатывается приватно.

---

<p align="center">
  <b>Поддержать проект</b><br>
  <sub>⭐ Star этого репозитория или финансово:</sub><br><br>
  <code>USDT (TRC20): soon</code><br>
  <code>BTC: soon</code><br>
  <a href="https://pressf.com/dys0n/donate">pressf.com/dys0n/donate</a>
</p>

<p align="center">
  <sub>© ZAPRET CORE — zapretcore.ru</sub>
</p>
