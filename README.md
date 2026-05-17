# Цифрове портфоліо вчителя математики

Сайт побудовано на основі шаблону [Astrofy](https://github.com/manuelernestog/astrofy)
та адаптовано як цифрове портфоліо вчителя математики в межах університетського
практикуму.

## Стек

- [Astro](https://astro.build/) (статичний генератор сайтів)
- [TailwindCSS](https://tailwindcss.com/) + [DaisyUI](https://daisyui.com/) (стилі та компоненти)
- Власна світла тема DaisyUI `portfolio` (сині та графітові акценти)
- Конфігурація та нова логіка — на чистому JavaScript (без TypeScript)

## Структура сайту

- `/` — **Головна**: візитка вчителя, педагогічне кредо, професійні інтереси, контакти.
- `/module-1` — **Модуль 1. Цифрова дидактика**: сертифікати, есе, хмаринка слів, рефлексія.
- `/module-2` — **Модуль 2. Візуалізація та динамічне моделювання**: заготовка для GeoGebra,
  графіків функцій, динамічної геометрії та інтерактивних моделей.
- `/module-3` — **Модуль 3. ШІ в освіті**: заготовка для матеріалів про використання
  штучного інтелекту в навчанні математики.

## Локальний запуск

```bash
pnpm install
pnpm run dev
```

Сайт буде доступний на `http://localhost:4321`.

## Збірка

```bash
pnpm run build
pnpm run preview
```

Сгенерований сайт з'явиться в каталозі `dist/` — готовий до деплою на
[Vercel](https://vercel.com/) або [Netlify](https://www.netlify.com/)
(не потрібно ані бекенду, ані бази даних).

## Структура проєкту

```
public/
  favicon.svg
  images/             # profile-placeholder.jpg, word-cloud-placeholder.png
  certificates/       # safe-space.pdf, academic-integrity.pdf, digigram.pdf
src/
  components/
    BaseHead.astro
    Card.astro
    CertificateCard.astro
    Footer.astro
    Header.astro
    HorizontalCard.astro
    SideBar.astro
    SideBarMenu.astro
  layouts/
    BaseLayout.astro
  pages/
    index.astro
    module-1.astro
    module-2.astro
    module-3.astro
  styles/
    global.css
  config.js           # SITE-конфіг і пункти меню (plain JS)
astro.config.mjs
tailwind.config.cjs
package.json
```

## Налаштування

- Назву сайту, опис та пункти меню змініть у файлі [`src/config.js`](src/config.js).
- Кольори світлої теми — у [`tailwind.config.cjs`](tailwind.config.cjs)
  (секція `daisyui.themes.portfolio`).
- Контент сторінок редагується безпосередньо в `src/pages/*.astro`
  (масиви `interests`, `certificates`, `items` тощо у frontmatter — звичайний JavaScript).

## Заглушки

- Файли в `public/certificates/` — мінімальні PDF-заглушки; замініть їх на справжні
  сертифікати з тими ж іменами.
- Зображення `profile-placeholder.jpg` та `word-cloud-placeholder.png` поки відсутні —
  розмітка коректно показує текстову заглушку завдяки атрибуту `onerror`.
  Просто покладіть реальні файли в `public/images/` із тими ж іменами.

## Деплой

### Vercel
1. Імпортуйте репозиторій у Vercel.
2. Framework preset: **Astro** (визначиться автоматично).
3. Build command: `pnpm run build`, output: `dist/`.

### Netlify
1. New site → Import from Git.
2. Build command: `pnpm run build`, publish directory: `dist`.

---

Створено з ❤️ для практичного завдання з цифрової педагогіки.

