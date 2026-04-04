# SwapMe — Website Build Prompt

## Общее описание проекта

SwapMe — это OTC криптообменник в Праге. Основные операции: обмен USDT на наличные EUR/USD/CZK и обратно. Нужен полноценный сайт-обменник с калькулятором курсов, мультиязычностью (RU/EN) и конверсией клиентов через Telegram-бота.

---

## Бренд-ассеты

В папке проекта находятся следующие файлы:
- `logo_full.png` — полный логотип SwapMe (белый текст "swap" + оранжевый "me", иконка из двух стрелок-треугольников: белая вправо-вверх, оранжевая влево-вниз)
- `logo_icon.png` — иконка без текста (две стрелки)
- `mascot.jpeg` — маскот — дружелюбный 3D лисёнок в белой футболке с логотипом SwapMe, держит монету Bitcoin, рядом монеты Tether (₮) и Euro (€). Тёмный фон с геометрическим паттерном

### Цветовая палитра
| Элемент | Цвет |
|---|---|
| Фон | `#1A1A1A` (тёмно-серый, почти чёрный) |
| Акцент | `#FF6600` (яркий оранжевый) |
| Текст основной | `#FFFFFF` |
| Текст вторичный | `#A0A0A0` |
| Поверхности/карточки | `#222222` или `#2A2A2A` |
| Успех/позитив | `#00C853` (зелёный) |
| Ошибка | `#FF3D00` |

### Шрифты
- Логотип использует геометрический sans-serif, lowercase
- Для сайта: основной — **DM Sans** или **Satoshi**, заголовки — **Cabinet Grotesk** или **General Sans**
- Не использовать: Inter, Roboto, Arial

---

## Структура сайта

### 1. Hero-секция
- Полноэкранный тёмный фон с subtle геометрическим паттерном (как на маскоте)
- Логотип SwapMe крупно в центре или слева
- Заголовок:
  - RU: "Обмен криптовалют в Праге • Быстро • Безопасно • Наличные"
  - EN: "Crypto Exchange in Prague • Fast • Secure • Cash"
- Подзаголовок:
  - RU: "USDT, Bitcoin, Ethereum → EUR, USD, CZK. Личная встреча или курьер."
  - EN: "USDT, Bitcoin, Ethereum → EUR, USD, CZK. In-person or courier."
- CTA кнопка → Telegram (@swapme_bot или ссылка)
- Маскот-лисёнок справа (на десктопе)
- Переключатель языка RU/EN в хедере

### 2. Калькулятор обмена (ключевая секция)
- Интерактивный калькулятор в стиле карточки с glassmorphism эффектом
- **Отдаёте**: выпадающий список валют + поле суммы
  - Крипто: USDT (TRC20), USDT (ERC20), BTC, ETH, TON
  - Фиат: EUR, USD, CZK
- **Получаете**: автоматический расчёт по курсу + выпадающий список
- Курсы: захардкодить начальные значения, можно добавить API потом
- Кнопка "Обменять" → открывает Telegram
- Показывать комиссию и финальную сумму
- Иконки валют рядом с названиями

### 3. Как это работает (Steps)
3 шага с иконками/анимациями:
1. **Оставьте заявку** — напишите нам в Telegram бот, укажите сумму и направление обмена
2. **Получите курс** — мы зафиксируем лучший курс на 15 минут
3. **Обмен** — встреча в центре Праги или курьерская доставка

### 4. Почему SwapMe
Карточки с преимуществами (4-6 штук):
- 🔒 Безопасность — Все сделки лично, без третьих сторон
- ⚡ Скорость — Обмен за 30 минут
- 💰 Лучший курс — Конкурентный курс без скрытых комиссий
- 🏙️ Прага — Работаем в центре города, удобные точки встреч
- 📱 24/7 — Telegram-бот работает круглосуточно
- 🦊 Доверие — 500+ довольных клиентов

### 5. Поддерживаемые валюты
Визуальная сетка/карусель с иконками монет:
- USDT (Tether) — TRC20, ERC20
- BTC (Bitcoin)
- ETH (Ethereum)
- TON (Toncoin)
- EUR, USD, CZK (фиат)
- Анимация при hover, glow-эффект на иконках

### 6. FAQ (Аккордеон)
- Минимальная сумма обмена?
- Какие документы нужны?
- Как происходит встреча?
- Какие гарантии?
- Работаете ли вы с юридическими лицами?
- Время работы?

### 7. Контакты / CTA
- Большая CTA секция с маскотом
- Telegram кнопка (основная)
- WhatsApp (опционально)
- Email
- Локация: "Praha, Czech Republic" (без точного адреса)
- Рабочие часы

