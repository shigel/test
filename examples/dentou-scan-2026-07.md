# mizai 実施例: 伝統文化(日本の伝統工芸・伝統芸能の技能継承と存続)走査 2026-07-03 【要約版】

> **免責**: 本例は mizai スキルの実行プロセスのデモであり、カードの質・新規性判定は走査日(2026-07-03)時点の暫定判定である。FTO調査ではない。
>
> 走査日: 2026-07-03 / taxonomy 1.0 / 走査モード: 全類型掃引(標準)
> 完全ログの基準例は在宅介護走査(kaigo-scan-2026-07.md)。本例は要約版であり、中間成果物の全文は走査時の作業ディレクトリにのみ存在する。

## 1. 照準ログ(Phase 0)

- 対象領域: 日本の伝統工芸・伝統芸能の技能継承と存続。「技能継承と存続」で問題圏が限定済みと判定し、工芸(モノづくり)と芸能(身体芸)を同一走査で扱う
- (a) 価値の定義: 継承者・職人の技能習得の速度と質、および産業としての存続
- (b) 除外制約: 真正性を毀損する「安易な代替」ではなく、継承・記録・市場を強くする方向を優先
- (c) 走査モード: 全類型掃引(A→H)

## 2. 領域地図の要約(Phase 1、10クエリ・4系統)

### 支配的アプローチ
- 伝産法+振興協会+補助金(後継者育成・原材料・需要開拓)が制度の柱。出口は「補助金依存からの自立化」 https://www.meti.go.jp/policy/mono_info_service/mono/nichiyo-densan/densan/plan.html https://www.meti.go.jp/policy/mono_info_service/mono/nichiyo-densan/hojokin/fullversion_guidebook_2401.pdf
- 生産額1983年5,400億円→2016年960億円、従事者28.8万人(1979)→約5.4万人(R2) https://shikinobi.com/traditionalcrafts-info https://www.soumu.go.jp/main_content/000818488.pdf
- 技能継承の主流は徒弟制(見て盗む)+OJT https://o-temoto.com/asami-saisho/tsuchiya-kaban2/ 。芸能は国立劇場の伝承者養成事業、保持者平均年齢70歳超 https://www.gov-online.go.jp/useful/article/202112/4.html https://www.wdvf.org/archives/493

### 直近イネーブラ
1. モーキャプ+AI分析の技能可視化(基礎習得7年→4年の事例報告) https://www.nobby-tech.co.jp/media/3Dmition/skill_tradition https://syokunin.work/column/craftsman-skill-transfer-guide/
2. 三次元映像による「動きを伴う技能」の国主導アーカイブ構想 https://www.mext.go.jp/b_menu/shingi/gijyutu/gijyutu3/toushin/attach/1332159.htm
3. VR/AR技能伝承ソリューションの商用化 https://xrcloud.jp/blog/articles/business/13995/ / 作業分析ソフトの教育転用 https://www.otrs.jp/overview/training/
4. Zoom遠隔稽古の実績(狂言) https://norikomaniwa.hatenablog.com/entry/2020/05/20/161959 / 職人動画メディア・工房定点生配信 https://nippon-teshigoto.jp/movies https://prtimes.jp/main/html/rd/p/000000007.000046661.html

### ワークアラウンド(未言語化需要の化石)
- 「教えない/見て盗む」は技術=食い扶持の経済構造への応急処置 https://news.careerconnection.jp/?p=20781 https://sushitake-uehara.com/mede-nusume/
- 広報用の手元定点配信を事実上の記録として運用 https://prtimes.jp/main/html/rd/p/000000007.000046661.html / 高校生受け入れを機に自作の教え方マニュアル https://www.biglife21.com/column/11193/
- 材料・道具の不足は振興協会「不足情報」で相互融通 https://kyokai.kougeihin.jp/lack/ / 型・口伝は紙の記譜+家元アーカイブ(観世文庫約2,600点) https://japanknowledge.com/introduction/keyword.html?i=2001 https://ndlsearch.ndl.go.jp/rnavi/humanities/nohgaku
- 漆の乾燥管理は「マニュアルなし・各自の経験で環境を作る」+安価湿度計を目安に入れる https://www.9emon.co.jp/post/japan_environment https://tamenuri.com/curing-urushi-concept-tips-qa/

