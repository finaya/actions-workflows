# Github Actions Reusable Workflows

The idea of this repository is to host reusable github actions workflows

![img](./assets/github_actions_workflows_reusable.jpeg)


## Input `runs-on`

Todo reusable workflow (`on: workflow_call`) aceita o input opcional `runs-on`, com o JSON do runner. O default é `"ubuntu-latest"`, então quem já chama o workflow **não precisa mudar nada**.

```yaml
jobs:
  sonar:
    uses: finaya/actions-workflows/.github/workflows/sonar-front.yml@main
    with:
      # string simples (JSON de string) ou array de labels (JSON)
      runs-on: '["self-hosted","linux","arm64","finaya-shared"]'
```

O valor é lido com `fromJSON(inputs.runs-on)`: passe `'"ubuntu-latest"'` (com aspas internas) para uma label única, ou um array JSON para várias labels.
