# Инструкции по миграции

## Перемещение изображений

Если у вас есть изображения из оригинального проекта, переместите их в соответствующие папки:

### Изображения профиля и проектов
```
Переместите из корня в src/images/:
- resume photo.jpg → src/images/profile.jpg
- ecommerce.jpg → src/images/ecommerce.jpg
- project1.png → src/images/project1.png
- project2.png → src/images/project2.png
- portfolio.jpg → src/images/portfolio.jpg
- blog-site.jpg → src/images/blog-site.jpg
- Data-Visualization-Tools.jpg → src/images/Data-Visualization-Tools.jpg
```

### Иконки PWA
```
Переместите из images/ в assets/icons/:
- icon-192.png → assets/icons/icon-192.png
- icon-512.png → assets/icons/icon-512.png
```

## Настройка под себя

### 1. Персональная информация
Откройте `index.html` и замените:
- "Ваше Имя" на ваше реальное имя
- Контактную информацию (email, телефон, местоположение)
- Описание в секции "Обо мне"

### 2. Проекты
- Замените изображения проектов в `src/images/`
- Обновите описания проектов в HTML
- Измените технологии в тегах `<span class="tech">`

### 3. Навыки
Отредактируйте список навыков в секции `#skills`:
```html
<ul class="skills-list">
  <li>Ваш навык 1</li>
  <li>Ваш навык 2</li>
  <!-- Добавьте свои навыки -->
</ul>
```

### 4. Социальные сети
Обновите ссылки на социальные сети в hero секции:
```html
<div class="social-icons">
  <a href="https://github.com/yourusername" aria-label="GitHub">
    <i class="fab fa-github"></i>
  </a>
  <!-- Добавьте другие сети -->
</div>
```

### 5. PWA настройка
В `manifest.json`:
- Измените `name` и `short_name`
- Обновите `theme_color` если нужно
- Убедитесь, что пути к иконкам правильные

### 6. Package.json
В `package.json`:
- Замените "Ваше Имя" на ваше имя
- Обновите `repository.url` на ваш репозиторий

## Запуск проекта

1. **Простой запуск:**
   ```bash
   # Просто откройте index.html в браузере
   ```

2. **С локальным сервером:**
   ```bash
   # Установите зависимости
   npm install
   
   # Запустите сервер разработки
   npm run dev
   
   # Или используйте простой сервер
   npm start
   ```

## Проверка PWA

1. Откройте сайт в Chrome
2. Откройте DevTools (F12)
3. Перейдите на вкладку "Application"
4. Проверьте:
   - Manifest загружается корректно
   - Service Worker зарегистрирован
   - Кэш работает

## Оптимизация для продакшена

1. **Сожмите изображения:**
   - Используйте WebP формат
   - Оптимизируйте размеры

2. **Минифицируйте CSS и JS:**
   - Используйте инструменты типа UglifyJS, CSSNano

3. **Настройте кэширование:**
   - Обновите `urlsToCache` в service-worker.js

## Структура после миграции

```
portfolio-site/
├── index.html              # ✅ Обновлен
├── manifest.json           # ✅ Обновлен
├── package.json            # ✅ Создан
├── README.md              # ✅ Создан
├── .gitignore             # ✅ Создан
├── src/
│   ├── css/
│   │   ├── main.css       # ✅ Создан
│   │   ├── base.css       # ✅ Создан
│   │   ├── hero.css       # ✅ Создан
│   │   ├── sections.css   # ✅ Создан
│   │   └── components.css # ✅ Создан
│   ├── js/
│   │   ├── main.js        # ✅ Обновлен
│   │   └── service-worker.js # ✅ Обновлен
│   └── images/            # 📁 Переместите изображения сюда
├── assets/
│   ├── fonts/             # 📁 Для шрифтов
│   └── icons/             # 📁 Переместите иконки PWA сюда
└── docs/                  # ✅ Создан
```

## Следующие шаги

1. Переместите изображения в правильные папки
2. Настройте персональную информацию
3. Добавьте свои проекты
4. Настройте социальные сети
5. Протестируйте PWA функциональность
6. Разверните на GitHub Pages или другом хостинге 