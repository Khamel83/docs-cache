Title: Install Tailscale on CentOS Stream 9 · Tailscale Docs

URL Source: https://tailscale.com/kb/1183/funnel/

Markdown Content:
Install Tailscale on CentOS Stream 9 · Tailscale Docs
===============

![Image 1](https://d.adroll.com/cm/b/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 2](https://d.adroll.com/cm/bombora/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 3](https://d.adroll.com/cm/experian/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 4](https://d.adroll.com/cm/eyeota/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 5](https://d.adroll.com/cm/g/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 6](https://d.adroll.com/cm/index/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 7](https://d.adroll.com/cm/l/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 8](https://d.adroll.com/cm/n/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 9](https://d.adroll.com/cm/o/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 10](https://d.adroll.com/cm/outbrain/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 11](https://d.adroll.com/cm/pubmatic/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 12](https://d.adroll.com/cm/taboola/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 13](https://d.adroll.com/cm/triplelift/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)![Image 14](https://d.adroll.com/cm/x/out?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&advertisable=TKO7FOASLRCK5J2S4BRIFC)

![Image 15](https://ipv4.d.adroll.com/seg4/TKO7FOASLRCK5J2S4BRIFC/5J25I7J2IBDGRESKWR4LV3?adroll_fpc=f154d923efe30d0987547f2ceb1af6a4-1773439257447&pv=72970243241.89923&arrfrr=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&cookie=&adroll_s_ref=&keyw=&p0=2164&adroll_external_data=&adroll_version=2.0)

### Your Privacy Choices

Welcome! We’re glad you’re here and want you to know that we respect your privacy and your right to control how we collect, use, and share your personal data. Please read our [Privacy Policy](https://tailscale.com/privacy-policy "privacyPolicy") to learn about our privacy practices.

Reject All Customize Settings Confirm

[](https://www.ketch.com/?utm_campaign=customer%20banner&utm_source=ketchcookiebanner&utm_medium=banner&org=tailscale)

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

*   [![Image 16: Alt text ](https://cdn.sanity.io/images/w77i7m8x/production/a06dc612b1e3e4f4df53a72030002600639a8738-300x120.png?w=640&q=75&fit=clip&auto=format)Title here How Cribl Enables Secure Work From Anywhere with Tailscale](https://tailscale.com/customers)

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


        [Download ↗](https://tailscale.com/downloads)
        [Update Tailscale](https://tailscale.com/docs/features/client/update)
        [Uninstall Tailscale](https://tailscale.com/docs/features/client/uninstall)
        *   Toggle[Deploy with MDM](https://tailscale.com/docs/mdm)

    *   Toggle[Quick guides](https://tailscale.com/docs/quick-guides)
    [OpenVPN migration guide](https://tailscale.com/docs/solutions/migrate-openvpn-tailscale)
    [Legacy VPN migration guide](https://tailscale.com/docs/solutions/migrate-legacy-vpn-tailscale)
    *   Toggle[Set up an identity provider](https://tailscale.com/docs/integrations/identity)
    [What is Tailscale?](https://tailscale.com/docs/concepts/what-is-tailscale)

*   Toggle[Manage Access](https://tailscale.com/docs/manage)

    *   Toggle[Manage access control](https://tailscale.com/docs/features/access-control)
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
2.   [Install Tailscale](https://tailscale.com/docs/install)›
3.   Centos›
4.   Install Tailscale on CentOS Stream 9

### Documentation

Close navigation

*   Toggle[Start](https://tailscale.com/docs/install/start)

    [Quickstart](https://tailscale.com/docs/how-to/quickstart)
    *   Toggle[Install Tailscale](https://tailscale.com/docs/install)


        [Download ↗](https://tailscale.com/downloads)
        [Update Tailscale](https://tailscale.com/docs/features/client/update)
        [Uninstall Tailscale](https://tailscale.com/docs/features/client/uninstall)
        *   Toggle[Deploy with MDM](https://tailscale.com/docs/mdm)

    *   Toggle[Quick guides](https://tailscale.com/docs/quick-guides)
    [OpenVPN migration guide](https://tailscale.com/docs/solutions/migrate-openvpn-tailscale)
    [Legacy VPN migration guide](https://tailscale.com/docs/solutions/migrate-legacy-vpn-tailscale)
    *   Toggle[Set up an identity provider](https://tailscale.com/docs/integrations/identity)
    [What is Tailscale?](https://tailscale.com/docs/concepts/what-is-tailscale)

*   Toggle[Manage Access](https://tailscale.com/docs/manage)

    *   Toggle[Manage access control](https://tailscale.com/docs/features/access-control)
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

Install Tailscale on CentOS Stream 9
====================================

Last validated: Feb 21, 2025

Packages are available for x86 and ARM CPUs, in both 32-bit and 64-bit variants.

1.   Add the Tailscale repository and install Tailscale:


```shell
sudo dnf config-manager --add-repo https://pkgs.tailscale.com/stable/centos/9/tailscale.repo
sudo dnf install tailscale
```
2.   Use `systemctl` to enable and start the service:


```shell
sudo systemctl enable --now tailscaled
```
3.   Connect your machine to your Tailscale network and authenticate in your browser:


```shell
sudo tailscale up
```
4.   You can find your Tailscale IPv4 address by running:


```shell
tailscale ip -4
```

If the device you added is a server or remotely-accessed device, you may want to consider [disabling key expiry](https://tailscale.com/docs/features/access-control/key-expiry) to prevent the need to periodically re-authenticate.

Some routing features such as [exit nodes](https://tailscale.com/docs/features/exit-nodes) may not work on CentOS because Tailscale's routing is [not yet compatible with firewalld](https://github.com/tailscale/tailscale/issues/3416).

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

[Terms of Service](https://tailscale.com/terms)[Privacy Policy](https://tailscale.com/privacy-policy)[California Notice](https://tailscale.com/privacy-policy#california-notice)[Cookie Notice](https://tailscale.com/cookie-notice)![Image 17: Check mark and x on a white and blue pill button](https://cdn.sanity.io/images/w77i7m8x/production/07d853f507039b2489d9818cb6ee7442c1b60e2a-30x14.svg)Your Privacy Choices

WireGuard is a registered trademark of Jason A. Donenfeld.

[](https://twitter.com/tailscale)[](https://www.facebook.com/tailscale/)[](https://www.linkedin.com/company/tailscale)[](https://hachyderm.io/@tailscale)[](https://www.youtube.com/@Tailscale)

© 2026 Tailscale Inc. All rights reserved. Tailscale is a registered trademark of Tailscale Inc.

![Image 18](https://bat.bing.com/action/0?ti=17188063&Ver=2&mid=89a18135-c778-4ebe-ac33-3155d937381e&bo=1&sid=1d4781a01f2811f1bfc705f7980b6bde&vid=1d477dc01f2811f19c7087fda63f6e23&vids=1&msclkid=N&pi=918639831&lg=en-US&sw=800&sh=600&sc=24&tl=Install%20Tailscale%20on%20CentOS%20Stream%209%20%C2%B7%20Tailscale%20Docs&p=https%3A%2F%2Ftailscale.com%2Fdocs%2Finstall%2Fcentos%2Fcentos-stream-9&r=&lt=332&evt=pageLoad&sv=2&cdb=AQUR&rn=182844)

![Image 19](https://px.ads.linkedin.com/collect/?pid=8552020&fmt=gif)
