# mizai 実施例: ゲーム(遊びの設計と体験)走査 2026-07(要約版)

> **免責**: 本例は mizai スキルの実行プロセスのデモであり、カードの質・新規性判定は走査日(2026-07-03)時点の暫定判定である。FTO調査ではない。
>
> 走査日: 2026-07-03 / taxonomy 1.0 / 走査モード: 全類型掃引(標準) / 完全ログの基準例は kaigo-scan-2026-07.md を参照

---

## 1. 照準ログ(Phase 0)

- 対象領域: ゲーム(デジタル・アナログを含む遊びの設計と体験)。広いが呼び出し側プリセットで全類型掃引を指定のため分割せず、「遊びの設計と体験」に固定(ハード製造・eスポーツ興行は周縁扱い)
- (a) 価値の定義: プレイヤーの体験の質の新しい次元、および作り手の創造の幅(プリセット)
- (b) 除外制約: 射幸性を煽る仕組み(ガチャ・ルートボックス等)は除外(プリセット)
- (c) 走査モード: 全類型掃引 A→H(プリセット)

## 2. 領域地図の要約(Phase 1、10クエリ・4系統)

### (a) 支配的アプローチ
- 世界市場31兆円・モバイル約6割。ライブサービス・サブスク・UGCが主流 https://gamemakers.jp/article/2025_12_16_126448/ https://www.cesa.or.jp/action/industry-research/2025/ https://www.stand.tech/stacareetech/contents/know-how-004
- 開発コスト高騰・人材不足・生成AIシフトが構造課題。「AIによる面白さの再定義」が業界議題 https://www.creativevillage.ne.jp/category/skillup/industry-commentary/game/169230/ https://gamemakers.jp/article/2025_08_12_114626/

### (b) 直近イネーブラ
1. 生成AI NPC対話の量産出荷(Ghostwriter、NVIDIA ACE) https://beyondtmrw.org/article/generative-ai-in-game-development-npcs-assets-and-ip-risk https://www.hashmeta.ai/en/generative-ai/generative-ai-gaming
2. LLM手続き的ナラティブの学術実装(PANGeA) https://arxiv.org/pdf/2404.19721
3. バイオメトリクス(EEG・視線・EDA)のゲーム応用が実用段階 https://globallearning.world.edu/2025/04/09/the-role-of-biometric-feedback-in-gaming-in-2025/ https://imotions.com/blog/learning/best-practice/biometric-game-testing-from-home-gaming-experience/
4. ハプティクスの価格低下(エントリー$250〜) https://www.techtimes.com/articles/313184/20251208/next-level-immersion-how-vr-haptic-gear-haptic-gaming-suits-are-revolutionizing-sensory-gaming.htm
5. AI GM の研究着手 https://www.teu.ac.jp/gakubu/2023.html?id=141

### (c) ワークアラウンド一覧
- ハウスルール: 人数差・レベル差・先手有利をプレイヤーが自力補正 https://boardgame.nyanta.jp/word/%E3%83%8F%E3%82%A6%E3%82%B9%E3%83%AB%E3%83%BC%E3%83%AB/ https://bodoge.hoobby.net/games/splendor/talks/112 https://note.com/studiogg/n/n00cb19b346bc
- 100均・段ボールの自作コンポーネント、おはじきトークン代用 https://note.com/colonarc/n/nf34a3ecb06f8 https://bdg.kirinnox.com/entry/benri-goods-bdg
- 視覚障害者のメニュー暗記・音響航法。穴は有志Modが塞ぐ https://inviocean.com/play/mod-makers-helping-blind-and-visually-impaired-gamers/ https://www.nexusmods.com/hades/mods/100 https://www.curseforge.com/minecraft/mc-mods/blind-accessibility
- GM不足→有償GM依頼という人力市場 https://qtaro-to-syuzo.hateblo.jp/entry/dont-want-to-do-gamemaster https://coconala.com/categories/175?keyword=trpg https://anond.hatelabo.jp/20220909112357
- 戦績記録は手動アプリ・スプレッドシート https://www.bgstatsapp.com/ https://oneboardfamily.com/keeping-track-of-your-gaming/

