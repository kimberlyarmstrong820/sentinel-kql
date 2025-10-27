# Microsoft Sentinel KQL Detections (英日併記 / EN + JA)

This repository contains **Microsoft Sentinel hunting queries** and **analytics detections**, documented with **bilingual comments (English + 日本語)**.  
リポジトリには Microsoft Sentinel 用のハンティングクエリおよび検出ルールを英日併記で収録しています。

---

## Purpose / 目的

### English
- Centralize and version-control all custom Sentinel KQL detections.  
- Encourage bilingual (EN/JA) documentation for knowledge sharing.  
- Support reuse across customers and internal SOC environments.  
- Align detection coverage with **MITRE ATT&CK** framework.

### 日本語
- Sentinel のカスタム検出クエリを一元管理し、バージョン管理を行う。  
- 英日併記コメントにより、社内・顧客間で知識共有を容易にする。  
- MITRE ATT&CK に準拠した検出範囲を維持・改善する。

---

## Repository Structure / 構成

sentinel-kql/
├── README.md # Overview (this file)
│
├── detections/ # Detection queries grouped by domain
│ ├── network/ # ネットワーク関連検出
│ ├── endpoint/ # エンドポイント関連検出
│ └── identity/ # ID・認証関連検出
│
├── templates/ # Import templates for Sentinel
│ ├── analytic_rule_template.yaml # スケジュール分析ルールの雛形
│ └── hunting_query_template.kql # ハンティングクエリの雛形
│
├── references/ # Documentation references
│ ├── mitre_mapping.md # MITRE ATT&CK mapping table
│ └── data_table_notes.md # Table & schema notes
│
└── docs/ # Japanese documentation / 開発メモ
├── README_ja.md
├── 用語集.md
└── 開発メモ.md

---

## Naming Convention / 命名規則

**Format:**

**Examples:**
- `Network_UnusualDNSLookup_T1071.004.kql`
- `Endpoint_ProcessInjection_T1055.kql`
- `Identity_SuspiciousLogin_T1078.kql`

---

## Commenting Style / コメントスタイル

Each query includes bilingual comments for quick understanding.

```kql
// EN: Detect endpoints performing DNS lookups to rarely seen domains.
// JA: 組織内で稀なドメインへのDNS問い合わせを検出。

Usage in Sentinel / Sentinel での利用
Importing a Hunting Query

Open Microsoft Sentinel → Hunting.

Click Add > New Query.
Paste the .kql content from /detections/.

Importing an Analytics Rule
Use /templates/analytic_rule_template.yaml.
Replace the query: section with your .kql content.
Deploy via Sentinel portal or ARM template.

References / 参考リンク

Microsoft Sentinel GitHub (Official Detections)
MITRE ATT&CK Matrix
Kusto Query Language (KQL) Documentation

Contributor Guide / 貢献ルール
Action	Rule
Add new detection	Place under correct domain folder (e.g. detections/network/)
Edit comments	Maintain EN + JA format
Test	Validate query in Sentinel before commit
Map	Update references/mitre_mapping.md accordingly

License / ライセンス

This project is licensed under the MIT License – see the LICENSE
 file for details.
本プロジェクトは MIT ライセンス の下で公開されています。詳細は LICENSE
 をご覧ください。

Maintained by: Kimberly Armstrong & Collaborators
Last Updated: 2025-10-27
