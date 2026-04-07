# インフラ検証環境の構築計画 (フェーズ1)

## 概要
全てのシステム（AD, Mailcow, Nextcloud等）をオンプレミスで構築することを目指し、まずはローカルの **Mac PC** 上で全てのコンテナを Docker Compose で立ち上げ、統合検証を行います。

## 検証環境の構成
1.  **ホスト (Mac PC)**:
    *   Docker Desktop または OrbStack を使用。
    *   `docker-compose.yml` により、全サービスを同一ネットワーク内で起動。
2.  **サービス群**:
    *   Windows Server 2025 (VM または LDAPシミュレータ)
    *   Mailcow, Nextcloud, NPM, Authentik, etc. (Dockerコンテナ)

## 準備タスク
- [ ] **Mac PC の環境構築**
    - [ ] Docker環境の整備。
    - [ ] 統合用 `docker-compose.yml` の作成。
- [ ] **統合テストの実施**
    - [ ] 全コンテナの正常起動確認。
    - [ ] 同期スクリプトによる AD ↔ Mailcow の疎通テスト。
- [ ] **移行準備**
    - [ ] データの永続化設定。
    - [ ] 将来のVPS移行を見据えた設定の変数化。

## 今後のスケジュール
1.  全コンテナを Mac 上で揃える。
2.  同期アプリの実装と検証。
3.  検証完了後、実機（Lenovoサーバー）への展開。
