# mizai 実施例: 子育て(乳幼児〜小学生の家庭養育)走査 2026-07 【要約版】

> **免責**: 本例は mizai スキルの実行プロセスのデモであり、カードの質・新規性判定は走査日(2026-07-03)時点の暫定判定である。FTO調査ではない。
>
> 走査日: 2026-07-03 / フレームワーク版: taxonomy 1.0 / 走査モード: 全類型掃引(標準)
> 完全ログの基準例は在宅介護走査(kaigo-scan-2026-07.md)。本例は同一書式の要約版であり、中間成果物(00〜06)はスクラッチパッドに出力した。

## 1. 照準ログ(Phase 0)

- 対象領域: 子育て(乳幼児〜小学生の家庭養育)。広さ判定: 「家庭養育」+年齢帯で場面限定済み、サブ領域分割不要と判断(呼び出し側プリセットにより質問なし)
- (a) 価値の定義: 親(特に主養育者)の身体的・精神的負担、および子の安全と発達
- (b) 除外制約: 医療行為(診断・治療)は除外。数万円オーダーまでの家庭導入価格帯を優先。**子の監視強化に偏る案は慎重に扱う**
- (c) 走査モード: 全類型掃引(A→H、標準)

## 2. 領域地図の要約(Phase 1、11クエリ・4系統)

### (a) 支配的アプローチ

- ベビーテック国内市場約123億円。見守りカメラ・睡眠管理・スマート哺乳瓶が主流 https://service.xenobrain.jp/forecastresults/market-size/babytech https://tamagodaruma.com/education/baby-tech/
- AI泣き声解析(あわベビ)・スマートモニター(CuboAi殿堂入り)が受賞常連 https://prtimes.jp/main/html/rd/p/000000048.000026733.html https://edu.watch.impress.co.jp/docs/news/2085676.html
- 小学生の見守りはGPS端末が支配的(6割以上保有・自治体助成) https://benesse.jp/kosodate/202107/20210712-2.html https://shopro.co.jp/manabico/cate01/7746
- 中核苦痛: 0歳児母の睡眠4時間以下約6割・「睡眠不足による疲労感」83.8%・寝かしつけ苦労83.3%・ワンオペ実感41.8% https://www.wacoal.jp/news/newsrelease/202004/release144794.html https://s.mxtv.jp/tokyomxplus/mx/article/202501310650/detail/ https://baby.mikihouse.co.jp/information/post-9268.html

### (b) 直近イネーブラ

1. 泣き声解析AIの成熟(CES2024・精度95%主張、自治体導入) https://chizaizukan.com/news/1VpmNB10aq9C0wgKZEivS6/ https://www.saga-s.co.jp/articles/-/1722444
2. LLM育児相談の一般化(幼稚園24時間QA・学術チャットボット研究) https://www.keikakuhiroba.net/jirei/arcott-2/ https://www.jstage.jst.go.jp/article/pjsai/JSAI2024/0/JSAI2024_4Xin251/_pdf/-char/ja
3. 市販ウォッチの睡眠・中途覚醒・HRVストレス計測の標準化 https://corp.tacklenote.jp/columns/smartwatch-sleep-tracking/ https://smartwatch-blog.com/comparison-of-stress-check-functions/18611/
4. 音声感情認識APIの成熟(怒り判定・日本語対応) https://webempath.com/ https://emotion-voice-ai.userlocal.jp/
5. 家事「見える化」アプリ群の定着 https://donikatachi.github.io/housework_lp/ https://cinnamonista.com/apps/childnote

### (c) ワークアラウンド(抜粋)

