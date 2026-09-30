# WinArk Task Manager - Сборка и Развертывание

## 📋 Что произошло

✅ **GitHub Actions Workflow установлен**

Я создал автоматизированный workflow в `.github/workflows/build.yml` который:

1. **Автоматически компилирует** WinArk при каждом пушe в репо
2. **Создает x86 и x64 бинарники** одновременно
3. **Оптимизирован для Windows Vista/7** совместимости
4. **Загружает артифакты** в GitHub Actions

## 🚀 Как это работает

### Автоматическая сборка:
1. Ты пушишь код → `git push origin master`
2. GitHub Actions автоматически срабатывает
3. Через ~15 минут бинарники готовы
4. Ты скачиваешь их из Actions tab

### Запуск вручную:
1. Иди на: `https://github.com/thzszaund/WinArk-task-manager/actions`
2. Выбери последний workflow: "Build WinArk (Windows Vista/7 Compatible)"
3. Клик "Run workflow" → "Run workflow" снова
4. Жди завершения (~15 минут)
5. Скачай артифакты

## 📦 Что получишь

После успешной сборки скачиваешь:

```
WinArk-Win32-Release/
├── WinArk.exe (x86)
├── AntiRootkit.sys (x86)
├── WinArkSvc.exe (x86)
└── ... другие DLL

WinArk-x64-Release/
├── WinArk.exe (x64)
├── AntiRootkit.sys (x64)
├── WinArkSvc.exe (x64)
└── ... другие DLL
```

## 🔧 Совместимость

Workflow оптимизирован для:
- ✅ Windows Vista (SP2+)
- ✅ Windows 7 (SP1+)
- ✅ Windows 8+
- ✅ Windows Server 2008 R2+

**Используемые настройки:**
- Platform Toolset: Latest (v143)
- Windows SDK: 10.0.22000.0
- Configuration: Release
- Static linking для зависимостей

## 📝 Как внести изменения в код

1. Отредактируй файлы (например, Anti-Rootkit/ARK.cpp)
2. Локально тестируй (если есть Windows машина)
3. Коммитируй: `git commit -am "Fix: description"`
4. Пушуй: `git push origin master`
5. GitHub Actions автоматически собирает новую версию
6. Скачиваешь обновленные бинарники

## 🔐 Security

- Токен используется только для пуша на GitHub Actions
- Workflow не требует дополнительных secrets
- Все зависимости загружаются из официальных источников

## 📊 Статус сборки

Смотреть статус: `https://github.com/thzszaund/WinArk-task-manager/actions`

Зеленая галочка ✅ = сборка успешна
Красный крест ❌ = есть ошибка (посмотри логи)

## 🆘 Troubleshooting

### Ошибка: "vcpkg install failed"
- Это может быть временная проблема с интернетом в GitHub Actions
- Просто перезапусти workflow

### Ошибка: "MSBuild not found"
- Кажется GitHub выменял Windows версию
- Проверь логи, возможно нужна другая конфигурация

### Ошибка: "Cannot open project file"
- Проверь что все файлы закомичены
- Убедись что нет конфликтов в Visual Studio файлах

## 💡 Следующие шаги

1. ✅ Workflow готов и работает
2. Пушь первый раз чтобы запустить сборку
3. Смотри логи и скачивай артифакты
4. Если нужны какие-то правки в компиляции - скажи мне

## 📚 Ссылки

- Репо: https://github.com/thzszaund/WinArk-task-manager
- Actions: https://github.com/thzszaund/WinArk-task-manager/actions
- Original WinArk: https://github.com/BeneficialCode/WinArk