### 8. Footer
- Логотип SwapMe
- Навигация
- Дисклеймер: "SwapMe is not a licensed financial institution. Services provided under Czech Republic legislation."
- © 2024-2026 SwapMe

---

## Технические требования

### Stack
- **React** (single-page, JSX артифакт для claude.ai)
- **Tailwind CSS** для стилизации
- CSS переменные для цветовой схемы
- Никаких внешних API на первом этапе — курсы захардкодить

### Дизайн-стиль: "Космический обменник нового века"

Общий вайб: **Calm Futurism + Chromatic Mash-Up** — сайт должен ощущаться как интерфейс из будущего. Не generic crypto template, а что-то на уровне awwwards.com. Каждый элемент должен "жить" и реагировать.

#### Ключевые визуальные приёмы (Web Design Trends 2026):

**1. Glassmorphism 2.0 (Основа UI)**
- Все карточки и панели — полупрозрачные с backdrop-filter: blur(20px)
- Тонкая светящаяся граница (border: 1px solid rgba(255,102,0,0.15))
- Многослойная глубина — карточки перекрывают друг друга с разной прозрачностью
- Калькулятор — главный showcase этого эффекта

**2. Floating Elements + Parallax (Космический эффект)**
- Фоновые элементы "плавают" с разной скоростью при скролле
- Иконки криптовалют медленно вращаются и парят в hero-секции
- Светящиеся орбы/сферы на фоне (оранжевый и белый, размытые, большие)
- Частицы (маленькие точки-звёзды) дрейфуют по фону
- CSS: transform: translateY() привязанный к scroll position

**3. Glow & Neon Effects (Оранжевый как неон)**
- Кнопки CTA: пульсирующий оранжевый glow (box-shadow: 0 0 30px rgba(255,102,0,0.4))
- Текст заголовков: subtle text-shadow с оранжевым свечением
- Hover на карточках: граница начинает светиться ярче
- Иконки валют: цветной glow соответствующий цвету монеты (BTC=золотой, ETH=синий, USDT=зелёный)

**4. Kinetic Typography (Живой текст)**
- Заголовок hero: слова появляются по одному с fade+slide анимацией
- Числа статистики: animated counter от 0 до значения при скролле в viewport
- Hover на навигации: буквы слегка "расходятся" (letter-spacing transition)
- Gradient text на ключевых словах (оранжевый → белый)

**5. Scroll-Triggered Animations (Каждая секция оживает)**
- Intersection Observer API для запуска анимаций при скролле
- Элементы "выезжают" снизу/сбоку с blur→clear эффектом
- Staggered reveal: карточки появляются одна за другой с задержкой 100ms
- Прогресс-бар скролла в хедере (тонкая оранжевая линия)

**6. Cursor Effects (Интерактивная магия)**
- Кастомный курсор: маленький оранжевый круг который увеличивается при hover на интерактивных элементах
- Gradient spotlight: легкое оранжевое свечение следует за курсором на hero-секции
- Magnetic buttons: кнопки слегка "притягиваются" к курсору при приближении

**7. Bento Grid Layout (Секция преимуществ)**
- Карточки разного размера в стиле Apple/bento
- Некоторые карточки больше (2x), создавая ритм
- Каждая карточка с уникальной анимацией внутри
- Общая сетка реагирует на resize

**8. Micro-interactions повсюду**
- Кнопка "Обменять": ripple effect при клике
- Переключатель валют: smooth slide с physics-based easing
- FAQ аккордеон: плавное раскрытие с bounce эффектом
- Переключатель языка: flip animation
- Иконки соцсетей: scale + rotate при hover

