# 職務経歴書

2026年10月12日現在
氏名：星野 竜吾（Ryugo Hoshino）

---

## 職務要約

千葉工業大学 情報変革科学部 情報工学科 1年。
Flosrumの創業者として、AR環境アセスメントアプリ「Provirium」を開発・提供している。
2021年からWebサービス・Bot・組込みシステムを個人で開発しており、バックエンド開発を得意とする。
現在はOS・低レイヤ領域を中心に技術を深めている。

---

## 学歴

| 年月 | 内容 |
|---|---|
| 2026年4月 | 千葉工業大学 情報変革科学部 情報工学科 入学 |

---

## 職務経歴

### Flosrum　代表（2025年4月開業／本格始動前）

個人で立ち上げたプロダクト開発組織。企画・設計・実装・Web制作・価格設定までを一人で担当。

#### Provirium — AR環境アセスメントアプリ（2024年11月〜／現行 v1.6.1）

- **概要**：建設予定の構造物（風力発電機）をスマートフォンのARで擬似配置し、景観の変化を確認できるアプリケーション
- **技術**：Unity 2022.3 / C# / AR Foundation 5.2 / Niantic Lightship ARDK / Google Sheets API / UniTask / Unity Localization / NativeGallery
- **プラットフォーム**：iOS（Androidビルド設定あり）
- **実装内容**
  - GPS座標と端末の真北方位から、建設予定地点をAR空間上の位置に変換する位置情報型AR
  - 国土地理院の測量計算アルゴリズムに基づく、GRS80楕円体上の距離・方位角計算を自前実装
  - 建設予定物の方位をコンパスバーにアイコン表示
  - 最大3事業の風車を同時配置。ハブ高・ブレード長などの諸元に応じて3Dモデルの寸法を調整
  - AR FoundationとLightshipのオクルージョン・セマンティックセグメンテーションによる、手前の建物や人物の遮蔽表現（オン・オフ切り替え可）
  - 事業データ（AR設定データ）をGoogle Sheetsから取得し、端末側で設定ファイルとして管理
  - 撮影画面のスクリーンショット保存、日本語・英語の多言語対応
- **規模**：自作スクリプト約3,100行（C#・21ファイル）
- **提供形態**：閲覧無料、AR設定データの登録は1事業あたり2,000円、登録後半年時点でPay What You Want方式
- **実績**：（仮称）西山風力発電開発事業（12基）のデータを、地域住民からの申込みにより登録・公開

#### Flosrum公式サイト（2025年4月〜）

- **技術**：Node.js / Express / EJS / SCSS / Google Sheets API
- **内容**：企業サイト、Provirium製品ページ、登録データ一覧ページ（Google Sheetsから動的生成）、法的情報・プライバシーポリシー
- **規模**：50コミット（2025年4月〜2026年10月）

#### Tsugimichi — ドライブ先発見のための写真投稿サービス（2026年9月〜／開発中）

- **概要**：ドライブで訪れたスポットの写真を投稿し、Pinterest風のグリッドで次の行き先を探せるUGCサービス
- **技術**：Go 1.26 / Gin / sqlc / PostgreSQL + PostGIS / Next.js（App Router） / TypeScript / Cloudflare R2 / Docker Compose
- **実装内容**
  - 投稿・スポット・認証・画像アップロード・管理のREST API
  - JWT（httpOnly Cookie）とbcryptによる自前認証、レートリミット
  - R2のpresigned URLによるクライアント直接アップロード、サイズ制限と圧縮
  - PostGISのGiSTインデックスと`ST_DWithin`による近傍スポット検索
  - golang-migrateによるスキーマ管理（マイグレーション6本）
  - 地図・住所補完つき検索、投稿管理、通報、管理画面
- **規模**：約11,700行・117ファイル
- **設計資料**：仕様書・API定義（12エンドポイント）・DB設計書を整備

---

## 個人開発

### Hunter Eye System — 赤外線追跡によるARロックオンシステム（2025年〜）

- **概要**：対象に装着した赤外線LEDをカメラで追跡し、個別のAR演出を重ねるシステム
- **技術**：Python / Raspberry Pi / Picamera2 / OpenCV / scikit-learn（DBSCAN） / OpenGL（GLFW） / シリアル通信
- **内容**：赤外線光点の検出とクラスタリング、ロックオン表示の描画、外部機器とのシリアル連携。試作を段階的に重ね、7世代の追跡アルゴリズムを実装

---

## 初期の制作物（2021〜2022年）

| 名称 | 技術 | 内容 |
|---|---|---|
| CSI_System | JavaScript / Discord.js v13 | 指定チャンネルへの投稿有無をメンバーごとに判定するDiscord Bot（MIT License で公開） |
| Discord時報Bot | Python / discord.py | 管理者が対話形式で時刻を設定できる時報Bot |
| Starkaru_gundan_web | PHP / Laravel | ブログ・お知らせの投稿管理機能を持つグループ公式サイト |
| hello-cha | PHP | ユーザー登録・投稿・メール機能を持つ投稿型SNS |
| 体温報告サーバー | PHP | 体温の登録・閲覧・削除を行うWebシステム |
| Arc_compressor | Batch | ゲームMOD用ファイルの一括圧縮・リネームツール（一般配布） |

---

## スキル

| 分類 | 内容 |
|---|---|
| 言語 | C / C++ / C# / Go / JavaScript / TypeScript / Python / Swift / Kotlin / PHP |
| バックエンド | Go（Gin, sqlc）/ Node.js（Express）/ PHP（Laravel） |
| フロントエンド | Next.js / EJS / SCSS |
| AR・モバイル | Unity / AR Foundation / Niantic Lightship ARDK（iOS） |
| データベース | PostgreSQL / PostGIS / Google Sheets API |
| インフラ | Docker / Docker Compose / Cloudflare R2 |
| 組込み・ハードウェア | Raspberry Pi / Arduino / OpenCV / OpenGL |

