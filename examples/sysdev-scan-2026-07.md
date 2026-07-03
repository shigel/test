# mizai 実施例: システム開発(設計・実装・レビュー・テスト・保守)走査 2026-07-03 【要約版】

> **免責**: 本例は mizai スキルの実行プロセスのデモであり、カードの質・新規性判定は走査日(2026-07-03)時点の暫定判定である。FTO調査ではない。
>
> 走査日: 2026-07-03 / taxonomy 1.0 / 走査モード: 全類型掃引(標準)。完全ログの基準例は「在宅介護」実施例を参照。本例は要約版であり、中間成果物(00〜06)は走査時の作業領域に保存した。

## 1. 照準ログ(Phase 0)

- 対象領域: システム開発(ソフトウェア開発の実務)。プリセットにより「実務プロセス(設計〜保守)」に限定済みと判断、サブ領域分割せず
- (a) 価値の定義: 開発者の認知負荷と、本番障害・品質事故の削減
- (b) 除外制約: 特定ベンダー製品の機能追加提案は除外。方法・装置・記法のレベルを優先
- (c) 走査モード: 全類型掃引(A→H)。ユーザーへの質問はプリセットにより省略

## 2. 領域地図の要約(Phase 1、12クエリ・4系統)

### 支配的アプローチ
- PRレビュー+CI/CDが標準。AI採用はスループットと正相関だが不安定性も増(DORA 2025) https://www.splunk.com/en_us/blog/learn/state-of-devops.html https://devops.com/dora-2025-faster-but-are-we-any-better/
- LLMコードレビューは大規模運用段階(Atlassian: PRサイクル30.8%短縮、解決率は人間コメント未満) https://arxiv.org/html/2601.01129v1
- 障害対応はブレームレス・ポストモーテムが標準 https://sre.google/workbook/postmortem-culture/

### 直近イネーブラ
- AI支援の主流化(84%利用/プロの51%が毎日)と信頼の逆行(出力を信頼29%のみ) https://survey.stackoverflow.co/2025/ai https://stackoverflow.blog/2025/12/29/developers-remain-willing-but-reluctant-to-use-ai-the-2025-developer-survey-results-are-here/
- AIによる暗黙知の写像(Meta)・生成ドキュメント常時更新(Google Code Wiki) https://engineering.fb.com/2026/04/06/developer-tools/how-meta-used-ai-to-map-tribal-knowledge-in-large-scale-data-pipelines/ https://kartaca.com/en/stop-documenting-start-understanding-a-deep-dive-into-googles-code-wiki/
- フラグ掃除の自動化(Uber Piranha 系) https://medium.com/@sandeepchakravartty/piranha-automated-flag-debt-refactoring-at-uber-240c8f1309a1
- 決定的リプレイ×AIデバッグの接続 https://debugg.ai/resources/deterministic-replay-meets-debug-ai-time-travel-debugging-llm-reproduce

### ワークアラウンド(未言語化需要の化石)
- フレーキーテストは「リトライ3回・隔離」でしのぐ常態。実欠陥を隠すと知りつつ使う https://trunk.io/blog/the-ultimate-guide-to-flaky-tests https://evilmartians.com/chronicles/flaky-tests-be-gone-long-lasting-relief-chronic-ci-retry-irritation
- デバッガよりprint文が実務の既定 https://dev.to/shubhamjain/print-is-the-only-debug-tool-you-need-27d0
- Wikiは陳腐化しSlackの回答はスクロールに消え、新人は散らばったヒントを拾う https://getglueapp.com/blog/tribal-knowledge-software-teams
- フラグは「いつか消す」まま年単位で残置、掃除は専用スプリント頼み https://flagshark.com/blog/feature-flag-technical-debt-guide/ https://launchdarkly.com/docs/guides/flags/technical-debt

### 棚上げ案(死因付き)
- 形式手法: 死因=学習曲線・ツール統合欠如・ROI不信 https://ntrs.nasa.gov/citations/19970029196 https://arxiv.org/pdf/2010.16345
- UML/MDD: 死因=曖昧な意味論+自明な自動化のみで生産性低下 https://tratt.net/laurie/blog/2022/uml_my_part_in_its_downfall.html
- 文芸的プログラミング: 死因=著述コスト+リファクタ干渉+読者不在 https://news.ycombinator.com/item?id=10069748
- 決定的リプレイの本番常時適用: 死因=オーバーヘッドと運用複雑性 https://temporal.io/blog/time-travel-debugging-production-code

