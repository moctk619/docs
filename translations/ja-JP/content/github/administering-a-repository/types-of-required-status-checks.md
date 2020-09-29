---
title: 必須ステータスチェックのタイプ
intro: '必須ステータスチェックのタイプは、[loose] (寛容)、[strict] (厳格) のいずれかに設定できます。 選択した必須ステータスチェックのタイプにより、マージする前にブランチをベースブランチとともに最新にする必要があるかどうかが決まります。'
product: '{% data reusables.gated-features.protected-branches %}'
redirect_from:
  - /articles/types-of-required-status-checks
versions:
  free-pro-team: '*'
  enterprise-server: '*'
---

| 必須ステータスチェックのタイプ | 設定                                                                          | マージの要件                                    | 留意点                                                                                                                               |
| --------------- | --------------------------------------------------------------------------- | ----------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| **Strict**      | [**Require branches to be up-to-date before merging**] チェックボックスにチェックする      | マージ前、ブランチは、base ブランチとの関係で**最新でなければならない**。 | これは、必須ステータスチェックのデフォルト動作です。 他のコラボレーターが、保護された base ブランチにプルリクエストをマージした後に、あなたは head ブランチをアップデートする必要が出てくる可能性があるため、追加のビルドが必要になるかもしれません。 |
| **Loose**       | [**Require branches to be up-to-date before merging**] チェックボックスにチェック**しない** | マージ前、ブランチは base ブランチとの関係で**最新でなくてもよい**。   | 他のコラボレーターがプルリクエストをマージした後に head ブランチをアップデートする必要はないことから、必要となるビルドは少なくなります。 base ブランチと競合する変更がある場合、ブランチをマージした後のステータスチェックは失敗する可能性があります。 |
| **無効**          | [**Require status checks to pass before merging**] チェックボックスにチェック**しない**     | ブランチのマージについての制限はない                        | 必須ステータスチェックが有効化されていない場合、base ブランチにあわせてアップデートされているかどうかに関わらず、コラボレーターはいつでもブランチをマージできます。 このことで、変更の競合が発生する可能性が高まります。                   |

### 参考リンク

- [ステータスチェック必須について](/articles/about-required-status-checks)
- [ステータスチェック必須の有効化](/articles/enabling-required-status-checks)