- お茶パックで離乳食野菜を1鍋同時調理・100均茶こしで裏ごし代用・製氷皿冷凍 https://veryweb.jp/kids/722623/ https://mamanoko.jp/articles/15636
- 腱鞘炎・腰痛は器具でなく「抱き方の工夫」が標準回答 https://brand.taisho.co.jp/tokuhon/body_pain/kensyoen004/ https://journal.obstetrics.jp/2022/08/24/right_posture_for_childcare/
- 「考える・覚えておく」をリマインダ・共有アプリへ外部化 https://www.softbank.jp/sbnews/entry/20241206_02
- ベビーモニター誤報→「スイッチを切りっぱなしで使わなくなった」機器離脱 https://jyonshop.com/babysense-home-reputation/

### (d) 棚上げ案(死因付き)

- スマートおむつ: 死因=「センサーなしで分かる」+価格。介護用に販売終了品 https://nazology.kusuguru.co.jp/archives/122445 https://asahi-sg.co.jp/products/omutsu-sensor/
- 第一世代泣き声翻訳: 死因=翻訳結果が対処行動に接続しない(仮定) https://tabi-labo.com/288382/journey-chatter-baby
- 家庭用体動センサー: 死因=誤報疲れ。家庭でのSIDS予防エビデンス不足の指摘 https://news.yahoo.co.jp/expert/articles/2a9e30021fbb34a5932ee4848585e187ade2ad6c

### 暗黙前提(12件から抜粋)・隣接分野

1.[慣習]ベビーテックは子を観測する機器であり親を観測しない/3.[経験則]親の睡眠不足は「そういう時期」と正常化される/4.[慣習]抱っこの身体負担は体の使い方で解決すべき/6.[経験則]夜泣き対応は親が起きて行うもの/8.[慣習]乳幼児へのウェアラブル装着は忌避される/12.[経験則]機器は常に1児単位で設計される(ほか6件は01-map参照)。
隣接分野: 在宅介護/ペットケア/労働安全/航空/飲食/防災/スポーツ科学/農業

## 3. 原石一覧(Phase 2、31件+強制離心5件)

- A1. 親自身の消耗(睡眠分断・心拍・活動)を計測し限界前に休息を促す「親メーター」 / A+G
- A2. 双方の睡眠計測と翌日の予定から「今夜どちらが夜泣き当番か」を自動判定する夜間シフト裁定器 / A
- A3. 下の子対応中に上の子へ役割タスクを提示する2児同時設計の支援装置 / A
- A4. 家庭文脈を保持し「今週起きること」を先回り提示する文脈付き育児ナビ / A+H
- B1. 看護・物流の腰部負荷管理を抱っこ・沐浴動作に移植した装着計測法 / B
- B2. 航空チェックリスト文化を登園準備に移植した音声点呼装置 / B
- B3. 飲食店の仕込み計画を離乳食週次バッチ調理に移植した調理計画コンパイラ / B
- B4. スポーツ科学の負荷・回復管理を育児負荷に移植した回復度スコア / B+G
- C1. お茶パック同時調理を専用化した食材別区画・時間差引き上げゆでバスケット / C
- C2. 製氷皿冷凍ストックに在庫と月齢適合の自動管理を与える離乳食在庫トラッカー / C
- C3. リマインダ散在の「覚えておく」を家庭状態から自動起票する名もなき家事コンパイラ / C
- C4. 誤報で切られる体動センサーに家庭別ベースライン学習を与えた「切られない見守り」 / C+D
- D1. 泣き声翻訳(死因=対処に非接続)を育児記録×LLMで「次の一手」まで出す再設計 / D
- D2. 体動センサー(死因=誤報疲れ)を即時アラームから確認優先度提示へ再設計 / D
- D3. 手動育児記録を泣き声・環境音から自動生成するパッシブ育児ログ / D
- E1. [親の回復×スポーツ] 回復度で今日の負荷上限を示すコンディション予報 / E+G
- E2. [安全×防災] 月齢×住環境から次の家庭内事故を予報するヒヤリハット地図 / E
- E3. [記録×介護] 連絡帳記入を音声つぶやきから自動整形する申し送り生成器 / E
- E4. [抱っこ×労働安全] 抱っこ紐装着姿勢を写真1枚で採点する装着検定器 / E+B
- F1. 睡眠分断・活動量から「相談の目安」を示す非診断セルフモニタ / F+G
- F2. 夜間対応回数・抱っこ時間を自動記録し分担交渉の客観証拠にする育児労働ログ / F+G
- F3. ベビー用品の退役・譲渡・リコール確認を一括処理する卒業管理サービス / F
- F4. 下の子対応中も上の子との接続を保つ関与維持装置 / F
- G1. [未計測]親の夜間対応実回数 → 一階: 自動記録/二階: 分担裁定・レスパイト推奨 / G
- G2. [未計測]親の怒りの接近 → 一階: 自分の声・心拍から自己通知/二階: クールダウン誘導 / G
- G3. [未計測]子の「いつもと違う」 → 一階: 日次ベースライン逸脱スコア/二階: 前夜予兆通知 / G
- G4. [未計測]発達観察 → 一階: 家庭動画から自動抽出/二階: 不安の定量化 / G
- G5. [未計測]抱っこ姿勢の累積負荷 → 一階: ウォッチIMU記録/二階: 腱鞘炎危険域通知 / G
- H1. 寝かしつけ30〜60分/晩 vs 自力入眠数分(1桁) → 入眠条件の系統的ABテスト器 / H
- H2. 登園準備点検 vs RFID(2桁) → 玄関で不足品だけ音声通知する持ち物ゲート / H
- H3. 献立・アレルギー進行管理 数時間/週 vs 自動計画(1〜2桁) → 献立コンパイラ / H
- 強制離心(母集団=日本標準産業分類大分類10、開始時刻23:12の分1桁=2→**鉱業・採石業**): B-x1. 入坑管理タグボードを移植した「いま子を見ている責任者」明示の監督権バトン/E-x1. 坑内区画監視を移植した危険区画単独進入の局所検知/X-t1.[1950] 近隣預かり輪番台帳/X-t2.[2050] 月齢可変の子育てモード住宅/X-c1.[価格1/10] 紙の危険箇所チェックシート定期便
- 空振りの類型: なし