### 暗黙前提(12件から抜粋、全リストは中間成果物 01-map.md)
1. [慣習] レビューの単位はPR差分。捨てた代替案・意図はレビュー対象外
2. [慣習] テスト判定は緑/赤の2値(リトライが実質の第3状態) https://trunk.io/blog/the-ultimate-guide-to-flaky-tests
3. [経験則] 設定変更はコード変更よりレビューが軽い(のに大障害の主因) https://medium.com/@ismailkovvuru/microsoft-azure-outage-oct-29-2025-root-cause-impact-and-technical-analysis-3c7646d31703
4. [慣習] ポストモーテムは文書止まりで、コード・CIには還流しない https://sre.google/workbook/postmortem-culture/
5. [慣習] 一時コードの「寿命」はコード上に表現されない https://flagshark.com/blog/feature-flag-technical-debt-guide/

隣接分野: 航空(CRM)/医療(相互作用DB)/会計(複式簿記・監査)/製造(ポカヨケ)/図書館学(典拠)/食品(賞味期限)

## 3. 原石一覧(Phase 2、27件=類型別24+強制離心3)

- A1. レビュアーのために、PR差分に「捨てた代替案と制約」を構造化随伴させる記法 / A
- A2. CI利用者のために、テスト結果を信頼度スコア付きで報告する方法 / A+C
- A3. 運用者のために、設定変更をコード変更と同格の検査パイプラインに載せる方法 / A
- A4. チームのために、ポストモーテム対策を実行可能ガードとしてCIに還流する方法 / A+B
- B1. 変更を「意図/実装」の複式で記帳し不整合を機械検出する記法 / B(会計)
- B2. 依存×設定×フラグの「相互作用の既知事故DB」をデプロイ前照合する装置 / B(医療)
- B3. 一時コードに機械可読の「賞味期限」を刻みビルドで検出する記法 / B+C(食品)
- B4. 障害対応の口頭連携をコールアウト/リードバック形式で構造化する方法 / B(航空)
- C1. リトライ実績から「テスト信頼度台帳」を自動生成しPRに差分表示する装置 / C
- C2. print文デバッグを一級機能化した「使い捨て観測点」記法 / C
- C3. Slack・レビューの質疑をコード行に係留し次の変更者に提示する装置 / C
- C4. フラグ作成時に削除PRを同時生成し期限で自動レビューに載せる方法 / C
- D1. 文芸的プログラミングの著述コストをLLMに転嫁し物語を常時再生成する方法 / D
- D2. 自然言語仕様からLLMが形式仕様を起こす軽量形式検証の方法 / D
- D3. 異常予兆時のみ記録する選択的・決定的リプレイ装置 / D
- E1. APIの誤用を型・治具レベルで不可能にする「ポカヨケ度」検査の方法 / E(テスト×製造)
- E2. コードベースの概念に典拠コントロールを与える記法 / E(知識移転×図書館学)
- E3. レビュー承認を証跡+サンプリング再監査で抜き打ち検証する方法 / E(レビュー×会計)
- F1. 退職者の暗黙知をコード参照付きインタビューで採取・係留する方法 / F
- F2. レビューが防いだ/見逃した障害を事後突合して有効性を測る方法 / F+G
- F3. 依存ライブラリの「アップグレード苦痛度」を自動計測・公開する装置 / F
- G1. 「触りたくないコード」感覚を変更失敗率・回避行動から計測する装置+危険地帯地図 / G
- G2. IDE操作ログから認知負荷を推定する計測器+リファクタ優先度 / G
- G3. レビュー品質の疲労劣化を計測する装置+疲労考慮の割当法 / G
- H1. コミット直後のカナリア微分で障害検知を分単位に巻き戻す方法 / H(比2〜3桁)
- H2. コード固有知識をタスク駆動で対話供給するオンボーディング装置 / H(比2桁)
- H3. ドキュメント段落をコード要素に結線し変更で腐敗マークする記法 / H(比2桁)
- 強制離心(乱択=日本標準産業分類10分類、走査開始23:13の分の1桁=3→建設業): E-x1 中間工程検査(配筋検査式)/E-x2 竣工図の自動生成/B-x1 出来高査定検収

## 4. 選別の要約(Phase 3)

