# Tailscale Documentation

> Source: https://tailscale.com/kb/
> Category: services
> Cached: 2026-02-08

## Welcome to Tailscale

Tailscale securely connects your devices, no matter where they live. Built on WireGuard® for enterprise-grade networking.

## Quick Start

1. Install Tailscale
2. Create a network (tailnet)
3. Invite your team

## How-to Guides

### Manage Access
- Manage access control
- Manage just-in-time access
- Manage devices
- Manage users
- Tailnet Lock

### Route Traffic
- Set up a subnet router
- Set up an exit node
- Set up an app connector
- Use DNS
- Set up MagicDNS
- Set up high availability

### Set Up Servers
- Set up a server
- Use tags
- Install Tailscale with cloud-init
- Use auth keys
- Use Tailscale SSH
- Set up HTTPS certificates
- Run an ephemeral node
- Run unattended

### Access & Share Services
- View services
- Share nodes
- Use Taildrop

### Share a Web Server
- **Tailscale Funnel** - Expose local services publicly
- **Tailscale Serve** - Share services on your tailnet

### Solutions
- Code from your iPad
- Lock down a server
- Access a PiKVM
- Run a Pi-hole
- Secure external services
- Just-in-time access
- Automation

## Integrations

- Cloud servers (AWS, GCP, Azure, DigitalOcean, etc.)
- Containers and virtualization (Docker, Kubernetes, Podman)
- Serverless apps
- Databases
- Remote environments
- Developer tools
- Firewalls
- Web servers
- NAS devices

## Key Use Cases

- **Remote Access** - Access devices from anywhere
- **Site-to-site Networking** - Connect offices and locations
- **Multi-cloud Networking** - Unify cloud resources
- **Kubernetes Networking** - Connect K8s clusters
- **Edge & IoT Deployments** - Connect edge devices
- **Zero Trust Networking** - Replace VPNs with identity-based access
- **AI Workloads** - Secure AI infrastructure
- **Secure SaaS** - Control access to SaaS applications
- **Business VPN** - Modern VPN alternative
- **Homelab** - Personal infrastructure networking

## CLI Reference (Quick)

### Common Commands
- `tailscale up` - Connect to Tailscale
- `tailscale status` - Show connection status
- `tailscale ping <host>` - Ping another device
- `tailscale ip` - Get Tailscale IP address
- `tailscale down` - Disconnect

### Key Flags for `tailscale up`
- `--accept-routes` - Accept subnet routes from other nodes
- `--advertise-exit-node` - Offer to be an exit node
- `--advertise-routes=<ip>` - Expose subnet routes
- `--exit-node=<ip|name>` - Use specific exit node
- `--ssh` - Enable Tailscale SSH

---

Legacy CLI reference cached at: https://tailscale.com/kb/1080/client-api

The Tailscale CLI

is