## 4. 選別の要約(Phase 3)

統合→候補5件をゲート審査。**通過4件**: K1(A1+A2+B4+E1+F2+G1: 育児労働の自動記録+夜番裁定)、K2(G2: 親の怒り接近セルフモニタ)、K5(D1+A4: 泣き声×文脈LLM)、K7(B-x1: 監督権バトン)。部品実在性はウォッチ睡眠計測 https://corp.tacklenote.jp/columns/smartwatch-sleep-tracking/ ・HRVストレス検知 https://smartwatch-blog.com/comparison-of-stress-check-functions/18611/ ・音声感情認識API https://webempath.com/ 等で確認(詳細は03-triage)。

**落選26件(原石ベース)の理由分布**: 既存密集・差分薄8(B3,H3,C2,C4,D2,E3,H1,E-x1)/価値仮説不成立5(A3,B2,H2,C1,D3)/仮定部品過半5(B1,G5,E4,C3,G3)/対象外5(E2,F3,F4,X-t1,X-c1)/制約抵触3(F1=医療境界,G4=診断接近+監視偏重,X-t2=価格帯)。

## 5. 敵対的検証ログ(Phase 4)

ペルソナ宣言: 「私はこの案を殺すことが仕事の審査官である。生かす証拠ではなく殺す証拠を探す。」

### K1 存在検索