### 棚上げ案(死因付き)
- 国産原材料(漆・和紙原料等)供給網。死因=農林業への埋め込みが解けた https://www.bunka.go.jp/tokei_hakusho_shuppan/tokeichosa/dentokogei_chosa/pdf/r1408239_01.pdf https://www.jri.co.jp/column/opinion/detail/16305/
- 3D技能アーカイブ構想。死因=記録はできるが「記録から習得する側」の道具が続かない(仮定) https://www.mext.go.jp/b_menu/shingi/gijyutu/gijyutu3/toushin/attach/1332159.htm
- 補助金事業の多く。死因=補助金終了で持続せず https://www.meti.go.jp/policy/mono_info_service/mono/nichiyo-densan/hojokin/fullversion_guidebook_2401.pdf / コロナ期は約4割が廃業危機 https://note.com/aeru_/n/n3e6f392e683d

### 暗黙前提(12件から抜粋、全文は01-map)
[慣習]技能は見て盗むもの/[経験則]技術は食い扶持で教えると損/[慣習]修業は暦年で数える/[慣習]記録は保存用で習得用でない/[経験則]職人の勘(力加減・音・乾き)は計測できない/[慣習]支援は作り手優先で道具・材料職人は影/[慣習]工程の機械化は真正性を毀損する/[慣習]品質判定は師匠の目視・手触りのみ、ほか

## 3. 原石一覧(Phase 2、32件+離心4、裏取りなし)

乱択記録: 母集団=日本標準産業分類・大分類10分野、走査開始時刻23:12の分1桁=2→鉱業・採石業(E掃引追加乱択は分十位=1→漁業)。

