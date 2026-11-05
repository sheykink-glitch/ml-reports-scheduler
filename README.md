# Public scheduler for private ml-reports

GitHub Free often does **not** fire `on.schedule` inside **private** repositories.
This **public** repo runs the cron and calls `workflow_dispatch` on `sheykink-glitch/ml-reports`.

## Secret

Set Actions secret `DISPATCH_TOKEN` to a classic PAT / fine-grained token with access to private repo `ml-reports` (`actions: write` / `workflow`).

## Inactivity

GitHub disables `on.schedule` in a public repository after 60 days without a commit (`disabled_inactivity`). Workflow `keepalive.yml` commits every Monday so the Tuesday trigger stays enabled.
