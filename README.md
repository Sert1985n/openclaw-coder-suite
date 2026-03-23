# CasaOS App Store repo: OpenClaw Coder Suite v2

Готовый репозиторий для `Custom App Store` в CasaOS.

## Что внутри

- `Apps/openclaw-coder-suite/` — готовое приложение CasaOS
- `docker-compose.yml` — стек `openclaw + ollama + caddy`
- `rootfs/openclaw/openclaw.json` — базовый конфиг OpenClaw
- `rootfs/openclaw/agents/*` — русские агенты для кодинга, ревью, DevOps, GitHub и поиска
- `rootfs/openclaw/skills/*` — шаблоны навыков
- `rootfs/caddy/Caddyfile` — reverse proxy

## После установки

1. Открой приложение через порт `24443`.
2. В настройках приложения CasaOS при необходимости добавь env:
   - `BRAVE_API_KEY` — для web search
   - `GITHUB_SSH_PRIVATE_KEY` — приватный SSH-ключ GitHub
   - `GITHUB_KNOWN_HOSTS` — known_hosts для GitHub
   - `GITHUB_SSH_PASSPHRASE` — passphrase, если она есть

## Важно

- Первый запуск долгий: Ollama скачивает `qwen2.5-coder:32b` и `qwen2.5:32b`.
- В этой версии image OpenClaw переключён на тег `main`, чтобы не упираться в неразрешённый version tag. Для стабильного App Store потом лучше закрепить конкретный рабочий version tag.
- Вставить приватный ключ «прямо в чат» безопасно и корректно нельзя. Но здесь уже не требуется раскладывать файлы руками по папкам: ключи можно передать через env в настройках приложения CasaOS.
