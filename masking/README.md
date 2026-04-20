# Dynamic Data Masking

Docs: https://www.bytebase.com/docs/security/data-masking/overview/

Tutorials: [Data Masking with GitHub Actions](https://www.bytebase.com/docs/tutorials/github-action-data-masking-part1/)

## Workspace-level policies and settings

### Semantic type

Docs: https://www.bytebase.com/docs/security/data-masking/semantic-types/

API: https://api.bytebase.com/#tag/settingservice/PATCH/v1/settings/{setting}

```bash
curl --request PATCH ${bytebase_url}/v1/settings/SEMANTIC_TYPES \
  --header 'Authorization: Bearer '${bytebase_token} \
  --data @semantic-type.json
```

### Global masking rule

Docs: https://www.bytebase.com/docs/security/data-masking/global-masking-rule/

API: https://api.bytebase.com/#tag/orgpolicyservice/PATCH/v1/policies/{policy}

```bash
curl --request PATCH "${bytebase_url}/v1/workspaces/-/policies/masking_rule?allowMissing=true&updateMask=payload" \
  --header 'Authorization: Bearer '${bytebase_token} \
  --data @global-masking-rule.json
```

### Data classification

Docs: https://www.bytebase.com/docs/security/data-masking/data-classification/

API: https://api.bytebase.com/#tag/settingservice/PATCH/v1/settings/{setting}

```bash
curl --request PATCH ${bytebase_url}/v1/settings/DATA_CLASSIFICATION \
  --header 'Authorization: Bearer '${bytebase_token} \
  --data @data-classification.json
```

## Project-level masking exemption

Project-level masking exemption to overrule the workspace-level setting.

https://github.com/bytebase/database-security-github-actions-example/tree/main/masking/projects/project-sample

## Schema configuration

Configure metadata such as masking level, classification, semantic type at the table/column level.

https://github.com/bytebase/database-security-github-actions-example/tree/main/masking/databases
