# design-kit

UI-кит и дизайн-система на React + Vite для продукта bembox. Набор переиспользуемых
компонентов, лейаутов и утилит стилизации, собранных из рабочего WMS-интерфейса.

## Стек

- React 18, Vite 6 (SPA)
- Tailwind CSS 3 + PostCSS, CSS-переменные для тем
- lucide-react — иконки
- jsbarcode — генерация штрих-кодов (CODE128)
- Шрифт Inter

## Состав

- `ui-components/` — компоненты: Button, Badge, Input, Select, SearchSelect, Modal,
  Toast, Spinner, CopyBadge, SortTh, Barcode, FeedbackButton, WarehouseIcons.
- `context/` — React-контексты: ThemeContext (5 цветовых тем + тёмный режим),
  AuthContext (вход по JWT), AppSettingsContext (настройки приложения).
- `AdminLayout.jsx`, `EmployeeLayout.jsx` — готовые лейауты (сайдбар / хедер + bottom nav).
- `index.css` — глобальные стили, CSS-переменные тем, анимации.
- `tailwind.config.js`, `postcss.config.js`, `vite.config.js` — конфигурация сборки.
- `cn.js`, `fmt.js` — утилиты (classnames и форматирование чисел/дат).

## Запуск

```bash
npm install
npm run dev      # dev-сервер Vite на порту 5174
npm run build    # production-сборка
npm run preview  # предпросмотр сборки
```

## Использование

Темы переключаются через атрибут на `<html>`: `data-theme="purple|blue|green|orange|rose"`.
Компоненты импортируются из `ui-components/`, например `<Button variant="danger">Удалить</Button>`,
`<Modal open={...} onClose={...} title="...">`, хук `useToast()` для уведомлений.
Адрес API-прокси задаётся переменной окружения `VITE_API_PROXY_TARGET`.
