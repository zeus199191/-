# Жим Контроль — Android (WebView)

Готовый Android-проект приложения «Жим Контроль»: твоя программа тренировок,
учёт повторов, таймер отдыха с уведомлениями и прогрессия нагрузки.
Всё приложение (HTML/JS) лежит в `app/src/main/assets/index.html` и работает
офлайн — данные хранятся на телефоне.

## Как получить APK — 3 способа

### Способ A. GitHub Actions (без установки чего-либо, ~5 минут)
1. Создай новый репозиторий на github.com.
2. Загрузи туда все файлы из этой папки (кнопка "Add file → Upload files", можно перетащить).
3. Открой вкладку **Actions** → workflow **Build APK** запустится сам (или нажми "Run workflow").
4. Когда сборка позеленеет, зайди в неё → раздел **Artifacts** → скачай `ZhimKontrol-apk`.
5. Внутри — `app-debug.apk`. Перекинь на телефон и установи (разреши "установку из неизвестных источников").

### Способ B. Android Studio (если установлена)
1. File → Open → выбери эту папку.
2. Дождись синхронизации Gradle.
3. Build → Build Bundle(s)/APK(s) → Build APK(s).
4. APK будет в `app/build/outputs/apk/debug/`.

### Способ C. Командная строка (нужны JDK 17 + Android SDK)
```
gradle wrapper --gradle-version 8.9
./gradlew assembleDebug
```
APK: `app/build/outputs/apk/debug/app-debug.apk`

## Обновить содержимое приложения
Просто замени `app/src/main/assets/index.html` на новую версию и пересобери.

## Публикация в Google Play
Нужен аккаунт разработчика ($25 разово) и релизная подпись (release keystore).
Debug-APK из способов выше ставится напрямую, но для Play нужен подписанный release —
подскажу, когда дойдёшь до этого.
