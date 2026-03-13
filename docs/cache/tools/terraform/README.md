Title: Terraform CLI Documentation

URL Source: https://developer.hashicorp.com/terraform/cli

Published Time: 2025-11-19T13:27:46.000Z

Markdown Content:
Terraform CLI Documentation | Terraform | HashiCorp Developer
===============

[Skip to main content](https://developer.hashicorp.com/terraform/cli#main)

[HashiConf 2025 Don't miss the live stream of HashiConf Day 2 happening now View live stream](https://www.hashicorp.com/conferences/hashiconf#livestream)

HashiCorp Cloud Platform

Get started in minutes with our cloud products

[All HCP Products](https://developer.hashicorp.com/hcp)

*   Infrastructure Lifecycle Management
    *   [Terraform Manage infrastructure as code](https://developer.hashicorp.com/terraform)
    *   [Packer Build machine images](https://developer.hashicorp.com/packer)
    *   [Nomad Orchestrate workloads](https://developer.hashicorp.com/nomad)
    *   [Waypoint Standardize application patterns](https://developer.hashicorp.com/waypoint)
    *   [Vagrant Build developer environments](https://developer.hashicorp.com/vagrant)

*   Security Lifecycle Management
    *   [Vault Centrally manage secrets](https://developer.hashicorp.com/vault)
    *   [Boundary Secure remote access](https://developer.hashicorp.com/boundary)
    *   [Vault Radar Scan for embedded secrets](https://developer.hashicorp.com/hcp/docs/vault-radar)
    *   [Consul Secure network services](https://developer.hashicorp.com/consul)

Learn
*   [Certifications Get HashiCorp certified](https://developer.hashicorp.com/certifications)
*   [Tutorials Learn HashiCorp products](https://developer.hashicorp.com/tutorials)
*   [Validated Patterns Field-tested patterns for using HashiCorp products](https://developer.hashicorp.com/validated-patterns)
*   [Well-Architected Framework Adopt HashiCorp best practices](https://developer.hashicorp.com/well-architected-framework)

[Terraform](https://developer.hashicorp.com/terraform)

*   [Install](https://developer.hashicorp.com/terraform/install)
*   [Tutorials](https://developer.hashicorp.com/terraform/tutorials)
*
Documentation

    *   [Documentation](https://developer.hashicorp.com/terraform/docs)
    *   [Intro to Terraform](https://developer.hashicorp.com/terraform/intro)
    *   [Configuration Language](https://developer.hashicorp.com/terraform/language)
    *   [Terraform CLI](https://developer.hashicorp.com/terraform/cli)
    *   [HCP Terraform](https://developer.hashicorp.com/terraform/cloud-docs)
    *   [Terraform Enterprise](https://developer.hashicorp.com/terraform/enterprise)
    *   [Terraform MCP Server BETA](https://developer.hashicorp.com/terraform/mcp-server)
    *   [Terraform Migrate](https://developer.hashicorp.com/terraform/migrate)
    *   [Provider Use](https://developer.hashicorp.com/terraform/language/providers)
    *   [Plugin Development](https://developer.hashicorp.com/terraform/plugin)
    *   [Registry Publishing](https://developer.hashicorp.com/terraform/registry)
    *   [Integration Program](https://developer.hashicorp.com/terraform/docs/partnerships)

*   Sandbox
*   [Registry](https://registry.terraform.io/)(opens in new tab)
*   [Try Cloud](https://app.terraform.io/public/signup/account)(opens in new tab)

Search

⌘/ctrl

Command or control key

K

K key

*   Sign in
*   [Sign up](https://developer.hashicorp.com/sign-up)
*
* * *

*   Theme

Sign In[Sign Up](https://developer.hashicorp.com/sign-up)

Theme

[Terraform Home](https://developer.hashicorp.com/terraform)

Terraform CLI
-------------

*   [Terraform CLI](https://developer.hashicorp.com/terraform/cli)
*   [Basic CLI Features](https://developer.hashicorp.com/terraform/cli/commands)
*   Initializing Working Directories
*   Provisioning Infrastructure
*   Authenticating
*   Writing and Modifying Code
*   Inspecting Infrastructure
*   Import Infrastructure
*   Manually Update State
*   Manage Stacks
*   Managing Workspaces
*   Managing Plugins
*   CLI Configuration
*   Using HCP Terraform
*   Testing Terraform
*   Automating Terraform
*   Alphabetical List of Commands
*
* * *

*   [Terraform Internals](https://developer.hashicorp.com/terraform/internals)

* * *

*   ### Resources

*   [Tutorial Library](https://developer.hashicorp.com/tutorials/library?product=terraform)
*   [Certifications](https://developer.hashicorp.com/certifications/infrastructure-automation)
*   [Sandbox](https://developer.hashicorp.com/terraform/sandbox)
*   [Community Forum](https://discuss.hashicorp.com/c/terraform-core/27)(opens in new tab)
*   [Support](https://www.hashicorp.com/customer-success)(opens in new tab)
*   [GitHub](https://github.com/hashicorp/terraform)(opens in new tab)
*   [Terraform Registry](https://registry.terraform.io/)(opens in new tab)

1.   [Developer](https://developer.hashicorp.com/)
2.   [Terraform](https://developer.hashicorp.com/terraform)
3.   Terraform CLI

v1.14.x (latest)

*   Terraform
*   [v1.15.x (alpha)](https://developer.hashicorp.com/terraform/cli/v1.15.x)
*   [v1.13.x](https://developer.hashicorp.com/terraform/cli/v1.13.x)
*   [v1.12.x](https://developer.hashicorp.com/terraform/cli/v1.12.x)
*   [v1.11.x](https://developer.hashicorp.com/terraform/cli/v1.11.x)
*   [v1.10.x](https://developer.hashicorp.com/terraform/cli/v1.10.x)
*   [v1.9.x](https://developer.hashicorp.com/terraform/cli/v1.9.x)
*   [v1.8.x](https://developer.hashicorp.com/terraform/cli/v1.8.x)
*   [v1.7.x](https://developer.hashicorp.com/terraform/cli/v1.7.x)
*   [v1.6.x](https://developer.hashicorp.com/terraform/cli/v1.6.x)
*   [v1.5.x](https://developer.hashicorp.com/terraform/cli/v1.5.x)
*   [v1.4.x](https://developer.hashicorp.com/terraform/cli/v1.4.x)
*   [v1.3.x](https://developer.hashicorp.com/terraform/cli/v1.3.x)
*   [v1.2.x](https://developer.hashicorp.com/terraform/cli/v1.2.x)
*   [v1.1.x](https://developer.hashicorp.com/terraform/cli/v1.1.x)

Terraform CLI Documentation
===========================

Learn Terraform's CLI-based workflows. You can use the CLI alone or with HCP Terraform or Terraform Enterprise.

> **Hands-on:** Try the [Terraform: Get Started](https://developer.hashicorp.com/terraform/tutorials/aws-get-started?utm_source=WEBSITE&utm_medium=WEB_IO&utm_offer=ARTICLE_PAGE&utm_content=DOCS) tutorials.

This documentation provides reference information about Terraform CLI commands, as well as instructions for using commands to provision infrastructure and manage the infrastructure lifecyle. It is relevant to anyone working with Terraform's CLI-based workflows, including people who use Terraform CLI by itself, as well as those who use Terraform CLI in conjunction with HCTP Terraform or Terraform Enterprise.

For information about the Terraform configuration language syntax and coding patters, refer to the [Terraform configuration language documentation](https://developer.hashicorp.com/terraform/language).

[Edit this page on GitHub](https://github.com/hashicorp/web-unified-docs/blob/main/content/terraform/v1.14.x/docs/cli/index.mdx)

[](https://www.hashicorp.com/)Theme
*   [Certifications](https://developer.hashicorp.com/certifications)
*   [System Status](https://status.hashicorp.com/)
*   Cookie Manager
*   [Terms of Use](https://www.hashicorp.com/terms-of-service)
*   [Security](https://www.hashicorp.com/trust/security)
*   [Privacy](https://www.hashicorp.com/privacy)
*   [Trademark Policy](https://www.hashicorp.com/trademark-policy)
*   [Trade Controls](https://www.hashicorp.com/trade-controls)
*   [Accessibility](https://www.hashicorp.com/trust/accessibility)
*   [Give Feedback](https://forms.gle/fnHLuNahLEhjuKvE6)(opens in new tab)
*   stdin is not a tty
