# 職務経歴

[GitHub](https://github.com/suzuki-shunsuke) | [Twitter](https://twitter.com/szkdash)

## 要約

2015 年から約 9 年間ソフトウェアエンジニアとして従事し、 Backend Engineer や Corporate Engineer を経て現在は SRE や Platform Engineer として活動しています。
現職では 2022/07 より Mercari で Platform Engineer として開発者向けにツールの開発や技術支援、 CI/CD の改善などを行っています。
前職では Recruit で SRE としてサービスの信頼性改善に取り組みつつ、プロダクトチームが自己完結的に開発からリリースまで行えるよう、セルフサービス化やツール・ CI/CD Pipeline の開発・運用を行いました。
特に Terraform Monorepo の workflow の改善に数年取り組んでおり、プロダクトチームが Terraform を使って安全かつ快適に自分たちでプロダクトのインフラを用意できる環境づくりをしています。

OSS への貢献や開発にも力を入れており、 [aqua](https://aquaproj.github.io/) や [tfcmt](https://github.com/suzuki-shunsuke/tfcmt), [tfaction](https://github.com/suzuki-shunsuke/tfaction) を始めとした様々なツールを開発し、ソフトウェアによる問題解決に取り組んでいます。

ブログの執筆といった形で社内外への情報発信も積極的に行っております。

## 職務経歴

Quipper から Recruit への所属の変更は、 Recruit の組織再編によるものであり、転職ではありません。

在籍期間 | 企業名 | ポジション | ロール
--- | --- | --- | ---
2024-08 / Now | . | . | .
2022-07 / 2024-07 | [Mercari](https://about.mercari.com/) | Platform Engineer | Member
2021-10 / 2022-06 | [Recruit](https://www.recruit.co.jp/) | SRE | Member
2019-10 / 2021-09 | [Quipper Limited Japan Branch](https://www.quipper.com/) | SRE | Member
2017-04 / 2019-09 | [LINE Corporation](https://linecorp.com/en/) | Corporate Engineer | Member
2015-04 / 2017-03 | [Donuts Co. Ltd.](https://www.donuts.ne.jp/) | Web Application Engineer | Member, Tech Lead

## Mercari (Platform Engineer) 2022-07-01 ~ 2024-07-31

Mercari の [Platform Group](https://apply.workable.com/mercari/j/111722DA96/) の [Platform Developer Experience (DX) team](https://engineering.mercari.com/en/blog/entry/20220125-developer-experience-at-mercari/) で Platform Engineer として、 Product 開発を支援するツールや CI/CI pipeline の開発を行っていました。 7 人ほどのチームの 1 メンバーとして仕事していました。
幾つかの Project のリードを担当していました。
主に以下のようなことに携わっていました。

- Terraform Module や [k8s-kit](https://engineering.mercari.com/blog/entry/20220127-kubernetes-configuration-management-with-cue/), ChatBot の開発
- Terraform や Terraform Module, Provider の Upgrade
- BigQuery DataSet の Terraform 管理
- Renovate の導入、設定のチューニング
- [aqua](https://aquaproj.github.io/) の導入
- CI/CD pipeline の改善
  - Docker Image のビルドの高速化
  - [tfcmt](https://github.com/suzuki-shunsuke/tfcmt) の導入
  - [tfmigrate](https://github.com/minamijoyo/tfmigrate) の導入

Platform DX team では Platform の Developer Experience を高めるべく様々なツールを開発しており、私も日々それらの開発を行っていました。

Mercari の Terraform Monorepo は Terraform State の数が 1,000 を超える非常に大きな Monorepo であり、全 working directory に対して Module の upgrade などの変更を適用する場合、自動化が不可欠です。そこで Pull Request の作成から Terraform State の Migration, Merge まで安全に行う workflow を実装していました。

tfmigrate を導入し、 CI を通じて Terraform State 操作を行えるようにもしました。これまで管理者のみが手作業が行っていた State 操作をコードで誰でも安全に行えるようになり、履歴も残るようになりました。この仕組みを活用し、歴史的経緯によりコード管理されていなかった大量の BigQuery DataSet の import も行い、 Terraform を使って管理するようにしました。

Renovate を導入しツールのアップデートを自動化したり、 [aqua](https://aquaproj.github.io/) や [tfcmt](https://github.com/suzuki-shunsuke/tfcmt), [github-comment](https://github.com/suzuki-shunsuke/github-comment) といったツールを導入することで Developer Experience を改善しました。

### 技術スタック

- Shell Script, Go
- [CUE](https://cuelang.org/)
- Google Cloud, AWS (メインは Google Cloud)
- k8s (GKE)
- GitHub Actions, Cloud Build, CircleCI
- Terraform
- Datadog, PagerDuty
- Renovate

## Recruit, Quipper (SRE) 2019-10-01 ~ 2022-06-30

https://brand.studysapuri.jp/career/position/sre

プロダクト横断の SRE チームのメンバーとして自社プロダクトのためのプラットフォームの運用・開発を行っていました。
国内向けの「スタディサプリ小・中・高校講座、大学受験講座」、海外向けの「Quipper Video, Quipper School」といった教育に関するプロダクトに関わっていました。

7 人ほどのチームの 1 メンバーとして仕事していました。

プロダクトは主に AWS の EKS 上で動いており、 Google Cloud も一部使っていました。

- Terraform Monorepo の改善
- AWS Organizations, Control Tower, SSO の導入
- Application Monorepo の CI/CD の改善
  - shell script を Go でリライト
- Ansible Monorepo の CI/CD の改善
  - CI の高速化, .circleci/config.yml のリファクタリング
- SRE としてアラートハンドリング・ Developer サポート・ ミドルウェアの upgrade
- Go で MongoDB Atlas のリストアジョブの実装
- トイルを解消するためのツールの開発

色々挙げましたが、特に大きいのは Terraform Monorepo の改善でした。
こちらについては会社のブログで詳細を公開していますし、 [HashiTalks Japan 2021](https://events.hashicorp.com/hashitalksjapan2021) でも登壇しました。
Terraform State をサービス・環境ごとに分割し、開発者が自分たちのサービスのインフラに関しオーナーシップを持ち、 SRE に依存することなく開発を進められる体制を整えました。
更に、以下のような様々な改善を行いました。

- [tfnotify を Fork して tfcmt というツールを開発し、 terraform plan, apply の結果をよりわかりやすくしました](https://zenn.dev/shunsuke_suzuki/articles/improve-terraform-cicd-with-tfcmt)
- CI Platform を CircleCI から AWS CodeBuild, さらに GitHub Actions へと移行し、セキュリティと Developer Experience を改善
  - [2020-12-03 Terraform の CI/CD を CodeBuild に移行した話](https://blog.studysapuri.jp/entry/2020/12/03/080000)
  - [2022-02-04 Terraform の CI を AWS CodeBuild から GitHub Actions + tfaction に移行しました](https://blog.studysapuri.jp/entry/2022/02/04/080000)
- [コードを Scaffold する GitHub Actions の workflow を提供](https://suzuki-shunsuke.github.io/tfaction/docs/feature/scaffold-working-dir)
- [CI でコードを自動フォーマット](https://suzuki-shunsuke.github.io/tfaction/docs/feature/auto-fix)
- [tflint や tfsec, Conftest によって validation し結果を分かりやすく通知](https://suzuki-shunsuke.github.io/tfaction/docs/feature/linter)
- [Renovate によって Terraform や Terraform Provider などの update を自動化](https://blog.studysapuri.jp/entry/2022/02/18/080000)
- [Plan File を使うことでより安全な apply を実現](https://suzuki-shunsuke.github.io/tfaction/docs/feature/plan-file)
- [apply が失敗した場合のフォローアップを自動化](https://suzuki-shunsuke.github.io/tfaction/docs/feature/follow-up-pr)
- [tfmigrate による migration を CI で行えるようにしました](https://suzuki-shunsuke.github.io/tfaction/docs/feature/tfmigrate)
- [Terraform に関するリポジトリを一つの Monorepo に集約し、 CI のメンテナンス性及び品質を改善](https://blog.studysapuri.jp/entry/2021/04/01/080000)
- [Terraform 以外のツール(miam, roadworker) で管理されていたものを Terraform に移行し、ツールを Terraform に統一し、 Developer Experience を改善](https://blog.studysapuri.jp/entry/2021/08/02/080000)(この際 terraformer で生成されたコードのリファクタリングのために [tfmigrator](https://github.com/tfmigrator/cli) という CLI ツールを開発)
- etc

### 技術スタック

- Shell Script, Go, TypeScript
- AWS, Google Cloud
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
- AWS, Google Cloud
- Docker
- Jenkins
- Terraform, Ansible, Packer

## ブログの執筆

業務で行ったことを企業のブログで紹介したり、自分の OSS を個人のブログで紹介したりしています。
日本語が中心ですが、海外の方にも OSS を使ってもらうため、英語でも書いています。

https://suzuki-shunsuke.github.io/profile/blog

## OSS への貢献

様々な OSS に貢献していますが、代表的なところでいうと [Terraform Docker Provider](https://github.com/kreuzwerker/terraform-provider-docker) や [Terraform AWS Provider](https://github.com/hashicorp/terraform-provider-aws) があります。
Terraform Docker Provider では Collaborator として活動しています。
Terraform AWS Provider では AWS AppConfig のサポートなどを行いました。

[Pull Request による Contribution のリスト](https://suzuki-shunsuke.github.io/profile/oss-contribution)

## OSS の開発

CLI ツールや GitHub Actions などを中心に様々なツールを開発しています。
Go で開発することが多いです。

- [aqua](https://aquaproj.github.io/): 宣言的な CLI Version Manager
- [tfcmt](https://github.com/suzuki-shunsuke/tfcmt): [tfnotify](https://github.com/mercari/tfnotify) の Fork. GitHub への通知に特化し、様々な改良を加えています
- [tfaction](https://github.com/suzuki-shunsuke/tfaction): Terraform Monorepo のための GitHub Actions Collection
- [github-comment](https://github.com/suzuki-shunsuke/github-comment): GitHub にコメントしたり、コメントを非表示にしたりするツール。 CI の結果をユーザーフレンドリーに通知するのに使われている
- [go-graylog](https://github.com/suzuki-shunsuke/go-graylog): Graylog の Go クライアントと Terraform Provider. 開発は止まっている
- [tfmigrator](https://github.com/tfmigrator/cli): Terraform Configuration と State をマイグレーションするためのツール。大規模なマイグレーションや State の分割の際に便利
- etc

tfcmt, tfaction は weekly.tf で、 aqua は zenn で紹介されました。

- [weekly.tf 2022-01-26](https://weekly.tf/issues/weekly-tf-issue-70-monorepos-platform-infra-team-terraform-scale-environment-as-code-995507)
- [weekly.tf 2022-01-19](https://weekly.tf/issues/weekly-tf-issue-69-tools-for-terraform-workflow-tfcmt-compost-trunk-tfnotify-multi-end-deploy-hcl2json-984084)
- [CIで利用するCLIツールをaquaで管理してみよう](https://zenn.dev/zoetro/articles/eee98d772c2483)
- [Productivity Weekly (2022-01-26号)](https://zenn.dev/korosuke613/articles/productivity-weekly-20220126)
- [Productivity Weekly (2022-01-12号)](https://zenn.dev/korosuke613/articles/productivity-weekly-20220112)