- Q1 `夜泣き 対応 回数 記録 自動 夫婦 分担 アプリ デバイス` → 泣き止み音・睡眠改善アプリと研究アプリのみ https://www.jst.go.jp/pr/announce/20250227/index.html
- Q2 `night feeding split app couples who wakes up baby duty tracker wearable` → 手動入力の子ども記録アプリのみ(Le Baby「シフト交代時の伝達に」) https://www.lebaby.app/a-baby-tracker-to-share-with-your-partner
- Q3 `育児 負担 見える化 客観 記録 ワンオペ 証明 睡眠 分断 計測` → 手書きの表・チェックリストが標準解 https://kodomo-smile.metro.tokyo.lg.jp/st/soudan/story09.html
- Q4 `why is there no app that tracks invisible labor parenting night wakings automatically fair split` → 家事分担アプリの限界論(分割型の失敗・100日以内離脱70%) https://www.technologyreview.com/2022/05/10/1051954/chore-apps/
- Q5 `mental load tracker automatic parenting wearable app measure caregiving hours` → 介護者向け研究のみ、育児親向け製品なし https://pmc.ncbi.nlm.nih.gov/articles/PMC11774628/
- 特許: `site:patents.google.com infant care nighttime parental workload monitoring sleep interruption allocation` → 乳児睡眠スケジュール決定エンジン(US20130275171A1)等。親側計測+当番裁定は未確認 https://patents.google.com/patent/US20130275171
- 最接近先行例: Le Baby+US20130275171A1 / 差分: 手動でなく親側ウェアラブルの自動計測、子でなく親の労働記録、夜番裁定 / 判定: **差分新規**

### K1 墓場検索

- Q `baby tracker app shut down discontinued startup parenting workload failed` → 明確な死骸なし。近縁死因=手動入力負担と「分担」フレームの摩擦(chore apps離脱70%) https://www.technologyreview.com/2022/05/10/1051954/chore-apps/
- 死因解消: 部分的(自動計測が入力負担を消す。公平性フレームの摩擦は残る)

### K2 存在検索

- Q1 `親 イライラ 怒鳴る前 通知 アプリ ウェアラブル 育児 アンガーマネジメント デバイス` → 手動アンガーログ(おこノート)と6秒ルール等の技法のみ https://hugkum.sho.jp/417776
- Q2 `wearable detects anger before yelling parent alert device self regulation` → 研究のみ(Sense-IT司法精神科向け・PPG怒り検知)。Mayo Clinicは子のかんしゃく検知で親でなく子を計測 https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8663672/ https://newsnetwork.mayoclinic.org/discussion/mayo-clinic-smartwatch-system-helps-parents-shorten-and-defuse-childrens-severe-tantrums-early/
- Q3 `なぜない 怒り 事前 検知 ウェアラブル 自分 通知 虐待予防 テクノロジー` → 汎用「落ち着け」ブレスレットWellBe(2015)が最接近 https://wired.jp/2015/06/13/wellbe/
- Q4 `HRV biofeedback app parents emotional regulation product buy market` → 汎用HRV訓練市場は大だが実生活割込み型の育児特化なし https://www.researchandmarkets.com/reports/6190987/heart-rate-variability-biofeedback-app-global
- 特許: `site:patents.google.com caregiver anger detection wearable biofeedback alert parenting` → 汎用バイオフィードバック特許群のみ(US20120229270A1等) https://patents.google.com/patent/US20120229270A1/en
- 最接近先行例: WellBe+Sense-IT / 差分: 育児場面特化トリガ(泣き声継続×親の生理指標×時刻)+本人限定の事前割込み。研究実装のみ / 判定: **差分新規**(実装の未在)

### K2 墓場検索

