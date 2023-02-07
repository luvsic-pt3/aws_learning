- ELB (Elastic Load Balancing) には3つのLBがある
  - ALB (Application Load Balancer)
  - NLB (Network Load Balancer)
  - CLB (Classic Load Balancer)

- プロトコルがHTTP(S)なのであればALBが無難。HTTP(S)以外のTCPまたはUDPの場合はNLB。
  - CLBの機能のほとんどはALBとNLBでカバーされているので、CLBを使うのは稀

- NLB
  - ALBよりも高いトラフィック処理に対応している
  - LBのIPを固定できる
- ALB
  - ターゲットにLambdaを指定できる

- ELBの特徴
  - 複数AZに負荷分散することができる
    - 1つのAZで障害が発生しても、別のAZで処理を続けることができる
  - 自動スケーリング機能
    - CPUなどがしきい値を超えた場合に自動でEC2インスタンスを増やすことができる
  - ヘルスチェック機能
    - 異常なインスタンスへの振り分けを停止し、正常なもののみに振り分ける
  - モニタリング
    - CloudWatchによる監視、アクセスログをS3で保存、CloudTrailによるAPI監視など

