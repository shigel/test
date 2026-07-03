# mizai 実施例②: システムインフラ(構築・運用)走査 2026-07

> **免責**: 本例は mizai スキルの実行プロセスのデモであり、カードの質・新規性判定は走査日(2026-07-03)時点の暫定判定である。FTO調査ではない。本結果はスクリーニングであり、特許侵害調査(FTO)でも網羅的な先行研究調査でもない。
> 本例は要約版。フェーズ別完全ログの基準例は ①在宅介護(kaigo-scan-2026-07.md)を参照。

## 1. 照準ログ(Phase 0)
- 対象領域: システムインフラ(サーバー・ネットワーク・データセンター・クラウド基盤の構築と運用)。広いが「運用(Day-2)」に重心を置き、サブ分割せず走査
- 価値の定義: 運用者(SRE・インフラエンジニア)の負担(トイル・オンコール・認知負荷)と、障害の頻度・影響の削減(呼び出し側プリセット)
- 除外制約: 特定クラウドベンダーの機能追加提案は除外。方法・装置・記法のレベルを優先(同上)
- 走査モード: 全類型掃引 A→H+強制離心(標準)/ 走査日 2026-07-03 / taxonomy 1.0

## 2. 領域地図の要約(Phase 1)
**暗黙前提(12件から抜粋、完全版は走査ログ)**
- [慣習] 障害対応は人間のオンコール輪番が最終防衛線 — https://sre.google/sre-book/being-on-call/
- [経験則] トイルは自動化で減る(実際は2025年に5年ぶり増加、25%→30%。AI投資下でも増)— https://runframe.io/blog/state-of-incident-management-2025
- [慣習] 望ましい状態はIaCで宣言し drift は定期 plan で検出 — https://spacelift.io/blog/terraform-drift-detection
- [経験則] 自動修復は危険なので人間承認を挟む — https://scalr.com/learning-center/terraform-drift-detection-how-to-prevent-and-remediate
- [慣習] 引き継ぎはSlack/文書の申し送り — https://runframe.io/learn/on-call-handoff
- [経験則] 根本原因は事後に人間が相関から再構成する — https://www.pathsolutions.com/blog/why-aiops-tools-struggle
- [法則→崩壊中] 観測はオーバーヘッドゆえ選択的(eBPFが崩しつつある)— https://ebpf.foundation/the-ebpf-foundations-2025-year-in-review/