**9. Фоновые эффекты (Космос)**
- Основной фон: радиальный градиент от центра (#1A1A1A → #0D0D0D)
- Наложение: SVG паттерн из треугольников (как на маскоте) с opacity 0.03-0.05
- 2-3 размытых оранжевых/фиолетовых "туманности" (CSS radial-gradient) позиционированных абсолютно
- Noise texture overlay (SVG filter или CSS) для тактильности
- Линии grid: тонкие линии perspective grid уходящие в "горизонт" — как пол космической станции

**10. Animated Gradient Borders**
- Ключевые элементы (калькулятор, CTA) обрамлены анимированным градиентом
- Градиент медленно вращается по периметру (conic-gradient + animation)
- Создаёт эффект "живой" границы, как будто энергия течёт по контуру

#### Референсы стиля:
- Uniswap.org — чистый crypto UI
- Linear.app — glassmorphism и анимации
- Stripe.com — depth и scroll animations
- Apple.com — bento grid, reveal effects
- Cosmos Network — космический crypto вайб

#### Чего НЕ делать:
- Не использовать generic фиолетовый градиент на белом — это AI-slop
- Не перегружать анимациями до потери производительности
- Не делать "темплейтный" crypto сайт с stock графикой
- Маскот используется точечно (hero + CTA), не превращать в детский сайт

### Мультиязычность
- Объект `translations` с ключами `ru` и `en`
- Переключатель в хедере (флажки или текст RU/EN)
- Все тексты через `t('key')` функцию
- По умолчанию: RU

### Адаптивность
- Mobile-first дизайн
- Калькулятор должен быть удобен на телефоне
- Маскот скрывается или уменьшается на мобильных
- Hamburger-меню на мобильных

### Интерактив
- Калькулятор: реальный расчёт при вводе суммы
- Smooth scroll навигация
- Анимированные числа (counter) в секции статистики
- Аккордеон в FAQ
- Hover-эффекты на карточках

---

## Контент для перевода

### Статистика (для социального доказательства)
- "500+ обменов" / "500+ exchanges completed"
- "€2M+ оборот" / "€2M+ volume traded"
- "4.9★ рейтинг" / "4.9★ rating"
- "15 мин среднее время" / "15 min average time"

### Telegram
- Bot: `@swapme_bot` (или placeholder)
- Channel: `@swapme_channel`
- Ссылка: `https://t.me/swapme_bot`

---

## Примечания для агента

1. Это single-page React приложение в одном JSX файле
2. Используй загруженные изображения как `<img>` через URL или base64 если нужно
3. Все тексты bilingual — RU/EN через translation object
4. Калькулятор — центральный элемент, он должен быть функциональным и красивым
5. Не используй localStorage (не поддерживается в claude.ai артифактах)
6. Стиль: premium dark crypto — но не generic "AI slop". Уникальный, запоминающийся
7. Маскот-лисёнок — ключевой элемент бренда, используй его в hero и CTA секциях
8. Оранжевый (#FF6600) — акцентный цвет, не перебарщивать, использовать точечно
9. Кнопки "Обменять" всегда ведут в Telegram
10. Добавь subtle анимации: glow, fade-in, scale on hover

---

## Быстрый старт

```
Создай полноценный React-артифакт для сайта SwapMe — OTC криптообменника в Праге.
Используй бренд-ассеты, цвета и структуру из этого документа.
Начни с frontend-design скилла, затем создай JSX файл.

КРИТИЧЕСКИ ВАЖНО — дизайн уровня awwwards.com:
- Dark theme с космическим вайбом: floating orbs, particle background, perspective grid
- Glassmorphism 2.0 на всех карточках с animated gradient borders
- Kinetic typography: слова hero появляются по одному, gradient text
- Scroll-triggered animations: каждая секция оживает при скролле (Intersection Observer)
- Cursor spotlight: оранжевое свечение следует за мышкой в hero
- Glow effects: пульсирующий неон на CTA кнопках, цветной glow на иконках валют
- Bento grid для карточек преимуществ
- Staggered reveal: элементы появляются каскадом
- Animated counters в статистике
- Noise texture overlay для тактильности
- RU/EN переключатель, все CTA → Telegram
- Маскот-лисёнок в hero и CTA секциях

Сайт должен выглядеть как интерфейс космической станции,
а не как типичный crypto template. Каждый пиксель — осознанное решение.
```

## CSS-сниппеты для агента

### Animated gradient border
```css
.gradient-border {
  position: relative;
  border-radius: 16px;
  padding: 1px;
  background: conic-gradient(from var(--angle), #FF6600, #FF660020, #FF6600);
  animation: rotate-gradient 4s linear infinite;
}
@keyframes rotate-gradient {
  to { --angle: 360deg; }
}
@property --angle {
  syntax: '<angle>';
  initial-value: 0deg;
  inherits: false;
}
```

### Floating orbs background
```css
.orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  animation: float 20s ease-in-out infinite;
}
.orb-orange { background: rgba(255,102,0,0.15); width: 400px; height: 400px; }
.orb-white { background: rgba(255,255,255,0.05); width: 300px; height: 300px; }
@keyframes float {
  0%, 100% { transform: translate(0, 0) scale(1); }
  33% { transform: translate(30px, -50px) scale(1.1); }
  66% { transform: translate(-20px, 20px) scale(0.9); }
}
```

### Noise texture overlay
```css
.noise::before {
  content: '';
  position: absolute;
  inset: 0;
  background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.04'/%3E%3C/svg%3E");
  pointer-events: none;
  z-index: 1;
}
```

### Cursor spotlight (React)
```jsx
const [mousePos, setMousePos] = useState({ x: 0, y: 0 });
// onMouseMove → setMousePos({ x: e.clientX, y: e.clientY })
// <div style={{ background: `radial-gradient(600px at ${mousePos.x}px ${mousePos.y}px, rgba(255,102,0,0.06), transparent 80%)` }} />
```