### (d) 棚上げ案一覧(死因付き)
- Kinect: 死因=説得力ある用途不在 / Facebook Spaces: 死因=遊びの深さ欠如 https://comicbook.com/gaming/feature/5-biggest-failed-experiments-in-gaming-history-which-ones-could-make-a-comeback-in-2026/
- Virtual Boyマルチプレイ: 死因=ハード普及前の機能放棄 https://www.howtogeek.com/revolutionary-console-features-that-went-unused/
- Google Stadia: 死因=クラウド特質に合わぬ事業モデル https://wired.jp/membership/2021/03/05/google-stadia-games-entertainment-collapse/ https://www.itmedia.co.jp/news/articles/2210/12/news141_2.html
- ピピンアットマーク: 死因=コンセプト過剰・流通・ソフト不足 https://ja.wikipedia.org/wiki/%E3%83%94%E3%83%94%E3%83%B3%E3%82%A2%E3%83%83%E3%83%88%E3%83%9E%E3%83%BC%E3%82%AF
- VRゲーム一般: 死因=快適性・プレイテスト不足 https://blog.gamefirms.com/virtual-reality/why-most-vr-games-fail-and-what-developers-are-doing-wrong/ / AI「生きた世界」訴求: 死因=中身不伴でプレイヤー反発 https://www.hashmeta.ai/en/generative-ai/generative-ai-gaming

### 暗黙前提リスト(13件、抜粋表記)
1.[慣習]ゲームはセッションで時間を専有する 2.[慣習]入力は手指デバイス、生体信号はQA用 3.[慣習]バランス調整は開発者の専権、出荷後はハウスルール(無償労働) 4.[慣習]アナログのルールは紙+人間裁定 5.[経験則]アクセシビリティの穴はModが埋める 6.[慣習]TRPGは人間GMの高負荷労働前提 7.[慣習]難易度は自己申告 8.[経験則]生成AIは開発側で使いランタイムには壁 9.[慣習]戦績・思い出の記録は手作業 10.[慣習]視覚中心設計 11.[法則]同期マルチは同時在席要求 12.[経験則]周辺機器はキラーソフト不在で死ぬ 13.[経験則]体験の質は継続率・課金の代理指標でしか測られない

隣接分野: 教育 / スポーツ(審判・採点・ハンデ) / 即興演劇 / 音楽 / リハビリ医療 / 遊具設計 / 観光

## 3. 原石一覧(Phase 2、30件+離心5件、裏取りなし)

