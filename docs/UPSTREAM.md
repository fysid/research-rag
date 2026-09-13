# Связь с AnythingLLM

- Fork: [fysid/research-rag](https://github.com/fysid/research-rag).
- Upstream: [Mintplex-Labs/anything-llm](https://github.com/Mintplex-Labs/anything-llm).
- Исходная ветка: `master`.
- Снимок: [`3a85d3e75490f09453de7e8c440b9463f4a82019`](https://github.com/Mintplex-Labs/anything-llm/commit/3a85d3e75490f09453de7e8c440b9463f4a82019), 10 сентября 2026, package version `1.16.1`.
- Подготовка: 13 сентября 2026.

GitHub fork сохраняет историю. Локальная копия может быть shallow/sparse для подготовки метаданных; это не сокращает историю на GitHub. Публичный fork доступен всем; документы, индексы и конфигурация с секретами остаются вне Git.

## Обновления

Начать с чистого checkout. Проверить `git remote -v`: `origin` — этот fork, `upstream` — AnythingLLM. Если upstream отсутствует, добавить один раз:

```bash
git remote add upstream https://github.com/Mintplex-Labs/anything-llm.git
```

Если `git rev-parse --is-shallow-repository` возвращает `true`, загрузить историю через `git fetch --unshallow upstream`. Для sparse checkout выполнить `git sparse-checkout disable`. Затем:

```bash
git fetch origin
git fetch upstream
git switch master
git pull --ff-only origin master
git switch -c codex/upstream-sync-YYYY-MM-DD
git merge --no-commit --no-ff upstream/master
```

Вместо `YYYY-MM-DD` использовать дату. Проверить diff, разрешить конфликты, выполнить проверки, создать commit и PR в `fysid/research-rag:master`. Если новых изменений нет, commit не нужен. Не перезаписывать историю через force push.

Особенно проверить инструкции LLM, fork-документацию, шаблоны, `.gitignore`, новые workflows и условия ограничения публикации/cleanup/sponsors. Кнопка Sync fork не заменяет это ревью.

## Лицензия и upstream PR

Оригинальный [LICENSE](../LICENSE) и copyright сохраняются. Research RAG — самостоятельный fork, не официальный продукт Mintplex Labs.

Для разработки в fork действуют [наши правила](LLM_DEVELOPMENT.md). Для PR обратно в AnythingLLM отдельно выполнять их актуальные [CONTRIBUTING.md](https://github.com/Mintplex-Labs/anything-llm/blob/master/CONTRIBUTING.md). Подготовка fork не означает разрешения отправлять изменения в upstream.