統合後、通過5件: P1(B3+C4 賞味期限記法)/P2(C3 質疑の行係留)/P3(A2+C1 テスト信頼度台帳)/P4(A4 ポストモーテム→ガード)/P5(B2 相互作用事故DB)。
落選19件の理由分布: ゲート0(発明性)2件(F1, B-x1)/ゲート1(部品実在性: 仮定部品過半)4件(G1系, D2, D3, G2/G3)/ゲート2(フェルミ)1件(F3)/ゲート3(価値仮説: 桁改善を言えない)9件+統合吸収3件。
特徴: G系は「計測の妥当性」自体が仮定部品になる構造的弱点で全滅。H系は既存解との差分を桁で言えず全滅。

## 5. 敵対的検証ログ(Phase 4。カード化候補分のみ全列挙、棄却3件は判定根拠のみ)

宣言: 「私はこの案を殺すことが仕事の審査官である。生かす証拠ではなく殺す証拠を探す。」

**P3 棄却=既存**(早期打ち切り: 2系統で実質同一製品): フレーキー度スコア・隔離・PR表示は BuildPulse/Trunk/Datadog/Atlassian Flakinator が実装済み https://www.atlassian.com/blog/atlassian-engineering/taming-test-flakiness-how-we-built-a-scalable-tool-to-detect-and-manage-flaky-tests https://buildpulse.io/products/flaky-tests https://docs.datadoghq.com/tests/flaky_management/

**P2 棄却=既存**(同上): Unblocked が「特定ファイル・行への過去のPR・議論・文書のIDE提示」を実装、CodeStream・Swimm も近接 https://getunblocked.com/ https://newrelic.com/codestream https://docs.swimm.io/new-to-swimm/continuous-documentation/

**P1 棄却=既存**: expiring-TODO lint+Piranha/Gitar/FlagShark の掃除PR+特許 US11188313B1 で全構成が被覆(統一記法という差分は自明な統合) https://github.com/sindresorhus/eslint-plugin-unicorn/blob/main/docs/rules/expiring-todo-comments.md https://www.uber.com/blog/piranha/ https://flagshark.com/docs/features/cleanup-prs/ https://patents.google.com/patent/US11188313B1/en

### P4(障害教訓コンパイラ)存在検索
- Q1 `automatically generate policy rule from incident postmortem prevent recurrence` → LLMポリシーギャップ分析研究(提言止まり、CI強制なし) https://arxiv.org/pdf/2601.03287
- Q2 `LLM generate static analysis lint rule from outage report incident learnings` → KNighter: 過去パッチ→静的検査器のLLM合成(入力が非ポストモーテム) https://arxiv.org/html/2503.09002v2
- Q3 `why postmortem action items fail repeat incidents same root cause` → 対策未実行・再発率30%超の嘆き多数、同機能製品の言及なし https://incident.io/blog/why-do-post-mortem-action-items-fail-how-to-make-incident-follow-ups-actually-get-done https://phoenixincidents.com/blog/why-postmortems-fail
- Q4 `"guardrail" OR "paved road" encode incident learnings enforcement CI tool product` → AIR: AIエージェント安全向けのインシデント→ガードレール合成(対象領域が異なる) https://arxiv.org/pdf/2602.11749
- Q5 `postmortem incident management tool discontinued shut down startup failed` → 反例なし(Opsgenie終了は事業統合) https://incident.io/blog/best-postmortem-software-for-devops-teams-2026
- 特許 `site:patents.google.com generate validation rule incident report software system remediation` → セキュリティ・コンプライアンス是正エンジンのみ https://patents.google.com/patent/US20150281287A1/en
- 最接近先行例: KNighter/AIR。差分: 入力=SREポストモーテム+対策項目、出力=自組織CIへ配備される強制ガード+障害ID⇔ガードの追跡。**判定=差分新規**
- 墓場: 同案の死骸なし(6クエリで反例なし(暫定))。4c: 主類型A+副B・D(説明可能)。4d: 反証実験設計可能(カード参照)

