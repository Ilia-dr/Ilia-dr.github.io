# Technical OAuth site — Ilia-dr.github.io

## Назначение
Это **единственная общая публичная площадка** для технических страниц **собственных** OAuth-приложений владельца (начальный проект — Apps Script Fleet). Не создавайте новый GitHub Pages репозиторий или второй сайт для очередной личной интеграции, пока не проверены возможности повторного использования этой площадки. Не переносите сюда клиентские данные, приватные исходники или токены.

- Публичные страницы: `index.html`, `privacy.html`, `terms.html`, `styles.css`.
- Адрес после включения GitHub Pages: `https://ilia-dr.github.io/`.
- Новым личным приложениям добавлять отдельный подраздел/политику только при изменении фактических OAuth scopes, владельца данных и способа их обработки. Наличие сайта не даёт автоматически Google OAuth client credentials или разрешения от других приложений.
- Секреты и защищённое исполнение остаются в **приватных** репозиториях/секрет-хранилищах — эта площадка их не хранит.
- Не применять этот публичный сайт для **клиентских** OAuth consent screens без отдельного разрешения и юридической проверки.

## Включение публикации
GitHub repository `Settings → Pages → Deploy from a branch → main → /(root) → Save`. Проверить публичный `GET /`, `/privacy.html`, `/terms.html` в гостевом браузере.

## Google OAuth: непроверенный этап
`github.io` — общий домен GitHub. Google требует проверяемое владение доменом; Search Console URL-prefix и успешный хостинг **не гарантируют** принятие адреса на странице Google Auth Branding/Authorized domains. Есть документированные отклонения приложений, использующих `github.io`. Перед привязкой проверить точный ответ Google; если платформа не принимается, использовать **один** подконтрольный домен (можно направить его на этот же GitHub Pages репозиторий), а не плодить новые сайты.

Статус на 10.11.2026: файлы подготовлены; GitHub Pages publication, Google Search Console verification, Google OAuth `In production`, token rotation и end-to-end тест **ещё не подтверждены**.

Официальные источники:
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://developers.google.com/identity/protocols/oauth2/production-readiness/policy-compliance
- https://support.google.com/webmasters/answer/9008080
