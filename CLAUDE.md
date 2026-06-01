# Правила работы с Figma Design System

## Контекст
Ты работаешь с дизайн-системой в Figma. Твоя задача — создавать макеты,
используя ТОЛЬКО существующие компоненты и переменные из библиотек ниже.

---

## Библиотеки (file keys)

| Файл | Key |
|------|-----|
| Components | `p5Iua0EDfajBZuLzxjGChA` |
| Foundations (переменные) | `qF8eUWRGaTaLI0JizOIrnY` |
| Icons [Brand 1] | `d1fAKLn87enQBs3b1bfGli` |
| Icons [Brand 2] | `xNc2XSD1whPeel2UMradxL` |
| Graphic assets [Brand 1] | `of3SZHmr6i9kYhCzPHFl13` |
| Graphic assets [Brand 2] | `QjJURGS7jjYQczaYdzOkmF` |
| Guides | `kGuh2fit1kd0fAxxYVsnDv` |

---

## Переменные — иерархия использования

### Цвета
Всегда используй переменные из коллекции **Theme** (файл Foundations).
- Моды: `Light` / `Dark`
- Путь: `Brand 1/Default/...` или `Brand 1/Premium/...`
- Примеры: `Theme/Brand 1/Default/key/primary`, `Theme/Brand 1/Default/surface/low`

Для брендовых акцентов — коллекция **Brand**:
- Моды: `Brand 1` / `Brand 2` / `Brand 3`
- Примеры: `Brand/Color/key/primary`, `Brand/Color/surface/container`

Для семантических состояний — коллекция **Mode**:
- Моды: `Default` / `Premium`
- Примеры: `Mode/Brand 1/key/primary`, `Mode/Brand 1/surface/...`

> **ЗАПРЕЩЕНО** использовать коллекцию `Color primitives` напрямую — она скрыта
> и является только источником для вышестоящих токенов.

### Типографика
Используй переменные из коллекции **Adaptive** (файл Foundations):
- Моды: `Desktop` / `Tablet` / `Mobile`
- Примеры: `Adaptive/Brand 1/Heading 01/size`, `Adaptive/Brand 1/Heading 01/line-height`

### Отступы и размеры
Используй переменные из коллекции **Dimension primitives** (файл Foundations):
- Мод: `Value`
- Примеры: `Dimension primitives/Brand 1/x0`, `Brand 1/x`, `Brand 1/x2`, `Brand 1/x4`

---

## Компоненты — доступные группы

Все компоненты берутся из файла **Components** (`p5Iua0EDfajBZuLzxjGChA`).

| Группа | Описание |
|--------|----------|
| Atoms | Базовые элементы |
| Button | Кнопки всех видов |
| Icon button | Иконочные кнопки |
| Input | Текстовые поля |
| Select | Выпадающие списки |
| Search input | Поиск |
| Autocomplete | Автодополнение |
| Toggle | Переключатели |
| Checkbox Item / group | Чекбоксы |
| Radiubutton Item / group | Радиокнопки |
| Tag | Теги |
| Chips / Chips group | Чипы |
| Tab | Табы |
| Accordion / Accordion group | Аккордеон |
| List item / List item group | Элементы списка |
| Avatar | Аватары |
| Notification | Уведомления |
| Modal | Модальные окна |
| Tooltip | Тултипы |
| Dropdown menu | Дропдаун меню |
| Navigation bar | Навигационная панель |
| Section header | Заголовки секций |
| Pagination numeric / dots | Пагинация |
| Progress bar | Прогресс-бар |
| Button group | Группы кнопок |
| Label | Лейблы |
| Status bar | Статус-бар |
| Home Indicator & Home bar | Системные элементы iOS |
| Keyboard | Клавиатура |
| Store badge | Бейджи магазинов |

---

## Обязательные правила

### ЗАПРЕЩЕНО:
- Создавать новые компоненты (COMPONENT или COMPONENT_SET)
- Изменять существующие компоненты в библиотеке
- Использовать хардкодные цвета (hex, rgb, hsl) — только через `boundVariables`
- Использовать хардкодные отступы и размеры — только через `boundVariables`
- Создавать локальные стили (local styles)
- Создавать локальные переменные
- Использовать шрифты вне дизайн-системы

### ОБЯЗАТЕЛЬНО:
- Все цвета привязывать через `boundVariables` к коллекции **Theme** или **Brand**
- Все отступы/размеры привязывать через `boundVariables` к **Dimension primitives**
- Типографику привязывать через `boundVariables` к **Adaptive**
- Компоненты размещать только как `instance` (instanceOf существующего компонента)
- Перед размещением элемента — проверить наличие подходящего компонента в библиотеке
- Если подходящего компонента нет — сообщить пользователю, НЕ создавать новый

---

## Workflow — порядок действий

1. Получи задачу от пользователя
2. Определи, какие компоненты из библиотеки подходят
3. **Сообщи список компонентов и переменных, которые планируешь использовать**
4. Дождись подтверждения
5. Выполни задачу, строго используя только утверждённые элементы
6. После выполнения — проверь, что все свойства привязаны через переменные

---

## Если чего-то нет в дизайн-системе

Не создавай самостоятельно. Сообщи пользователю:
> "В дизайн-системе нет подходящего компонента/переменной для [описание].
> Как поступить?"
