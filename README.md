# 未在工学 / Absence Engineering

**なぜまだ無いのか、の系統的走査(Why-Not-Yet Scanning)**

未在工学は、未発見の発明を探すためのフレームワークである。ただし「アイデアの空間」は探索しない。探索するのは**「大発明が未発見のまま残存する構造的理由」の空間**である。

歴史上の大発明の多くは、部品も需要も揃ってから長く放置されていた。スーツケースに車輪が付くまで、人類は動力飛行の実現後さらに70年を要した。放置には理由の型がある——共有された偽の前提(前提の檻)、分野間の断絶、名前の無い需要、棚上げされた案の死因の失効、広すぎる組合せ空間、誘因の欠如、計測手段の不在、「十分よい」解の影。未在工学はこの型を分類学(未在類型 A〜H+X)として整備し、型ごとの検出手続きと敵対的検証を、LLM エージェントが実行可能な手順書に落とした。

## 約束しないこと・すること

- **約束しない**: 大発明の保証。新規性の確定判定(Web検索による判定はスクリーニングであり、特許調査ではない)。分布外の天才的跳躍
- **約束する**: 未発見が残存する構造的理由の系統的走査。検索ログ・死亡条件・最小実験を装備した、翌日から検証に動ける候補カード。そして体系自身の反証条件の明示(docs/00 §5)

## 30秒の使い方

このリポジトリを Claude Code で開き、こう頼む:

```
在宅介護の領域を未在走査して
```

`mizai` スキル(`.claude/skills/mizai/SKILL.md`)が起動し、照準→地図化→走査→選別→敵対的検証→カード化→帰還の7フェーズを実行して、発明候補カードを返す。

## 文書地図

| 文書 | 内容 |
|---|---|
| [docs/00-overview.md](docs/00-overview.md) | 総論: 中核の転回、パイプライン全景、限界と反証可能性 |
| [docs/01-taxonomy.md](docs/01-taxonomy.md) | **中核文書**: 未在類型 A〜H+X の分類学 |
| [docs/02-operators.md](docs/02-operators.md) | 類型別の検出オペレータ(発掘→変換) |
| [docs/03-verification.md](docs/03-verification.md) | 敵対的検証・三重ゲート・LLM幻覚対策・新規性判定の言語規約 |
| [docs/04-theory-map.md](docs/04-theory-map.md) | TRIZ・C-K理論等との接続と差分、想定反論への応答 |
| [docs/05-self-application.md](docs/05-self-application.md) | 自己適用: フレームワーク自身の発明候補カードと改訂ループ |
| [.claude/skills/mizai/SKILL.md](.claude/skills/mizai/SKILL.md) | エージェント実行手順書(Phase 0〜6) |

## 実施例(実走査の記録)

| 領域 | ファイル |
|---|---|
| 在宅介護(基準例・完全ログ) | [examples/kaigo-scan-2026-07.md](examples/kaigo-scan-2026-07.md) |
| ゲーム | [examples/game-scan-2026-07.md](examples/game-scan-2026-07.md) |
| 子育て | [examples/kosodate-scan-2026-07.md](examples/kosodate-scan-2026-07.md) |
| 伝統文化 | [examples/dentou-scan-2026-07.md](examples/dentou-scan-2026-07.md) |
| システム開発 | [examples/sysdev-scan-2026-07.md](examples/sysdev-scan-2026-07.md) |
| AI | [examples/ai-scan-2026-07.md](examples/ai-scan-2026-07.md) |
| システムインフラ | [examples/infra-scan-2026-07.md](examples/infra-scan-2026-07.md) |

## 知的誠実性の宣言

本フレームワークは大発明を保証しない。**未発見が残存する構造的理由を系統的に走査する**。生成されるカードの新規性判定はすべて走査日時点の暫定判定であり、判定の本体は判定語ではなく検索ログである。体系自身も同じ基準に服する: 自己診断は「差分新規」(docs/05)、死亡条件は明記済み(docs/00 §5)。

---

現行バージョン: taxonomy 1.0(2026-07)