- A1. 対局ログからハウスルール(人数補正・ハンデ)を自動生成し効果検証する卓上バランス調整器 / A+C
- A2. 専有時間ゼロで生活動線の中を進行する「環境ゲーム」駆動法 / A
- A3. 勝敗でなく名場面・逆転を自動抽出して語り直す物語型プレイ記録器 / A+G
- A4. 実行可能ルール+盤面認識で裁定・見落とし指摘を行う卓上審判装置 / A+B
- B1. ゴルフのハンディキャップ算定構造を移植したゲーム横断ハンデ記法・算定器 / B
- B2. 即興演劇の「イエス・アンド」を移植したLLMセッション進行支援 / B
- B3. 音楽のコード譜を移植した「進行骨格だけのシナリオ記法」/ B
- B4. 運動負荷処方を移植した体感ゲームの負荷自動処方器 / B
- C1. ハウスルールの記述・共有・効果測定の標準記法+レジストリ / C
- C2. 100均自作文化を専用化した互換寸法規格+印刷キット / C
- C3. 画面を音響空間へ自動翻訳するエンジンレベルのランタイム層 / C+F
- C4. GM労働(準備・進行負荷)の計測と振り返り自動生成器 / C+G
- D1. Kinectを「状態計測」(疲労・熱中)へ再目的化した調整カメラ / D
- D2. VR社交空間に常駐AIホストが遊び構造を供給する再挑戦機 / D
- D3. LLMナラティブで家庭用TRPG進行機を製品化 / D
- D4. 周辺機器をソフト非依存の「感覚翻訳層」に再設計 / D+C
- E1. [記録×教育] プレイログから判断の癖を返す思考の鏡 / E+G
- E2. [社交×観光] 実在店舗が非同期にクエスト供給する常設周遊装置 / E
- E3. [身体性×音楽] 動作同期度を音に変換する合奏型遊具 / E+G
- F1. 遊びの燃え尽き検出と「遊びの処方」/ F
- F2. 子どもの自由遊びの多様性を測る遊びっぷりメーター / F+G
- F3. 片手・視線入力への自動リマップをエンジン標準にする入力抽象化層 / F
- F4. サ終ゲームの体験を単機保存する記録器 / F
- G1. [未計測]場の盛り上がり → 一階:卓上マイクでスコア化 / 二階:推薦・効果測定 / G
- G2. [未計測]フロー状態 → 一階:入力・視線・生体で推定 / 二階:フロー維持難度調整 / G
- G3. [未計測]ルール説明コスト → 一階:説明時間・質問回数の標準計測 / 二階:自動チュートリアル / G
- G4. [未計測]手加減の質 → 一階:わざと悪手の検出 / 二階:気持ちよく負けられる接待較正 / G
- H1. ルール習得30〜60分 vs 漸進開示数分(1桁) → 読まずに遊び始める段階開示装置 / H
- H2. 人力プレイテスト数十時間 vs AIセルフプレイ数分(2〜3桁) → 自動バランス検査器 / H
- H3. 翻訳待ち数ヶ月 vs 即時(2桁) → 卓上リアルタイム翻訳レイヤ / H
- 離心(乱択: 産業分類10分野、開始23:13の分1桁=3→鉱業・採石): E-x1. 品位管理を移植したUGC自動選鉱器 / B-x1. 閉山計画を移植したサ終ゲームの計画的閉山装置 / X-t1. [1950] 郵便PBMの「1日1手」様式再設計 / X-t2. [2050] 家まるごと遊具化キット / X-c1. [制約反転] 1日5分の点滴ナラティブ進行装置
- 空振りの類型: なし

## 4. 選別の要約(Phase 3)

**統合→通過5件**: K1(A1+B1+C1: 卓上ハンデ工房)、K2(A4+H1+G3: 読まずに遊べる卓上審判)、K3(A3+G1: 卓の記録係)、K4(H2+E-x1: AIセルフプレイ検査器)、K5(G4: 接待較正器)。K4の部品検索で候補全体の先行例らしきものを検知したが、規約により判定せず4aへ持ち越し。

**落選24件の理由分布**: 価値仮説不成立7(A2,B3,D2,E1,E3,F1,F2)/既存密集・差分薄9原石(B2+D3,B4+D1,C3+F3+D4,G2,H3,X-t2)/対象外(規格・事業・様式・制度)6原石(C2,E2,F4+B-x1,X-t1,X-c1)/フェルミ不成立1(C4)。全件の個別理由は走査記録(03-triage)に記載。

## 5. 敵対的検証ログ(Phase 4)

宣言: **「私はこの案を殺すことが仕事の審査官である。生かす証拠ではなく殺す証拠を探す。」**