- A1. 師匠の手元映像に視線・注視点を重ね「どこを見て盗むか」を明示する動画変換 / A
- A2. 育てた弟子の収益の一部を師匠へ還流させ「教えるほど損」を消す仕組み / A
- A3. 修業の進捗を暦年でなく課題達成量で測る習得度メーター / A
- A4. 師匠の合否判定をペアデータ化し仕上がり自動判定器を作る / A+G
- A5. 真正性に無関係な雑務工程だけを機械化する工程再配分法 / A
- B1. スポーツのフォーム解析を鉋がけ・ろくろに移植した動作差分ビューア / B(スポーツ科学)
- B2. 外科教育の技能評価尺度と練習シミュレータを工芸手技に移植 / B(外科教育)
- B3. 力加減・速度・角度・順序を記述できる「工芸譜」記法 / B(音楽記譜)
- B4. 篤農家の暗黙知AIを材料の目利きに移植した判断コーパス / B+G(農業AI)
- C1. 広報用定点配信を教材化する工程インデックス・失敗注記の注釈規格 / C
- C2. 自作の教え方マニュアルをLLMで動画から自動下書き / C
- C3. 「不足情報」掲示板を廃業在庫まで含む相互融通市場に拡張 / C
- C4. 遠隔稽古を専用化(型の重ね描き・遅延補正・姿見分割) / C
- D1. 記録止まりの3D技能アーカイブを練習ドリルに自動変換 / D
- D2. 練習作品に自動品質等級を付け修業期の無収入を崩す / D+F
- D3. 漆林等の原材料をドローン・センサーで資源マップ化 / D+B
- E1. [練習×ゲーム] 手元プロジェクションで「次の手」を譜面のように流す練習台 / E
- E2. [品質判定×漁業] セリの即時等級付け構造を中間工程品に移植 / E+B
- E3. [材料調達×鉱業] 鉱脈品位マップ構造で国産漆・原木の採取適地探査 / E+B(乱択)
- E4. [記録×外科] 手術動画のステップ自動分割を工程動画に移植 / E
- E5. [評価×EC] 実物郵送依存の技能検定をスキャン提出+遠隔審査に / E
- F1. 廃業前に道具の形状・調整・使い癖を3Dスキャンで残す「道具のデジタル遺言」 / F
- F2. 高価な本材料(漆・金箔)の練習用代替材と換算則 / F
- F3. 恥として共有されない失敗事例の匿名再現データベース / F+C
- F4. 修業中途離脱者の習得済み技能を実技で証明するポータブル記録 / F
- G1. [未計測]力加減 → 一階: 圧・IMU付き道具柄。二階: 師弟の圧プロファイル差分提示 / G
- G2. [未計測]音による判断 → 一階: 作業音の音響指紋。二階: 逸脱アラートと音の教材化 / G
- G3. [未計測]乾き・粘度の手触り → 一階: 非接触水分計の工程組込み。二階: 「今日は塗るな」工程ナビ / G
- G4. [未計測]上達度 → 一階: 反復課題の3Dスキャン差分自動採点。二階: 修業カリキュラム最適化 / G+A
- H1. 師匠の指摘頻度: 週数回 vs 毎試行=2〜3桁差 → 毎試行自動フィードバック練習環境 / H+G
- H2. アーカイブ検索: 人手数時間 vs 秒=3桁差 → 工程語彙での記録動画横断検索 / H
- H3. 問屋流通: 数週間・多段マージン vs D2C即日=2桁差 → 受注・真贋証明一体の直販 / H
- E-x1. [乱択・鉱業] 坑道の切羽台帳構造で工房の「今日の作業面」を自動日誌化 / B-x
- E-x2. [時代1950] 紙の見本帳・型紙を工程条件付きで標準化した共有見本文庫 / C-x
- E-x3. [時代2050] 全作業が標準でログに残る「ログネイティブ工房」改装パッケージ / E-x
- E-x4. [制約反転(弟子の時間1/10)] 週末弟子向け材料+課題+遠隔添削の工房外修業キット / F-x

空振りの類型: なし

## 4. 選別の要約(Phase 3: ゲート0+三重ゲート)

統合: K1←G1+H1+B1+B2 / K2←A4+E2+G4+A3 / K3←D1+H2+E4+C1+A1 / K4←G3+B4 / K5←G2 / K6←F1 / K8←D3+E3

**通過5件**: K1(毎試行フィードバック練習環境)・K3(記録→教材変換)・K4(乾き工程ナビ)・K5(音響指紋)・K6(道具のデジタル遺言)。部品実在の代表確認: FSR402薄膜圧センサー https://akizukidenshi.com/catalog/g/g104002/ 、非接触水分計・温湿度ロガー https://metoree.com/categories/3281/ https://ureruzo.com/moi00000.htm 、動作セグメンテーション研究 https://arxiv.org/pdf/2305.19478 、異音検知AI https://metoree.com/categories/8503/ 、スマホ3Dスキャン https://3d-scantech.jp/column/smartphone/

**落選の分布(統合吸収3を除く19件)**: 対象外(制度・事業・コンテンツ・自明応用)11件(A2, A5, C2, C3, D2, E5, F3, F4, E-x2〜4)/既存密集・差分薄5件(K2, C4, K8, E1, H3)/価値仮説不成立2件(B3, E-x1)/部品実在性不成立1件(F2)。継承・存続領域は解が制度・事業に寄るため、発明性ゲート(ゲート0)の落選が最大勢力になった。

## 5. 敵対的検証ログ(Phase 4)

ペルソナ宣言: 「私はこの案を殺すことが仕事の審査官である。生かす証拠ではなく殺す証拠を探す。」

