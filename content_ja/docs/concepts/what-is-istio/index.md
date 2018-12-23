---
title: Istioとは?
description: Istioの紹介、解決する問題、アーキテクチャとデザインのゴール
weight: 15
aliases:
    - /docs/concepts/what-is-istio/overview
    - /docs/concepts/what-is-istio/goals
    - /about/intro
---

クラウドプラットフォームは、それを使用する組織に豊富なメリットをもたらします。ただし、クラウドを採用することでDevOpsチームに負担がかかる可能性があることは否定できません。
開発者は移植性を考慮して設計するためにマイクロサービスを使用する必要があります。一方、運用者は非常に大規模なハイブリッドおよびマルチクラウドのデプロイを管理しています。
Istioを使用することで、サービスが接続、保護、制御、および監視できるようになります。

Istioはこれらのデプロイの複雑さを軽減し、開発チームの負担を軽減します。それは既存の分散アプリケーションの上に透過的に重なる完全にオープンソースのサービスメッシュです。
また、あらゆるロギング、テレメトリまたはポリシーシステムに統合できるようにするAPIを含むプラットフォームもあります。
Istioの多様な機能によって、分散マイクロサービスアーキテクチャを効果的かつ効率的に実行できます。また、マイクロサービスを保護、接続、および監視するための統一された方法を提供します。

## サービスメッシュとは？

Istioは、モノリシックアプリケーションが分散型マイクロサービスアーキテクチャに移行するときに、開発者や運用者が直面する課題を解決します。
その方法を知るには、Istioのサービスメッシュをさらに詳しく調べると良いでしょう。

サービスメッシュという用語は、アプリケーションを構成するマイクロサービスのネットワークとそれらの間の相互作用を表すために使用されます。
サービスメッシュの大きさと複雑さが増すにつれて、理解と管理が難しくなります。その要件には、ディスカバリー、ロードバランシング、障害回復、メトリック、および監視が含まれます。
サービスメッシュには、A/Bテスト、カナリアリリース、レート制限、アクセス制御、エンドツーエンド認証など、より複雑な運用要件もあります。

Istioは、サービスメッシュ全体の振る舞いの可視化と運用管理を提供し、マイクロサービスアプリケーションの多様な要件を満たすための完全なソリューションを提供します。

## なぜIstioを使うのか?