### P5(デプロイ配合禁忌台帳)存在検索
- Q1 `dependency version combination known issues database compatibility incidents` → 個別トラブル記事のみ、構造化DBなし https://dev.to/vasughanta09/solving-dependency-hell-a-developers-guide-to-managing-package-conflicts-in-2026-o2o
- Q2 `known bad library version combination database check before deploy community` → 悪性パッケージDB(JFrog Xray)のみ、組合せ相互作用DBなし https://www.aikido.dev/blog/top-tools-to-detect-malware-in-dependencies
- Q3 `Renovate merge confidence crowdsourced dependency update success rate` → Renovate Merge Confidence: 群衆データで単一依存の更新リスクを予測 https://docs.renovatebot.com/merge-confidence/ https://www.mend.io/blog/merge-confidence/
- Q4 `"why is there no" shared database known incompatible dependency versions breaking upgrades` → 不在理由(エコシステム分断・推移的依存)の言及のみ https://www.herodevs.com/blog-posts/node-js-compatibility-chaos-why-your-dependencies-break-during-an-upgrade
- 特許 `site:patents.google.com compatibility knowledge base software dependency deployment risk check` → US7140013B2(単一システムのインストーラ領域)、US20070157195 https://patents.google.com/patent/US7140013B2/en https://patents.google.com/patent/US20070157195
- 墓場 `dependency compatibility service libraries.io abandoned discontinued Greenkeeper shut down` → Greenkeeper終了(2020、死因=単独事業不成立→Snyk統合。自動更新PR事業で同案の死骸ではない) https://greenkeeper.io/
- 最接近先行例: Renovate Merge Confidence。差分: 単一依存の更新成功統計でなく、依存×設定×フラグの「組合せ」を障害事例から構造化し配合禁忌として照合。**判定=差分新規**
- 4c: 主類型B+副F・C(説明可能)。4d: 反証実験設計可能(カード参照)

## 6. 発明候補カード(Phase 5、card-schema.md 準拠)

### 発明候補カード C-01: 障害教訓コンパイラ

