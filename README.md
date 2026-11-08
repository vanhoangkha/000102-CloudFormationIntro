# Introduction to Infrastructure as Code

> Introduction to AWS CloudFormation.

A hands-on workshop from the [AWS First Cloud Journey](https://github.com/vanhoangkha/aws-first-cloud-journey) series, available in English and Vietnamese.

**Read the workshop online:** https://vanhoangkha.github.io/000102-CloudFormationIntro/

## Overview

In this workshop series, we will introduce the basic concepts and benefits of IaC (Infrastructure as Code), compare different IaC frameworks, and walk through the steps to get started with IaC.

IaC is a methodology for managing infrastructure in which the deployment and management of infrastructure is done through source code. One of the biggest benefits of IaC is increased productivity.

## Workshop contents

1. Introduction
2. Preparation Steps
3. Creating Lambda Function
4. Create VPC and EC2
5. Three-Tier Architecture
   - Deploying CloudFormation Stack
   - Web Tier Access Test
   - Check Access to the Application Tier
   - Checking Database Tier Access
6. Cleaning up resources

## Prerequisites

- An AWS account with permissions to create the resources used in the labs
- Basic familiarity with the AWS Management Console
- [Hugo](https://gohugo.io/installation/) (extended edition) if you want to run the site locally

## Run locally

```bash
git clone https://github.com/vanhoangkha/000102-CloudFormationIntro.git
cd 000102-CloudFormationIntro
hugo server
```

Then open http://localhost:1313 in your browser.

## Repository structure

| Path | Purpose |
| --- | --- |
| `content/` | Workshop pages (`*.md` English, `*.vi.md` Vietnamese) |
| `static/` | Images and other static assets |
| `layouts/` | Hugo layout overrides |
| `themes/` | Hugo theme |
| `config.toml` | Site configuration |

## Cost and cleanup

The labs create AWS resources that may incur charges. Complete the **Clean up** chapter when you finish to remove them.

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

To report a security issue, see [SECURITY.md](SECURITY.md).

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
