---
layout: post
title: "Terraform Tutorial for Beginners"
date: 2023-04-15 10:00:00 -0500
categories: cloud
tags: [terraform,hashicorp,cloud]
---

If you're new to Terraform, that's fine!  This is a beginner tutorial for Terraform and by the end of this, you will feel like an expert!

{% include embed/youtube.html id='FmYvrxYvBP0' %}
📺 [Watch Video](https://www.youtube.com/watch?v=FmYvrxYvBP0)
## What is Terraform and how does it help?

Terraform is a powerful infrastructure as code tool to help you create and manage infrastructure  across multiple public or private clouds. It can help you provision, configure, and manage infrastructure using their simple and human readable configuration language. Using Terraform helps you automate your infrastructure and your DevOps workflow, do it consistently, and allows you to collaborate with teams in Git.

There are 7 key areas where Terraform shines:

- Automation: Terraform enables automation of infrastructure provisioning, configuration, and management, which reduces human error and saves time.

- Consistency: Terraform ensures that your infrastructure is consistent across all environments, from development to production.

- Collaboration: Terraform allows multiple teams to work together on infrastructure changes, using version control systems like Git.

- Cloud-agnostic: Terraform supports various cloud providers, including AWS, Google Cloud, and Microsoft Azure, allowing you to use the same tool to manage resources across different clouds.

- Scalability: Terraform is designed to handle large-scale infrastructure deployments and can easily manage thousands of resources.

- Reusability: Terraform modules enable you to reuse code and infrastructure components across multiple projects, making it easier to manage infrastructure at scale.

- Flexibility: Terraform is highly flexible and can be extended through plugins to integrate with other tools and services.

## Installing Terraform

This will work on Ubuntu and Windows + WSL

[Install `terraform` for other platforms](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)

Install dependencies

```bash
sudo apt update
sudo apt install  software-properties-common gnupg2 curl
```

Import the gpg key

```bash
curl https://apt.releases.hashicorp.com/gpg | gpg --dearmor > hashicorp.gpg
sudo install -o root -g root -m 644 hashicorp.gpg /etc/apt/trusted.gpg.d/
```

Add hashicorp repository

```bash
sudo apt-add-repository "deb [arch=$(dpkg --print-architecture)] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
```

Install `terraform`

```bash
sudo apt install terraform
```

Check the version

```bash
terraform --version
Terraform v1.4.0
on linux_amd64
```

Initialize terraform and Cloudflare

```bash
terraform init
```

We should see  that it installed plugins, and it should have created a lock file.

## Terraform Plan and Apply

Next we'll want to review our plan, we can see our proposed changes

```bash
terraform plan
```

Next we'll apply our changes.

```bash
terraform apply
```

Verify on the dashboard.

After applying we can verify the results.

we can also test with `nslookup`

```bash
nslookup yoursite.example.com
```

Check Cloudflare's site.

if we run plan again, we can see there's no work to do

```bash
terraform apply
```