### K1 存在検索
- Q1 `board game handicap calculator app skill difference balance beginners` → ゴルフ・ボウリング・囲碁の伝統ハンデのみ、反例なし https://www.usga.org/content/usga/home-page/handicapping/world-handicap-system/topics/handicap-index-calculation.html https://en.wikipedia.org/wiki/Handicap_(go)
- Q2 `ボードゲーム ハンデ 自動 算定 アプリ 初心者 勝率 補正` → ポーカーオッズ計算のみ、反例なし
- Q3 `house rule generator balance patch tabletop app suggest handicap based on play history` → ハウスルール一般論のみ、ツールの反例なし https://tabletopbellhop.com/gaming-advice/house-rules/
- Q4 `"why is there no" handicap system board games different skill levels play together` → BGG議論「公式ハンデ設計は稀」 https://boardgamegeek.com/thread/2450192/handicap-in-boardgames https://www.gamedeveloper.com/production/learning-to-love-handicaps-in-competitive-games
- 特許 `site:patents.google.com handicap adjustment player skill rating board game balancing` → デジタルDDA特許群・TCG固有ハンデ https://patents.google.com/patent/US9919217B2/en https://patents.google.com/patent/US20070202952?oq=yugioh https://patents.google.com/patent/US5556095A/en
- 墓場 `skill balancing handicap app startup discontinued failed board game matchmaking shut down` → 死骸なし https://www.lesswrong.com/posts/bASxnkwCaRnT2jmvD/handicapping-competitive-games / 死因: 該当なし
- 最接近先行例: 囲碁の置石制+DDA特許群+BG Stats(記録のみ) https://www.bgstatsapp.com/ / 差分: ゲーム横断・ログ駆動の「算定→ルール変換→接戦率で自動較正」ループ未実装 / 判定: **差分新規**

### K2 存在検索
- Q1 `app that teaches board game rules while playing step by step interactive tutorial` → Dized(状態非認識・台本人手制作) https://dized.com/
- Q2 `camera projector referee physical board game rules enforcement augmented reality tabletop` → AR基盤・研究のみ https://www.digitaltrends.com/gaming/tilt-five-tabletop-video-gaming/ https://www.researchgate.net/publication/301463299_VirtualTable_a_projection_augmented_reality_game
- Q3 `ボードゲーム ルール 覚えなくていい アプリ 遊びながら 教えてくれる` → デジタル移植アプリのみ、物理卓の裁定は反例なし https://app-liv.jp/games/boardgames/2789/
- 特許 `site:patents.google.com computer vision board game state recognition rule enforcement tutorial` → WO2015151106A1(駒移動のルール検証) https://patents.google.com/patent/WO2015151106A1/en https://patents.google.com/patent/US9802115B2/en
- 墓場 `board game companion tutorial app startup shut down discontinued Dized funding` → 死骸なし(Dized継続中) https://getdized.medium.com/our-journey-of-creating-the-board-game-companion-app-dized-2231a802a83 / 死因: 該当なし
- 最接近先行例: Dized+特許WO2015151106A1 / 差分: 「盤面状態に同期した段階的ルール開示×任意の市販ゲームへのLLM自動対応」は未実装 / 判定: **差分新規**(実装の未在)

### K3 存在検索
- Q1 `automatically record game night highlights laughter moments app tabletop memories` → PCゲーム向けクリップ(Powder等)のみ https://www.powder.gg/feature/ai-clips
- Q2 `TRPG セッション 自動 要約 録音 名場面 リプレイ 生成 AI` → TRPG音声感情分析の個人実装(最接近) https://qiita.com/Subara3/items/c83a12226b310f3f2765
- Q3 `board game playtest session audio analytics measure fun engagement microphone tool` → アンケート型・学術のみ https://playtestparlor.com/ https://arxiv.org/pdf/2409.09135
- Q4 `"game night" recap summary app physical board game photos audio automatic` → GM Assistant(議事録型、盛り上がり計測なし) https://gmassistant.app/
- 特許 `site:patents.google.com audio laughter engagement detection highlight generation players session` → 観戦ハイライト・笑い検出特許 https://patents.google.com/patent/US10363488B1/en https://patents.google.com/patent/US8571853B2/en
- 墓場 `Powder gg AI clipping app shut down discontinued pivot` → 死骸あり: Powder.gg(2025年閉鎖・財務理由) https://streamladder.com/blog/powder-gg-is-shutting-down-the-best-alternative-for-streamers-in-2025 / 死因: ストリーマー向けクリップ市場の収益化失敗 / 解消: 部分的(買い手が主催者・デザイナーで市場が異なる[仮定])→確信度を下げて生存
- 最接近先行例: GM Assistant+個人実装+観戦特許群 / 差分: 物理卓の「盛り上がり計測+名場面物語化+デザイン効果測定」統合製品は未実装 / 判定: **差分新規**(実装の未在)