available for [all plans](https://tailscale.com/pricing).

[Using the Tailscale CLI](https://tailscale.com/kb/1080/client-api#using-the-tailscale-cli)
-------------------------------------------------------------------------------------------

The location of the CLI varies depending on your platform:

On Linux, the CLI is your primary interface to Tailscale. The `tailscale` binary is likely already in your `$PATH`, so you can run commands with:

There is no CLI support for iOS and Android.

### [Tab completion](https://tailscale.com/kb/1080/client-api#tab-completion)

The Tailscale CLI supports tab-completion for commands, flags, and arguments. You can configure tab-completion with the [`completion` command](https://tailscale.com/kb/1080/client-api#completion).

Select your shell, then follow the instructions to load Tailscale CLI completions.

To load tab-completions for Bash, run the following command.

Run the following command to load completions for every new session on Linux, then reload your shell.

Run the following command to load completions for every new session on macOS, then reload your shell.

[Command Reference](https://tailscale.com/kb/1080/client-api#command-reference)
-------------------------------------------------------------------------------

Common flags for all commands:

*   `--socket=<path>` Path to the tailscaled socket.

### [up](https://tailscale.com/kb/1080/client-api#up)

Connect your device to Tailscale and authenticate if needed.

Running `tailscale up` without any flags connects to Tailscale.

Common flags:

*   `--accept-routes` Accept [subnet routes](https://tailscale.com/docs/features/subnet-routers) that other nodes advertise. The default depends on the host operating system. For certain platforms - Windows, iOS, Android, the macOS App Store variant, and the macOS standalone variant - the default is to accept routes. All other platforms default to not accepting routes.
*   `--advertise-exit-node` Offer to be an [exit node](https://tailscale.com/docs/features/exit-nodes) for outbound internet traffic from the Tailscale network. Defaults to not offering to be an exit node.
*   `--advertise-routes=<ip>` Expose physical [subnet routes](https://tailscale.com/docs/features/subnet-routers) to your entire Tailscale network.
*   `--exit-node=<ip|name>` Provide a [Tailscale IP](https://tailscale.com/docs/concepts/ip-and-dns-addresses) or [machine name](https://tailscale.com/docs/concepts/machine-names) to use as an exit node. To disable the use of an exit node, pass the flag with an empty argument: `--exit-node=`.
*   `--exit-node-allow-lan-access` Allow the client node access to its own LAN while connected to an exit node. Defaults to not allowing access while connected to an exit node.
*   `--force-reauth` Force re-authentication.
*   `--snat-subnet-routes` (Linux only) Disable source NAT. In normal operations, a subnet device sees the traffic originating from the subnet router. This simplifies routing, but does not allow traversing multiple networks. By disabling source NAT, the end machine sees the LAN IP address of the originating machine as the source.
*   `--stateful-filtering` Enable stateful filtering for [subnet routers](https://tailscale.com/docs/features/subnet-routers) and [exit nodes](https://tailscale.com/docs/features/exit-nodes). When enabled, inbound packets with another node's destination IP are dropped, unless they are a part of a tracked outbound connection from that node. Defaults to disabled.
*   `--shields-up`[Block incoming connections](https://tailscale.com/docs/features/client/manage-preferences) from other devices on your Tailscale network. Useful for personal devices that only make outgoing connections.
*   `--ssh` Run a [Tailscale SSH](https://tailscale.com/docs/features/tailscale-ssh) server, permitting access per the tailnet administrator's declared [access policy](https://tailscale.com/docs/features/access-control/acls), or the [default policy](https://tailscale.com/docs/reference/examples/acls#allow-all-default-acl) if none is defined. Defaults to false.

For a complete list of available flags, refer to the [`tailscale up`](https://tailscale.com/docs/reference/tailscale-cli/up) topic.

### [down](https://tailscale.com/kb/1080/client-api#down)

Disconnect from Tailscale. Running this command is the same as choosing to disconnect from or quit a Tailscale client.

When disconnected, you cannot reach devices over Tailscale. To reconnect, re-run `tailscale up` without any flags.

Available flags:

*   `--accept-risk=<risk>` Accept risk and skip confirmation for risk type. This can be either `lose-ssh` or `all`, or an empty string to not accept risk.
*   `--reason="<description>"` Specify the reason (inside quotes) for disconnecting Tailscale when the [system policies](https://tailscale.com/docs/features/tailscale-system-policies)`AlwaysOn.Enabled` and `AlwaysOn.OverrideWithReason` are enabled. For example, `tailscale down --reason="DNS issues"`.

### [bugreport](https://tailscale.com/kb/1080/client-api#bugreport)

The `bugreport` command is available in Tailscale v1.8 or later. If you don't see this command, consider [updating](https://tailscale.com/docs/features/client/update) your Tailscale client.

Generate a bug report with diagnostic information.

The `bugreport` command makes it easier to report bugs to the Tailscale team by marking diagnostic logs with indicators to make triage easier.

If you encounter a connectivity issue, run `tailscale bugreport` on the device experiencing the issue at the time you encounter it. This command prints a random identifier into diagnostic logs, which you can share with our team.

Identifiers look like this:

This command shares no personally identifiable information and is unused unless you share the bug identifier with our team.

Available flags:

*   `--diagnose` Prints additional verbose information about the system to the Tailscale logs after generating a `bugreport` identifier, which can then be viewed by our support team. Defaults to `false`.
*   `--record` Pause and then write another `bugreport`. Use this flag to create an initial `bugreport` identifier. During the pause, perform the action that reproduces your issue. Then, press Enter to create a second `bugreport` identifier. Share both bug identifiers with our team. Defaults to `false`.

### [cert](https://tailscale.com/kb/1080/client-api#cert)

Generate Let's Encrypt certificate and key files on the host for [HTTPS certificates](https://tailscale.com/docs/how-to/set-up-https-certificates) in your tailnet.

If you are trying to serve a folder of files or reverse proxy to an HTTP service, use the [`tailscale serve`](https://tailscale.com/kb/1080/client-api#serve) command instead.

Alternatively, if you want to save the certificate and private key to files, you can use the `--cert-file` and `--key-file` arguments:

The certificates provided by Let's Encrypt have a 90-day expiry and require periodic renewal. When a certificate is delivered as files on disk which you then move to an install location, such as when using `tailscale cert`, the [`tailscaled` daemon](https://tailscale.com/docs/reference/tailscaled) doesn't know where to place a renewed certificate or how to install it. As a result, you are responsible for renewing any certificates that you create using `tailscale cert`.

If a certificate is handled without the user initiating any file-based certificate installation (such as when using the [Caddy integration of Tailscale](https://github.com/tailscale/caddy-tailscale)) then the certificate will automatically renew without the user doing anything.

Available flags:

*   `--cert-file=<cert>` Specify the certificate output path.
*   `--key-file=<key>` Specify the private key output path.
*   `--min-validity=<duration>` Request a specified minimum remaining validity on the returned certificate. `duration` can be any value parseable by [`time.ParseDuration()`](https://pkg.go.dev/time#ParseDuration). For example, use `120h` to set the duration to five days.
*   `--serve-demo` Serve on port `:443` using the cert as a demo, instead of writing out the files to disk.

The `--min-validity` flag lets you ensure that the returned certificate is valid for at least the specified duration. If you specify a duration longer than the [certification lifetime set by Let's Encyrpt](https://letsencrypt.org/docs/faq#what-is-the-lifetime-for-let-s-encrypt-certificates-for-how-long-are-they-valid), it uses the maximum lifetime set by Let's Encrypt.

### [dns](https://tailscale.com/kb/1080/client-api#dns)

The `dns` command lets you access [Tailscale DNS settings](https://tailscale.com/docs/reference/dns-in-tailscale). It's available in Tailscale v1.74.0 and later.

Subcommands:

*   `status` Print the configuration of the local DNS forwarder and the tailnet-wide [MagicDNS](https://tailscale.com/docs/features/magicdns) configuration.
*   `query` Perform a DNS query using the local DNS forwarder. It's available in Tailscale v1.76.0 and later.

Available flags for `status`:

*   `--all` Outputs advanced debugging information.

### [drive](https://tailscale.com/kb/1080/client-api#drive)

Share a directory with your tailnet using [Taildrive](https://tailscale.com/docs/features/taildrive).

Subcommands:

*   `share` Create or modify a share.
*   `rename` Rename a share.
*   `unshare` Remove a share.
*   `list` List current shares.

### [completion](https://tailscale.com/kb/1080/client-api#completion)

Configure tab-completion for the Tailscale CLI.

Subcommands:

*   `bash` Configure tab-completion for the `bash` shell.
*   `zsh` Configure tab-completion for the `zsh` shell.
*   `fish` Configure tab-completion for the `fish` shell.
*   `powershell` Configure tab-completion for PowerShell.

Available flags:

*   `--flags=<true|false>` Configure whether to suggest flags (in addition to subcommands). Set to `true` by default.
*   `--descs=<true|false>` Configure whether to include descriptions of subcommands in the suggestions. Set to `true` by default.

### [configure](https://tailscale.com/kb/1080/client-api#configure)

Configure resources that you want to include in your tailnet.

Subcommands:

*   `kubeconfig` (alpha) Configure `kubectl` to connect to a Kubernetes cluster using Tailscale.
*   `mac-vpn` Install or uninstall the VPN configuration on [App Store](https://tailscale.com/docs/concepts/macos-variants#mac-app-store-variant) and [Standalone variant](https://tailscale.com/docs/concepts/macos-variants#standalone-variant) of macOS.
*   `synology` Configure Synology to enable outbound connections needed for Tailscale.
*   `sysext` Activate, deactivate, or manage the state of the Tailscale [system extension](https://tailscale.com/docs/concepts/macos-sysext) on the [Standalone variant](https://tailscale.com/docs/concepts/macos-variants#standalone-variant) of macOS.
*   `systray` Manage the `systray` client for Linux.

Available flags for `kubeconfig`:

*   `--http` Use HTTP instead of HTTPS to connect to the auth proxy. Ignored if you include a scheme in the hostname argument.

Available subcommands for `mac-vpn`:

*   `install` Write the Tailscale VPN configuration to the macOS settings.
*   `uninstall` Delete the Tailscale VPN configuration from the macOS settings.

Available subcommands for `sysext`:

*   `activate` Register the Tailscale system extension with macOS.
*   `deactivate` Deactivate the Tailscale system extension on macOS.
*   `status` Print the enablement status of the Tailscale system extension.

Available flags for `systray`:

*   `--enable-startup=<init-system>` Install the startup script for the init system. The only currently supported value is `systemd`.

Examples:

*   To configure your local `kubeconfig` file for authentication with a Kubernetes auth proxy:

*   To configure Synology to enable outbound connections:

### [exit-node](https://tailscale.com/kb/1080/client-api#exit-node)

Get information about [exit-nodes](https://tailscale.com/docs/features/exit-nodes) in your tailnet.

Available subcommands:

*   `list` Lists the exit nodes in your tailnet.
*   `suggest` Suggests a [recommended exit node](https://tailscale.com/docs/features/exit-nodes/auto-exit-nodes).

Available flags for `list`:

*   `--filter=<country>` Filter exit nodes by country.

### [file](https://tailscale.com/kb/1080/client-api#file)

Access and make files available to [Taildrop](https://tailscale.com/docs/features/taildrop).

Available commands:

*   `cp` Copy files to a host.
*   `get` Move files out of the Tailscale file inbox.

Available flags for `cp`:

*   `--name=<name>` Alternate filename to use, especially useful when `<file>` is `-` (`stdin`).
*   `--targets` List possible file `cp` targets.
*   `--verbose` Verbose output.

Available flags for `get`:

*   `--conflict=<behavior>``behavior` when a conflicting (same-named) file already exists in the target directory.
    *   `skip` Skip conflicting files: leave them in the Taildrop inbox and print an error. Get any non-conflicting files.
    *   `overwrite` Overwrite existing file.
    *   `rename` Write to a new number-suffixed filename.

*   `--loop` Run get in a loop, receiving files as they come in.
*   `--verbose` Verbose output.
*   `--wait` Wait for a file to arrive if inbox is empty.

### [funnel](https://tailscale.com/kb/1080/client-api#funnel)

Serve content and local servers from your Tailscale node to the internet.

To limit local service access to your tailnet, use the [`serve`](https://tailscale.com/kb/1080/client-api#serve) command.

Subcommands:

*   [`status`](https://tailscale.com/docs/reference/tailscale-cli/funnel#get-the-status) Gets the status.
*   [`reset`](https://tailscale.com/docs/reference/tailscale-cli/funnel#reset-tailscale-funnel) Resets the configuration.

For more information, refer to the [`tailscale funnel`](https://tailscale.com/docs/reference/tailscale-cli/funnel) topic.

### [ip](https://tailscale.com/kb/1080/client-api#ip)

Get a device's Tailscale IP address.

By default, this command returns both an [`100.x.y.z` IPv4 address](https://tailscale.com/docs/concepts/ip-and-dns-addresses) and an IPv6 address for the current device. You can return only an IPv4 or IPv6 address by passing either the `-4` or `-6` flags.

You can also find the Tailscale IP for other devices on your network by adding the device hostname after the command. For example:

Available flags:

*   `--4` Only return an IPv4 address.
*   `--6` Only return an IPv6 address.
*   `--1` Only return one address, preferring IPv4.

### [licenses](https://tailscale.com/kb/1080/client-api#licenses)

Get open source license information.

### [lock](https://tailscale.com/kb/1080/client-api#lock)

Manage [Tailnet Lock](https://tailscale.com/docs/features/tailnet-lock) for your tailnet.

Common subcommands:

*   [`init`](https://tailscale.com/docs/reference/tailscale-cli/lock#lock-init) Initializes Tailnet Lock.
*   [`status`](https://tailscale.com/docs/reference/tailscale-cli/lock#lock-status) Outputs the state of Tailnet Lock.
*   [`add`](https://tailscale.com/docs/reference/tailscale-cli/lock#lock-add) Adds one or more trusted signing keys to Tailnet Lock.
*   [`remove`](https://tailscale.com/docs/reference/tailscale-cli/lock#lock-remove) Removes one or more trusted signing keys from Tailnet Lock.
*   [`sign`](https://tailscale.com/docs/reference/tailscale-cli/lock#lock-sign) Signs a node key and transmits the signature to the coordination server.

Running `tailscale lock` with no subcommand and no arguments is equivalent to running [`tailscale lock status`](https://tailscale.com/docs/reference/tailscale-cli/lock#lock-status).

For a complete list of subcommands and flags, refer to the [`tailscale lock`](https://tailscale.com/docs/reference/tailscale-cli/lock) topic.

### [login](https://tailscale.com/kb/1080/client-api#login)

Log into Tailscale (and add this device to your Tailscale network). For more information about logging in, refer to [fast-user-switching](https://tailscale.com/docs/features/client/fast-user-switching).

Available flags:

*   `--accept-dns` Accept [DNS configuration](https://tailscale.com/docs/reference/dns-in-tailscale) from the admin console. Defaults to accepting DNS settings.
*   `--accept-routes` Accept [subnet routes](https://tailscale.com/docs/features/subnet-routers) that other nodes advertise. The default depends on the host operating system. For certain platforms - Windows, iOS, Android, the macOS App Store variant, and the macOS standalone variant - the default is to accept routes. All other platforms default to not accepting routes.
*   `--advertise-connector` Offer to be an [app connector](https://tailscale.com/docs/features/app-connectors) for domain-specific internet traffic for the tailnet.
*   `--advertise-exit-node` Offer to be an [exit node](https://tailscale.com/docs/features/exit-nodes) for outbound internet traffic from the Tailscale network. Defaults to not offering to be an exit node.
*   `--advertise-routes=<ip>` Expose physical [subnet routes](https://tailscale.com/docs/features/subnet-routers) to your entire Tailscale network.
*   `--advertise-tags=<tags>` Give tagged permissions to this device. You must be [listed in `"TagOwners"`](https://tailscale.com/docs/reference/syntax/policy-file#tag-owners) to be able to apply tags.
*   `--auth-key=<key>` Provide an [auth key](https://tailscale.com/docs/features/access-control/auth-keys) to automatically authenticate the node as your user account. For a best practice when handling the `--auth-key` value, refer to [Securely handle an auth key](https://tailscale.com/docs/features/access-control/auth-keys/how-to/secure-auth-keys).
*   `--client-id` Client ID used to generate [auth keys](https://tailscale.com/docs/features/access-control/auth-keys) by using [workload identity federation](https://tailscale.com/docs/features/workload-identity-federation).
*   `--client-secret`[OAuth Client](https://tailscale.com/docs/features/oauth-clients) secret used to generate [auth keys](https://tailscale.com/docs/features/access-control/auth-keys); if it begins with `file:`, then it's a path to a file containing the secret.
*   `--exit-node=<ip|name>` Provide a [Tailscale IP](https://tailscale.com/docs/concepts/ip-and-dns-addresses) or [machine name](https://tailscale.com/docs/concepts/machine-names) to use as an exit node. To disable the use of an exit node, pass the flag with an empty argument: `--exit-node=`.
*   `--exit-node-allow-lan-access` Allow the client node access to its own LAN while connected to an exit node. Defaults to not allowing access while connected to an exit node.
*   `--hostname=<name>` Provide a hostname to use for the device instead of the one provided by the OS. Note that this will change the machine name used in [MagicDNS](https://tailscale.com/docs/features/magicdns).
*   `--id-token` ID token from the identity provider to exchange with the control server for [workload identity federation](https://tailscale.com/docs/features/workload-identity-federation); if it begins with `file:`, then it's a path to a file containing the token.
*   `--audience` Audience used when requesting an ID token from an identity provider for auth keys generated by [workload identity federation](https://tailscale.com/docs/features/workload-identity-federation).
*   `--login-server=<url>` Provide the base URL of a control server instead of `https://controlplane.tailscale.com`. If you are using [Headscale](https://tailscale.com/blog/opensource#the-open-source-coordination-server) for your control server, use your Headscale instance's URL.
*   `--netfilter-mode=<mode>` Netfilter mode (one of `on`, `nodivert`, `off`). Refer to [Tailscale netfilter modes](https://tailscale.com/docs/reference/netfilter-modes) for more information.
*   `--nickname=<name>`[Nickname](https://tailscale.com/docs/features/client/fast-user-switching#setting-a-nickname) for the current account.
*   `--operator=<user>` Provide a Unix username other than `root` to operate `tailscaled`.
*   `--qr` Generate a QR code for the web login URL. Defaults to not showing a QR code.
*   `--qr-format=<format>` QR code formatting: `small` or `large`. Defaults to `small`.
*   `--stateful-filtering` Enable stateful filtering for [subnet routers](https://tailscale.com/docs/features/subnet-routers) and [exit nodes](https://tailscale.com/docs/features/exit-nodes). When enabled, inbound packets with another node's destination IP are dropped, unless they are a part of a tracked outbound connection from that node. Defaults to disabled.
*   `--shields-up`[Block incoming connections](https://tailscale.com/docs/features/client/manage-preferences) from other devices on your Tailscale network. Useful for personal devices that only make outgoing connections.
*   `--snat-subnet-routes` Source NAT traffic to local routes advertised with `--advertise-routes`.
*   `--ssh` Run a [Tailscale SSH](https://tailscale.com/docs/features/tailscale-ssh) server, permitting access per the tailnet administrator's declared [access policy](https://tailscale.com/docs/features/access-control/acls), or the [default policy](https://tailscale.com/docs/reference/examples/acls#allow-all-default-acl) if none is defined. Defaults to false.
*   `--timeout=<duration>` Maximum amount of time to wait for the Tailscale service to initialize. `duration` can be any value parseable by [`time.ParseDuration()`](https://pkg.go.dev/time#ParseDuration). Defaults to `0s`, which blocks forever.
*   `--unattended`(Windows only) Run in [unattended mode](https://tailscale.com/docs/how-to/run-unattended) where Tailscale keeps running even after the current user logs out.

### [logout](https://tailscale.com/kb/1080/client-api#logout)

Disconnect from Tailscale and expire the current log in. The next time you run `tailscale up`, you'll need to reauthenticate your device.

If you run `tailscale logout` on an [ephemeral node](https://tailscale.com/docs/features/ephemeral-nodes), the node will be removed from your tailnet immediately.

Available flags:

*   `--reason` Reason for the logout, if required by a [system policy](https://tailscale.com/docs/features/tailscale-system-policies).

### [metrics](https://tailscale.com/kb/1080/client-api#metrics)

Expose and collect [Tailscale client metrics](https://tailscale.com/docs/reference/tailscale-client-metrics) for use with third-party monitoring systems.

Subcommands:

*   `print` Shows client metrics in the current terminal session.
*   `write` Writes metric values to a text file.

### [netcheck](https://tailscale.com/kb/1080/client-api#netcheck)

Get a report on your current physical network conditions. This command is provided to help debug connection troubles.

`netcheck` will output a report like this:

(In the example output, the list of [DERP servers](https://tailscale.com/docs/reference/derp-servers) is truncated for brevity.)

*   `UDP` shows whether UDP traffic is enabled on the current network. If this is false, it's unlikely Tailscale will be able to make point-to-point connections, and will instead rely on our [encrypted TCP relays (DERP)](https://tailscale.com/docs/reference/derp-servers)
*   `IPv4` and **IPv6** show your network public IP addresses and support for both protocols.
*   `MappingVariesByDestIP` describes whether your device is behind a difficult NAT that varies the device's IP address depending on the destination.
*   `HairPinning` describes whether your router can route connections from endpoints on your LAN back to your LAN using those endpoints' globally-mapped IPv4 addresses/ports.
*   `PortMapping` describes a list of which three port-mapping services exist on your router. Possible values are "UPnP", "NAT-PMP", and "PCP".
*   `DERP latency` and `Nearest DERP` describe latency from our [encrypted TCP relays (DERP)](https://tailscale.com/docs/reference/derp-servers). The lowest latency ("nearest") server is used for traffic.

If any fields are blank, it means Tailscale wasn't able to measure that network property.

All the information from `tailscale netcheck` is also available in the [Machines](https://login.tailscale.com/admin/machines) page of the admin console, by selecting a particular machine.

Available flags:

*   `--every=<duration>` If non-zero, do an incremental report with the given frequency.
*   `--format=<format>` Output format; empty (for human-readable), `json` or `json-line`.
*   `--verbose` Verbose logs.

### [nc](https://tailscale.com/kb/1080/client-api#nc)

Connect to a port on a host, connected to stdin/stdout.

### [ping](https://tailscale.com/kb/1080/client-api#ping)

Attempt to ping another device exclusively over Tailscale.

The regular `ping` command often works fine over Tailscale, but `tailscale ping` provides more details about the connection over Tailscale that can be helpful when troubleshooting connectivity.

You can call `tailscale ping` using either a [100.x.y.z address](https://tailscale.com/docs/concepts/ip-and-dns-addresses) or a [machine name](https://tailscale.com/docs/concepts/machine-names).

Available flags:

*   `--c` Maximum number of pings to send. Defaults to 10.
*   `--icmp`, `--icmp=false` Perform an ICMP-level ping (through WireGuard, but not the local host OS stack). Defaults to false.
*   `--peerapi`, `--peerapi=false` Try hitting the peer's PeerAPI HTTP server. Defaults to false.
*   `--size=<size>` Size of the ping message (default pings only). 0 for minimum size.
*   `--tsmp`, `--tsmp=false` Perform a TSMP-level ping (through WireGuard, but not either host's OS stack). Defaults to false.
*   `--timeout=<duration>` Maximum amount of time to wait before giving up on a ping. `duration` can be any value parseable by [`time.ParseDuration()`](https://pkg.go.dev/time#ParseDuration). Defaults to `5s`.
*   `--until-direct`, `--until-direct=false` Stop once a direct path is established. Defaults to true.
*   `--verbose`, `--verbose=false` Show verbose output. Defaults to false.

There are [four types of ping messages](https://tailscale.com/docs/reference/ping-types) supported by the `tailscale ping` command.

### [serve](https://tailscale.com/kb/1080/client-api#serve)

Serve content and local servers from your Tailscale node to your tailnet.

To publicly share the local service to the internet, use the [`funnel`](https://tailscale.com/kb/1080/client-api#funnel) command.

Subcommands:

*   [`status`](https://tailscale.com/docs/reference/tailscale-cli/serve#get-the-status) Gets the status.
*   [`reset`](https://tailscale.com/docs/reference/tailscale-cli/serve#reset-tailscale-serve) Resets the configuration.

For more information, refer to the [`tailscale serve`](https://tailscale.com/docs/reference/tailscale-cli/serve) topic.

### [set](https://tailscale.com/kb/1080/client-api#set)

Change specified preferences.

Unlike [`tailscale up`](https://tailscale.com/kb/1080/client-api#up), this command does not require the complete set of desired settings. It only updates the settings you explicitly set. There are no default values. Note that when using [Fast User Switching](https://tailscale.com/docs/features/client/fast-user-switching), changes made are only for the currently connected tailnet.

Available flags:

*   `--accept-dns` Accept [DNS configuration](https://tailscale.com/docs/reference/dns-in-tailscale) from the admin console.
*   `--accept-risk=<risk>` Accept risk and skip confirmation for risk type. This can be either `lose-ssh` or `all`, or an empty string to not accept risk.
*   `--accept-routes`, `--accept-routes=false` Accept [subnet routes](https://tailscale.com/docs/features/subnet-routers) that other nodes advertise. The default depends on the host operating system. For certain platforms - Windows, iOS, Android, the macOS App Store variant, and the macOS standalone variant - the default is to accept routes. All other platforms default to not accepting routes.
*   `--advertise-connector` Offer to be an [app connector](https://tailscale.com/docs/features/app-connectors) for domain-specific internet traffic for the tailnet.
*   `--advertise-exit-node`, `--advertise-exit-node=false` Offer to be an exit node for internet traffic for the tailnet.
*   `--advertise-routes=<ip>` Expose physical [subnet routes](https://tailscale.com/docs/features/subnet-routers) to your entire Tailscale network. This is a comma-separated string, such as "10.0.0.0/8,192.168.0.0/24", or an empty string to not advertise routes.
*   `--auto-update`, `--auto-update=false` Enable or disable [auto-updates](https://tailscale.com/docs/features/client/update#auto-updates) for the client.
*   `--exit-node=<ip|name>` Provide a [Tailscale IP](https://tailscale.com/docs/concepts/ip-and-dns-addresses) or [machine name](https://tailscale.com/docs/concepts/machine-names) to use as an exit node. You can also use `--exit-node=auto:any` to track the suggested exit node and automatically switch to it when available exit nodes or network conditions change. To disable the use of an exit node, pass the flag with an empty argument using `--exit-node=`.
*   `--exit-node-allow-lan-access`, `--exit-node-allow-lan-access=false` Allow the client node access to its own LAN while connected to an exit node.
*   `--hostname=<name>` Hostname to use for the device instead of the one provided by the OS. Note that this will change the machine name used in [MagicDNS](https://tailscale.com/docs/features/magicdns).
*   `--netfilter-mode=<mode>` Netfilter mode (one of `on`, `nodivert`, `off`). Refer to [Tailscale netfilter modes](https://tailscale.com/docs/reference/netfilter-modes) for more information.
*   `--nickname=<name>`[Nickname](https://tailscale.com/docs/features/client/fast-user-switching#setting-a-nickname) for the current account.
*   `--operator=<user>` A Unix username other than `root` to operate `tailscaled`.
*   `--relay-server-port=<port>` Specify a UDP port to accept peer relay connections on. UDP port number (`0` will pick a random unused port) for the relay server to bind to, on all interfaces, or empty string to disable relay server functionality. Refer to [Tailscale Peer Relays](https://tailscale.com/docs/features/peer-relay) for more information.
*   `--relay-server-static-endpoints` Use static endpoints for [Tailscale Peer Relays](https://tailscale.com/docs/features/peer-relay).
*   `--report-posture` Allow management plane to gather [device posture](https://tailscale.com/docs/features/device-posture) information.
*   `--shields-up`, `--shields-up=false`[Block incoming connections](https://tailscale.com/docs/features/client/manage-preferences) from other devices on your Tailscale network. Useful for personal devices that only make outgoing connections.
*   `--snat-subnet-routes` Source NAT traffic to local routes advertised with `--advertise-routes`.
*   `--ssh`, `--ssh=false` Run a [Tailscale SSH](https://tailscale.com/docs/features/tailscale-ssh) server, permitting access per the tailnet administrator's declared [access policy](https://tailscale.com/docs/features/access-control/acls), or the [default policy](https://tailscale.com/docs/reference/examples/acls#allow-all-default-acl) if none is defined.
*   `--stateful-filtering` Apply stateful filtering to forwarded packets (subnet routers, exit nodes, and so on).
*   `--update-check` Notify about available Tailscale updates.
*   `--webclient`, `--webclient=false` Expose the [web interface](https://tailscale.com/docs/features/client/device-web-interface) to your tailnet persistently in the background on port `:5252.`

### [ssh](https://tailscale.com/kb/1080/client-api#ssh)

Establish a [Tailscale SSH](https://tailscale.com/docs/features/tailscale-ssh) session to a Tailscale machine.

You can often use the regular `ssh` command or another SSH client to make an SSH session to a Tailscale machine. However, when your local node is in [userspace-networking](https://tailscale.com/docs/reference/kernel-vs-userspace-routers#userspace-netstack-mode) mode and can't make a direct connection, use `tailscale ssh`. This sets up an SSH `ProxyCommand` to connect through the local `tailscaled` daemon. You can also use `tailscale ssh` when your local node is in [kernel](https://tailscale.com/docs/reference/kernel-vs-userspace-routers#kernel-mode) mode.

The `tailscale ssh` command automatically checks the destination server's SSH host key against the node's SSH host key as advertised by using the Tailscale coordination server.

`<args>` is one of the following forms:

*   `host` The destination server. An interactive session will prompt you for the user name to use for the session.
*   `user@host` The user name for the session and the destination server.

For both forms, `host` can be the destination server's [MagicDNS](https://tailscale.com/docs/features/magicdns) name (even if `--accept-dns=false` was set on the local node) or the destination server's [Tailscale IP address](https://tailscale.com/docs/concepts/ip-and-dns-addresses).

`tailscale ssh` is not available on sandboxed macOS builds—use the regular `ssh` client instead.

### [status](https://tailscale.com/kb/1080/client-api#status)

Get the status of your connections to other Tailscale devices.

This command returns a condensed table of information in human-readable format:

From left-to-right, these columns represent:

*   Column 1 is a [**Tailscale IP**](https://tailscale.com/docs/concepts/tailscale-ip-addresses), which you can use to connect to the device.
*   Column 2 is the [**machine name**](https://tailscale.com/docs/concepts/machine-names) of the device. If you use [MagicDNS](https://tailscale.com/docs/features/magicdns), you can also use this name to connect.
*   Column 3 is the **email address** for the owner of the device.
*   Column 4 is the **device OS**.
*   Column 5 shows the current **connection status**.

Connection status (column 5) is shown using three terms:

*   `active` means traffic is currently being sent/received from this device. It also includes the connection type, which can be `direct`, `relay`, or `peer-relay`.
    *   If the connection is `direct`, it includes peer device's IP address.
    *   If the connection is `relay`, it includes the [DERP server](https://tailscale.com/docs/reference/derp-servers)'s city code (`nyc`, `fra`, `tok`, `syd`) for the respective location.
    *   If the connection is [`peer-relay`](https://tailscale.com/docs/features/peer-relay), it includes the Tailscale IP address of the peer relay and the VNI (virtual network interface) used.

*   `idle` means traffic is not currently being sent/received from this device.
*   `-` means no traffic has ever been sent/received from this device.

`active` and `idle` connection statuses will also include `tx`/`rx` values indicating the number of bytes sent (`tx`) and received (`rx`) from this device.

Running `tailscale status` with the `--json` flag returns a machine-readable JSON response.

Unlike `tailscale status`, using this flag gives a detailed list of peers and users in your tailnet that makes it well-suited for automation tasks. It also includes additional metadata associated with your device.

Combine this with [`jq`](https://stedolan.github.io/jq) to automate data collection about your network. For example, the following command counts and sorts the relay servers your Tailscale peers are connected to.

Available flags:

*   `--active` Filter output to only peers with active sessions (not applicable to web mode).
*   `--browser` Open a browser in web mode (default `true`).
*   `--header` Show column headers in table format (default `false`).
*   `--json` Output in JSON format (WARNING: format subject to change).
*   `--listen=<address>` Listen address for web mode; use port 0 for automatic (default `127.0.0.1:8384`).
*   `--peers` Show status of peers (default `true`).
*   `--self` Show status of local machine (default `true`).
*   `--web` Run webserver with HTML showing status.

### [switch](https://tailscale.com/kb/1080/client-api#switch)

Switch to a different Tailscale account. For more information about switching accounts, refer to [fast-user-switching](https://tailscale.com/docs/features/client/fast-user-switching).

Examples:

*   To switch to the `alice@example.com` account:

*   To switch to the account that has the [nickname](https://tailscale.com/docs/features/client/fast-user-switching#setting-a-nickname) "work":

Available flags:

*   `--list` Lists available accounts.

Subcommands:

*   `remove <id>` removes a Tailscale account from the local machine. This does not delete the account itself, but it will no longer be available for switching to. You can add it back by logging in again. This command is currently in alpha and may change in the future.

### [syspolicy](https://tailscale.com/kb/1080/client-api#syspolicy)

List system policies, reload system policies, or inspect errors related to the [system policies](https://tailscale.com/docs/features/tailscale-system-policies) configured in your tailnet.

Subcommands:

*   `list` Shows system policies, reload system policies, or explore errors related to the [system policies](https://tailscale.com/docs/features/tailscale-system-policies) configured on the device.
*   `reload` Forces the Tailscale client to reload and reapply system policy settings on the device.

Available flags:

*   `--json` Return a machine-readable JSON response.

### [systray](https://tailscale.com/kb/1080/client-api#systray)

The `systray` command is available on the Linux client, is currently in [beta](https://tailscale.com/docs/reference/tailscale-release-stages#beta), and is available in Tailscale v1.88 or later.

Run the [system tray (`systray`) application](https://tailscale.com/docs/features/client/linux-systray) for Linux desktop clients to access some common actions like fast user switching and exit node selection.

Do not run `tailscale systray` as superuser (`sudo tailscale systray`), because systray is not designed to run as superuser and the command will fail.

### [update](https://tailscale.com/kb/1080/client-api#update)

The `update` command is available in Tailscale v1.36 or later for Windows and Ubuntu/Debian Linux, in v1.48.0 or later for the Mac Apple Store version and Synology, and in v1.54.0 or later for QNAP and the [Standalone variant of the macOS application](https://tailscale.com/docs/concepts/macos-variants#standalone-variant). If you don't see this command and you are running one of these operating systems, consider [updating your Tailscale client](https://tailscale.com/docs/features/client/update).

Update the Tailscale client version to the latest version, or to a different version.

Available flags:

*   `--dry-run` Show what update would do, without performing the update and without prompting to start the update.
*   `--track` The track to check for updates, either "stable" or ["unstable"](https://tailscale.com/docs/install/unstable). If not specified, the update uses the track currently in effect for the client.
*   `--version` An explicit version to use for the update or downgrade. You cannot specify both `--track` and `--version`. This flag is not available on the macOS client.
*   `--yes` Perform the update without interactive prompts. Defaults to false.

If you downgrade to a version that does not have the `tailscale update` functionality, you won't be able to run `tailscale update` to return to the prior version. You would need to [perform an update](https://tailscale.com/docs/features/client/update) without using the Tailscale CLI.

To determine the current version on a client, run [`tailscale version`](https://tailscale.com/kb/1080/client-api#version).

Examples:

Update to the latest version within your current track (stable or unstable, depending on what you're running):

Update to the latest version within your current track without using interactive prompts:

Update to Tailscale v1.34:

Update to the latest unstable version:

### [version](https://tailscale.com/kb/1080/client-api#version)

Print the version of Tailscale.

Available flags:

*   `--daemon` Also print local node's daemon version. Defaults to false.
*   `--json` Return a machine-readable JSON response.
*   `--upstream` Print the latest upstream release version from `pkgs.tailscale.com`. Defaults to false.

Running `tailscale version` also prints other information, including the Go version. Here's an example of the output:

### [web](https://tailscale.com/kb/1080/client-api#web)

Start a web server for controlling the `tailscaled` daemon. Starting a web server is useful when the CLI or a native app is impractical (such as on NAS devices).

Available flags:

*   `--cgi=<true|false>` Run the web server as a CGI script. Defaults to false.
*   `--listen=<ip|name>` Set the listen address. Use port `0` for automatic. Defaults to `localhost:8088`.
*   `--origin=<hostname>` Origin at which the web UI is served (if behind a reverse proxy or used with CGI).
*   `--prefix=<string>` Set the URL prefix added to requests (for CGI or reverse proxies).
*   `--readonly` Run the web server in read-only mode.

### [whois](https://tailscale.com/kb/1080/client-api#whois)

Get the machine and user associated with a Tailscale IP.

For user devices, this command returns:

For devices that are tagged, this command returns:

For each of these fields:

*   `Machine`, `Name` is the [machine name](https://tailscale.com/docs/concepts/machine-names) of the device. If you use [MagicDNS](https://tailscale.com/docs/features/magicdns), you can also use this name to connect.
*   `Machine`, `ID` is the [node id](https://tailscale.com/docs/reference/glossary#node) of the device.
*   `Machine`, `Addresses` are the [Tailscale IP](https://tailscale.com/docs/concepts/tailscale-ip-addresses), which you can use to connect to the device.
*   `Machine`, `AllowedIPs` are the subnet routes available to the device.
*   `Machine`, `Tags` are the tags to which the device belongs.
*   `User`, `Name` is the email address for the owner of the device.
*   `User`, `ID` is the unique ID of the user
*   `Capabilities` show the grants for the device.

Running `tailscale whois` with the `--json` flag will return a machine-readable JSON response. (Note that the `--json` option must come before the `ip[:port]` argument.)

Available flags:

*   `--json` Output in JSON format.
*   `--proto=<proto>` Protocol for the WhoIs request; one of `tcp` or `udp`; empty mans both.

### [appc-routes](https://tailscale.com/kb/1080/client-api#appc-routes)

Print the current [app connector](https://tailscale.com/docs/features/app-connectors) route status.

By default this command prints the domains configured in the app connector configuration and how many routes have been learned for each domain.

Available flags:

*   `--all` Print learned domains and routes and extra policy configured routes.
*   `--map` Print the map of learned domains.
*   `--n` Print the total number of routes this node advertises.
