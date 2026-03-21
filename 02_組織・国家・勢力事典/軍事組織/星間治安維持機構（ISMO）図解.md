# 星間治安維持機構（ISMO）図解

## 管理メタ

- 基準時点: 現代
- 公知度: 作者用整理
- 主な認知層: 作者
- 真偽: 現行設定
- 変動性: 高
- 時点依存: 高
- 例外的認知者:

## 注記

- 現時点の設定を視覚化した整理用図解
- 役職名や階級体系は未確定部分があるため、まずは構造と責任範囲の見取り図を優先する
- 細部は今後の議論で更新する前提

## 中枢部組織図

```mermaid
flowchart TB
    Audit["星間国家連合監査"]
    Commander["最高司令官"]

    Audit -. "外部監査" .-> Commander

    subgraph Command["指揮・決裁系"]
        Office["司令官室"]
        Ops["中央作戦統括局"]
        Cases["事案統括局"]
    end

    subgraph Intel["情報・脅威対応系"]
        Analysis["情報総合解析局"]
        Inquiry["情報調査局"]
        Eliminator["対エリミネーター統括局"]
    end

    subgraph Systems["技術・制度系"]
        Tech["技術研究開発局"]
        Legal["法務・規約審査局"]
        Logistics["兵站・艦隊維持局"]
    end

    subgraph Community["人材・共同体系"]
        Personnel["人事・訓練局"]
        Welfare["厚生・共同体支援局"]
        Internal["監察・内部統制局"]
    end

    subgraph Advisory["助言系統"]
        Experts["中央専門家会議"]
        Veterans["現場特任諮問席"]
        Alina["アリナ"]
    end

    Commander --> Office
    Commander --> Ops
    Commander --> Cases
    Commander --> Analysis
    Commander --> Inquiry
    Commander --> Eliminator
    Commander --> Tech
    Commander --> Legal
    Commander --> Logistics
    Commander --> Personnel
    Commander --> Welfare
    Commander --> Internal

    Commander -. "諮問" .-> Experts
    Commander -. "諮問" .-> Veterans
    Commander -. "特別助言" .-> Alina

    Ops --> Fleet["各艦隊司令部"]
    Cases --> Incidents["重大案件再配分"]
    Analysis --> Intelligence["統合分析"]
    Legal --> Rules["ISMO籍 / 特権パスポート / 介入規約"]
    Welfare --> CommunityOps["家族 / 教育 / 退役 / 遺族支援"]
```

## 艦隊編成図

```mermaid
flowchart TB
    FleetCmd["艦隊司令"]

    subgraph Flagship["指令母艦（旗艦）"]
        FleetHQ["艦隊司令部"]
        WideComm["広域通信・統制"]
        FlagOps["艦隊作戦管理"]
    end

    subgraph TaskGroup["機動群（×複数）"]
        subgraph Carrier["母艦"]
            CaseCtrl["案件管理"]
            Med["医療・生活"]
            Supply["補給・整備"]
            Relay["通信中継"]
        end
        Escorts["護衛・戦闘艦 ×数隻"]
        SmallCraft["小型任務艇 ×12前後"]
    end

    subgraph Support["整備群"]
        Yard["工廠艦"]
        Maintain["整備艦"]
        ReSupply["補給艦"]
    end

    FleetCmd --> Flagship
    FleetCmd --> TaskGroup
    FleetCmd --> Support

    FleetHQ --> Carrier
    FleetHQ --> Escorts
    FleetHQ --> SmallCraft
    Support --> Carrier
    Support --> Escorts
```

## 母艦内部署図

```mermaid
flowchart TB
    Captain["母艦指揮層"]

    subgraph Control["司令系"]
        Bridge["艦橋・統制部"]
        CaseBoard["事案管制部"]
        Tactics["作戦部"]
        IntelCell["情報解析部"]
    end

    subgraph SupportDepts["支援系"]
        Medical["医療部"]
        Engineering["整備部"]
        LogisticsDept["補給・兵站部"]
        CraftOps["艦載艇運用部"]
        Life["生活管理部"]
    end

    subgraph Field["現場系"]
        TacticalTeams["戦術要員部"]
        Boats["小型任務艇群"]
    end

    Captain --> Bridge
    Captain --> CaseBoard
    Captain --> Tactics
    Captain --> IntelCell
    Captain --> Medical
    Captain --> Engineering
    Captain --> LogisticsDept
    Captain --> CraftOps
    Captain --> Life
    Captain --> TacticalTeams

    IntelCell --> CaseBoard
    CaseBoard --> Tactics
    Tactics --> Bridge
    Bridge --> CraftOps
    CraftOps --> Boats
    Tactics --> TacticalTeams
    Medical --> TacticalTeams
    Engineering --> Boats
    LogisticsDept --> Boats
    Life --> TacticalTeams
```

## 読み方メモ

- `中枢部組織図` は、最高司令官直下で何がぶら下がるかを見る図
- `艦隊編成図` は、旗艦、機動群、整備群の三層を見る図
- `母艦内部署図` は、母艦が `動く基地` としてどう回るかを見る図
- 今後 `役職・階級体系` が固まったら、この図の各ノードへ肩書を追記できる
