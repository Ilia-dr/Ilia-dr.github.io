# Technical OAuth site — Ilia-dr.github.io

## Назначение
Это **единственная общая публичная площадка** для технических страниц **собственных** OAuth-приложений владельца (начальный проект — Apps Script Fleet). Не создавайте новый GitHub Pages репозиторий или второй сайт для очередной личной интеграции, пока не проверены возможности повторного использования этой площадки. Не переносите сюда клиентские данные, приватные исходники или токены.

- Публичные страницы: `index.html`, `privacy.html`, `terms.html`, `styles.css`.
- Действующий адрес Pages: `https://ilia-dr.github.io/` (GitHub deploy PASS; отдельный внешний guest GET не проверен).
- Новым личным приложениям добавлять отдельный подраздел/политику только при изменении фактических OAuth scopes, владельца данных и способа их обработки. Наличие сайта не даёт автоматически Google OAuth client credentials или разрешения от других приложений.
- Секреты и защищённое исполнение остаются в **приватных** репозиториях/секрет-хранилищах — эта площадка их не хранит.
- Не применять этот публичный сайт для **клиентских** OAuth consent screens без отдельного разрешения и юридической проверки.

## Публикация
**GitHub Pages уже включён:** `main/(root)`, HTTPS Enforced, Google OAuth Branding использует публичные адреса этого сайта. Доказательство со стороны GitHub: [Pages Actions #42771061818](https://github.com/Ilia-dr/Ilia-dr.github.io/actions/runs/42771061818) `success`. Отдельная проверка трёх URL внешним гостевым HTTP-клиентом пока не подтверждена; это не блокер восстановления личного OAuth. Не создавать новый сайт без конкретной причины.

## Google OAuth: непроверенный этап
`github.io` — общий домен GitHub. Google требует проверяемое владение доменом; Search Console URL-prefix и успешный хостинг **не гарантируют** принятие адреса на странице Google Auth Branding/Authorized domains. Есть документированные отклонения приложений, использующих `github.io`. Перед привязкой проверить точный ответ Google; если платформа не принимается, использовать **один** подконтрольный домен (можно направить его на этот же GitHub Pages репозиторий), а не плодить новые сайты.

**Актуальный статус на 10.11.2026:** Pages опубликован (GitHub Actions PASS). Владелец подтвердил Google OAuth `External / In production` для существующего `apps-script-fleet-oauth`, новый Client Secret и Refresh Token сохранены **только** в приватных GitHub Actions Secrets Fleet. После ротации три реальных admin read-only OAuth-запроса Google API успешны: [inspect #42794949594](https://github.com/Ilia-dr/apps-script-fleet/actions/runs/42794949594), [Drive inventory #42797219320](https://github.com/Ilia-dr/apps-script-fleet/actions/runs/42797219320), [processes #42797409844](https://github.com/Ilia-dr/apps-script-fleet/actions/runs/42797409844), каждый `completed/success` и `ok=true` в приватном result JSON. Это не означает верификацию branding/scopes Google и не подтверждает работу всех AUTO, `GAS_RUN_*` или срок действия токена. Google Search Console ownership и внешний гостевой HTTP GET здесь всё ещё NOT_VERIFIED. Источник актуального admin OAuth: [приватный Fleet README](https://github.com/Ilia-dr/apps-script-fleet/blob/main/README.md); общие нормы — [GAS-FLEET-REUSE-01](https://docs.google.com/document/d/12u4_WRxhAuW8CtUoIOew8oiN3fLYhH2AV5f4ShIQLqY/edit).

Официальные источники:
- https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- https://developers.google.com/identity/protocols/oauth2/production-readiness/policy-compliance
- https://support.google.com/webmasters/answer/9008080
