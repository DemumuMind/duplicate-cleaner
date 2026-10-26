# Duplicate Cleaner

🇷🇺 [RU] · 🇺🇸 [EN]

Плагин для **exteraGram**, который чистит дубли сообщений в **Избранном**.
Находит повторы и удаляет лишние, **оригинал не трогает**.

🇺🇸 An **exteraGram** plugin that removes duplicate messages from **Saved Messages**.
It finds copies and deletes the extras — **an unpaired original is never touched**.

---

## 🇷🇺 [RU]

**Название:** Duplicate Cleaner
**Автор:** [@leamanfo](https://t.me/leamanfo)
**Лицензия:** MIT

### Описание

Чистит дубли в Избранном. **29 независимых режимов**, любой можно выключить:

текст · ссылки · фото · видео · GIF · файлы · аудио · голос · стикеры · наборы
стикеров · кружки · веб-страницы · гео · места · контакты · дайсы · игры · истории ·
опросы · викторины · счета · розыгрыши · итоги · премиум-стикеры · платное медиа ·
задачи · трансляции · **альбомы** (до 10 вложений) · **комбо** (то же фото или
ссылка, пересланные с другим текстом — тоже дубль).

**Оставляется свежее** — в Telegram свежее лежит ниже в списке. Можно переключить
на «оставлять старое». **Альбомы сравниваются целиком, а не по одному файлу.**

**Быстрый повторный скан:** плагин строит индекс, и второй поиск читает только
новое — секунды вместо минут на Избранном в 6000+ записей.

### Использование

1. Настройки exteraGram → **Плагины** → **Установить из файла**.
   ⚠️ **Не** тапать по файлу в чате — Android покажет «неизвестный источник».
2. Открыть **Избранное** → Настройки плагина → **«Найти дубликаты»**.
3. Дождаться конца скана (окно прогресса закроется само).
4. Отметить лишние (по умолчанию отмечено найденное) → **«Удалить»** → подтвердить.

**Удаление необратимо**, как и обычное удаление в Telegram.

### Настройки

| настройка | по умолчанию | что делает |
|---|---|---|
| 29 тумблеров режимов | все включены | какие типы искать |
| «Оставлять старое» | выкл | иначе остаётся свежее |
| «Быстрый повторный скан» | вкл | читает только новое по индексу |
| «Пропускать короткий текст» | выкл | не считать дублем «ок», «+» |
| «Сбросить кэш скана» | — | чистит индекс и файл, и в памяти |
| «САМОТЕСТ» | — | 107 встроенных проверок на живых объектах |
| «Показать лог» | — | журнал последнего запуска |

### Требования

- **exteraGram 12.5.1+** (на более старых сборках SDK уходит в safe mode и модули
  плагинов не инициализируются)
- exteraPlugins API **1.4.4.3+**
- Python 3.11 (Chaquopy)

### Диагностика

**«САМОТЕСТ»** прогоняет 107 проверок на живых объектах приложения и печатает
`ПРОЙДЕНО N из M`. Если что-то сломано — видно, что именно.
**«Показать лог»** и **«Копировать лог»** дают подробный журнал последнего запуска.

### Данные

Файлы лежат в домашнем каталоге приложения:

```
~/arashimind_favorites_index.json   # индекс быстрого повтора
~/arashimind_favorites_log.txt      # журнал (кольцевой буфер)
```

**Файлы не покидают устройство.** Плагин не имеет сетевого кода.

### Ограничения

- Удаляются только **ваши** сообщения (`forAll=False`). Чужие не трогаются.
- Нужно право на удаление в этом чате.
- При `FLOOD_WAIT` плагин ждёт и продолжает, а не сыплет ошибками.

---

## 🇺🇸 [EN]

**Title:** Duplicate Cleaner
**Author:** [@leamanfo](https://t.me/leamanfo)
**License:** MIT

### Description

Removes duplicates from Saved Messages. **29 independent modes**, each can be
switched off:

text · links · photos · videos · GIFs · documents · audio · voice · stickers ·
sticker sets · round videos · web pages · geo · venues · contacts · dice · games ·
stories · polls · quizzes · invoices · giveaways · giveaway results · premium
stickers · paid media · to-dos · video streams · **albums** (up to 10 attachments) ·
**combo** (the same photo or link forwarded with a different caption is also a
duplicate).

**Keeps the newest** — in Telegram the newest sits lower in the list. Switchable
to "keep oldest". **Albums are compared as a whole**, not file by file.

**Fast re-scan:** the plugin builds an index and the second run reads only what is
new — seconds instead of minutes on a 6000+ item Saved Messages.

### Usage

1. exteraGram Settings → **Plugins** → **Install from file**.
   ⚠️ Do **not** tap the file in a chat — Android will show "unknown source".
2. Open **Saved Messages** → plugin settings → **"Find duplicates"**.
3. Wait for the scan to finish (the progress window closes itself).
4. Tick the extras (everything found is ticked by default) → **"Delete"** → confirm.

**Deletion is irreversible**, exactly like a normal delete in Telegram.

### Settings

| setting | default | what it does |
|---|---|---|
| 29 mode toggles | all on | which types to look for |
| "Keep oldest" | off | otherwise the newest is kept |
| "Fast re-scan" | on | reads only what is new, via the index |
| "Skip short text" | off | "ok", "+" are not duplicates |
| "Reset scan cache" | — | clears the index on disk and in memory |
| "SELF-TEST" | — | 107 checks on live objects |
| "Show log" | — | journal of the last run |

### Requirements

- **exteraGram 12.5.1+** (older builds put the SDK into safe mode where plugin
  modules refuse to initialize)
- exteraPlugins API **1.4.4.3+**
- Python 3.11 (Chaquopy)

### Diagnostics

**"SELF-TEST"** runs 107 checks against live app objects and prints
`PASSED N of M`. If something is broken, it says what.
**"Show log"** / **"Copy log"** give a detailed journal of the last run.

### Data

Files live in the app's home directory:

```
~/arashimind_favorites_index.json   # fast re-scan index
~/arashimind_favorites_log.txt      # journal (ring buffer)
```

**Nothing leaves the device.** The plugin has no network code.

### Limitations

- Only **your own** messages are deleted (`forAll=False`). Others are untouched.
- You need delete rights in the chat.
- On `FLOOD_WAIT` the plugin waits and continues instead of erroring out.

---

## Установка / Install

1. Скачать `.plugin` из [Releases](../../releases).
   Download the `.plugin` from [Releases](../../releases).
2. Настройки exteraGram → Плагины → Установить из файла.
   exteraGram Settings → Plugins → Install from file.
3. Прогнать **САМОТЕСТ** перед первым использованием.
   Run the **SELF-TEST** before first use.

## Лицензия / License

MIT — используйте как угодно, без гарантий.
MIT — use it however you want, with no warranty.

## Баги / Bugs

Нашли баг — пишите [@leamanfo](https://t.me/leamanfo).
Found a bug — ping [@leamanfo](https://t.me/leamanfo).
