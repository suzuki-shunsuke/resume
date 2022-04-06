# Resume - Shunsuke Suzuki

[GitHub](https://github.com/suzuki-shunsuke) | [Twitter](https://twitter.com/szkdash)

## Summary

I have been working as a software engineer for about 7 years and have experience in development and operation.

I joined Donuts as a web application engineer and developed web services for 2 years. I experienced a wide range of processes (Requirement definition, Design, Implementation, Testing, and Release) and technical areas (front-end, back-end, and infrastructure) in a small team.

At LINE Corporation, I worked as a Corporate Engineer for 2.5 years and operated and developed internal systems.
I have worked with packaged products such as Confluence and GitHub Enterprise, introduced OSS such as Drone and Prometheus, and developed systems using Python and Go.

In my current position, I have been a member of the cross-product SRE team for 2.5 years, operating and developing platform for our own products which are working on Kubernetes on AWS.
I develop tools and CI/CD pipelines so that the product team can perform development and release in a self-contained manner without SRE.
In particular, I'm focusing on improving the Terraform Monorepo workflow to create an environment where product teams can safely and comfortably set up their own product infrastructure using Terraform.

I'm also personally contributing to OSS such as [Terraform Provider AWS](https://github.com/hashicorp/terraform-provider-aws) and [Terraform Provider Docker](https://github.com/kreuzwerker/terraform-provider-docker) and developing OSS such as [tfcmt](https://github.com/suzuki-shunsuke/tfcmt), [aqua](https://aquaproj.github.io/), and [tfaction](https://github.com/suzuki-shunsuke/tfaction) to solve problems through software.

I also write blogs actively to share knowledge internally and externally.

## Professional Career

Note that the change in affiliation from Quipper to Recruit is due to a reorganization of Recruit and is not a job change.

term | Company | Position | Role
--- | --- | --- | ---
2021-10 / Now | [Recruit](https://www.recruit.co.jp/) | SRE | Member
2019-10 / 2021-09 | [Quipper Limited Japan Branch](https://www.quipper.com/) | SRE | Member
2017-04 / 2019-09 | [LINE Corporation](https://linecorp.com/en/) | Inhouse System Engineer | Member
2015-04 / 2017-03 | [Donuts Co. Ltd.](https://www.donuts.ne.jp/) | Web Application Engineer | Member, Tech Lead

## Current Position: Recruit, Quipper (SRE) 2019-10-01 / Now

https://brand.studysapuri.jp/career/position/sre

In my current position, I am a member of the cross-product SRE team, operating and developing platforms for the company's products.
I am involved in educational products such as [StudySapuri Elementary/Junior High/High School Courses and University Entrance Exam Courses for Japan](https://studysapuri.jp/) and [Quipper Video and Quipper School for overseas](https://www.quipper.com/).

I work as a member of a team of about 7 people.

The product is mainly running on AWS EKS, with some use of GCP.

* Improve Terraform Workflow
* Introduce AWS Organizations, AWS Control Tower, and AWS SSO
* Improve CI/CD of Application Monorepo
  * Rewrote shell scripts in Go
* Improve CI/CD of Ansible Monorepo
  * Accelerated CI, refactoring of .circleci/config.yml
* Alert handling, Developer support, middleware upgrade as SRE
* Implement MongoDB Atlas restore jobs in Go
* Develop tools to resolve toils

I have mentioned many things, but the most significant is the improvement of Terraform Monorepo.
I have divided Terraform State by service and environment, allowing developers to take ownership of their own service infrastructure and develop without SRE.
In addition, I have made various improvements as follows.

* [Fork tfnotify and develop tfcmt to make the results of terraform plan and apply easier to understand](https://zenn.dev/shunsuke_suzuki/articles/improve-terraform-cicd-with-tfcmt)
* Migrate CI Platform from CircleCI to AWS CodeBuild, and from AWS CodeBuild to GitHub Actions to improve security and Developer Experience
  * [2020-12-03 Terraform の CI/CD を CodeBuild に移行した話](https://blog.studysapuri.jp/entry/2020/12/03/080000)
  * [2022-02-04 Terraform の CI を AWS CodeBuild から GitHub Actions + tfaction に移行しました](https://blog.studysapuri.jp/entry/2022/02/04/080000)
* [Provide GitHub Actions workflow for Scaffolding](https://suzuki-shunsuke.github.io/tfaction/docs/feature/scaffold-working-dir)
* [Automatically format code in CI](https://suzuki-shunsuke.github.io/tfaction/docs/feature/auto-fix)
* [validation by tflint, tfsec, and Conftest with clear notification of results](https://suzuki-shunsuke.github.io/tfaction/docs/feature/linter)
* [Automatic update of Terraform, Terraform Provider, etc with Renovate](https://blog.studysapuri.jp/entry/2022/02/18/080000)
* [Using Terraform Plan File to apply safely](https://suzuki-shunsuke.github.io/tfaction/docs/feature/plan-file)
* [Automate follow-up if apply fails](https://suzuki-shunsuke.github.io/tfaction/docs/feature/follow-up-pr)
* [Provide workflow to migrate State with tfmigrate](https://suzuki-shunsuke.github.io/tfaction/docs/feature/tfmigrate)
* [Consolidate Terraform repositories into a single Monorepo to improve CI maintainability and quality](https://blog.studysapuri.jp/entry/2021/04/01/080000)
* [Migrate tools other than Terraform (miam, roadworker) to Terraform to improve Developer Experience](https://blog.studysapuri.jp/entry/2021/08/02/080000)
  * I developed [tfmigrator](https://github.com/tfmigrator/cli) to refactor the code generated by [terraformer](https://github.com/GoogleCloudPlatform/terraformer)
* etc

### Technical Stack

* Shell Script, Go, TypeScript
* AWS, GCP
* k8s
* Datadog, Sentry
* Jenkins, CircleCI, GitHub Actions
* MongoDB (MCM, Atlas)
* Terraform, Ansible
* Renovate
  * Renovate is easy to introduce, but requires a high level of expertise to reduce the human burden and operate it safely and without strain. I have tuned the configuration of various repositories including Terraform Monorepo
* Conftest
  * I have implemented our internal policies regarding Terraform and k8s manifests with Conftet. I have written the document for each Policy to provide clear guidance to users. We have also introduced automatic formatting with opa fmt and Policy Testing.
  * ref. [Conftest の Policy 違反を分かりやすくする](https://zenn.dev/shunsuke_suzuki/articles/improve-cicd-with-github-comment#conftest-%E3%81%AE-policy-%E9%81%95%E5%8F%8D%E3%82%92%E5%88%86%E3%81%8B%E3%82%8A%E3%82%84%E3%81%99%E3%81%8F%E3%81%99%E3%82%8B)
  * ref. [OPA で Table Driven Tests っぽいことをしてみる](https://techblog.szksh.cloud/opa-table-driven-test/)

## LINE Corporation (Corporate Engineer): 2017-04-01 / 2019-09-30

At LINE Corporation, I developed and operated internal systems as a Corporate Engineer.
I developed tools to integrate data between systems using Go and Python, and operated internal systems such as Confluence and GitHub Enterprise.
LINE has its own Private Cloud, so rather than utilizing cloud services, I utilizes OSS such as Drone and Graylog.
[I introduced Drone instead of Jenkins to improve CI](https://engineering.linecorp.com/ja/blog/detail/218/), and Graylog for secure log management.
Drone was originally introduced for internal use in our department, but it was well received and spread throughout the company.

### Technical Stack

* Go, Python
* k8s, Rancher
* Zabbix, Prometheus, Grafana
* Jenkins, [Drone](https://www.drone.io/)
* Fluentd, Graylog
* Terraform, Ansible

## Donuts (Web Application Engineer): 2015-04-01 ~ 2017-03-31

I joined Donuts as a new graduate as a Web Application Engineer and developed our web services.
I experienced a wide range of processes (design, development, testing, release) and technical areas (Frontend, Backend, Infrastructure).

### Techinical Stack

* Python, JavaScript
* MySQL
* AWS, GCP
* Docker
* Jenkins
* Terraform, Ansible, Packer

## Blog

I published what I did in my work on the corporate blog and my OSS on my personal blog.
I write mostly in Japanese, but sometimes I also write in English.

https://suzuki-shunsuke.github.io/profile/blog

## Contribute to OSS

I contribute to various OSS, most notably [Terraform Docker Provider](https://github.com/kreuzwerker/terraform-provider-docker) and [Terraform AWS Provider](https://github.com/hashicorp/terraform-provider-aws).
Especially, I contribute to Terraform Docker Provider as a Collaborator.

[List of Contributions by Pull Request](https://suzuki-shunsuke.github.io/profile/oss-contribution)

## OSS Development

I develop various tools, mainly CLI tools and GitHub Actions.
I often develop in Go.

* [tfcmt](https://github.com/suzuki-shunsuke/tfcmt): Fork of [tfnotify](https://github.com/mercari/tfnotify). Specializing in GitHub notifications, with various improvements
* [aqua](https://aquaproj.github.io/): Declarative CLI Version Manager
* [tfaction](https://github.com/suzuki-shunsuke/tfaction): GitHub Actions Collection for Terraform Monorepo
* [go-graylog](https://github.com/suzuki-shunsuke/go-graylog): Graylog's Go Client and Terraform Provider. Development has stopped.
* [github-comment](https://github.com/suzuki-shunsuke/github-comment): CLI to post and hide comments on GitHub. Used for user-friendly notification of CI results
* [tfmigrator](https://github.com/tfmigrator/cli): A tool for migrating Terraform Configuration and State. Useful for large scale migration and state partitioning
* etc

tfcmt and tfaction were introduced in [weekly.tf](https://weekly.tf/) and aqua was introduced in [zenn](https://zenn.dev/).

* [weekly.tf 2022-01-26](https://weekly.tf/issues/weekly-tf-issue-70-monorepos-platform-infra-team-terraform-scale-environment-as-code-995507)
* [weekly.tf 2022-01-19](https://weekly.tf/issues/weekly-tf-issue-69-tools-for-terraform-workflow-tfcmt-compost-trunk-tfnotify-multi-end-deploy-hcl2json-984084)
* [CIで利用するCLIツールをaquaで管理してみよう](https://zenn.dev/zoetro/articles/eee98d772c2483)
* [Productivity Weekly (2022-01-26号)](https://zenn.dev/korosuke613/articles/productivity-weekly-20220126)
* [Productivity Weekly (2022-01-12号)](https://zenn.dev/korosuke613/articles/productivity-weekly-20220112)
