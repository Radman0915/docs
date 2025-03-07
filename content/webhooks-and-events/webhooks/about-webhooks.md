---
title: About webhooks
intro: Learn the basics of how webhooks work to help you build and set up integrations.
redirect_from:
  - /webhooks
  - /developers/webhooks-and-events/about-webhooks
  - /developers/webhooks-and-events/webhooks/about-webhooks
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Webhooks
---

{% data reusables.webhooks.webhooks-ipv6 %}

Webhooks allow you to build or set up integrations, such as [{% data variables.product.prodname_github_apps %}](/apps/creating-github-apps/setting-up-a-github-app) or [{% data variables.product.prodname_oauth_apps %}](/apps/oauth-apps/building-oauth-apps), which subscribe to certain events on GitHub.com. When one of those events is triggered, we'll send a HTTP POST payload to the webhook's configured URL. Webhooks can be used to update an external issue tracker, trigger CI builds, update a backup mirror, or even deploy to your production server. You're only limited by your imagination.

Webhooks can be installed on{% ifversion ghes or ghae %} [{% data variables.product.prodname_enterprise %}](/rest/enterprise-admin#global-webhooks/),{% endif %} an [organization][org-hooks], a specific [repository][repo-hooks], or a {% data variables.product.prodname_github_app %}. Once installed, the webhook will be sent each time one or more subscribed events occurs.

You can create up to {% ifversion ghes or ghae %}250{% else %}20{% endif %} webhooks for each event on each installation target {% ifversion ghes or ghae %}({% data variables.product.prodname_ghe_server %} instance, specific organization, or specific repository).{% else %}(specific organization or specific repository).{% endif %}

## Events

{% data reusables.webhooks.webhooks_intro %}

Each event corresponds to a certain set of actions that can happen to your organization and/or repository. For example, if you subscribe to the `issues` event you'll receive detailed payloads every time an issue is opened, closed, labeled, etc.

For a complete list of available webhook events and their payloads, see "[AUTOTITLE](/webhooks-and-events/webhooks/webhook-events-and-payloads)."

## Ping event

{% data reusables.webhooks.ping_short_desc %}

For more information about the `ping` event webhook payload, see the [`ping`](/webhooks-and-events/webhooks/webhook-events-and-payloads#ping) event.

[org-hooks]: /rest/orgs#webhooks/
[repo-hooks]: /rest/repos#webhooks