**イネーブラ(直近5年)**: eBPF主流化(ゼロ計装観測)/LLMインシデント対応(IRCopilot https://arxiv.org/pdf/2505.20945 、Agentic Observability https://arxiv.org/pdf/2602.02585 )/液冷の本番標準化 — https://www.datacenterfrontier.com/cooling/article/55292167/liquid-cooling-comes-to-a-boil-tracking-data-center-investment-innovation-and-infrastructure-at-the-2025-midpoint /DCデジタルツイン — https://arxiv.org/pdf/2410.05133 /浸漬槽の自律ロボット保守 — https://www.tomshardware.com/pc-components/cooling/the-data-center-cooling-state-of-play-2025-liquid-cooling-is-on-the-rise-thermal-density-demands-skyrocket-in-ai-data-centers-and-tsmc-leads-with-direct-to-silicon-solutions

**ワークアラウンド(未言語化需要の化石)**
- W1: IP/VLAN台帳をExcel+ゼロ詰め・アドインで管理 — https://www.ipv4.global/events/network-excel/ , https://checkthenetwork.com/ip-tools-for-excel
- W2: 引き継ぎは「Slackに先月書いた特殊フラグ」等の部族知識+手動シフトレポート — https://upstat.io/blog/oncall-handoff-process-guide
- W3: ポストモーテムのタイムラインをSlackから手作業再構成 — https://rootly.com/sre/automated-postmortem-tools-boost-engineer-learning-f46ac
- W4: 是正項目は文書止まりでチケット化されず放置 — https://incident.io/blog/why-do-post-mortem-action-items-fail-how-to-make-incident-follow-ups-actually-get-done
- W5: driftはコンソール手修正の堆積を定期planで発見し手動import — https://developer.hashicorp.com/terraform/tutorials/state/resource-drift

**棚上げ案(死因付き)**
- G1 AIOps自動根本原因分析 — 死因: 因果文脈の欠如で相関どまり(Gartnerがカテゴリ名を放棄)— https://www.pathsolutions.com/blog/why-aiops-tools-struggle , https://www.augmentcode.com/guides/what-is-aiops
- G2 全社chaos engineering — 死因: 本番破壊への文化抵抗+予防のパラドックス — https://www.gartner.com/peer-community/oneminuteinsights/omi-chaos-engineering-adoption-dop
- G3 Intent-Based Networking — 死因: マーケ乱用による語の汚染+意図→検証ループ未完 — https://www.illumio.com/blog/intent-based-networking , https://blog.ipspace.net/2017/09/intent-based-hype/
- G4 完全自律修復 — 死因: 誤修復の破壊リスクで人間承認が外せない — https://www.env0.com/blog/the-ultimate-guide-to-terraform-drift-detection-how-to-detect-prevent-and-remediate-infrastructure-drift

## 3. 原石一覧(Phase 2: 28件+離心。1行仕様のみ)
強制離心の乱択母集団: 日本標準産業分類・大分類10分野、開始時刻23:12の分の下1桁=2 → 鉱業。
- A1 一次対応権限を故障クラス別に機械へ段階委譲し可逆操作のみ自動実行する運用方法
- A2 全変更に因果IDを貫通させ障害時に因果連鎖を機械再生する「フライトレコーダ」装置・記法
- A3 機械消費専用の圧縮テレメトリ表現(意味注釈付き差分ストリーム)の記法
- A4 全デプロイに微小故障注入を常時混ぜ復元力を連続量として計測する方法
- B1 航空の交代ブリーフィング構造を機械強制する引き継ぎプロトコル記法
- B2 「行動を要求できないアラームは退役」(ISA-18.2)をアラート予算制として自動執行する方法
- B3 システムごとの「カルテ」(既往障害・危険操作・過去の処置)を機械可読で保持する記法
- B4 変更リスクを過去データから保険料率化し自動承認/人間審査を振り分ける方法
- C1 シフト中の調査・操作・仮説を自動収集し次番へ機械可読で渡す「引き継ぎコンパイラ」装置
- C2 是正項目を監視ルールに結び、未実施項目起因の再発を自動表面化させる方法
- C3 コンソール手動変更を検出時にコード差分(PR)へ逆コンパイルする装置
- C4 Excel台帳と実ネットワーク観測を突合し台帳を自己修正する装置
- D1 eBPF全事象記録+トポロジ上でLLMが因果仮説を生成・棄却する根本原因探索法
- D2 修復操作を逆操作証明済みに限定しロールバック保証付きで実行する「可逆修復トランザクション」
- D3 本番でなくデジタルツイン上で連続故障注入する方法
- D4 既存設定+チケット文面から意図を逆推定して差分検証する方法
- E1 [監視×医療] 多数メトリクスを早期警戒スコア(NEWS)方式の単一悪化スコアへ集約する記法
- E2 [冷却×医療] 冷媒ループの「血液検査」(粒子・化学組成分析)で故障予兆を検出する装置
- E3 [容量×保険] 需要スパイクをオプション価格化し予約/オンデマンド構成を導出する方法
- F1 未使用資源・アラートの退役候補を列挙し削除の安全性を証明する方法
- F2 実対応の操作ログとrunbook記述の乖離を検出し陳腐化を自動警告する方法
- F3 可観測性+引き継ぎ+台帳を一人情シス向け単一低運用装置に束ねる方法
- G-1 変更と過去障害の類似度から「危険な匂いスコア」を算出する計測法
- G-2 drift量・手動介入頻度・アラート無視率からインフラ疲労度を計測する記法
- G-3 調査分岐数・文脈切替回数からオンコール認知負荷を計測する方法
- H1 全因果記録+再生で診断時間を2桁縮める装置(現行/理論限界≒2桁)
- H2 アラート発行に「行動可能性の証明」を要求する記法(行動可能率 数%→理論100%≒2桁)
- H3 「読まれる確率」で保持・解像度を決める需要駆動テレメトリ保持法(読取率<0.01%≒4桁)
- E-x1 [離心×鉱業] カナリア指標悪化時に組織全体の変更を自動凍結する「強制退避」プロトコル
- E-x2 [離心×鉱業] 有限資源(IPv4・ポート・ID空間)を鉱床埋蔵量方式で管理する記法
- 離心-時代1950: 全操作を「操作と逆操作の対」で記帳する複式運用記帳(D2に合流)/2050・制約反転: 空振り

## 4. 選別の要約(Phase 3)
統合後22候補。通過6件: K1 因果フライトレコーダ(A2+H1)/K2 アラート失効予算(B2+H2)/K3 可逆修復トランザクション(D2+離心1950)/K4 引き継ぎコンパイラ(C1+B1)/K6 drift逆コンパイラ(C3)/K7 冷媒血液検査(E2)。
落選16件の理由分布: ゲート0(発明性: 制度・製品統合・事業手法)×3/ゲート1(仮定部品が中核: 業界横断データセット・挙動twin・安全性証明器)×3/ゲート3(価値の桁を提示できず)×10。全落選は走査ログに理由付きで記録。

## 5. 敵対的検証ログ(Phase 4: カード化候補分は全列挙)
宣言: 「私はこの案を殺すことが仕事の審査官である。生かす証拠ではなく殺す証拠を探す。」

**K1 存在検索**(6クエリ+墓場)
- Q1 `change event causality tracking infrastructure incident diagnosis tool` → 事後相関の製品・特許群 https://www.bigpanda.io/blog/accelerate-change-alert-discovery-and-incident-resolution-with-root-cause-changes/
- Q2 `change intelligence platform correlate deployments configuration changes incidents` → change intelligence 市場は事後相関 https://www.infoq.com/articles/beyond-monitoring-change-intelligence/
- Q3 `"flight recorder" infrastructure outage replay causal chain` → PyTorch NCCL Flight Recorder(訓練通信限定)、US8082275 https://pytorch.org/blog/flight-recorder-a-new-lens-for-understanding-nccl-watchdog-timeouts/
- Q4 `site:patents.google.com causal graph root cause analysis configuration change propagation` → 観測からの因果推定特許群(US11809267B2等)https://patents.google.com/patent/US11809267B2/en
- Q5 `why is there no distributed tracing for infrastructure changes provenance propagation control plane` → 最接近: SAC'25 CPID論文(K8s制御平面限定・研究のみ)https://arxiv.org/pdf/2411.01336
- Q6 `deployment audit trail cross-system change provenance root cause product` → 貫通因果IDの製品なし https://www.harness.io/blog/devops-audit-trail-introduction-benefits-and-how-harness-does-it
- 墓場 `change correlation observability startup discontinued shut down failed` → 死骸なし/死因: 該当なし
- 判定: **差分新規**(差分: 因果IDの貫通伝搬+決定的再生の実装・適用範囲の未在)

**K2 存在検索**(6クエリ、うち1本墓場兼)
- Q1 `alarm rationalization ISA-18.2 applied to IT monitoring alert management` → IT向けTRは策定中=移転未完 https://www.isa.org/standards-and-publications/isa-standards/isa-18-series-of-standards
- Q2 `automatically retire non-actionable alerts unused alert rules cleanup tool SRE` → Azure SRE Agent は推奨のみ(執行なし)https://techcommunity.microsoft.com/blog/appsonazureblog/azure-sre-agent-for-azure-monitor-alerts-reduce-alert-fatigue-investigate-what-m/4513458
- Q3 `"alert" lifecycle expiration require documented action why alerts never deleted` → 失効+再検証は他領域(SharePoint通知)のみ https://www.mrsharepoint.com/sharepoint-alerts-retirement-guide/
- Q4 `site:patents.google.com alert rationalization actionability monitoring system lifecycle` → フィルタ・エスカレーション特許のみ https://patents.google.com/patent/US20160307100A1
- Q5 `alert quality score enforcement monitoring hygiene actionable rate metric team` → 計測・手動レビュー慣行のみ https://oneuptime.com/blog/post/2026-01-30-alert-quality-metrics/view , https://docs.newrelic.com/docs/tutorial-create-alerts/manage-alert-quality/
- Q6(墓場兼)`alert noise reduction tool shutdown discontinued postmortem failed startup` → 死骸なし/死因: 該当なし
- 判定: **差分新規**(差分: 計測・推奨に対し、行動可能性記録の強制と自動失効の執行機構・記法)

**K7 存在検索**(6クエリ+墓場)
- Q1 `data center liquid cooling coolant quality monitoring particle counter predictive maintenance sensor` → pH/導電率/濁度は既存、粒子計は「advanced」扱い https://datacenterpost.com/predictive-coolant-health-the-missing-reliability-layer-in-ai-data-centers/
- Q2 `direct-to-chip cooling fluid health analysis corrosion biofilm CDU monitoring service` → 定期採取ラボ分析(2〜6ヶ月周期)https://polarislabs.com/direct-to-chip-cooling-fluid-monitoring-in-modern-data-centers/ , https://coolantiq.chemtecenergy.com/
- Q3 `oil analysis condition monitoring applied to data center coolant loop tribology style lab testing` → TestOil/Intertek のオフライン試験 https://testoil.com/advanced-testing/coolant-health-testing-for-data-centers-5-reasons-its-important/
- Q4 `site:patents.google.com coolant monitoring degradation data center liquid cooling sensor` → 漏洩・CDU汚染検知のみ(EP4696890A1)https://patents.google.com/patent/EP4696890A1/zh
- Q5 `inline elemental analysis wear debris coolant identify degrading component source LIBS spectroscopy loop` → LIBS合金分類は潤滑油分野の標準(ASTM D8182)、DCループ適用は反例なし https://store.astm.org/d8182-18.html
- Q6 `why no early warning coolant degradation failure liquid cooled servers outage caused by coolant` → 「Si/Cu/Cr粒子劣化は熱的予兆なしに進行」「郵送ラボで数日待ち」。細菌検知のみリアルタイム化($31M調達)https://www.techtimes.com/articles/319388/20260630/ai-coolant-startup-raises-31m-catch-bacterial-outbreaks-before-gpu-racks-go-dark.htm , https://www.liangditech.com/news/News/what-happens-when-a-liquid-cooling-system-fails.html
- 墓場 `coolant monitoring startup data center discontinued failed shut down` → 死骸なし/死因: 該当なし
- 判定: **差分新規**(差分: 元素組成指紋のインライン連続分析による劣化部位の位置同定)

**検証棄却(要約。早期打ち切り規則適用)**: K3 可逆修復=既存(Berkeley ROC Undo http://roc.cs.berkeley.edu/projects/undo/index.html +US11829796B2+PolicyCortex Safety Sandwich https://policycortex.com/platform/autonomous-remediation )/K4 引き継ぎコンパイラ=既存(PagerDuty Shift/Scribe、Rootly catch-up、Datadog Incident AI https://docs.datadoghq.com/incident_response/incident_management/investigate/incident_ai/ )/K6 drift逆コンパイラ=既存(Firefly codify https://www.firefly.ai/academy/how-to-fix-terraform-drift----and-use-firefly-for-ongoing-monitoring 、Terracotta AI)

**4c/4d**: K1=主類型A(副D)、K2=主類型B(副H)、K7=主類型B(副D。発火Eからのずれ)。残余X なし。反証実験は K1/K2 が48時間可、K7 は[要14日]。

## 6. 発明候補カード(Phase 5: card-schema.md 準拠)

### 発明候補カード INFRA-01: 変更因果フライトレコーダ
- **仮称**: 変更因果フライトレコーダ
- **一行仕様**: 障害調査者のために、CI/CD・クラウドAPI・構成管理・手動操作を貫通する因果IDを全変更に付与し、障害時に因果連鎖を機械再生する装置・記法
- **未在診断**: 主類型A(前提の檻)、副類型D。「分散トレーシングはRPCの要求-応答対にしか適用できない」という前提が制御平面(変更)への適用の着想を遮った。「変更と障害の関係は事後相関で推定するもの」という慣習が檻を補強した。
- **イネーブラ**: OTelコンテキスト伝搬の標準化とK8s制御平面伝搬の研究登場(CPID)— https://arxiv.org/pdf/2411.01336 。eBPFゼロ計装捕捉 — https://ebpf.foundation/the-ebpf-foundations-2025-year-in-review/
- **部品表**: 因果ID発番・伝搬[実在確認済み https://arxiv.org/pdf/2411.01336 ]/変更イベント収集(監査ログ・CI/CDフック)[実在確認済み https://www.harness.io/blog/devops-audit-trail-introduction-benefits-and-how-harness-does-it ]/因果グラフ格納・再生[実在確認済み https://patents.google.com/patent/US11809267B2/en ]/非RPC制御ループ間のID合流規則[仮定]
- **価値仮説**: SREの診断時間(MTTR支配項)。障害の62%は変更起因 — https://citk.com/blog/what-is-change-intelligence 。因果連鎖が記録済みなら診断は時間→分で約2桁改善
- **フェルミ検算**: 変更10^3〜10^4件/日×数KB=数十MB/日(保存費無視可能)。eBPF負荷1〜3%。診断: 数時間の相関探索→再生で数分≒2桁
- **新規性ログ**: §5 K1 の7クエリ全列挙のとおり。最接近先行例: arXiv:2411.01336(K8s限定・研究のみ)+事後相関のchange intelligence製品群/差分: 貫通因果ID+決定的再生の実装は反例なし/判定=**差分新規**
- **死亡条件**: (1) 非RPC制御ループのID合流が組合せ爆発し再生不能 (2) クラウド監査ログの粒度では手動操作の因果起点を特定できない
- **最小実験**: 48時間 — 小規模K8s+Terraform+CIにwebhook/annotationで変更ID伝搬を実装、注入障害10件の診断時間を記録あり/なしで比較
- **先行指標**: OTelのcontrol-plane伝搬標準化/CPID後続実装/監査ログへの相関ID標準追加/change intelligence製品の事前記録化
- **確信度**: 中(仮定部品1件だが合流規則のスケール未検証)
- **メタ**: 走査日2026-07-03/taxonomy 1.0/全類型掃引

### 発明候補カード INFRA-02: アラート失効予算
- **仮称**: アラート失効予算(行動可能性の執行機構)
- **一行仕様**: オンコール担当者のために、全アラートルールに「要求される操作者行動」の記録を義務付け、記録なき・行動実績なきルールを予算内で自動失効させる方法・記法
- **未在診断**: 主類型B(領域の断絶)、副類型H。プラント計装のアラーム管理(ISA-18.2)とIT監視は学会・業界誌・人材が重ならず規律が移転しなかった。IT側は「うるさければミュート」という満足化で探索が止まった。
- **イネーブラ**: ISA-18のIT向けTR(Alerts, Events, Prompts)策定開始 — https://www.isa.org/standards-and-publications/isa-standards/isa-18-series-of-standards 。行動可能率計測の普及 — https://oneuptime.com/blog/post/2026-01-30-alert-quality-metrics/view
- **部品表**: ルールの合理化記録欄[実在確認済み https://www.isa.org/getmedia/55b4210e-6cb2-4de4-89f8-2b5b6b46d954/PAS-Understanding-ISA-18-2.pdf ]/行動実績の自動計測[実在確認済み https://docs.newrelic.com/docs/tutorial-create-alerts/manage-alert-quality/ ]/失効・再検証ワークフロー[実在確認済み https://www.mrsharepoint.com/sharepoint-alerts-retirement-guide/ ]
- **価値仮説**: オンコールのページ負荷と信頼毀損。行動可能率 数%→70-80%水準で夜間ページ1桁以上削減、アラート不信起因の見逃しを削減
- **フェルミ検算**: アラート10^2〜10^3件/週、行動可能率5%→50%でページ1/10。実装は監視スタックのポリシー層のみ≒10^1人日
- **新規性ログ**: §5 K2 の6クエリ全列挙のとおり。最接近先行例: Azure SRE Agentの改善推奨+New Relic alert quality管理/差分: 既存は計測と推奨、発行時の行動可能性強制+自動失効の執行機構は反例なし/判定=**差分新規**
- **死亡条件**: (1) 失効させた低頻度アラートが重大障害の唯一の検知線だった事例で組織が機構を無効化 (2) 記録記入コストがミュート運用より高く形骸化
- **最小実験**: 48時間 — 1チームのルール群にシャドーモードで失効政策を適用し、行動記録なしルールの比率と、失効候補が過去90日に実障害を検知した回数を測定
- **先行指標**: ISA-18 IT向けTR発行/監視SaaSへの「required action」欄追加/オンコール負荷の労務問題化
- **確信度**: 中(部品は全て実在確認済みだが組織的受容が最大の不確実性)
- **メタ**: 走査日2026-07-03/taxonomy 1.0/全類型掃引

### 発明候補カード INFRA-03: 冷媒血液検査
- **仮称**: 冷媒血液検査(インライン摩耗粒子組成による劣化部位同定)
- **一行仕様**: 液冷データセンター運用者のために、冷却ループ冷媒中の粒子の元素組成をインライン連続分析し、どの部材(銅冷板・アルミCDU・シール)が劣化中かを位置同定する装置
- **未在診断**: 主類型B(領域の断絶)、副類型D。摩耗粒子の合金分類は潤滑油分析業界の標準(ASTM D8182)だが、同業界とDC運用は人材・業界誌が重ならず移転しなかった。液冷の本番標準化は2025年で需要自体が若い。
- **イネーブラ**: 液冷主流化 — https://www.datacenterfrontier.com/cooling/article/55292167/liquid-cooling-comes-to-a-boil-tracking-data-center-investment-innovation-and-infrastructure-at-the-2025-midpoint 。LIBS摩耗粒子分類の標準化 — https://store.astm.org/d8182-18.html 。冷媒監視への投資機運 — https://www.techtimes.com/articles/319388/20260630/ai-coolant-startup-raises-31m-catch-bacterial-outbreaks-before-gpu-racks-go-dark.htm
- **部品表**: インラインLIBS/分光ユニット[実在確認済み https://store.astm.org/d8182-18.html ]/ループのバイパス採取部(CDU計装)[実在確認済み https://www.us.endress.com/en/endress-hauser-group/press-center/news-and-press-releases/how-does-liquid-cooling-in-a-CDU-improve-data-center-efficiency ]/材質→劣化源対応表(Cu=冷板, Al=CDU, Si=シール)[実在確認済み https://www.liangditech.com/news/News/what-happens-when-a-liquid-cooling-system-fails.html ]/水系冷媒向けLIBS感度較正[仮定]
- **価値仮説**: 液冷DC運用者/熱的予兆なしに進行する劣化起因の突発停止(冷却起因は未計画停止の約1/5)/郵送ラボの数日遅延→連続監視でリードタイム2桁短縮、GPUラック停止(数時間・数千万円規模)を予防
- **フェルミ検算**: センサ+配管10^4〜10^5円/ループ vs 保護対象10^8円+停止損失。分析周期2〜6ヶ月→連続=時間分解能10^3倍
- **新規性ログ**: §5 K7 の7クエリ全列挙のとおり。最接近先行例: DC冷媒ラボ分析(TestOil/Polaris)+pH・導電率インライン監視+細菌リアルタイム監視/差分: 元素組成指紋による劣化部位の位置同定のインライン化は反例なし/判定=**差分新規**
- **死亡条件**: (1) 水系冷媒中の金属粒子濃度がインラインLIBS検出限界以下で予兆リードタイムが得られない (2) 細菌監視勢が組成分析へ拡張し実質同一品を先行投入
- **最小実験**: [要14日] — 試験ループに銅腐食片・シール摩耗粉を段階播種し、組成検知が熱・流量偏差より先行することを確認(48時間では劣化統計不能のため最小統計単位14日)
- **先行指標**: 細菌監視勢の機能拡張/OCP等での冷媒品質テレメトリ標準化/インラインLIBS低価格化/冷媒起因障害の保険商品化
- **確信度**: 中(仮定部品1件だが検出限界が物理的リスク)
- **メタ**: 走査日2026-07-03/taxonomy 1.0/全類型掃引

## 7. 帰還レポート(Phase 6)
**類型別ヒット率**(分子=4c最終診断の主類型): A 4→1(INFRA-01)/B 4→2(INFRA-02, INFRA-03)/C 4→0/D 4→0/E 3→0/F 3→0/G 3→0/H 3→0/離心 2→0。INFRA-03 は発火E→最終診断Bのずれあり(掃引の非自明セルは断絶の座標を指す、というオペレータ較正情報)。
**棄却分布**: ゲート0×3、ゲート1×3、ゲート3×10、Phase 4a 既存×3(可逆修復・引き継ぎコンパイラ・drift逆コンパイラ。いずれも2024〜2026の製品ラッシュが先着)。**残余X: なし**。
**改訂提案**: (1) C類型はこの領域では発見→製品化の遅延が1〜2年しかなく、走査鮮度の要求が高い(C原石は最新4半期の情報で裏取りすべき) (2) EオペレータにB判別(業界の重なり確認)を組み込む (3) Gオペレータの二階(計測の上に建つ発明)記入を必須化。
**最有望**: INFRA-03。部品が全て枯れており(LIBS+CDU計装)、液冷主流化という新鮮な死因解消があり、隣接する資金調達($31M、細菌限定)が需要を実証しつつ組成分析の空白を残しているため。

---
走査日 2026-07-03 / taxonomy 1.0 / mizai スキル実行: Claude Code
