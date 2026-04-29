# ИИ-Навык (AI Skill): Типографика (Design Typography)

Этот документ задает правила работы со шрифтами для премиального внешнего вида.

## 1. Шрифты (Font Families)
*   **Основной шрифт (Primary Font):** Использовать современные гротески. Рекомендуются: `Inter`, `Outfit` или `SF Pro Display`.
*   Настройки в CSS/Tailwind: `font-family: 'Inter', sans-serif;`.

## 2. Иерархия Заголовков (Heading Hierarchy)
Заголовки должны быть контрастными и тяжелыми.
*   **H1 (Главный заголовок):**
    *   Размер (Desktop): `48px` (`text-5xl`).
    *   Размер (Mobile): `36px` (`text-4xl`).
    *   Вес: `font-weight: 800` (Extra Bold) или `700` (Bold).
*   **H2 (Заголовок секции):**
    *   Размер (Desktop): `32px` (`text-3xl`).
    *   Вес: `font-weight: 700` (Bold).
*   **H3 (Заголовок карточки):**
    *   Размер: `24px` (`text-xl` или `text-2xl`).
    *   Вес: `font-weight: 600` (Semi Bold).

## 3. Основной Текст (Body Text)
*   **Читабельность:**
    *   Размер: `16px` или `18px` (`text-base` или `text-lg`).
    *   Межстрочный интервал (Line Height): `1.5` - `1.6` (в Tailwind `leading-relaxed`).
    *   Вес: `font-weight: 400` (Regular) или `500` (Medium).

## 4. Специфичные правила навигации
*   **Навигация (Capsule Navigator):** Всегда использовать **ЗАГЛАВНЫЕ БУКВАМ** (`text-transform: uppercase;` или класс `uppercase`).
*   Вес для навигации: `font-weight: 600` (Semi Bold).
*   Трекинг (Letter Spacing): Слегка увеличенный для заглавных букв (`letter-spacing: 0.05em;` или класс `tracking-wider`).