### 通過後に殺された2件(早期打ち切り規則)
- K3: `動画 手順書 自動生成 AI 現場 ナレッジ 検索 tebiki 製品` → tebiki(動画の手順分割・教材化・検索) https://tebiki.jp/feature/ai / 第2系統(比較記事)`動画からマニュアル自動作成 ツール6選` → 商用多数 https://divedx.com/blog/video-manual-ai → 2系統で実質同一の現行製品カテゴリ確認 → **既存**・棄却
- K5: `官能検査 音 熟練者 代替 AI 製品 打音検査 判定 導入事例` → AI音振判定・AI打音チェッカー・トヨタ九州AI異音検査 https://www.elmec-gms.com/products-software/aiwavelet http://www.port-d.co.jp/p_pdc-100.htm https://skydisc.jp/showcase/3357/ / `音響 異常検知 AI エッジ マイク 製造 設備 音 判定 製品` → メーカー9社 https://metoree.com/categories/8503/ https://fast-d.hmcom.co.jp/ → **既存**(工芸適用は用途差分のみ)・棄却

### K1 存在検索
- Q1 `職人 技能 習得 センサー 道具 圧力 フィードバック 練習 システム 製品` → 産業向けAI技能評価の事例記述のみ、工芸向け製品なし https://syokunin.work/column/craftsman-skill-evaluation-guide/
- Q2 `instrumented tool pressure sensor craft skill training real-time feedback novice expert comparison` → 歯科・医療手技の計装トレーナーが最接近 https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/10109220 https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4075507/
- Q3 `ろくろ 鉋 力加減 計測 見える化 練習 研究 伝統工芸 訓練装置` → 陶芸「デジタルマイスター」研究(記録・CG再現止まり、力触覚は将来課題) https://www.mext.go.jp/b_menu/shingi/gijyutu/gijyutu3/toushin/attach/1332159.htm https://www.tel.co.jp/museum/magazine/manufacture/131125_topics_07/02.html
- Q4 `why is there no smart tool for craft apprenticeship training pressure feedback woodworking pottery` → 徒弟制情報のみ、反例なし
- 特許 `site:patents.google.com sensor instrumented hand tool training feedback expert profile craft skill acquisition` → US20170061817A1・US10109220・US20240201677A1 https://patents.google.com/patent/US20170061817A1/en https://patents.google.com/patent/US20240201677A1
- 墓場 `技能伝承 デジタルマイスター プロジェクト その後 実用化されなかった 終了 センサー 訓練` → 撤退記録なし・続報なし=事実上の休眠。死因: 当時の力触覚計測の未達+習得側ツール不在(仮定)/解消: 部分的(FSR数百円化 https://akizukidenshi.com/catalog/g/g104002/ )
- 最接近先行例: US10109220+デジタルマイスター研究 / 差分: 実道具後付け・師匠プロファイル差分・毎試行提示の工芸実装なし / 判定: **差分新規**(実装の未在)

### K4 存在検索
- Q1 `漆風呂 湿度 管理 IoT センサー モニタリング 乾燥 制御 装置` → 汎用温湿度管理のみ、漆特化の工程判断製品なし https://metoree.com/categories/8787/ https://it-trend.jp/humidity_temperature/article/1069-4978
- Q2 `urushi lacquer curing humidity chamber monitoring sensor control system` → 実務は安価湿度計を「目安」に入れる運用(ワークアラウンド確認) https://tamenuri.com/curing-urushi-concept-tips-qa/ https://www.kintsugi.art/en/post/create-a-drying-chamber-for-kintsugi-or-a-hardening-box-for-urushi-lacquer
- Q3 `陶芸 乾燥 割れ 防ぐ 含水率 タイミング 経験 勘 センサー アプリ` → 経験則記事のみ、計測支援製品への言及なし https://www.aitohko.com/manual/toki/t01.html https://www.zowhow.com/pottery_index_tec/tips-to-reduce-cracks/
- Q4 `"漆" 乾燥 予測 アプリ ない 難しい 経験 湿度 失敗 縮み` → 「マニュアルなし・各自の経験」の明文化=需要の輪郭。反例なし https://www.9emon.co.jp/post/japan_environment https://www.yamakyu-urushi.co.jp/shikki/157_160/
- 特許 `site:patents.google.com lacquer drying state prediction humidity temperature craft workpiece moisture monitoring` → 汎用乾燥終点制御(US5649372A等)・漆至適条件の記載(WO2005078031A1) https://patents.google.com/patent/US5649372A/en https://patents.google.com/patent/WO2005078031A1/en
- 墓場 `工芸 工房 IoT 実証実験 終了 続かなかった 導入 失敗 センサー` → 工芸特化の死骸なし。隣接死因=PoC死(計測が判断に接続されない) https://data.wingarc.com/theblog-failed-iot-4407
- 最接近先行例: 汎用乾燥終点制御+汎用温湿度監視 / 差分: 環境監視でなく「材料状態×環境×工程判断(塗る/待つ)」の助言 / 判定: **差分新規**

### K6 存在検索
- Q1 `職人 道具 3Dスキャン デジタルアーカイブ 廃業 記録 保存 プロジェクト` → 文化財・完成品(茶杓・織機)のスキャンは多数、「道具+調整+使い癖」の再現目的様式は非ヒット https://note.com/word_giken/n/nf16bbf4dd604 https://www.tbts.co.jp/others/digital-archiving-solutions-cultural-property/
- Q2 `craft tool 3D scanning preservation disappearing toolmaker reproduction heritage` → 博物館3Dスキャン+複製は確立、現役道具の実用再現向け記録は非ヒット https://www.si.edu/content/MCIImagingStudio/papers/scanning_paper.pdf https://www.artec3d.com/3d-scanning-solutions/heritage-preservation
- Q3 `道具 職人 いない 手に入らない 廃業 特注 再現 困る 伝統工芸 篦 鉋 刃物` → 供給断絶の実態(与板の鍛冶117人→伝統工芸士4人)。記録手段への言及なし https://daiku-dougu.jp/kikou-masayuki.html https://yoita-uchihamono.com/
- Q4 `なぜ 残さない 廃業前 工房 機械 道具 デジタル 記録 サービス ない 惜しい` → 専用サービス未確認。学術の最接近: J-Stage「デジタル記録とオンラインを活用した伝統技術の継承と復元製作」 https://www.jstage.jst.go.jp/article/jsda/5/2/5_86/_article/-char/ja/
- 特許 `site:patents.google.com 3D scan tool geometry usage parameters archive reproduction manufacturing knowledge capture` → リバースエンジニアリング汎用特許(USRE48498E1等)のみ https://patents.google.com/patent/USRE48498E1/en
- 墓場 `デジタルアーカイブ 事業 予算 終了 更新されない 死蔵 課題 文化財` → 同案の死骸なし。隣接死因=運用予算切れの死蔵 https://www.kantei.go.jp/jp/singi/titeki2/250603/siryou7.pdf
- 最接近先行例: J-Stage復元製作研究+文化財3Dスキャン実務 / 差分: 過去遺物の復元でなく、現役道具の「形状+仕込み・研ぎ・使い癖」を再製作可能性を目的関数に定型記録 / 判定: **差分新規**(様式と実装の未在)

### 4c 説明責任テスト / 4d 反証可能性
- K1: 主F(工房零細で買い手不在・研究は論文で完結)、副B・G。成立/反証可能(48時間で熟練・新人の圧プロファイル判別)
- K4: 主G(乾き頃は計測されない量)、副C。成立/反証可能(塗り2サイクル/48時間。季節較正は[要90日])
- K6: 主F(受益者=未来の使い手に購買力なし・道具職人は支援の影)、副G。成立/記録は48時間可、再現検証は[要30日]
- 残余X: なし

## 6. 発明候補カード(Phase 5、3枚)

### 発明候補カード K1: 手応えけいこメーター
- **仮称**: 手応えけいこメーター(師匠プロファイル差分計)
- **一行仕様**: 伝統工芸の修業者のために、実際の道具(箆・鉋・ろくろ等)に後付けした薄膜圧・IMUセンサーで毎試行の力加減・角度を記録し、師匠の基準プロファイルとの差分を試行直後に提示する練習装置
- **未在診断**: 主類型F(動機の盲点)、副類型B・G。着想は研究で既出だが工房は零細で買い手が見えず、研究は記録・論文で完結。医療・スポーツでは同構造の訓練器が商用化済みなのに、両分野と工芸の人材・学会が重ならない。
- **イネーブラ**: FSRの数百円化 https://akizukidenshi.com/catalog/g/g104002/ 、モーキャプ技能伝承の実績(7年→4年報告) https://www.nobby-tech.co.jp/media/3Dmition/skill_tradition (主類型FのためイネーブラOKは補助要因)
- **部品表**: 薄膜圧センサーFSR402[実在確認済み https://akizukidenshi.com/catalog/g/g104002/ ]/圧力分布フィルム[実在確認済み https://www.arbrown.com/products/tm/wp-content/uploads/2023/11/AR_BROWN_Tekscan_catalog_compressed.pdf ]/IMU・マイコン[実在確認済み(汎用品)]/師匠基準プロファイルと差分提示ロジック[仮定]
- **価値仮説**: 修業者と受け入れ工房。師匠の指摘頻度を週数回→毎試行(2〜3桁増)にし「見て盗む」の試行錯誤年数を圧縮。修業1年短縮=生活費・機会費用で百万円級/人
- **フェルミ検算**: FSR×4+IMU+マイコン ≈ 1万円。修業1年短縮の価値 ≈ 10^6円 → 費用対効果2桁。対象は従事者5.4万人+毎年の研修生
- **新規性ログ**: 5節K1の全7クエリ(存在4+特許1+墓場1、全列挙済み)。最接近先行例: US10109220+デジタルマイスター研究 / 差分: 実道具後付け・師匠差分・毎試行提示の工芸実装なし / 判定=**差分新規**(実装の未在)
- **死亡条件**: (1)センサー装着で道具の手応えが変わり職人が拒否 (2)圧プロファイルが個人差に埋もれ熟練度と相関しない
- **最小実験**: FSR付き箆または鉋で熟練1名・新人2名を48時間内に収録し、盲検でプロファイルから熟練/新人を判別(精度>80%)できるか検証
- **先行指標**: 外科・歯科訓練器の民生価格化/職業訓練校のデジタル教材予算/力触覚記録研究の再活性/産地組合研修へのセンサー導入
- **確信度**: 中(部品ほぼ実在だが差分提示ロジックが仮定。F型ゆえ「作っても買われない」リスクが本体)
- **制約適合メモ**: 技能を代替せず習得を加速する方向で、真正性毀損の除外制約に抵触しない
- **メタ**: 走査日2026-07-03 / taxonomy 1.0 / 全類型掃引

### 発明候補カード K4: 塗り頃ナビ
- **仮称**: 塗り頃ナビ(乾き番)
- **一行仕様**: 漆芸・陶芸の新任者と小工房のために、材料状態(含水率・硬化進行)と環境(温湿度履歴)を安価なセンサーで常時記録し、「塗る/待つ/危険(ちぢみ・割れ予兆)」の工程判断の目安を提示する装置(判断の主体は職人のまま)
- **未在診断**: 主類型G(観測の欠如)、副類型C。「乾き頃・塗り頃」は手の感覚とされ計測対象にならず、量に名前がなく製品カテゴリも立たなかった。実務は「マニュアルなし・各自の経験で環境を作る」と明文化されている。
- **イネーブラ**: 非接触(高周波式)水分計の民生化 https://metoree.com/categories/3281/ 、水分+温湿度同時ロガーの低価格化 https://ureruzo.com/moi00000.htm 、安価BLE温湿度センサーの遍在 https://metoree.com/categories/8787/
- **部品表**: 高周波式水分計[実在確認済み https://metoree.com/categories/3281/ ]/温湿度ロガー[実在確認済み https://ureruzo.com/moi00000.htm ]/「ちぢみ/なまり/割れ」予兆と環境・材料状態の対応則[仮定(至適条件の文献値のみ https://patents.google.com/patent/WO2005078031A1/en )]
- **価値仮説**: 新任者・小工房の乾燥起因の失敗。手戻り1回=数時間の工賃+材料。勘の習得を待たず初年から失敗率を熟練水準へ(適時化1桁)。気候変動で経験則が狂う局面の保険
- **フェルミ検算**: センサー+ロガー ≈ 2万円。失敗1回のロス ≈ 数万円 → 年数回の回避で1年内回収
- **新規性ログ**: 5節K4の全7クエリ(存在4+特許1+墓場1、全列挙済み)。最接近先行例: 汎用乾燥終点制御特許+汎用温湿度監視 / 差分: 環境監視でなく材料状態×環境×工程判断の助言 / 判定=**差分新規**
- **死亡条件**: (1)「良い乾き」が材料ロット・塗り厚・漆の鮮度に依存しすぎ温湿度+含水率では予測精度が出ない (2)職人ごとの流儀差で汎用の目安が受容されない
- **最小実験**: 漆風呂に温湿度ロガー+試験片で塗り2サイクル/48時間、「ちぢみ/なまり」が環境ログから事後分離できるかのみ検証。季節横断較正は[要90日]
- **先行指標**: 漆器産地組合のIoT実証/非破壊含水率計の高精度化/気候変動による乾燥事故報告の増加/他分野の工程判断IoT(発酵等)の商用前例
- **確信度**: 低〜中(部品実在だが対応則が仮定。最小実験が安価で反証が速い)
- **制約適合メモ**: 判断主体は職人のまま勘の習得を補助。工程の自動化・代替ではない
- **メタ**: 走査日2026-07-03 / taxonomy 1.0 / 全類型掃引

### 発明候補カード K6: 道具のデジタル遺言
- **仮称**: 道具のデジタル遺言(再現仕様書キット)
- **一行仕様**: 将来の作り手と産地のために、廃業・引退前の道具職人と使い手の「道具の形状+仕込み・研ぎ角・調整値+使い癖」を、3Dスキャン+定型聞き取り様式で「第三者が再製作・再調整できる仕様書」として残す方法・記法
- **未在診断**: 主類型F(動機の盲点)、副類型G。受益者は「未来の使い手」で現在に購買力・発言力がなく、道具職人は支援の影にいる周辺技術のため誰にも記録の誘因がない。文化財スキャンは過去の遺物に向かい、現役の道具には向かってこなかった。
- **イネーブラ**: スマホ3Dスキャンの無償〜低価格化 https://3d-scantech.jp/column/smartphone/ https://digital-construction.jp/column/630 、文化財3D複製ワークフローの確立 https://www.si.edu/content/MCIImagingStudio/papers/scanning_paper.pdf (主類型FのためイネーブラOKは補助要因)
- **部品表**: スマホ3Dスキャンアプリ[実在確認済み https://3d-scantech.jp/column/smartphone/ ]/リバースエンジニアリング手法[実在確認済み https://patents.google.com/patent/USRE48498E1/en ]/仕込み・研ぎ角・使い癖の定型聞き取り様式(再現可能性を目的関数とする記法)[仮定]
- **価値仮説**: 産地と将来の作り手。供給断絶(与板の鍛冶117人→伝統工芸士4人 https://daiku-dougu.jp/kikou-masayuki.html )後の特注再現は数十万円〜不可能。1本数百円+聞き取り2時間で断絶後の再現可能性を残す=コスト比3桁。工芸・芸能の存続の下部構造(能面・三味線等の道具)を保全
- **フェルミ検算**: 記録 ≈ スキャン0円+聞き取り2h(数千円)/断絶後の代替 ≈ 数十万円または入手不能 → 3桁差。指定241品目×主要道具数十種=記録対象数万件で人手可能な規模
- **新規性ログ**: 5節K6の全7クエリ(存在4+特許1+墓場1、全列挙済み)。最接近先行例: J-Stage復元製作研究+文化財3Dスキャン実務 / 差分: 現役道具の再製作可能性を目的関数に形状+仕込み・研ぎ・使い癖を定型記録 / 判定=**差分新規**(様式と実装の未在)
- **死亡条件**: (1)形状+聞き取りでは再現に足りず鋼材・熱処理の暗黙知が残る(再現実験の失敗) (2)記録費用の払い手が現れない(F型の罠の再帰)。隣接死因=アーカイブの運用予算切れ死蔵 https://www.kantei.go.jp/jp/singi/titeki2/250603/siryou7.pdf は一回性の「遺言」形式で回避する設計が前提
- **最小実験**: 道具1本をスキャン+聞き取り様式で記録し、記録だけで第三者の鍛冶が使用に耐える再現品を作れるか検証[要30日](鍛造を含むため48時間では不可)
- **先行指標**: 文化財DX予算の現役道具への拡張/振興協会「不足情報」掲示の増加 https://kyokai.kougeihin.jp/lack/ /金属3Dプリントの工具鋼対応/道具職人の廃業報道
- **確信度**: 中(部品実在・仮定は様式1件。供給断絶という需要の構造的証拠が強い)
- **制約適合メモ**: 機械量産による代替でなく断絶時の再現可能性の保全。除外制約に該当しない
- **メタ**: 走査日2026-07-03 / taxonomy 1.0 / 全類型掃引

## 7. 帰還レポート(Phase 6)

| 仮称 | 一行仕様(短縮) | 主類型 | 新規性判定 | 確信度 |
|---|---|---|---|---|
| 手応えけいこメーター | 実道具後付けセンサーで師匠との差分を毎試行提示 | F(+B,G) | 差分新規 | 中 |
| 塗り頃ナビ | 材料状態×環境から「塗る/待つ」の目安を提示 | G(+C) | 差分新規 | 低〜中 |
| 道具のデジタル遺言 | 廃業前に道具の形状+使い癖を再現仕様書として残す | F(+G) | 差分新規 | 中 |

最有望はK6(道具のデジタル遺言)。道具・材料の供給断絶は工芸・芸能双方の存続の下部構造を静かに壊しており、記録コスト(ほぼゼロ)と断絶後の代替コスト(数十万円〜不能)の桁差が3桁ある。部品は全て実在し、仮定は聞き取り様式1件のみで、需要は与板の鍛冶の激減など構造的証拠に裏付けられている。

**類型別ヒット率**(原石32+離心4 → 通過5 → 生存3。分子は4c最終診断の主類型): F=2(K1, K6)、G=1(K4)。発火類型ベースの寄与はB・G・H→K1、G→K4、F→K6。K1は発火G/H/B→診断Fのずれあり(オペレータは発掘器であり診断器ではない)。「担い手の地位が低い領域はF・C」という走査モード目安どおりFが主戦場だった。D原石は全滅、Eは既存密集の検出器として機能、離心(鉱業・漁業)は直接生存なし。

**残余X**: なし(生存3件すべて4cで説明成立)。

**改訂提案**: (1) operators-prompts C型に職人領域の信号語(「自作 治具」「代用」「廃業 在庫」)を追記——生活領域語「Excel 管理」は趣味層にヒットが吸われた。(2) 継承・存続系領域では対象外落選(制度・事業)が最大勢力(11/24)になるため、Phase 2 共通規則に「1行仕様は装置・方法・記法へ強制変換してから書く」を追加。(3) search-playbook 解釈規約に「隣接産業(製造業DX等)の現行製品は、差分が用途名だけなら『実質同一』とみなす」を明文化(K3・K5の早期棄却の一般化)。

**定型免責**: 本結果はスクリーニングであり、特許侵害調査(FTO)でも網羅的な先行研究調査でもない。新規性判定はすべて走査日(2026-07-03)時点の暫定判定である。