- Q `Spire stone stress wearable discontinued emotion tracking wearable startup failed` → 死骸あり: Spire Stone(2019年頃販売終了) https://www.outdoorgearlab.com/reviews/fitness/pedometer/spire-stone
- 死因: 専用ハードが汎用ウォッチに吸収 / 死因解消: あり(市販ウォッチのストレスAPIに乗る設計 https://smartwatch-blog.com/comparison-of-stress-check-functions/18611/ )

### K5 存在検索(初手で既存確定)

- Q1 `泣き声 解析 アプリ AI 感情 対処法 提案 育児記録 連携` → あわベビ(11感情87%+対処法59種)・パパっと育児(解析+記録連携) https://apps.apple.com/jp/app/%E3%81%82%E3%82%8F%E3%83%99%E3%83%93-%E6%B3%A3%E3%81%8D%E5%A3%B0%E7%90%86%E8%A7%A3%E4%BF%83%E9%80%B2%E3%82%A2%E3%83%97%E3%83%AA/id1631767999 https://prtimes.jp/main/html/rd/p/000000006.000023831.html
- Q2 `baby cry analysis app AI personalized advice context LLM parenting assistant` → **実質同一の現行製品**: BabyMind(ChatGPT搭載・育児ログ文脈込み助言)・Nanni AI https://babymind.app/ https://www.freethink.com/robots-ai/ai-translates-baby-babble
- Q3以降打ち切り(2系統で実質同一を確認。早期打ち切り規則) → 判定: **既存**、棄却

### K7 存在検索

- Q1 `water watcher tag card designated supervisor drowning prevention pool` → 米国水辺安全の「Water Watcherタグ」(物理カード手渡し・15分交代)が最接近。水辺限定の啓発グッズ https://ndpa.org/designateawaterwatcher/ https://www.waterwisekids.com/education/water-watcher-card.html
- Q2 `子ども 見守り 当番 交代 「見ていると思った」 事故防止 タグ グッズ 家庭` → 日本語圏該当なし。施設向けビーコン・迷子GPSのみ https://hoiku.mynavi.jp/contents/hoikurashi/information/news/16735/
- Q3 `water watcher tag electronic timer rotation reminder device product smart lanyard` → 反例なし(無関係ヒットのみ)。電子化・交代リマインド付き製品は未確認
- Q4 `water watcher program supervision tag failed abandoned criticism effectiveness` → 失敗事例なし。「大人は近くにいたが割り当てられた大人が不在」という有効性根拠 https://www.catchthewaveswim.com/water-watcher-system-a-designated-supervision-strategy-to-prevent-drowning/
- 特許: `site:patents.google.com child supervision responsibility handoff token indicator caregiver` → 監督責任受け渡し検知のウェアラブル特許ファミリー(US11786123等)。家庭向け製品は未確認 https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/11786123
- 最接近先行例: Water Watcherタグ+US11786123ファミリー / 差分: 水辺限定の啓発カードを家庭日常の汎用監督権バトンへ拡張(保持時間リマインド・受け渡し記録・日本語圏への移植) / 判定: **差分新規**

### K7 墓場検索

- Q: Q4兼用 → 死骸なし(米国で公的機関が推奨継続中) / 死因: 該当なし

### 4c 説明責任テスト・4d 反証可能性テスト

- K1: 着想可能・部品あり・誰も作らない → 主類型F(育児記録の誘因は子に偏り、主養育者は購買力の谷)、副G。4d: 可能[要7晩]
- K2: 「怒鳴りそうな親」向け製品は購入=自認のタブー谷 → 主類型F、副G。4d: 可能[要14日](怒りイベントが疎)
- K7: 米国水辺安全の実践が日本の家庭日常と交流なく未移植 → 主類型B、副C。4d: 可能(48時間)
- 残余X: なし

## 6. 発明候補カード(Phase 5、3枚)

### 発明候補カード K1: ワンオペメーター(夜番裁定つき)

- **仮称**: ワンオペメーター(夜番裁定つき)
- **一行仕様**: 乳幼児を育てる夫婦のために、親側ウェアラブルと枕元センサーで夜間対応回数・抱っこ時間・中断睡眠を自動記録し、双方の累積消耗から「今夜どちらが起きるか」の裁定案を毎晩提示する装置・方法
- **未在診断**: 主類型F(動機の盲点)、副類型G(観測の欠如)。育児記録アプリは慣習的に「子の記録」であり、親の労働は誰も計測してこなかった。主養育者は無償労働者で購買力・発言力の谷にあり、需要が製品要求に翻訳されない。
- **イネーブラ**: 市販ウォッチの睡眠・中途覚醒計測の一般化 https://corp.tacklenote.jp/columns/smartwatch-sleep-tracking/ https://sleepshift.jp/smartwatch-sleep-accuracy-recommend/ 、「見えない家事・メンタルロード」の社会的言語化 https://www.technologyreview.com/2022/05/10/1051954/chore-apps/ (主類型FのためイネーブラOKは補助要因)
- **部品表**: 市販スマートウォッチ2台[実在確認済み https://corp.tacklenote.jp/columns/smartwatch-sleep-tracking/ ]/夜間対応イベント(起床・入室・抱っこ)の判別モデル[仮定]/公平裁定ロジック[実在部品の組合せ、重み設計は設計事項]
- **価値仮説**: 主養育者(0歳児母の睡眠4時間以下約6割・疲労感83.8% https://s.mxtv.jp/tokyomxplus/mx/article/202501310650/detail/ https://www.wacoal.jp/news/newsrelease/202004/release144794.html )の睡眠分断と「証明できないワンオペ」。分担再配分で連続睡眠を概ね倍化(1桁)+分担交渉・行政相談の客観証拠
- **フェルミ検算**: ウォッチ2台1万円級+アプリ数百円/月。産後うつ・疲労起因の離職・受診損失は年数十万円/世帯 → 2桁余裕。0〜2歳児世帯は国内数百万規模
- **新規性ログ**: 5節K1の全7クエリ(存在6+墓場1)。最接近先行例: Le Baby+US20130275171A1 / 差分: 親側の自動計測・親の労働記録・夜番裁定 / 判定=**差分新規**
- **死亡条件**: (1)中途覚醒データから「育児対応の起床」と「自然覚醒」を判別できない (2)公平の数値化が夫婦の摩擦を増やす(chore appsの失敗構造の再現 https://www.technologyreview.com/2022/05/10/1051954/chore-apps/ )
- **最小実験**: ウォッチ2台+手動ラベルで7晩記録し夜間対応イベントの検出再現率>80%を確認[要7晩]
- **先行指標**: ウォッチOSの覚醒理由ラベルAPI公開/行政調査での客観ログ採用/ベビーモニター×親側ウェアラブル連携製品/メンタルロード計測研究の製品化
- **確信度**: 中(部品ほぼ実在だがイベント判別が仮定。F型ゆえ「作っても買われない」+公平化の逆効果リスク)
- **メタ**: 走査日2026-07-03 / taxonomy 1.0 / 全類型掃引

### 発明候補カード K2: 六秒前ブザー(親の爆発予報)

- **仮称**: 六秒前ブザー(親の爆発予報)
- **一行仕様**: 育児中の親自身のために、市販ウォッチの生理指標(心拍・HRV)と泣き声の継続時間・時刻を組み合わせ、「怒鳴る前」の高リスク状態を本人だけに振動通知しクールダウンへ誘導する方法・アプリ(子でなく親を観測する)
- **未在診断**: 主類型F(動機の盲点・タブー)、副類型G(観測の欠如)。「怒鳴りそうな親」向けと明示した製品は購入が自認になるタブーの谷にあり、企業も研究(司法精神科向け)から踏み出さない。怒りの接近は本人にも計測されない量だった。
- **イネーブラ**: ウォッチのHRVストレス検知・リラックス通知の標準搭載 https://smartwatch-blog.com/comparison-of-stress-check-functions/18611/ 、音声感情認識APIの成熟 https://webempath.com/ https://emotion-voice-ai.userlocal.jp/ 、バイオキューイングの学術実証(Sense-IT) https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8663672/ (主類型FのためイネーブラOKは補助要因)
- **部品表**: HRV計測ウォッチ[実在確認済み https://smartwatch-blog.com/comparison-of-stress-check-functions/18611/ ]/泣き声継続検知(スマホマイク)[実在確認済み(泣き声解析AIの流用) https://chizaizukan.com/news/1VpmNB10aq9C0wgKZEivS6/ ]/個人別「爆発前」閾値の学習モデル[仮定(育児場面での先行性が未実証)]
- **価値仮説**: 親自身の「怒鳴った→自責→抑うつ」ループと子への心理的影響。事後の後悔(手動アンガーログ)を事前の割込みへ適時化し、怒鳴りエピソード半減で親のメンタルと親子関係の損失を1桁圧縮(仮説)
- **フェルミ検算**: 手持ちウォッチ+アプリで追加原価ほぼゼロ〜1万円台。ペアレントトレーニング(数万円・数週間)や関係悪化の長期コストに対し1〜2桁安い
- **新規性ログ**: 5節K2の全6クエリ(存在5+墓場1)。最接近先行例: WellBe https://wired.jp/2015/06/13/wellbe/ +Sense-IT研究 / 差分: 育児場面特化トリガ+本人限定の事前割込み、製品なし / 判定=**差分新規**(実装の未在)
- **死亡条件**: (1)汎用ストレス指標が怒りの接近に先行しない(事後にしか上がらない)ことが実測で判明 (2)通知が「監視されている」感覚を生み装着が続かない(タブー谷の再現)
- **最小実験**: ウォッチのストレスログ+自己申告アンガーログを突合し、怒りエピソード前の指標立ち上がりを検証[要14日](イベントが疎なため)
- **先行指標**: ウォッチOSのリアルタイムストレスAPI開放/自治体虐待予防事業のテック採用/バイオキューイングの一般向け展開/産後メンタルヘルス市場の拡大
- **確信度**: 低〜中(部品は実在するが先行性という中核仮定が未実証、タブー谷ゆえ受容性リスク大。最小実験は安価)
- **メタ**: 走査日2026-07-03 / taxonomy 1.0 / 全類型掃引

### 発明候補カード K7: みてるよバトン(監督権の物理トークン)

- **仮称**: みてるよバトン(監督権の物理トークン)
- **一行仕様**: 複数の大人がいる場面(帰省・来客・入浴前後・ベランダ作業中)の乳幼児のために、「いま子を見ている責任者」を物理バトンで一意に明示し、保持時間の経過で交代を促し、受け渡しを記録する装置・方法(子でなく大人の側の仕組み)
- **未在診断**: 主類型B(領域の断絶)、副類型C(名前なき需要)。米国水辺安全分野には「Water Watcherタグ」として実在するが、水辺安全教育と日本の家庭日常は学会・業界・言語が重ならず移植されていない。「監督の空白」には日本語の名前がなく、事故のたび「目を離した隙に」と個人の注意に還元される。
- **イネーブラ**: イネーブラ不要(常に可能だった)。物理トークンは太古から実在し、主類型B/Cと整合。電子化する場合もNFC・BLEは汎用品
- **部品表**: 物理バトン(リストバンド・カード)[実在確認済み(Water Watcherタグとして流通) https://swimlessonsuniversity.com/water-watcher-tags/ ]/経過タイマー・振動リマインド[実在確認済み(汎用品)]/NFCタップ受け渡し記録アプリ[実在確認済み(汎用部品の組合せ)]
- **価値仮説**: 乳幼児の家庭内・行楽先の重大事故(溺水・転落)。溺水事例レビューでは「大人が近くにいたが割り当てられた大人が不在」が大きな割合 https://www.catchthewaveswim.com/water-watcher-system-a-designated-supervision-strategy-to-prevent-drowning/ 。監督空白時間の明示的引き継ぎによるほぼゼロ化(発生頻度1桁以上削減の仮説)。子の監視強化でなく大人側の運用変更(除外制約に整合)
- **フェルミ検算**: 紙+ストラップ数百円、タイマー・NFC付きでも原価2千円級。乳幼児の不慮の事故1件の期待損失に対し4桁以上安い。競合は「ゼロ円の口約束」で、価格でなく習慣化が関門
- **新規性ログ**: 5節K7の全6クエリ(存在5+墓場1兼用)。最接近先行例: Water Watcherタグ https://ndpa.org/designateawaterwatcher/ +特許US11786123ファミリー https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/11786123 / 差分: 水辺限定の啓発カードを家庭日常の汎用監督権バトンへ拡張(時間リマインド・受け渡し記録・日本語圏移植)。特許先行ありのため実装設計で回避要 / 判定=**差分新規**
- **死亡条件**: (1)日常運用で「バトンを持つ」行為が2週間で形骸化(啓発グッズの一般的死因) (2)保持者以外の注意が下がり総リスクが増える(リスク補償)
- **最小実験**: 紙バトン+キッチンタイマーで大人3人以上の場面2回(週末)に運用し、「誰が見ているか即答できない瞬間」の回数を前後比較(48時間で可能)
- **先行指標**: 消費者庁・こども家庭庁資料への「監督者指名」概念の登場/Water Watcher系製品の日本上陸/保育引率での同種トークン採用/US11786123ファミリーの製品化動向
- **確信度**: 中(部品全て実在・先行実践に有効性根拠。日常への習慣移植と特許回避が不確実)
- **メタ**: 走査日2026-07-03 / taxonomy 1.0 / 全類型掃引(乱択ペアリング: 鉱業・採石の入坑管理タグボード由来)

## 7. 帰還レポート(Phase 6)

### カード要約表

| 仮称 | 一行仕様(短縮) | 主類型 | 新規性判定 | 確信度 |
|---|---|---|---|---|
| ワンオペメーター | 親の夜間対応・睡眠分断を自動記録し夜番を裁定 | F(+G) | 差分新規 | 中 |
| 六秒前ブザー | 親自身の怒り接近を本人だけに事前通知 | F(+G) | 差分新規 | 低〜中 |
| みてるよバトン | 「いま見ている責任者」を物理トークンで一意化 | B(+C) | 差分新規 | 中 |

最有望はK7(みてるよバトン)。部品は全て実在し、米国水辺安全分野で「割り当てられた大人の不在」が溺水の主因という有効性根拠が公的に確立している。数百円の物理トークンで子の監視を増やさずに監督空白を潰せる点が、本走査の除外制約(監視強化への慎重)に最も適合する。

### 類型別ヒット率(原石31+離心5 → 通過4 → 生存3。分子は4c最終診断の主類型で計上)

A:4→2寄与(K1起点、診断はFへ)/B:4→1(B4→K1)/C:4→0(商業メディアがワークアラウンドを常時収穫し専用品化が速い)/D:3→0(D1→K5は他社着手済みで既存)/E:4→1(統合寄与)/F:4→1(K1・K2の最終主類型はF)/G:5→2(親側の未計測量が高収率)/H:3→0(既存密集)/離心:5→1(乱択・鉱業→K7が単独生存)。
発火類型と最終診断のずれ2件(K1: A/G発→F診断、K2: G発→F診断)。子育て領域は「着想も部品もあるがタブーと購買力の谷で誰も作らない」F型が背景構造。

### 残余X事例

なし。生存3候補すべて4cで説明成立(K1=F+G, K2=F+G, K7=B+C)。

### 分類学への改訂提案

1. **C型の商業的収穫速度補正**: 大衆消費領域ではワークアラウンドがメディア・100均・メーカーに即収穫されC型の残存期間が短い。「その応急処置は何年放置されているか」の事前チェックをC型に追記提案。
2. **安全管理系産業は家庭領域への高収率移植元**: 乱択の鉱業(入坑管理)が生存カードに直結。B型移植元に「産業安全プロトコル×家庭のアマチュア運用」を定型ペアとして追記提案。
3. **タブー谷(F)候補の受容性反証の必須化**: 「購入=自認」型は売り場が存在せず存在検索で反例が出にくく新規性が過大評価される。F型(タブー)診断カードには4dで受容性反証(買うか・使い続けるか)の実験設計を必須化する提案。

### 定型免責

本結果はスクリーニングであり、特許侵害調査(FTO)でも網羅的な先行研究調査でもない。新規性判定はすべて走査日(2026-07-03)時点の暫定判定である。
