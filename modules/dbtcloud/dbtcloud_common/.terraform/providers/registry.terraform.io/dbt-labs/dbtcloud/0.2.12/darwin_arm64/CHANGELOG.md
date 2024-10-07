# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.11...HEAD)

## [0.2.11](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.10...v0.2.11)

## Changes

- Update docs and examples for jobs and add the ability to set/unset running CI jobs on Draft PRs

## [0.2.10](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.9...v0.2.10)

## Fix

- [#197](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/197) - Community contribution to handle cases where more than 100 groups are created in dbt Cloud
- [#199](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/199) - Update logic to allow finding users by their email addresses in a cases insensitive way
- [#198](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/198) - Update some internal logic to call endpoints by their unique IDs instead of looping through answers to avoid issues like #199 and paginate through results for endpoints where we can't query the ID directly

## Changes

- [#189](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/189) - Allow users to retrieve project data sources by providing project names instead of project IDs. This will return an error if more than 1 project has the given name and takes care of the pagination required for handling more than 100 projects

## [0.2.9](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.8...v0.2.9)

## Changes

- Add support for extended attributes for environments [(docs)](https://docs.getdbt.com/docs/dbt-cloud-environments#extended-attributes-beta), allowing people to add connection attributes available in dbt-core but not in the dbt Cloud interface
- [#191](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/191) - Allow setting a description for jobs

## [0.2.8](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.7...v0.2.8)

## Fix

- [#190](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/190) - Allow setting deferral for jobs at the environment level rather than at the job level. This is due to changes in CI in dbt Cloud. Add docs about those changes on the dbtcloud_job resource page

## [0.2.7](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.6...v0.2.7)

## Fix

- [#184](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/184) - Fix issue when updating SSO groups for a given RBAC group

## [0.2.6](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.5...v0.2.6)

## Changes

- [#178](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/178) and [#179](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/179): Add support for [dbtcloud_license_map](https://registry.terraform.io/providers/dbt-labs/dbtcloud/latest/docs/resources/license_map), allowing the assignment of SSO groups to different dbt Cloud license types

## [0.2.5](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.4...v0.2.5)

## Fixes

- [#172](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/172): Fix issue when changing the schedule of jobs from a list of hours to an interval in a [dbtcloud_job](https://registry.terraform.io/providers/dbt-labs/dbtcloud/latest/docs/resources/job)
- [#175](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/175): Fix issue when modifying the `environment_id` of an existing [dbtcloud_job](https://registry.terraform.io/providers/dbt-labs/dbtcloud/latest/docs/resources/job)
- [#154](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/154): Allow the creation of [Databricks connections](https://registry.terraform.io/providers/dbt-labs/dbtcloud/latest/docs/resources/connection) using Service Tokens when it was only possible with User Tokens before

## Changes

- Use the `v2/users/<id>` endpoint to get the groups of a user

## [0.2.4](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.3...v0.2.4)

## Fixes

- More update to docs

## Changes

- [#171](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/171) Add the ability to define which [environment](https://registry.terraform.io/providers/dbt-labs/dbtcloud/latest/docs/resources/environment) is the production one (to be used with cross project references in dbt Cloud)
- Add [guide](https://registry.terraform.io/providers/dbt-labs/dbtcloud/latest/docs/guides/2_leveraging_http_provider) on how to use the Hashicorp HTTP provider
- [#174](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/174) Add the ability to assign User groups to dbt Cloud users.

## [0.2.3](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.2...v0.2.3)

## Fixes

- Update CI to avoid Node version warnings
- Fixes to the docs

## Changes

- [164](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/164) Add the ability to define `priority` and `execution_project` for [BigQuery connections](https://registry.terraform.io/providers/dbt-labs/dbtcloud/latest/docs/resources/bigquery_connection)
- [168](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/168) Add the ability to set up [email notifications](https://registry.terraform.io/providers/dbt-labs/dbtcloud/latest/docs/resources/notification) (to internal users and external email addresses) based on jobs results

## [0.2.2](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.1...v0.2.2)

## Fixes

- [#156](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/156) Fix the `dbtcloud_connection` for Databricks when updating the `http_path` or `catalog` + add integration test
- [#157](https://github.com/dbt-labs/terraform-provider-dbtcloud/issues/157) Fix updating an environment with credentials already set + add integration test

## Changes

- Add [guide](https://registry.terraform.io/providers/dbt-labs/dbtcloud/latest/docs/guides/1_getting_started) to get started with the provider
- Add missing import and fix more docs
- Update docs template to allow using Subcategories later

## [0.2.1](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.2.0...v0.2.1)

## Changes

- Resources deleted from dbt Cloud won't crash the provider and we now consider the resource as deleted, removing it from the state. This is the expected behavior of a provider.
- Add examples in the docs to resources that didn't have any so far

## [0.2.0](https://github.com/dbt-labs/terraform-provider-dbtcloud/compare/v0.1.12...v0.2.0)

## Important changes

- The resources and data sources are now available as `dbtcloud_xxx` (following the terraform convention) in addition to `dbt_cloud_xxx` (legacy). The legacy version will be removed from v0.3.0 onwards. Instructions on how to use the new resources are available on [the main page of the Provider](https://registry.terraform.io/providers/dbt-labs/dbtcloud/latest/docs).

## 0.1.12

## Changes

- The provider is now published under the dbt-labs org: https://registry.terraform.io/providers/dbt-labs/dbtcloud/latest
