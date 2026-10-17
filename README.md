# Terraform Infrastructure

Look up Terraform providers and modules and work with infrastructure workspaces; requires Docker, with account access for hosted workspaces.

Install the release archive through OpenAgent Integrations → Plugins. This is an independent adaptation.

## Plugin settings

Requires a Runtime with the configuration-v1 feature. Open Integrations → Plugins → this plugin to save parameters and credentials. Password fields show only whether a token exists; leave blank to keep it, or explicitly clear and save. OAuth HTTP connectors offer Test, Authorize and local Disconnect here. These operations preserve package data and existing credential files. Running daemons need a restart after changing settings. Actual account operations still require provider-specific acceptance.

## Setup

- Docker and optional Terraform Enterprise token saved in plugin settings.

Run /terraform:setup. Package state belongs in plugin-data/terraform/; private settings and credentials are stored by the Runtime in plugin-settings/terraform.json. Never place secrets in plugin.json or commit them. Refresh the plugin after changing credentials.

## Verification

bun test tests

Bundled tests cover immutable artifacts, config conversion and service configuration and missing prerequisites. Runtime acceptance also verifies a real staged installation, slash-command catalog and integration_status. External account authentication, real provider operations and macOS permissions require the prerequisites above; package tests do not claim those credentials are available.

## 中文

查询 Terraform 提供商和模块，并操作基础设施工作区；需要 Docker，托管工作区还需账号权限。 安装发布包后运行 /terraform:setup 查看配置要求。凭据和状态保存在当前 OpenAgent 数据目录的 plugin-data/terraform/ 下，修改后刷新插件。

Upstream source and exact revision are recorded in provenance.json. Bundled source remains available for inspection.