- **仮称**: 障害教訓コンパイラ
- **一行仕様**: 再発障害に苦しむ開発組織のために、ポストモーテム文書と対策項目を、CIで機械実行されるガード(ポリシー・lint・設定検査)へ変換・配備・追跡する方法
- **未在診断**: 主類型A(「ポストモーテムは文書、成果物は対策チケット」という慣習前提の檻)、副類型B(SRE文化とpolicy-as-code実務の担い手断絶)・D(散文→規則の変換はLLM以前は人手で高コスト)。障害の教訓は文書化された瞬間に読む人の記憶へ退蔵され、コードベースを守る装置に変換されないまま再発する。
- **イネーブラ**: (1) LLMによる規則合成が実用域(KNighter) https://arxiv.org/html/2503.09002v2 (2) 規則実行基盤(OPA/Conftest)のCI常備 https://www.openpolicyagent.org/docs/cicd (3) ポストモーテム構造の業界標準化 https://sre.google/workbook/postmortem-culture/
- **部品表**: 構造化ポストモーテム[実在確認済み https://sre.google/workbook/postmortem-culture/ ]/LLM規則合成[実在確認済み(研究) https://arxiv.org/html/2503.09002v2 ]/ポリシーエンジン[実在確認済み https://www.openpolicyagent.org/docs/cicd ]/人間承認フロー[実在確認済み(汎用PRレビューで代用、教科書的)]/ガード⇔障害IDの追跡台帳[仮定]
- **価値仮説**: 再発率30%超も珍しくない組織の「同根の再発障害」 https://phoenixincidents.com/blog/why-postmortems-fail を対象に、対策の実装を「チケット消化(数ヶ月)」から「ガード生成+承認(数日)」へ短縮し、再発クラス障害を1桁削減
- **フェルミ検算**: 重大障害12件/年×再発率30%=3〜4件/年。1件数百万円(対応+機会損失)→年1千万円規模。ガード生成・承認は1件数時間≈数万円 → 便益比2桁
- **新規性ログ**: クエリ全列挙=§5のP4のQ1〜Q5+特許クエリ(6件)。最接近先行例: KNighter https://arxiv.org/html/2503.09002v2 ・AIR https://arxiv.org/pdf/2602.11749 。差分: 入力=ポストモーテム+対策項目、出力=自組織CIの強制ガード+追跡。判定=**差分新規**
- **死亡条件**: (1) 生成ガードの誤ブロック率が高く一律overrideで形骸化 (2) 対策の大半が規則化不能(組織・アーキテクチャ変更)で規則化可能な残余が小さい
- **最小実験**: 公開ポストモーテム20件をLLMでOPA/lint規則へ変換し、機械実行可能率と誤ブロック率をサンプルリポジトリで測る(48時間・低予算)
- **先行指標**: incident管理SaaSの「対策→コード」機能発表/KNighter系のSRE領域転用論文/OPA向けLLM規則生成ツールの登場
- **確信度**: 中(部品は揃うが対策の規則化可能率が未測定。仮定部品1)
- **メタ**: 走査日 2026-07-03/taxonomy 1.0/全類型掃引(標準)

### 発明候補カード C-02: デプロイ配合禁忌台帳

- **仮称**: デプロイ配合禁忌台帳
- **一行仕様**: アップグレードを恐れる開発・運用チームのために、依存ライブラリ×設定×フィーチャーフラグの「悪い組合せ」を障害事例から構造化した相互作用DBとして蓄積し、デプロイ前に処方箋のように照合する装置
- **未在診断**: 主類型B(医療の薬剤相互作用DBという構造の移植先不在=分野断絶)、副類型F(組織横断DBを維持する誘因主体の不在)・C(「アップグレードが怖い」は名前のない常態、ワークアラウンドはロックファイル固定)。単一依存の脆弱性DBはあるが「組合せ」の事故知識はブログとissuesに散逸している。
- **イネーブラ**: (1) Renovate Merge Confidence が群衆データ収集経路を実証 https://docs.renovatebot.com/merge-confidence/ (2) 障害報告のLLM構造化抽出が実用域 https://arxiv.org/html/2603.16818 (3) 設定起因の大規模障害の周期的発生(Azure Front Door) https://medium.com/@ismailkovvuru/microsoft-azure-outage-oct-29-2025-root-cause-impact-and-technical-analysis-3c7646d31703
- **部品表**: lockfile依存グラフ抽出[実在確認済み(各パッケージマネージャ標準、教科書的)]/更新リスクの群衆データ収集[実在確認済み https://docs.renovatebot.com/merge-confidence/ ]/障害報告のLLM構造化抽出[実在確認済み(研究) https://arxiv.org/html/2603.16818 ]/依存×設定×フラグの三項相互作用スキーマ[仮定]/デプロイ前照合フック[実在確認済み https://www.openpolicyagent.org/docs/cicd ]
- **価値仮説**: 依存起因の週次障害事例 https://dev.to/vasughanta09/solving-dependency-hell-a-developers-guide-to-managing-package-conflicts-in-2026-o2o のような組織の「既知なのに踏む」事故の再踏率を1〜2桁削減
- **フェルミ検算**: 依存2,000件超のアプリで組合せ空間 2,000C2≈2×10^6 対に対し、記録可能な既知事故は高々数千件 → DB数MB・照合ミリ秒〜秒。障害1件(数百万円)を年1件防げば収集・審査数百人時と桁が釣り合う
- **新規性ログ**: クエリ全列挙=§5のP5のQ1〜Q4+特許+墓場(6件)。最接近先行例: Renovate Merge Confidence https://docs.renovatebot.com/merge-confidence/ 。差分: 単一依存の統計でなく組合せ相互作用の障害事例DB(特許US7140013B2は単一システムのインストーラ領域)。判定=**差分新規**
- **死亡条件**: (1) 事故の大半が組織固有文脈で知識が組織間移転しない(検出率数%) (2) エコシステム分断でスキーマ正規化が破綻し維持費が便益超過
- **最小実験**: GitHub issues・公開障害報告から悪い組合せ100件をLLM構造化し、別ソースの公開ポストモーテムへ遡及照合して「事前警告できたはずの率」を測る(48時間・低予算)
- **先行指標**: Renovate/Dependabot の「組合せ」次元の信号追加/OSVが非セキュリティ互換性事故を収載/保険・監査業界のデプロイリスク定量化参入
- **確信度**: 中(差分は明確だが知識の組織間移転率が未測定。仮定部品1)
- **メタ**: 走査日 2026-07-03/taxonomy 1.0/全類型掃引(標準)

## 7. 帰還レポート(Phase 6)

- 類型別ヒット率(原石→通過→生存、分子は4c最終診断の主類型): A 4→2→1(C-01、発火と診断一致)/B 5→2→1(C-02、一致。ただし副F・Cは4cで追加=発火時の複数発火見落とし)/C 4→2→0(2件とも既存で死亡)/D 3→0→0/E 5→0→0/F 3→0→0/G 3→0→0(計測妥当性が仮定部品になる構造的弱点)/H 3→0→0(既存解との差分を桁で言えない)
- 棄却分布: ゲート0=2、ゲート1=4、ゲート2=1、ゲート3=9(+統合吸収3)、Phase4既存=3。本領域は探索密度が高く「良い案はもう製品がある」率が高い(通過5件中3件が既存死)
- 残余X: なし(生存2件ともA/Bで説明可能)
- 改訂提案: 探索密度の高い領域ではHの「理論限界比2桁」信号が機能しにくい(市場が2桁差を放置しない)。Hの検出信号に「探索密度の低いニッチに限る」旨の適用条件を注記する価値あり

> 本結果はスクリーニングであり、特許侵害調査(FTO)でも網羅的な先行研究調査でもない。新規性判定はすべて走査日時点の暫定判定である。
