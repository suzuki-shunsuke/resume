# 職務経歴

[GitHub](https://github.com/suzuki-shunsuke) | [Twitter](https://twitter.com/szkdash)

## 要約

社会人になって約7年間ソフトウェアエンジニアとして開発・運用を経験してきました。

新卒で Donuts に Web アプリケーションエンジニアとして入社し、 2 年間 Web サービスの開発を行いました。少人数のチームで幅広い工程(要件定義・設計・実装・テスト・リリース)や技術領域(フロントエンド・バックエンド・インフラ) を経験しました。

LINE では Corporate Engineer として 2.5 年ほど社内システムの運用・開発を行いました。
Confluence や GitHub Enterprise のようなパッケージ製品の運用、 Drone や Prometheus のような OSS の導入、 Python や Go を用いたシステムの開発を行いました。

現職では 2.5 年弱ほどプロダクト横断の SRE チームのメンバーとして自社プロダクトのためのプラットフォームの運用・開発を行っています。
プロダクトチームが SRE に依存せず自己完結的に開発からリリースまで行えるよう、セルフサービス化やツール・ CI/CD Pipline の開発・運用を行っています。
特に Terraform Monorepo の workflow の改善に注力しており、プロダクトチームが Terraform を使って安全かつ快適に自分たちで自分たちのプロダクトのインフラを用意できる環境づくりをしています。

個人的に OSS への貢献や開発にも力を入れており、 [tfcmt](https://github.com/suzuki-shunsuke/tfcmt) や [aqua](https://aquaproj.github.io/), [tfaction](https://github.com/suzuki-shunsuke/tfaction) を始めとした様々なツールを開発し、ソフトウェアによる問題解決に取り組んでいます。

ブログの執筆といった形で社内外への情報発信も積極的に行っております。

## 職務経歴

Quipper から Recruit への所属の変更は、 Recruit の組織再編によるものであり、転職ではありません。

在籍期間 | 企業名 | ポジション | ロール
--- | --- | --- | ---
2021-10 / 現在 | [Recruit](https://www.recruit.co.jp/) | SRE | Member
2019-10 / 2021-09 | [Quipper Limited Japan Branch](https://www.quipper.com/) | SRE | Member
2017-04 / 2019-09 | [LINE Corporation](https://linecorp.com/en/) | Inhouse System Engineer | Member
2015-04 / 2017-03 | [Donuts Co. Ltd.](https://www.donuts.ne.jp/) | Web Application Engineer | Member, Tech Lead

## 現職: Recruit, Quipper (SRE) 2019-10-01 ~

https://brand.studysapuri.jp/career/position/sre

現職ではプロダクト横断の SRE チームのメンバーとして自社プロダクトのためのプラットフォームの運用・開発を行っています。
国内向けの「スタディサプリ小・中・高校講座、大学受験講座」、海外向けの「Quipper Video, Quipper School」といった教育に関するプロダクトに関わっています。

7 人ほどのチームの 1 メンバーとして仕事しています。

プロダクトは主に AWS の EKS 上で動いており、 GCP も一部使っています。

* Terraform Monorepo の改善
* AWS Organizations, Control Tower, SSO の導入
* Application Monorepo の CI/CD の改善
  * shell script を Go でリライト
* Ansible Monorepo の CI/CD の改善
  * CI の高速化, .circleci/config.yml のリファクタリング
* SRE としてアラートハンドリング・ Developer サポート・ ミドルウェアの upgrade
* Go で MongoDB Atlas のリストアジョブの実装
* トイルを解消するためのツールの開発

色々挙げましたが、特に大きいのは Terraform Monorepo の改善です。
こちらについては会社のブログで詳細を公開していますし、 HashiTalks Japan 2021 でも登壇しています。
Terraform State をサービス・環境ごとに分割し、開発者が自分たちのサービスのインフラに関しオーナーシップを持ち、 SRE に依存することなく開発を進められる体制を整えました。
更に、以下のような様々な改善を行いました。

* [tfnotify を Fork して tfcmt というツールを開発し、 terraform plan, apply の結果をよりわかりやすくしました](https://zenn.dev/shunsuke_suzuki/articles/improve-terraform-cicd-with-tfcmt)
* CI Platform を CircleCI から AWS CodeBuild, さらに GitHub Actions へと移行し、セキュリティと Developer Experience を改善
  * [2020-12-03 Terraform の CI/CD を CodeBuild に移行した話](https://blog.studysapuri.jp/entry/2020/12/03/080000)
  * [2022-02-04 Terraform の CI を AWS CodeBuild から GitHub Actions + tfaction に移行しました](https://blog.studysapuri.jp/entry/2022/02/04/080000)
* [コードを Scaffold する GitHub Actions の workflow を提供](https://suzuki-shunsuke.github.io/tfaction/docs/feature/scaffold-working-dir)
* [CI でコードを自動フォーマット](https://suzuki-shunsuke.github.io/tfaction/docs/feature/auto-fix)
* [tflint や tfsec, Conftest によって validation し結果を分かりやすく通知](https://suzuki-shunsuke.github.io/tfaction/docs/feature/linter)
* [Renovate によって Terraform や Terraform Provider などの update を自動化](https://blog.studysapuri.jp/entry/2022/02/18/080000)
* [Plan File を使うことでより安全な apply を実現](https://suzuki-shunsuke.github.io/tfaction/docs/feature/plan-file)
* [apply が失敗した場合のフォローアップを自動化](https://suzuki-shunsuke.github.io/tfaction/docs/feature/follow-up-pr)
* [tfmigrate による migration を CI で行えるようにしました](https://suzuki-shunsuke.github.io/tfaction/docs/feature/tfmigrate)
* [Terraform に関するリポジトリを一つの Monorepo に集約し、 CI のメンテナンス性及び品質を改善](https://blog.studysapuri.jp/entry/2021/04/01/080000)
* [Terraform 以外のツール(miam, roadworker) で管理されていたものを Terraform に移行し、ツールを Terraform に統一し、 Developer Experience を改善](https://blog.studysapuri.jp/entry/2021/08/02/080000)(この際 terraformer で生成されたコードのリファクタリングのために [tfmigrator](https://github.com/tfmigrator/cli) という CLI ツールを開発)
* etc

### 技術スタック

- Shell Script, Go, TypeScript
- AWS, GCP
- k8s
- Datadog, Sentry
- Jenkins, CircleCI, GitHub Actions
- MongoDB (MCM, Atlas)
- Terraform, Ansible
- Renovate: Renovate は導入するのは簡単ですが、人間の負担を減らし、無理なく安全に運用するには高い専門性が求められます。これまで Terraform を始めとして様々なリポジトリの設定をリポジトリに合わせてチューニングしてきました
- Conftest: Terraform や k8s manifest に関する社内の Policy を Conftet で実装してきました。 Policy ごとにドキュメントを作成し、ユーザーに分かりやすく案内するようにしました。 opa fmt による自動フォーマットや、 Policy Testing なども導入しました
  - [Conftest の Policy 違反を分かりやすくする](https://zenn.dev/shunsuke_suzuki/articles/improve-cicd-with-github-comment#conftest-%E3%81%AE-policy-%E9%81%95%E5%8F%8D%E3%82%92%E5%88%86%E3%81%8B%E3%82%8A%E3%82%84%E3%81%99%E3%81%8F%E3%81%99%E3%82%8B)
  - [OPA で Table Driven Tests っぽいことをしてみる](https://techblog.szksh.cloud/opa-table-driven-test/)

## LINE (Corporate Engineer): 2017-04-01 ~ 2019-09-30

LINE では Corporate Engineer として社内システムの開発・運用を行っていました。
Go や Python によってシステム間でデータ連携するようなツールを開発したり、 Confluence や GitHub Enterprise のような社内システムを運用したりしていました。
LINE では独自の Private Cloud が採用されているため、クラウドサービスを活用するというより、 Private Cloud 上で Drone や Graylog のような OSS を導入したりしました。
Jenkins の代わりに Drone を導入して CI を改善したり、ログ管理に Graylog を導入してログ管理を改善したりしました。
Drone は元々部署内向けに導入したものの、他部署でも利用したいという声を受け全社に展開しました。

### 技術スタック

- Go, Python
- k8s, Rancher
- Zabbix, Prometheus, Grafana
- Jenkins, [Drone](https://www.drone.io/)
- Fluentd, Graylog
- Terraform, Ansible

## Donuts (Web Application Engineer): 2015-04-01 ~ 2017-03-31

新卒で Donuts に Web Application Engineer として入社し、自社の Web サービスの開発を行いました。
少人数で開発を行っており、幅広い工程 (設計・開発・テスト・リリース) ・技術領域 (Frontend, Backend, Infrastructure) を経験しました。

### 技術スタック

- Python, JavaScript
- MySQL
- AWS, GCP
- Docker
- Jenkins
- Terraform, Ansible, Packer

## ブログの執筆

業務で行ったことを企業のブログで紹介したり、自分の OSS を個人のブログで紹介したりしています。
日本語が中心ですが、海外の方にも OSS を使ってもらうため、英語でも書いています。

https://github.com/suzuki-shunsuke/profile#blog

## OSS への貢献

様々な OSS に貢献していますが、代表的なところでいうと [Terraform Docker Provider](https://github.com/kreuzwerker/terraform-provider-docker) や [Terraform AWS Provider](https://github.com/hashicorp/terraform-provider-aws) があります。
Terraform Docker Provider では Collaborator として活動しています。
Terraform AWS Provider では AWS AppConfig のサポートなどを行いました。

[Pull Request による貢献のリスト](https://github.com/suzuki-shunsuke/profile#contribution-pull-request)

## OSS の開発

CLI ツールや GitHub Actions などを中心に様々なツールを開発しています。
Go で開発することが多いです。

* [tfcmt](https://github.com/suzuki-shunsuke/tfcmt): [tfnotify](https://github.com/mercari/tfnotify) の Fork. GitHub への通知に特化し、様々な改良を加えています
* [aqua](https://aquaproj.github.io/): 宣言的な CLI Version Manager
* [tfaction](https://github.com/suzuki-shunsuke/tfaction): Terraform Monorepo のための GitHub Actions Collection
* [go-graylog](https://github.com/suzuki-shunsuke/go-graylog): Graylog の Go クライアントと Terraform Provider. 開発は止まっている
* [github-comment](https://github.com/suzuki-shunsuke/github-comment): GitHub にコメントしたり、コメントを非表示にしたりするツール。 CI の結果をユーザーフレンドリーに通知するのに使われている
* [tfmigrator](https://github.com/tfmigrator/cli): Terraform Configuration と State をマイグレーションするためのツール。大規模なマイグレーションや State の分割の際に便利
* etc

tfcmt, tfaction は weekly.tf で、 aqua は zenn で紹介されました。

* [weekly.tf 2022-01-26](https://weekly.tf/issues/weekly-tf-issue-70-monorepos-platform-infra-team-terraform-scale-environment-as-code-995507)
* [weekly.tf 2022-01-19](https://weekly.tf/issues/weekly-tf-issue-69-tools-for-terraform-workflow-tfcmt-compost-trunk-tfnotify-multi-end-deploy-hcl2json-984084)
* [CIで利用するCLIツールをaquaで管理してみよう](https://zenn.dev/zoetro/articles/eee98d772c2483)
* [Productivity Weekly (2022-01-26号)](https://zenn.dev/korosuke613/articles/productivity-weekly-20220126)
* [Productivity Weekly (2022-01-12号)](https://zenn.dev/korosuke613/articles/productivity-weekly-20220112)