Istioを使用すると、ロードバランシング、サービス間認証、監視などを使用して、サービスのコードを[ほとんど](/docs/tasks/telemetry/distributed-tracing/overview/#understanding-what-happened)変更することなく、デプロイしたサービスのネットワークを簡単に作成できます。
マイクロサービス間のすべてのネットワーク通信を傍受する特別なサイドカープロキシを環境全体にデプロイしてIstioをサービスに追加し、そのコントロールプレーンの機能を使用してIstioを設定、管理します。コントロールプレーンの機能は：

* HTTP、gRPC、WebSocket、およびTCPトラフィックの自動ロードバランシング

* 豊富なルーティングルール、リトライ、フェイルオーバー、およびフォルトインジェクションを使用した、トラフィックのきめ細かい制御。

* アクセス制御、レート制限、クォータをサポートするプラガブルなポリシーレイヤと設定API。

* クラスターの受信と送信を含む、クラスター内のすべてのトラフィックの自動メトリック、ログ、およびトレース。

* IDベースの強力な認証と認可を使用した、クラスタ内のセキュアなサービス間通信。

Istioは拡張性を考慮して設計されており、さまざまなデプロイのニーズを満たします。

## 主要機能

Istioは、サービスのネットワーク全体にわたって多数の主要機能を提供します。

### トラフィック管理

Istioの簡単なルール設定とトラフィックルーティングにより、サービス間のトラフィックの流れとAPI呼び出しを制御できます。
Istioは、サーキットブレーカー、タイムアウト、リトライなどのサービスレベルプロパティの設定を単純化し、A / Bテスト、カナリアロールアウト、および段階的ロールアウトなどの重要なタスクをパーセンテージベースのトラフィック分割で設定するのを容易にします。

トラフィックの視認性が向上し、これまでと異なる障害回復機能があるため、どんな状況であっても問題が発生する前に問題を察知して、通信の信頼性を高め、ネットワークをより堅牢にすることができます。

### セキュリティ

Istioのセキュリティ機能により、開発者はアプリケーションレベルのセキュリティに集中することができます。
Istioは、基盤となる安全な通信チャネルを提供し、サービス通信の認証、認可、および暗号化を大規模に管理します。
Istioでは、サービス通信はデフォルトで保護されているため、アプリケーションをほとんど変更することなく、さまざまなプロトコルやランタイムにわたって一貫してポリシーを適用できます。

IstioはKubernetes（またはインフラストラクチャ）のネットワークポリシーと一緒に使用することでプラットフォームに依存しませんが、ネットワークおよびアプリケーション層でのPod-to-PodまたはService-to-Service通信を保護する機能など、利点はさらに大きくなります。

### 可観察性

Istioの強力なトレース、監視、およびロギングにより、サービスメッシュのデプロイに関する深い洞察が得られます。
カスタムダッシュボードですべてのサービスのパフォーマンスを可視化し、そのパフォーマンスが他のプロセスにどのように影響しているかを確認しながら、サービスのパフォーマンスがアップストリームおよびダウンストリームにどのように影響するかを実際に理解できます。

IstioのMixerコンポーネントは、ポリシー管理とテレメトリ収集を担当します。
バックエンドの抽象化と仲介を行ない、個々のインフラストラクチャバックエンドの実装の詳細からIstioの他のコンポーネントを隔離し、メッシュとインフラストラクチャバックエンド間のすべての相互作用を細かく制御できるようにします。

これらすべての機能により、サービスのSLOをより効果的に設定、監視、および実施できます。もちろん、肝心な点は、問題を迅速かつ効率的に検出して修正できることです。

### プラットフォームのサポート

* Service deployment on Kubernetes

* Services registered with Consul

* Services running on individual virtual machines

Istioはプラットフォームに依存せず、クラウド、オンプレミス、Kubernetes、Mesosなど、さまざまな環境で動作するように設計されています。
Kubernetes、またはNomad with ConsulにIstioをデプロイできます。Istioがは現在サポートしているのは：

* Kubernetesでのサービスデプロイ

* Consulに登録されているサービス

* 個々の仮想マシンで実行されているサービス

### 統合とカスタマイズ

Istioのポリシー適用コンポーネントは、ACL、ロギング、監視、クォータ、監査などの既存のソリューションと統合するように拡張およびカスタマイズできます。

## Architecture

An Istio service mesh is logically split into a **data plane** and a **control
plane**.

* The **data plane** is composed of a set of intelligent proxies
  ([Envoy](https://www.envoyproxy.io/)) deployed as sidecars. These proxies
  mediate and control all network communication between microservices along
  with [Mixer](/docs/concepts/policies-and-telemetry/), a general-purpose
  policy and telemetry hub.

* The **control plane** manages and configures the proxies to route traffic.
  Additionally, the control plane configures Mixers to enforce policies and
  collect telemetry.

The following diagram shows the different components that make up each plane:

{{< image width="80%"
    link="./arch.svg"
    alt="The overall architecture of an Istio-based application."
    caption="Istio Architecture"
    >}}

### Envoy

Istio uses an extended version of the
[Envoy](https://envoyproxy.github.io/envoy/) proxy. Envoy is a high-performance
proxy developed in C++ to mediate all inbound and outbound traffic for all
services in the service mesh. Istio leverages Envoy’s many built-in features,
for example:

* Dynamic service discovery
* Load balancing
* TLS termination
* HTTP/2 and gRPC proxies
* Circuit breakers
* Health checks
* Staged rollouts with %-based traffic split
* Fault injection
* Rich metrics

Envoy is deployed as a **sidecar** to the relevant service in the same
Kubernetes pod. This deployment allows Istio to extract a wealth of signals
about traffic behavior as
[attributes](/docs/concepts/policies-and-telemetry/#attributes). Istio can, in
turn, use these attributes in [Mixer](/docs/concepts/policies-and-telemetry/)
to enforce policy decisions, and send them to monitoring systems to provide
information about the behavior of the entire mesh.

The sidecar proxy model also allows you to add Istio capabilities to an
existing deployment with no need to rearchitect or rewrite code. You can read
more about why we chose this approach in our [Design
Goals](/docs/concepts/what-is-istio/#design-goals).

### Mixer

[Mixer](/docs/concepts/policies-and-telemetry/) is a platform-independent
component. Mixer enforces access control and usage policies across the service
mesh, and collects telemetry data from the Envoy proxy and other services. The
proxy extracts request level
[attributes](/docs/concepts/policies-and-telemetry/#attributes), and sends them
to Mixer for evaluation. You can find more information on this attribute
extraction and policy evaluation in our [Mixer Configuration
documentation](/docs/concepts/policies-and-telemetry/#configuration-model).

Mixer includes a flexible plugin model. This model enables Istio to interface
with a variety of host environments and infrastructure backends. Thus, Istio
abstracts the Envoy proxy and Istio-managed services from these details.

### Pilot

[Pilot](/docs/concepts/traffic-management/#pilot-and-envoy) provides
service discovery for the Envoy sidecars, traffic management capabilities
for intelligent routing (e.g., A/B tests, canary deployments, etc.),
and resiliency (timeouts, retries, circuit breakers, etc.).

Pilot converts high level routing rules that control traffic behavior into
Envoy-specific configurations, and propagates them to the sidecars at runtime.
Pilot abstracts platform-specific service discovery mechanisms and synthesizes
them into a standard format that any sidecar conforming with the [Envoy data
plane APIs](https://github.com/envoyproxy/data-plane-api) can consume. This
loose coupling allows Istio to run on multiple environments such as Kubernetes,
Consul, or Nomad, while maintaining the same operator interface for traffic
management.

### Citadel

[Citadel](/docs/concepts/security/) enables strong service-to-service and
end-user authentication with built-in identity and credential management. You
can use Citadel to upgrade unencrypted traffic in the service mesh. Using
Citadel, operators can enforce policies based on service identity rather than
on relatively unstable layer 3 or layer 4 network identifiers. Starting from
release 0.5, you can use [Istio's authorization feature](/docs/concepts/security/#authorization)
to control who can access your services.

### Galley

Galley validates user authored Istio API configuration on behalf of
the other Istio control plane components. Over time, Galley will take
over responsibility as the top-level configuration ingestion, processing and
distribution component of Istio. It will be responsible for insulating
the rest of the Istio components from the details of obtaining user
configuration from the underlying platform (e.g. Kubernetes).

## Design Goals

A few key design goals informed Istio’s architecture. These goals are essential
to making the system capable of dealing with services at scale and with high
performance.

* **Maximize Transparency**: To adopt Istio, an operator or developer is
  required to do the minimum amount of work possible to get real value from the
  system. To this end, Istio can automatically inject itself into all the
  network paths between services. Istio uses sidecar proxies to capture traffic
  and, where possible, automatically program the networking layer to route
  traffic through those proxies without any changes to the deployed application
  code. In Kubernetes, the proxies are injected into pods and traffic is
  captured by programming ``iptables`` rules. Once the sidecar proxies are
  injected and traffic routing is programmed, Istio can mediate all traffic.
  This principle also applies to performance. When applying Istio to a
  deployment, operators see a minimal increase in resource costs for the
  functionality being provided. Components and APIs must all be designed with
  performance and scale in mind.

* **Extensibility**: As operators and developers become more dependent on the
  functionality that Istio provides, the system must grow with their needs.
  While we continue to add new features, the greatest need is the ability to
  extend the policy system, to integrate with other sources of policy and
  control, and to propagate signals about mesh behavior to other systems for
  analysis. The policy runtime supports a standard extension mechanism for
  plugging in other services. In addition, it allows for the extension of its
  vocabulary to allow policies to be enforced based on new signals that the
  mesh produces.

* **Portability**: The ecosystem in which Istio is used varies along many
  dimensions. Istio must run on any cloud or on-premises environment with
  minimal effort. The task of porting Istio-based services to new environments
  must be trivial. Using Istio, you are able to operate a single service
  deployed into multiple environments. For example, you can deploy on multiple
  clouds for redundancy.

* **Policy Uniformity**: The application of policy to API calls between
  services provides a great deal of control over mesh behavior. However, it can
  be equally important to apply policies to resources which are not necessarily
  expressed at the API level. For example, applying a quota to the amount of
  CPU consumed by an ML training task is more useful than applying a quota to
  the call which initiated the work. To this end, Istio maintains the policy
  system as a distinct service with its own API rather than the policy system
  being baked into the proxy sidecar, allowing services to directly integrate
  with it as needed.
