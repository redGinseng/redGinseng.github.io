---
title: Grafana Enterprise
category: Grafana
order: 2
permalink: /Grafana/introduction/grafana_enterprise/
description: 그라파나 엔터프라이즈 소개
image: ./../../images/grafana/
lastmod: 2022-11-05T20:20:00+09:00
comments: true
originalRefName: Grafana
originalRefLink: https://grafana.com/docs/grafana/latest/introduction/
parent: Introduction to Grafana
isParent: true
parentUrl: /Grafana/introduction/
priority: 0.7
---

### 목차

- [Grafana Enterprise](#Grafana-Enterprise)
  + [Enterprise features in Grafana Cloud](#Explore-metrics-logs-and-traces)
  + [Annotations](#Annotations)
    - [Dashboard variables](#Dashboard-variables)
    - [Configure Grafana](#Configure-Grafana)
    - [Import dashboards and plugins](#Import-dashboards-and-plugins)
    - [Authentication](#Authentication)
    - [Provisioning](#Provisioning)
    - [Permissions](#Permissions)
    - [Enhanced LDAP integration](#Enhanced-LADP-integration)
    - [SAML authentication](#SAML-authentication)
    - [protected roles](#protected-roles)
  + [Enterprise features](#enterprise-features)
  + [Enterprise data sources](#enterprise-data-sources)
  + [Try Grafana Enterprise](#try-grafana-enterprise)

---
# Grafana Enterprise

그라파나 엔터프라이즈는 오픈소스 버전에는 지원되지 않는 부가적인 기능을 포함한 버전입니다.
그라파나 엔터프라이즈에는 오픈소스에서 사랑받는 모든 요소 이외에도, [전용 데이터소스 플러그인]({{ '#enterprise-plugins' }})과 [부가 기능]({{ 'enterprise-features' }})이 추가됩니다. 코어 그라파나 팀으로부터 연중무휴 지원 및 교육을 받을 수도 있습니다.
더 자세한 사항은 [our product page](https://grafana/enterprise)에서 확인해보세요.

## Enterprise features in Grafana Cloud

그라파나 엔터프라이즈 기능 중 다수는 [Grafana Cloud]({{ '/docs/grafana-cloud' }}) Pro 및 Advanced 계정에서도 사용이 가능합니다. 더 자세한 사항은 [the Grafana cloud features table](https://grafana.com/pricing/#featuresTable).에서 확인해보세요.
## Authentication

그라파나 엔터프라이즈는 회원을 인증하는 더 다양하고 강력한 방법을 지원합니다. 
### Team sync

[Team sync]({{'../setup-grafana/configure-security/configure-team-sync/'}}) allows you to set up synchronization between teams in Grafana and teams in your auth provider so that your users automatically end up in the right team.
[Team sync]{{ '../setup-grafana/configure-security/configure-team-sync/' }}를 사용하면, 그라파나에 등록된 팀과 외부 인증시스템에 등록된 팀을 동기화할 수 있습니다. 이를 통해 그라파나 시스템에서도 사용자를 올바른 팀에 소속시킬 수 있습니다.

지원되는 인증 시스템:
- [Auth Proxy]({{ '../setup-grafana/configure-security/configure-authentication/auth-proxy/#team-sync-enterprise-only' >}})
- [Azure AD OAuth]({{ '../setup-grafana/configure-security/configure-authentication/azuread/#team-sync-enterprise-only'}})
- [GitHub OAuth]({{'../setup-grafana/configure-security/configure-authentication/github/#team-sync-enterprise-only'}})
- [GitLab OAuth]({{'../setup-grafana/configure-security/configure-authentication/gitlab/#team-sync-enterprise-only'}})
- [LDAP]({{'../setup-grafana/configure-security/configure-authentication/enhanced-ldap/#ldap-group-synchronization-for-teams'}})
- [Okta]({{'../setup-grafana/configure-security/configure-authentication/okta/#team-sync-enterprise-only'}})
- [SAML]({{'../setup-grafana/configure-security/configure-authentication/saml/#configure-team-sync'}})

### Enhanced LDAP integration

With [enhanced LDAP integration]({{'../setup-grafana/configure-security/configure-authentication/enhanced-ldap/'}}), you can set up active LDAP synchronization.
[강화된 LDAP 통합]({{'../setup-grafana/configure-security/configure-authentication/enhanced-ldap/'}})으로, LDAP 동기화 설정이 가능합니다.
### SAML authentication

[SAML authentication]({{'../setup-grafana/configure-security/configure-authentication/saml/'}}) enables users to authenticate with single sign-on services that use Security Assertion Markup Language (SAML).
[SAML authentication]({{'../setup-grafana/configure-security/configure-authentication/saml/'}}) 을 통해 SAML(Single Assertion Markup Language)기반의 SSO 인증 서비스 사용이 가능합니다.
### Protected roles

With [protected roles]({{'../setup-grafana/configure-security/configure-authentication/#protected-roles'}}), you can define user roles that are exempt from being converted from one authentication type to another when changing auth providers.
[protected roles]({{'../setup-grafana/configure-security/configure-authentication/#protected-roles'}}), 인증 방법을 변경할 때 한 인증 유형에서 다른 인증 유형으로 변환되지 않는 사용자 역할을 정의할 수 있습니다.

## Enterprise features

Grafana Enterprise adds the following features:
그라파나 엔터프라이즈에는 다음과 같은 기능들도 포함됩니다.

- [Role-based access control]({{'../administration/roles-and-permissions/access-control/'}}) to control access with role-based permissions.
- [Data source permissions]({{'../administration/data-source-management#data-source-permissions'}}) to restrict query access to specific teams and users.
- [Data source query caching]({{'../administration/data-source-management/#query-caching'}}) to temporarily store query results in Grafana to reduce data source load and rate limiting.
- [Reporting]({{'../dashboards/create-reports/'}}) to generate a PDF report from any dashboard and set up a schedule to have it emailed to whomever you choose.
- [Export dashboard as PDF]({{'../dashboards/share-dashboards-panels/#export-dashboard-as-pdf'}})
- [Custom branding]({{'../setup-grafana/configure-grafana/configure-custom-branding/'}}) to customize Grafana from the brand and logo to the footer links.
- [Usage insights]({{'../dashboards/assess-dashboard-usage/'}}) to understand how your Grafana instance is used.
- [Recorded queries]({{'../administration/recorded-queries'}}) to see trends over time for your data sources.
- [Vault integration]({{'../setup-grafana/configure-security/configure-database-encryption/encrypt-secrets-using-hashicorp-key-vault/'}}) to manage your configuration or provisioning secrets with Vault.
- [Auditing]({{'../setup-grafana/configure-security/audit-grafana/'}}) tracks important changes to your Grafana instance to help you manage and mitigate suspicious activity and meet compliance requirements.
- [Request security]({{'../setup-grafana/configure-security/configure-request-security/'}}) makes it possible to restrict outgoing requests from the Grafana server.
- [Settings updates at runtime]({{'../setup-grafana/configure-grafana/settings-updates-at-runtime'}}) allows you to update Grafana settings at runtime without requiring a restart.

## Enterprise data sources

With a Grafana Enterprise license, you also get access to premium data sources, including:
그라파나 엔터프라이즈 라이센스로 아래의 프리미엄 데이터소스에 접근할 수 있습니다.

- [AppDynamics](https://grafana.com/grafana/plugins/dlopes7-appdynamics-datasource)
- [Azure Devops](https://grafana.com/grafana/plugins/grafana-azuredevops-datasource)
- [DataDog](https://grafana.com/grafana/plugins/grafana-datadog-datasource)
- [Dynatrace](https://grafana.com/grafana/plugins/grafana-dynatrace-datasource)
- [Gitlab](https://grafana.com/grafana/plugins/grafana-gitlab-datasource)
- [Honeycomb](https://grafana.com/grafana/plugins/grafana-honeycomb-datasource)
- [Jira](https://grafana.com/grafana/plugins/grafana-jira-datasource)
- [MongoDB](https://grafana.com/grafana/plugins/grafana-mongodb-datasource)
- [New Relic](https://grafana.com/grafana/plugins/grafana-newrelic-datasource)
- [Oracle Database](https://grafana.com/grafana/plugins/grafana-oracle-datasource)
- [Salesforce](https://grafana.com/grafana/plugins/grafana-salesforce-datasource)
- [SAP HANA®](https://grafana.com/grafana/plugins/grafana-saphana-datasource)
- [ServiceNow](https://grafana.com/grafana/plugins/grafana-servicenow-datasource)
- [Snowflake](https://grafana.com/grafana/plugins/grafana-snowflake-datasource)
- [Splunk](https://grafana.com/grafana/plugins/grafana-splunk-datasource)
- [Splunk Infrastructure monitoring (SignalFx)](https://grafana.com/grafana/plugins/grafana-splunk-monitoring-datasource)
- [Wavefront](https://grafana.com/grafana/plugins/grafana-wavefront-datasource)

## Try Grafana Enterprise

To purchase or obtain a trial license, contact the Grafana Labs [Sales Team](https://grafana.com/contact?about=support&topic=Grafana%20Enterprise).
평가판 라이선스를 구입하거나 취득하시려면, 그라파나 랩스 [영업팀](https://grafana.com/contact?about=support&topic=Grafana%20Enterprise) 에 문의해주세요.