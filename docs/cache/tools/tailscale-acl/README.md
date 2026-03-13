Title: Manage permissions using ACLs · Tailscale Docs

URL Source: https://tailscale.com/kb/1018/acl/

Markdown Content:
Manage permissions using ACLs · Tailscale Docs
===============

[](https://tailscale.com/ "Homepage")

Product

Solutions

[Enterprise](https://tailscale.com/enterprise)[Customers](https://tailscale.com/customers)[Docs](https://tailscale.com/docs)[Blog](https://tailscale.com/blog)[Pricing](https://tailscale.com/pricing)

[Download](https://tailscale.com/download)[Log in](https://login.tailscale.com/welcome)[Schedule a demo](https://tailscale.com/contact/sales)[Get started - it's free!](https://login.tailscale.com/start)

Product

Meet Tailscale

*   [How it works](https://tailscale.com/blog/how-tailscale-works)
*   [Why Tailscale](https://tailscale.com/why-tailscale)
*   [WireGuard® for Enterprises](https://tailscale.com/wireguard-vpn)
*   [Bring Tailscale to Work](https://tailscale.com/bring-tailscale-to-work)

Explore

*   [Integrations](https://tailscale.com/integrations)
*   [Features](https://tailscale.com/features)
*   [Compare Tailscale](https://tailscale.com/compare)
*   [Community Projects](https://tailscale.com/community/community-projects)
*   [Partnerships](https://tailscale.com/partnerships)

Solutions

By use-case

*   [Business VPN](https://tailscale.com/use-cases/business-vpn)
*   [CI/CD](https://tailscale.com/use-cases/ci-cd)
*   [Infra Access](https://tailscale.com/use-cases/infrastructure-access)
*   [Cloud Connectivity](https://tailscale.com/use-cases/cloud-connectivity)
*   [Zero Trust Networking](https://tailscale.com/use-cases/zero-trust-networking)
*   [Homelab](https://tailscale.com/use-cases/homelab)
*   [Securing AI](https://tailscale.com/use-cases/securing-ai)

By role

*   [DevOps](https://tailscale.com/solutions/devops)
*   [IT](https://tailscale.com/solutions/it)
*   [Security](https://tailscale.com/solutions/security)

[Enterprise](https://tailscale.com/enterprise)

[Customers](https://tailscale.com/customers)

Nav heading here

*   [![Image 1: Alt text ](https://cdn.sanity.io/images/w77i7m8x/production/a06dc612b1e3e4f4df53a72030002600639a8738-300x120.png?w=640&q=75&fit=clip&auto=format)Title here How Cribl Enables Secure Work From Anywhere with Tailscale](https://tailscale.com/customers)

[Docs](https://tailscale.com/docs)

[Blog](https://tailscale.com/blog)

[Pricing](https://tailscale.com/pricing)

[Download](https://tailscale.com/download)

[Schedule a demo](https://tailscale.com/contact/sales)

[Get started - it's free!](https://login.tailscale.com/start)[Log in](https://login.tailscale.com/welcome)

[](https://twitter.com/tailscale)[](https://www.facebook.com/tailscale/)[](https://www.linkedin.com/company/tailscale)[](https://www.youtube.com/@Tailscale)

© 2026

*   Toggle[Start](https://tailscale.com/docs/install/start)

    [Quickstart](https://tailscale.com/docs/how-to/quickstart)
    *   Toggle[Install Tailscale](https://tailscale.com/docs/install)
    *   Toggle[Quick guides](https://tailscale.com/docs/quick-guides)
    [OpenVPN migration guide](https://tailscale.com/docs/solutions/migrate-openvpn-tailscale)
    [Legacy VPN migration guide](https://tailscale.com/docs/solutions/migrate-legacy-vpn-tailscale)
    *   Toggle[Set up an identity provider](https://tailscale.com/docs/integrations/identity)
    [What is Tailscale?](https://tailscale.com/docs/concepts/what-is-tailscale)

*   Toggle[Manage Access](https://tailscale.com/docs/manage)

    *   Toggle[Manage access control](https://tailscale.com/docs/features/access-control)


        [Manage ACLs](https://tailscale.com/docs/features/access-control/acls)
        [Manage grants](https://tailscale.com/docs/features/access-control/grants)
        [Migrate from ACLs to grants](https://tailscale.com/docs/reference/migrate-acls-grants)
        [Edit the tailnet policy file](https://tailscale.com/docs/features/tailnet-policy-file/manage-tailnet-policies)
        *   Toggle[Manage Tailscale with GitOps](https://tailscale.com/docs/gitops)

    *   Toggle[Manage just-in-time access](https://tailscale.com/docs/features/access-control/just-in-time-access)
    *   Toggle[Manage devices](https://tailscale.com/docs/features/access-control/device-management)
    *   Toggle[Manage users](https://tailscale.com/docs/manage-users)
    [Tailnet Lock](https://tailscale.com/docs/features/tailnet-lock)

*   Toggle[Route Traffic](https://tailscale.com/docs/route)

    *   Toggle[Set up a subnet router](https://tailscale.com/docs/features/subnet-routers)
    *   Toggle[Set up an exit node](https://tailscale.com/docs/features/exit-nodes)
    *   Toggle[Set up an app connector](https://tailscale.com/docs/features/app-connectors/how-to/setup)
    *   Toggle[Use DNS](https://tailscale.com/docs/reference/dns-in-tailscale)
    [Set up MagicDNS](https://tailscale.com/docs/features/magicdns)
    [Set up high availability](https://tailscale.com/docs/how-to/set-up-high-availability)

*   Toggle[Set Up Servers](https://tailscale.com/docs/servers)

    [Set up a server](https://tailscale.com/docs/how-to/set-up-servers)
    [Use tags](https://tailscale.com/docs/features/tags)
    [Install Tailscale with cloud-init](https://tailscale.com/docs/install/with-cloud-init)
    [Use auth keys](https://tailscale.com/docs/features/access-control/auth-keys)
    [Automate key expiry](https://tailscale.com/docs/features/access-control/key-expiry)
    *   Toggle[Use Tailscale SSH](https://tailscale.com/docs/features/tailscale-ssh)
    [Set up HTTPS certificates](https://tailscale.com/docs/how-to/set-up-https-certificates)
    [Run an ephemeral node](https://tailscale.com/docs/features/ephemeral-nodes)
    [Run unattended](https://tailscale.com/docs/how-to/run-unattended)

*   Toggle[Access & Share Services](https://tailscale.com/docs/share)

    [Tailscale services](https://tailscale.com/docs/features/tailscale-services)
    [Endpoint collection](https://tailscale.com/docs/features/services)
    [Share nodes](https://tailscale.com/docs/features/sharing)
    *   Toggle[Use Taildrop](https://tailscale.com/docs/features/taildrop)

*   Toggle[Share a web server](https://tailscale.com/docs/share-web-server)

    *   Toggle[Tailscale Funnel](https://tailscale.com/docs/features/tailscale-funnel)
    *   Toggle[Tailscale Serve](https://tailscale.com/docs/features/tailscale-serve)

*   Toggle[Solutions](https://tailscale.com/docs/solutions)

    [Secure traffic with Apple TV](https://tailscale.com/docs/solutions/secure-traffic-public-wifi-appletv)
    [Secure GitHub Actions runners](https://tailscale.com/docs/solutions/connect-github-CICD-workflows-to-private-infrastructure-without-public-exposure)
    [Block ads with a Raspberry Pi](https://tailscale.com/docs/solutions/block-ads-all-devices-anywhere-using-raspberry-pi)
    [Access remote desktops with Windows RDP](https://tailscale.com/docs/solutions/access-remote-desktops-using-windows-rdp)
    [Access remote desktops with RustDesk](https://tailscale.com/docs/solutions/access-remote-desktops-with-rustdesk)
    [Connect to MongoDB Atlas](https://tailscale.com/docs/solutions/create-a-secure-connection-to-mongodb-atlas)
    [Code from your iPad](https://tailscale.com/docs/solutions/code-on-ipad-vscode-caddy-code-server)
    [Lock down a server](https://tailscale.com/docs/how-to/secure-ubuntu-server-with-ufw)
    [Protect production databases](https://tailscale.com/docs/solutions/protect-postgresql-unencrypted-macbooks)
    [Access a PiKVM](https://tailscale.com/docs/integrations/pikvm)
    [Secure external services](https://tailscale.com/docs/concepts/ip-blocklist-relays)
    *   Toggle[Just-in-time access](https://tailscale.com/docs/features/access-control/just-in-time-access)
    *   Toggle[Automation](https://tailscale.com/docs/automations)

*   Toggle[Integrations](https://tailscale.com/docs/integrations)

    *   Toggle[Cloud servers](https://tailscale.com/docs/cloud-server)
    *   Toggle[Containers and virtualization](https://tailscale.com/docs/containers-and-virtualization)
    *   Toggle[Serverless apps](https://tailscale.com/docs/integration-serverless-apps)
    *   Toggle[Databases](https://tailscale.com/docs/database)
    *   Toggle[Remote environments](https://tailscale.com/docs/remote-code)
    *   Toggle[Developer tools](https://tailscale.com/docs/integration-dev-tools)
    *   Toggle[Firewalls](https://tailscale.com/docs/firewall)
    *   Toggle[Web servers](https://tailscale.com/docs/integrations/web-servers)
    *   Toggle[NAS](https://tailscale.com/docs/integrations/nas)

*   Toggle[FAQ](https://tailscale.com/docs/reference/faq)
*   Toggle[Logging, Streaming, and Events](https://tailscale.com/docs/reference/logging-streaming-events)

    [Logging overview](https://tailscale.com/docs/features/logging)
    [Configuration audit logging](https://tailscale.com/docs/features/logging/audit-logging)
    [Network flow logs](https://tailscale.com/docs/features/logging/network-flow-logs)
    [Log streaming](https://tailscale.com/docs/features/logging/log-streaming)
    *   Toggle[SSH session recording](https://tailscale.com/docs/features/tailscale-ssh/tailscale-ssh-session-recording)
    [Client metrics](https://tailscale.com/docs/reference/tailscale-client-metrics)
    [Webhooks](https://tailscale.com/docs/features/webhooks)

*   Toggle[Manage Your Organization](https://tailscale.com/docs/account)

    [Contact preferences](https://tailscale.com/docs/reference/contact-preferences)
    *   Toggle[Pricing and billing](https://tailscale.com/docs/account/billing)
    [Tailnet name](https://tailscale.com/docs/concepts/tailnet-name)
    [Domain ownership](https://tailscale.com/docs/concepts/domain-ownership)

*   Toggle[Reference](https://tailscale.com/docs/reference)

    *   Toggle[Tailnet policy file syntax](https://tailscale.com/docs/reference/syntax/policy-file)
    [ACL examples](https://tailscale.com/docs/reference/examples/acls)
    [Grant examples](https://tailscale.com/docs/reference/examples/grants)
    *   Toggle[CLI](https://tailscale.com/docs/reference/tailscale-cli)
    *   Toggle[API](https://tailscale.com/docs/reference/tailscale-api)
    [Key prefixes](https://tailscale.com/docs/reference/key-prefixes)
    *   Toggle[Production best practices](https://tailscale.com/docs/reference/best-practices/production)
    [Shared responsibility](https://tailscale.com/docs/concepts/shared-responsibility)
    *   Toggle[Technical overviews](https://tailscale.com/docs/concepts)
    *   Toggle[Terminology and concepts](https://tailscale.com/docs/reference/glossary)
    [Tailscale messages](https://tailscale.com/docs/reference/messages)
    [GitHub ↗](https://github.com/tailscale/tailscale)

*   Toggle[Get Support](https://tailscale.com/docs/support)

    *   Toggle[Troubleshooting](https://tailscale.com/docs/reference/troubleshooting)
    [Support options](https://tailscale.com/docs/reference/support-options)
    [Contact support ↗](https://tailscale.com/contact/support)
    [Generate a bug report](https://tailscale.com/docs/account/bug-report)

*   Toggle[Resources](https://tailscale.com/docs/resources)

    [Changelog ↗](https://tailscale.com/changelog)
    [Comparisons ↗](https://tailscale.com/compare)
    [Release stages](https://tailscale.com/docs/reference/tailscale-release-stages)
    [Security ↗](https://tailscale.com/security)
    [Tailscale Community Projects](https://tailscale.com/docs/reference/tailscale-community-projects)
    *   Toggle[Versions](https://tailscale.com/docs/reference/tailscale-client-versions)
    [Use cases](https://tailscale.com/docs/use-cases)
    [Invite only features](https://tailscale.com/docs/reference/invite-only-feature)
    [Feedback ↗](https://tailscale.com/feedback)

1.   [Docs](https://tailscale.com/docs)›
2.   [Features](https://tailscale.com/docs/features)›
3.   [Access control](https://tailscale.com/docs/features/access-control)›
4.   Manage permissions using ACLs

### Documentation

Close navigation

*   Toggle[Start](https://tailscale.com/docs/install/start)

    [Quickstart](https://tailscale.com/docs/how-to/quickstart)
    *   Toggle[Install Tailscale](https://tailscale.com/docs/install)
    *   Toggle[Quick guides](https://tailscale.com/docs/quick-guides)
    [OpenVPN migration guide](https://tailscale.com/docs/solutions/migrate-openvpn-tailscale)
    [Legacy VPN migration guide](https://tailscale.com/docs/solutions/migrate-legacy-vpn-tailscale)
    *   Toggle[Set up an identity provider](https://tailscale.com/docs/integrations/identity)
    [What is Tailscale?](https://tailscale.com/docs/concepts/what-is-tailscale)

*   Toggle[Manage Access](https://tailscale.com/docs/manage)

    *   Toggle[Manage access control](https://tailscale.com/docs/features/access-control)


        [Manage ACLs](https://tailscale.com/docs/features/access-control/acls)
        [Manage grants](https://tailscale.com/docs/features/access-control/grants)
        [Migrate from ACLs to grants](https://tailscale.com/docs/reference/migrate-acls-grants)
        [Edit the tailnet policy file](https://tailscale.com/docs/features/tailnet-policy-file/manage-tailnet-policies)
        *   Toggle[Manage Tailscale with GitOps](https://tailscale.com/docs/gitops)

    *   Toggle[Manage just-in-time access](https://tailscale.com/docs/features/access-control/just-in-time-access)
    *   Toggle[Manage devices](https://tailscale.com/docs/features/access-control/device-management)
    *   Toggle[Manage users](https://tailscale.com/docs/manage-users)
    [Tailnet Lock](https://tailscale.com/docs/features/tailnet-lock)

*   Toggle[Route Traffic](https://tailscale.com/docs/route)

    *   Toggle[Set up a subnet router](https://tailscale.com/docs/features/subnet-routers)
    *   Toggle[Set up an exit node](https://tailscale.com/docs/features/exit-nodes)
    *   Toggle[Set up an app connector](https://tailscale.com/docs/features/app-connectors/how-to/setup)
    *   Toggle[Use DNS](https://tailscale.com/docs/reference/dns-in-tailscale)
    [Set up MagicDNS](https://tailscale.com/docs/features/magicdns)
    [Set up high availability](https://tailscale.com/docs/how-to/set-up-high-availability)

*   Toggle[Set Up Servers](https://tailscale.com/docs/servers)

    [Set up a server](https://tailscale.com/docs/how-to/set-up-servers)
    [Use tags](https://tailscale.com/docs/features/tags)
    [Install Tailscale with cloud-init](https://tailscale.com/docs/install/with-cloud-init)
    [Use auth keys](https://tailscale.com/docs/features/access-control/auth-keys)
    [Automate key expiry](https://tailscale.com/docs/features/access-control/key-expiry)
    *   Toggle[Use Tailscale SSH](https://tailscale.com/docs/features/tailscale-ssh)
    [Set up HTTPS certificates](https://tailscale.com/docs/how-to/set-up-https-certificates)
    [Run an ephemeral node](https://tailscale.com/docs/features/ephemeral-nodes)
    [Run unattended](https://tailscale.com/docs/how-to/run-unattended)

*   Toggle[Access & Share Services](https://tailscale.com/docs/share)

    [Tailscale services](https://tailscale.com/docs/features/tailscale-services)
    [Endpoint collection](https://tailscale.com/docs/features/services)
    [Share nodes](https://tailscale.com/docs/features/sharing)
    *   Toggle[Use Taildrop](https://tailscale.com/docs/features/taildrop)

*   Toggle[Share a web server](https://tailscale.com/docs/share-web-server)

    *   Toggle[Tailscale Funnel](https://tailscale.com/docs/features/tailscale-funnel)
    *   Toggle[Tailscale Serve](https://tailscale.com/docs/features/tailscale-serve)

*   Toggle[Solutions](https://tailscale.com/docs/solutions)

    [Secure traffic with Apple TV](https://tailscale.com/docs/solutions/secure-traffic-public-wifi-appletv)
    [Secure GitHub Actions runners](https://tailscale.com/docs/solutions/connect-github-CICD-workflows-to-private-infrastructure-without-public-exposure)
    [Block ads with a Raspberry Pi](https://tailscale.com/docs/solutions/block-ads-all-devices-anywhere-using-raspberry-pi)
    [Access remote desktops with Windows RDP](https://tailscale.com/docs/solutions/access-remote-desktops-using-windows-rdp)
    [Access remote desktops with RustDesk](https://tailscale.com/docs/solutions/access-remote-desktops-with-rustdesk)
    [Connect to MongoDB Atlas](https://tailscale.com/docs/solutions/create-a-secure-connection-to-mongodb-atlas)
    [Code from your iPad](https://tailscale.com/docs/solutions/code-on-ipad-vscode-caddy-code-server)
    [Lock down a server](https://tailscale.com/docs/how-to/secure-ubuntu-server-with-ufw)
    [Protect production databases](https://tailscale.com/docs/solutions/protect-postgresql-unencrypted-macbooks)
    [Access a PiKVM](https://tailscale.com/docs/integrations/pikvm)
    [Secure external services](https://tailscale.com/docs/concepts/ip-blocklist-relays)
    *   Toggle[Just-in-time access](https://tailscale.com/docs/features/access-control/just-in-time-access)
    *   Toggle[Automation](https://tailscale.com/docs/automations)

*   Toggle[Integrations](https://tailscale.com/docs/integrations)

    *   Toggle[Cloud servers](https://tailscale.com/docs/cloud-server)
    *   Toggle[Containers and virtualization](https://tailscale.com/docs/containers-and-virtualization)
    *   Toggle[Serverless apps](https://tailscale.com/docs/integration-serverless-apps)
    *   Toggle[Databases](https://tailscale.com/docs/database)
    *   Toggle[Remote environments](https://tailscale.com/docs/remote-code)
    *   Toggle[Developer tools](https://tailscale.com/docs/integration-dev-tools)
    *   Toggle[Firewalls](https://tailscale.com/docs/firewall)
    *   Toggle[Web servers](https://tailscale.com/docs/integrations/web-servers)
    *   Toggle[NAS](https://tailscale.com/docs/integrations/nas)

*   Toggle[FAQ](https://tailscale.com/docs/reference/faq)
*   Toggle[Logging, Streaming, and Events](https://tailscale.com/docs/reference/logging-streaming-events)

    [Logging overview](https://tailscale.com/docs/features/logging)
    [Configuration audit logging](https://tailscale.com/docs/features/logging/audit-logging)
    [Network flow logs](https://tailscale.com/docs/features/logging/network-flow-logs)
    [Log streaming](https://tailscale.com/docs/features/logging/log-streaming)
    *   Toggle[SSH session recording](https://tailscale.com/docs/features/tailscale-ssh/tailscale-ssh-session-recording)
    [Client metrics](https://tailscale.com/docs/reference/tailscale-client-metrics)
    [Webhooks](https://tailscale.com/docs/features/webhooks)

*   Toggle[Manage Your Organization](https://tailscale.com/docs/account)

    [Contact preferences](https://tailscale.com/docs/reference/contact-preferences)
    *   Toggle[Pricing and billing](https://tailscale.com/docs/account/billing)
    [Tailnet name](https://tailscale.com/docs/concepts/tailnet-name)
    [Domain ownership](https://tailscale.com/docs/concepts/domain-ownership)

*   Toggle[Reference](https://tailscale.com/docs/reference)

    *   Toggle[Tailnet policy file syntax](https://tailscale.com/docs/reference/syntax/policy-file)
    [ACL examples](https://tailscale.com/docs/reference/examples/acls)
    [Grant examples](https://tailscale.com/docs/reference/examples/grants)
    *   Toggle[CLI](https://tailscale.com/docs/reference/tailscale-cli)
    *   Toggle[API](https://tailscale.com/docs/reference/tailscale-api)
    [Key prefixes](https://tailscale.com/docs/reference/key-prefixes)
    *   Toggle[Production best practices](https://tailscale.com/docs/reference/best-practices/production)
    [Shared responsibility](https://tailscale.com/docs/concepts/shared-responsibility)
    *   Toggle[Technical overviews](https://tailscale.com/docs/concepts)
    *   Toggle[Terminology and concepts](https://tailscale.com/docs/reference/glossary)
    [Tailscale messages](https://tailscale.com/docs/reference/messages)
    [GitHub ↗](https://github.com/tailscale/tailscale)

*   Toggle[Get Support](https://tailscale.com/docs/support)

    *   Toggle[Troubleshooting](https://tailscale.com/docs/reference/troubleshooting)
    [Support options](https://tailscale.com/docs/reference/support-options)
    [Contact support ↗](https://tailscale.com/contact/support)
    [Generate a bug report](https://tailscale.com/docs/account/bug-report)

*   Toggle[Resources](https://tailscale.com/docs/resources)

    [Changelog ↗](https://tailscale.com/changelog)
    [Comparisons ↗](https://tailscale.com/compare)
    [Release stages](https://tailscale.com/docs/reference/tailscale-release-stages)
    [Security ↗](https://tailscale.com/security)
    [Tailscale Community Projects](https://tailscale.com/docs/reference/tailscale-community-projects)
    *   Toggle[Versions](https://tailscale.com/docs/reference/tailscale-client-versions)
    [Use cases](https://tailscale.com/docs/use-cases)
    [Invite only features](https://tailscale.com/docs/reference/invite-only-feature)
    [Feedback ↗](https://tailscale.com/feedback)

Manage permissions using ACLs
=============================

Last validated: Jan 5, 2026

Tailscale now secures access to resources using [grants](https://tailscale.com/docs/features/access-control/grants), a next-generation access control policy syntax. Grants provide [all original ACL functionality plus additional capabilities](https://tailscale.com/docs/reference/grants-vs-acls).

ACLs will continue to work **indefinitely**; Tailscale will not remove support for this first-generation syntax from the product. However, Tailscale recommends [migrating to grants](https://tailscale.com/docs/reference/migrate-acls-grants) and using grants for all new tailnet policy file configurations because ACLs will not receive any new features.

ACLs are available on all plans, but [certain functionality might be restricted](https://tailscale.com/kb/1018/acl/#availability-by-plan) on some plans.

Tailscale's [access control](https://tailscale.com/docs/features/access-control) methodology follows the [least privilege](https://tailscale.com/learn/principle-of-least-privilege) and [zero trust](https://tailscale.com/docs/concepts/zero-trust) principles. There are two ways to define access controls for your tailnet: access control lists (ACLs) and grants. Both methods follow a deny-by-default principle and are defined in the [tailnet policy file](https://tailscale.com/docs/features/tailnet-policy-file) using a [declarative huJSON syntax](https://tailscale.com/docs/reference/syntax/policy-file).

ACLs represent the traditional [network layer](https://en.wikipedia.org/wiki/Network_layer) approach to managing access within your tailnet, where you define [a set of devices or users](https://tailscale.com/docs/reference/targets-and-selectors) who can access ports on other devices. Each ACL you create must define a source and a destination. They let you precisely define access controls for users and devices on your Tailscale network (known as a tailnet).

```json
{
  "acls": [
    {
      "action": "accept",
      "src": [ <list-of-sources> ], // These sources (devices or users)
      "dst": [ <destination>:<port> ], // can access these destination devices on their defined ports
    }
  ]
}
```

You can use the [visual policy editor](https://tailscale.com/docs/features/visual-editor) to manage your tailnet policy file. Refer to the [visual editor reference](https://tailscale.com/docs/reference/visual-editor) for guidance on using the visual editor.

When you first create your tailnet, the [default tailnet policy file](https://tailscale.com/docs/reference/examples/acls#allow-all-default-acl) enables communication between all devices within the tailnet. You can modify your policy file (including [editing ACLs](https://tailscale.com/kb/1018/acl/#edit-acls)) to fit your needs.

ACLs are deny-by-default, directional, locally enforced, and don't affect local network traffic.

*   **Deny-by-default**. Using a default deny policy prevents communication between devices without explicit access to each other. However, in the absence of an `acls` section in the tailnet policy file, Tailscale applies the [default allow all policy](https://tailscale.com/docs/reference/examples/acls#allow-all-default-acl).
*   **Directional**. Allowing a source to connect to a destination doesn't mean the destination can connect to the source (unless a policy explicitly enables it).
*   **Locally enforced**. A device enforces incoming connections based on the access rules distributed to all devices in your tailnet. Rule enforcement happens on each device directly, without further involvement from Tailscale's coordination server.
*   ACLs do not affect what a device can or cannot access on its local network.

For more information about Tailscale's approach to access control, refer to [RBAC like it was meant to be](https://tailscale.com/blog/rbac-like-it-was-meant-to-be).

If you don't define any access control policies, Tailscale applies the [default allow all ACL policy](https://tailscale.com/docs/reference/examples/acls#allow-all-default-acl). To deny all traffic, use an [empty object for the `acls` section](https://tailscale.com/docs/reference/examples/acls#deny-all) in your tailnet policy file.

[Edit ACLs](https://tailscale.com/kb/1018/acl/#edit-acls)
---------------------------------------------------------

You can edit your tailnet's access rules by using the [Access controls](https://login.tailscale.com/admin/acls) page of the admin console, [GitOps for Tailscale ACLs](https://tailscale.com/docs/gitops), or the [Tailscale API](https://tailscale.com/docs/reference/tailscale-api). Refer to [Editing ACLs](https://tailscale.com/docs/features/tailnet-policy-file/manage-tailnet-policies) for more information.

Refer to [tailnet policy file syntax](https://tailscale.com/docs/reference/syntax/policy-file) to learn about creating access control policies or the [sample ACLs](https://tailscale.com/docs/reference/examples/acls) for examples of common policies.

[Availability by plan](https://tailscale.com/kb/1018/acl/#availability-by-plan)
-------------------------------------------------------------------------------

ACLs are available on all plans, but certain functionality might be restricted on some plans.

| **Availability** | **On [all plans](https://tailscale.com/pricing)** | **On [the Personal, Personal Plus, Premium, and Enterprise plans](https://tailscale.com/pricing)** |
| --- | --- | --- |
| Access rules for... | * Any * Tailscale IP * Subnet CIDR Range * Autogroups * Tags * Hosts * IP sets | * Any * Tailscale IP * Subnet CIDR Range * Autogroups * Groups * Users * Tags * Hosts * IP sets |
| Access rules specifying... | * Ports * Protocols |  |
| ACL sections for... | * `acl` * `hosts` * `tests` * `tagOwners` * `autoApprovers` * `nodeAttrs` * `postures` with default device posture attributes only * `ipsets` | * `acl` * `groups` * `hosts` * `tests` * `tagOwners` * `autoApprovers` * `ssh` for Tailscale SSH * `nodeAttrs` for Tailscale Funnel * `postures` with default, custom, and third-party attributes (Personal, Personal Plus, and Enterprise plans only) * `ipsets` |

On this page

*   [Edit ACLs](https://tailscale.com/kb/1018/acl/#edit-acls)
*   [Availability by plan](https://tailscale.com/kb/1018/acl/#availability-by-plan)

Scroll to top

Product

[How it works](https://tailscale.com/blog/how-tailscale-works)[Pricing](https://tailscale.com/pricing)[Integrations](https://tailscale.com/integrations)[Features](https://tailscale.com/features)[Compare Tailscale](https://tailscale.com/compare)

Use Cases

[Business VPN](https://tailscale.com/use-cases/business-vpn)[CI/CD](https://tailscale.com/use-cases/ci-cd)[Infra Access](https://tailscale.com/use-cases/infrastructure-access)[Cloud Connectivity](https://tailscale.com/use-cases/cloud-connectivity)[Zero Trust Networking](https://tailscale.com/use-cases/zero-trust-networking)[Homelab](https://tailscale.com/use-cases/homelab)

Resources

[Blog](https://tailscale.com/blog)[Events & Webinars](https://tailscale.com/events-webinars)[Partnerships](https://tailscale.com/partnerships)

Company

[Company](https://tailscale.com/company)[Careers](https://tailscale.com/careers)[Press](https://tailscale.com/press)

Help & Support

[Support](https://tailscale.com/contact/support)[Sales](https://tailscale.com/contact/sales)[Security](https://tailscale.com/security)[Legal](https://tailscale.com/legal)[Open Source](https://tailscale.com/opensource)[Changelog](https://tailscale.com/changelog)[Tailscale Status](https://status.tailscale.com/)

Learn

[SSH keys](https://tailscale.com/learn/generate-ssh-keys)[Docker SSH](https://tailscale.com/learn/ssh-into-docker-container)[NAT Traversal](https://tailscale.com/blog/how-nat-traversal-works)[MagicDNS](https://tailscale.com/blog/2021-09-private-dns-with-magicdns)[PAM](https://tailscale.com/learn/privileged-access-management)[All articles](https://tailscale.com/learn)

[](https://tailscale.com/ "Homepage")

[Terms of Service](https://tailscale.com/terms)[Privacy Policy](https://tailscale.com/privacy-policy)[California Notice](https://tailscale.com/privacy-policy#california-notice)[Cookie Notice](https://tailscale.com/cookie-notice)![Image 2: Check mark and x on a white and blue pill button](https://cdn.sanity.io/images/w77i7m8x/production/07d853f507039b2489d9818cb6ee7442c1b60e2a-30x14.svg)Your Privacy Choices

WireGuard is a registered trademark of Jason A. Donenfeld.

[](https://twitter.com/tailscale)[](https://www.facebook.com/tailscale/)[](https://www.linkedin.com/company/tailscale)[](https://hachyderm.io/@tailscale)[](https://www.youtube.com/@Tailscale)

© 2026 Tailscale Inc. All rights reserved. Tailscale is a registered trademark of Tailscale Inc.