### K4・K5(早期打ち切り→棄却。参考要約)
- K4: 2系統で実質同一の現行サービス・研究群(testingbg・RuleSmith・Boardgame Lab・AlphaZero個人開発) https://www.testingbg.com/ https://arxiv.org/pdf/2602.06232 https://eliteai.tools/tool/boardgame-lab https://note.com/nekodaman/n/nb496ae68605f → **既存**
- K5: 3系統で実質同一(接待どうぶつ将棋AI・動的手加減研究JSAI2023・undetectable DDA特許) https://qiita.com/youwht/items/5989e046d0edac565f05 https://www.jstage.jst.go.jp/article/pjsai/JSAI2023/0/JSAI2023_2M5GS1004/_article/-char/ja/ https://arxiv.org/pdf/1905.10863 → **既存**

### 4c 説明責任テスト / 4d 反証可能性
- K1: 主類型C副B(需要はハウスルールとして無名のまま化石化)。反証実験可能[要2〜3セッション]
- K2: 主類型D副H(壁=ゲーム別人手制作コスト、LLMで解消中)。可能[要7日]
- K3: 主類型G副C(物理卓の盛り上がりは計測されない量)。可能(48時間内)
- 残余X: なし

## 6. 発明候補カード(Phase 5、3枚)

### 発明候補カード K1: 卓上ハンデ工房
- **仮称**: 卓上ハンデ工房(ゲーム横断ハンディキャップ算定器)
- **一行仕様**: 腕前差のある卓(家族・サークル・初心者混在)のために、対局ログから実力とゲーム別実効ハンデを算定し、ルール要素(初期資源・手番・目標点)に変換したハンデ案を提示して適用後の接戦率で自動較正する方法・アプリ
- **未在診断**: 主類型C(名前なき需要)、副類型B(ゴルフWHS・囲碁置石の構造が現代ボドゲに未移植)。腕前差の苦痛はハウスルールという無償の応急処置に吸収され、「卓の公平化」は製品カテゴリとして命名されなかった。
- **イネーブラ**: イネーブラ不要(常に可能だった。レーティング理論は古典)。補助要因: 対局ログアプリの普及 https://www.bgstatsapp.com/
- **部品表**: 対局ログ収集[実在確認済み https://www.bgstatsapp.com/ ]/レーティング算定[実在確認済み(教科書的、置石換算の前例 https://en.wikipedia.org/wiki/Handicap_(go) )]/ハンデ→ルール要素変換テーブル[仮定]
- **価値仮説**: 初心者・子ども混在卓の「勝負にならない」離脱と上級者の接待疲れ。初心者の接戦率を1桁改善。作り手に「ハンデ耐性」という設計次元(創造の幅)
- **フェルミ検算**: 追加ハードゼロ。レーティングはゲームごと対局30件程度で初期較正可。ニッチアプリ市場規模で成立
- **新規性ログ**: 上記5節K1の全6クエリ(存在5+墓場1)。最接近: 囲碁置石+DDA特許US9919217B2+BG Stats / 差分: 横断・ログ駆動・物理卓向け較正ループの不在 / 判定=**差分新規**
- **死亡条件**: (1)ハンデ→ルール変換がゲーム別人手設計になりスケールしない (2)ハンデ明示を初心者が屈辱と感じ使われない
- **最小実験**: 同一グループ同一ゲーム10対局、簡易レーティングから初期資源ハンデを算定・適用し接戦率(最終得点差)を前後比較[要2〜3セッション]
- **先行指標**: ログアプリのAPI開放/BGGハンデ議論の増加/出版社の公式ハンデ表事例/世代混在卓の需要統計
- **確信度**: 中(変換テーブルが仮定。受容性の死亡条件が文化依存)
- **メタ**: 走査日2026-07-03 / taxonomy 1.0 / 全類型掃引

### 発明候補カード K2: 読まずに遊べる卓上審判
- **仮称**: 読まずに遊べる卓上審判(盤面同期チューター)
- **一行仕様**: ルールブックが参入の壁になっている卓のために、スマホカメラの盤面認識とルールブックのLLM変換(実行可能ルール)を組み合わせ、いま必要な規則だけを状況同期で段階開示し違反・見落としをその場で指摘する装置・方法
- **未在診断**: 主類型D(実現手段の遅延)、副類型H(「ルールは読んで覚えるもの」という満足化)。盤面監視×ルール検証は特許・研究で止まり、製品はゲーム別の台本・認識モデルの人手制作コストが壁だった。LLM変換と汎用視覚モデルがその制作コストを桁で下げた。
- **イネーブラ**: 死因=ゲーム別コンテンツの人手制作(Dizedの台本モデル https://getdized.medium.com/our-journey-of-creating-the-board-game-companion-app-dized-2231a802a83 )⇔ 解消=LLMのルール解析・実行可能化 https://arxiv.org/pdf/2602.06232 、盤面認識CVの汎用化 https://blog.roboflow.com/automated-chess-game-recording-computer-vision/
- **部品表**: スマホカメラ+盤面認識CV[実在確認済み https://blog.roboflow.com/automated-chess-game-recording-computer-vision/ ]/ルールの機械実行[実在確認済み https://eliteai.tools/tool/boardgame-lab ]/段階的ルール開示カリキュラム[仮定]
- **価値仮説**: 重量級の新規参加者とインスト役の苦痛。ルール習得30〜60分→5分前後(1桁短縮)、見落としによる「台無しの一戦」を排除。作り手は「説明可能な複雑さ」の天井から解放(創造の幅の新次元)
- **フェルミ検算**: 追加ハード=スタンド数千円。インスト30分×4人=2人時/卓が毎回消える→年10回の卓で20人時回収。1ゲームの初期整備がLLM+少数撮影で数時間なら数千タイトルに展開可
- **新規性ログ**: 上記5節K2の全5クエリ(存在4+墓場1)。最接近: Dized+WO2015151106A1 / 差分: 状態同期の段階開示×任意市販ゲームへの自動対応の不在 / 判定=**差分新規**(実装の未在)
- **死亡条件**: (1)雑然とした実卓での認識精度が実用線(誤指摘1ゲーム数回以下)に届かない (2)LLMのルール解釈誤りが「間違う審判」として信頼を一撃破壊
- **最小実験**: 既存チェス認識+LLM裁定で「見落とし指摘」のみ実装、初見者5人の質問回数・開始所要時間を対照比較[要7日(構築込み)]
- **先行指標**: 出版社のルール機械可読化/Dizedの盤面認識対応発表/AR眼鏡の卓上普及/LLMルール解釈ベンチマーク成熟
- **確信度**: 中(死因解消の証拠はあるが、実環境CVとLLM裁定の二重関門が死亡条件に直結)
- **メタ**: 走査日2026-07-03 / taxonomy 1.0 / 全類型掃引

### 発明候補カード K3: 卓の記録係
- **仮称**: 卓の記録係(盛り上がりレコーダー)
- **一行仕様**: ボドゲ会・家族卓の主催者と自作ゲームの作り手のために、卓上のスマホ1台で笑い・歓声・沈黙・発話均等度から「場の盛り上がり」を時系列計測し、名場面の短い物語とルール変更・ハウスルールの効果測定を返す装置・方法
- **未在診断**: 主類型G(観測の欠如)、副類型C。「あの回は盛り上がった」は主催者の勘としてのみ存在し、物理卓では計測されない量だった。デジタルでは同じ量が感情検知でクリップ化されるのに、卓上には計測器が持ち込まれていない。
- **イネーブラ**: 笑い検出の音響AIが騒音環境でも87〜90%精度 https://project-archive.inf.ed.ac.uk/ug4/20222999/ug4_proj.pdf https://www.isca-archive.org/interspeech_2021/gillick21_interspeech.html 、会話エンゲージメント推定研究 https://arxiv.org/pdf/2409.09135 、要約LLMの汎用化
- **部品表**: スマホ(マイク)[実在確認済み(汎用品)]/笑い・歓声検出モデル[実在確認済み https://github.com/jrgillick/laughter-detection ]/話者分離+文字起こし[実在確認済み(汎用API)]/盛り上がりスコア→名場面対応付け[仮定]
- **価値仮説**: 「遊んだ時間がスコアしか残らない」苦痛と、作り手の「どの瞬間に場が沸くか測れない」苦痛。手動記録比で手間1〜2桁減、プレイテストに盛り上がり実測という新計測次元
- **フェルミ検算**: 追加ハードゼロ。3時間音声の処理は数十〜数百円/回。主催者・デザイナー国内数万人×月額数百円で成立
- **新規性ログ**: 上記5節K3の全6クエリ(存在5+墓場1)。最接近: GM Assistant+TRPG感情分析個人実装+観戦特許US10363488B1 / 差分: 物理卓の「計測+物語化+効果測定」統合製品の不在 / 判定=**差分新規**(実装の未在)
- **死亡条件**: (1)常時録音への卓参加者の抵抗(同意設計)が普及を止める (2)Powderの死因(「嬉しいが払わない」)が本市場でも再現する
- **最小実験**: ボドゲ会2回(各3時間)をスマホ録音し、公開笑い検出モデルのスコア時系列と参加者事後申告の「盛り上がった瞬間」との一致率(上位5場面の再現率)を測定
- **先行指標**: スピーカーOSの笑い検出API公開/ボドゲカフェの体験記録サービス化/プレイテスト定量化需要の顕在化/常時録音の社会受容の変化
- **確信度**: 低〜中(対応付けが仮定。録音受容性と支払意思の両方に死亡条件、近接市場に死骸1体)
- **メタ**: 走査日2026-07-03 / taxonomy 1.0 / 全類型掃引

## 7. 帰還レポート(Phase 6)

| 仮称 | 一行仕様(短縮) | 主類型 | 判定 | 確信度 |
|---|---|---|---|---|
| 卓上ハンデ工房 | 対局ログからゲーム横断ハンデを算定しルール変更案として較正 | C(+B) | 差分新規 | 中 |
| 読まずに遊べる卓上審判 | 盤面認識+LLM実行可能ルールで段階開示と裁定 | D(+H) | 差分新規 | 中 |
| 卓の記録係 | 卓の盛り上がりを音響計測し名場面を物語化・効果測定 | G(+C) | 差分新規 | 低〜中 |

最有望はK2。壁だった「ゲーム別コンテンツの人手制作コスト」がLLMルール変換で桁ごと崩れつつあり(D型の死因解消)、Dized・特許WO2015151106A1という近接先行例が需要とルート実在を示している。「説明可能な複雑さの天井」からの解放は、プリセットの価値定義(作り手の創造の幅)に最も直接に効く。

**類型別ヒット率**(原石30+離心5→通過5→生存3): A=4/3寄与(全カードの起点、ただし主類型では残らず)、B=4/1、C=4/1、D=4/0(原石全滅、だがK2の最終診断はD)、E=3/0、F=4/0、G=4/2(最高効率)、H=3/1、離心=5/0。発火類型と最終診断のずれはK2(A/H/G発→D診断)の1件。

**残余X**: なし(3候補とも4cで説明成立)。

**改訂提案**: (1)領域パラメータ「探索密度」の導入——ゲームのようにAI応用の探索密度が高い領域ではD型原石はほぼ着手済み(K4・K5とも既存死)。D型の期待値を下げC/G型へ配分する較正則を提案 (2)C型判別に「需要に固有名詞が付いているか」チェックを追加(「接待」のように命名済みの需要は競争地帯である率が高い) (3)Phase 3部品検索→4a持ち越しの「持ち越しタグ」書式をsearch-playbookに正式追加(K4で有効に機能)。

**定型免責**: 本結果はスクリーニングであり、特許侵害調査(FTO)でも網羅的な先行研究調査でもない。新規性判定はすべて走査日(2026-07-03)時点の暫定判定である。
