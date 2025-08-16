# Diagrams

### Service Structure Diagram

```mermaid
flowchart TD
    %% Groups level
    G1[Group]
    G2[Group]
    G3[Group]
    G4[Group]
    G5[Group]
    G6[Group]
    G7[Group]
    G8[Group]
    G9[Group]
    G10[Group]
    G11[Group]
    G12[Group]
    
    %% Local Service level
    GSF[Group Support Forum GSF]
    LSC[Local Service Conference LSC]
    MSC1[Metropolitan Service Committee MSC]
    MSC2[Metropolitan Service Committee MSC]
    
    %% Area Service Committees
    ASC1[Area Service Committee ASC]
    ASC2[Area Service Committee ASC]
    ASC3[Area Service Committee ASC]
    ASC4[Area Service Committee ASC]
    
    %% Regional Service Committees
    RSC1[Regional Service Committee RSC]
    RSC2[Regional Service Committee RSC]
    RSC3[Regional Service Committee RSC]
    RSC4[Regional Service Committee RSC]
    
    %% Regional Assembly
    RA[Regional Assembly]
    
    %% Zonal level
    ZF1[Zonal Forum]
    ZF2[Zonal Forum]
    
    %% World Service Conference
    WSC[World Service Conference WSC]
    
    %% World Services
    WB[World Board]
    EC[Executive Committee]
    WG[Workgroups or Committees]
    HRP[Human Resource Panel]
    WP[World Pool]
    WSO[World Service Office]
    
    %% Groups to Local Services
    G1 -->|GSR| GSF
    G2 -->|GSR| GSF
    G3 -->|GSR| GSF
    G4 -->|GSR| LSC
    G5 -->|GSR| MSC1
    G6 -->|GSR| MSC1
    G7 -->|GSR| ASC1
    G8 -->|GSR| ASC2
    G9 -->|GSR| ASC3
    G10 -->|GSR| ASC4
    G11 -->|GSR| MSC2
    G12 -->|GSR| MSC2
    
    %% Local to Area
    GSF --> ASC1
    LSC -->|RCM| RSC1
    MSC1 --> ASC2
    MSC2 --> ASC3
    
    %% Area to Regional
    ASC1 -->|RCM| RSC1
    ASC2 -->|RCM| RSC2
    ASC3 -->|RCM| RSC3
    ASC4 -->|RCM| RSC4
    
    %% Regional Assembly connection
    RSC2 --> RA
    
    %% Regional to Zonal
    RSC1 -->|Regional Delegate| ZF1
    RSC2 -->|Regional Delegate| ZF1
    RSC3 -->|Regional Delegate| ZF2
    RSC4 -->|Regional Delegate| ZF2
    
    %% Zonal to World Service Conference
    ZF1 -->|Zonal Delegate| WSC
    ZF2 -->|Zonal Delegate| WSC
    
    %% World Service Conference oversight
    WSC --> WB
    WSC --> HRP
    
    %% World Board services
    WB --> EC
    WB --> WG
    WB --> WSO
    HRP --> WP
    
    %% Styling
    classDef groupStyle fill:#4a90e2,stroke:#2171b5,stroke-width:2px,color:#fff
    classDef localStyle fill:#5cb85c,stroke:#449d44,stroke-width:2px,color:#fff
    classDef areaStyle fill:#5cb85c,stroke:#449d44,stroke-width:2px,color:#fff
    classDef regionalStyle fill:#f0ad4e,stroke:#ec971f,stroke-width:2px,color:#fff
    classDef zonalStyle fill:#f7e835,stroke:#f0d000,stroke-width:2px,color:#000
    classDef worldStyle fill:#d9534f,stroke:#c9302c,stroke-width:3px,color:#fff
    classDef serviceStyle fill:#9b59b6,stroke:#8e44ad,stroke-width:2px,color:#fff
    classDef poolStyle fill:#1abc9c,stroke:#16a085,stroke-width:2px,color:#fff
    
    class G1,G2,G3,G4,G5,G6,G7,G8,G9,G10,G11,G12 groupStyle
    class GSF,LSC,MSC1,MSC2 localStyle
    class ASC1,ASC2,ASC3,ASC4 areaStyle
    class RSC1,RSC2,RSC3,RSC4,RA regionalStyle
    class ZF1,ZF2 zonalStyle
    class WSC worldStyle
    class WB,EC,WG,WSO serviceStyle
    class HRP,WP poolStyle
```

### Translations Process

```mermaid
flowchart TD
    START([Start]) --> RESOURCES{Are local resources available?}
    
    RESOURCES -->|No| HIRE[Hire a Translator]
    RESOURCES -->|Yes| LOCAL[Local Translation Committee]
    
    HIRE --> WRITE[Write Draft]
    LOCAL --> WRITE
    
    WRITE --> IP1{Is it IP#1/Glossary?}
    
    IP1 -->|Yes| STAFF1[Staff reviews & documents]
    IP1 -->|No| STAFF2[Staff reviews & documents]
    
    STAFF1 --> WB_EVAL[World Board & Evaluator]
    STAFF2 --> LTC_REVIEW[LTC review]
    
    WB_EVAL --> STAFF_COMPILE[Staff compiles comments]
    LTC_REVIEW --> STAFF_COMPILE
    
    STAFF_COMPILE --> PROOF[Proofreading]
    
    PROOF --> PROOFREADER[Proofreader]
    
    PROOFREADER --> ISSUES{Are there issues?}
    
    ISSUES -->|Yes| STAFF_COMPILE
    ISSUES -->|No| TYPESET[Typesetting]
    
    TYPESET --> LTC_FINAL[LTC final approval]
    
    LTC_FINAL --> STAFF_APPROVAL{Staff Approval}
    
    STAFF_APPROVAL -->|No| STAFF_COMPILE
    STAFF_APPROVAL -->|Yes| QUALITY[Staff quality control]
    
    QUALITY --> PRINTER[Goes to printer]
    
    %% Styling
    classDef startStyle fill:#4CAF50,stroke:#45a049,stroke-width:2px,color:#fff
    classDef processStyle fill:#2196F3,stroke:#1976D2,stroke-width:2px,color:#fff
    classDef decisionStyle fill:#FF9800,stroke:#F57C00,stroke-width:2px,color:#fff
    classDef reviewStyle fill:#9C27B0,stroke:#7B1FA2,stroke-width:2px,color:#fff
    classDef finalStyle fill:#4CAF50,stroke:#45a049,stroke-width:2px,color:#fff
    
    class START startStyle
    class WRITE,HIRE,LOCAL,STAFF_COMPILE,PROOF,PROOFREADER,TYPESET,QUALITY,PRINTER processStyle
    class RESOURCES,IP1,ISSUES,STAFF_APPROVAL decisionStyle
    class STAFF1,STAFF2,WB_EVAL,LTC_REVIEW,LTC_FINAL reviewStyle
    class PRINTER finalStyle
```

### Fund Flow

```mermaid
flowchart TD
    GROUP[GROUP]
    AREA[AREA]
    METRO[METRO]
    REGION[REGION]
    ZONE[ZONE]
    WORLD[WORLD SERVICES]

%% Direct donations from groups
    GROUP -->|Direct donation| AREA
    GROUP -->|Direct donation| METRO
    GROUP -->|Direct donation| REGION
    GROUP -->|Direct donation| ZONE
    GROUP -->|Direct donation| WORLD

%% Fund flow through hierarchy
    AREA -->|Funnel for metro services| METRO
    METRO -->|Return excess funds| AREA
    AREA -->|Contribute excess funds| REGION
    AREA -->|Contribute excess funds| WORLD
    REGION -->|Contribute excess funds| ZONE
    REGION -->|Contribute excess funds| WORLD
    ZONE -->|Contribute excess funds| WORLD
    
%% Styling
    classDef groupStyle fill:#e1f5fe,stroke:#01579b,color:#000,stroke-width:2px
    classDef areaStyle fill:#f3e5f5,stroke:#4a148c,color:#000,stroke-width:2px
    classDef metroStyle fill:#e8f5e8,stroke:#1b5e20,color:#000,stroke-width:2px
    classDef regionStyle fill:#fff3e0,stroke:#e65100,color:#000,stroke-width:2px
    classDef worldStyle fill:#fce4ec,stroke:#880e4f,color:#000,stroke-width:2px
    classDef zoneStyle fill:#fce4ec,stroke:#880e4f,color:#000,stroke-width:2px

    class GROUP groupStyle
    class AREA areaStyle
    class METRO metroStyle
    class REGION regionStyle
    class WORLD worldStyle
    class ZONE zoneStyle
```

## Area Service Committee

```mermaid
flowchart TD
    G1[G]
    G2[G]
    G3[G]
    G4[G]
    G5[G]
    G6[G]
    G7[G]
    G8[G]
    G9[G]
    
    ASC[AREA SERVICE COMMITTEE]
    
    HI[H&I]
    PI[PI]
    TRANS[TRANSLATIONS]
    LIT[LITERATURE SUPPLY]
    ACT[ACTIVITIES]
    OUT[OUTREACH]
    PHONE[PHONELINE]
    NEWS[NEWSLETTER]
    
    %% Groups send GSRs to Area Service Committee
    G1 -->|GSR| ASC
    G2 -->|GSR| ASC
    G3 -->|GSR| ASC
    G4 -->|GSR| ASC
    G5 -->|GSR| ASC
    G6 -->|GSR| ASC
    G7 -->|GSR| ASC
    G8 -->|GSR| ASC
    G9 -->|GSR| ASC
    
    %% Area Service Committee oversees subcommittees
    ASC --> HI
    ASC --> PI
    ASC --> TRANS
    ASC --> LIT
    ASC --> ACT
    ASC --> OUT
    ASC --> PHONE
    ASC --> NEWS
    
    %% Styling
    classDef groupStyle fill:#e3f2fd,stroke:#1976d2,stroke-width:2px,color:#000
    classDef ascStyle fill:#f3e5f5,stroke:#7b1fa2,stroke-width:3px,color:#000
    classDef subcommitteeStyle fill:#e8f5e8,stroke:#388e3c,stroke-width:2px,color:#000
    
    class G1,G2,G3,G4,G5,G6,G7,G8,G9 groupStyle
    class ASC ascStyle
    class HI,PI,TRANS,LIT,ACT,OUT,PHONE,NEWS subcommitteeStyle
```


### Rural Area with CO-OPS

```mermaid
flowchart TD
    subgraph COOP1 ["CO-OP #1: Groups A, B, C, D<br/>Four close rural towns"]
        A[Group A]
        B[Group B]
        C[Group C]
        D[Group D]
    end
    
    E[Group E]
    F[Group F]
    G[Group G]
    
    subgraph COOP2 ["CO-OP #2: Groups H, I, J, K, L"]
        H[Group H]
        I[Group I]
        J[Group J]
        K[Group K]
        L[Group L]
    end
    
    COUNTY[County Seat]
    
    %% Connections to County Seat
    COOP1 --> COUNTY
    E --> COUNTY
    F --> COUNTY
    G --> COUNTY
    COOP2 --> COUNTY
    
    %% Styling
    classDef groupStyle fill:#e3f2fd,stroke:#1976d2,stroke-width:2px,color:#000
    classDef coopStyle fill:#fff3e0,stroke:#f57c00,stroke-width:2px,color:#000
    classDef countyStyle fill:#f3e5f5,stroke:#7b1fa2,stroke-width:3px,color:#000
    
    class A,B,C,D,E,F,G,H,I,J,K,L groupStyle
    class COUNTY countyStyle
    
    %% Style the subgraphs
    classDef default fill:#fff8e1,stroke:#ff8f00,stroke-width:2px
```

### Area Shared Services Committee

```mermaid
flowchart TD
    %% Groups for each area
    G1A[G] 
    G2A[G]
    G3A[G]
    
    G1B[G]
    G2B[G]
    G3B[G]
    G4B[G]
    
    G1C[G]
    G2C[G]
    
    G1D[G]
    G2D[G]
    
    G1E[G]
    G2E[G]
    
    %% Areas and their subcommittees
    AREA1[AREA]
    SUB1[SUB]
    
    AREA2[AREA]
    SUB2[SUB]
    
    AREA3[AREA]
    SUB3[SUB]
    
    AREA4[AREA]
    SUB4[SUB]
    
    AREA5[AREA]
    SUB5[SUB]
    
    %% Shared Services Committee
    SSC[SHARED SERVICES COMMITTEE]
    
    %% Note box
    NOTE["Shared services committee<br/>fulfills generally one or<br/>two specific functions"]
    
    %% Groups to Areas
    G1A --> AREA1
    G2A --> AREA1
    G3A --> AREA1
    
    G1B --> AREA2
    G2B --> AREA2
    G3B --> AREA2
    G4B --> AREA2
    
    G1C --> AREA3
    G2C --> AREA3
    
    G1D --> AREA4
    G2D --> AREA4
    
    G1E --> AREA5
    G2E --> AREA5
    
    %% Areas to Shared Services Committee
    AREA1 --> SSC
    AREA2 --> SSC
    
    %% Note connection
    NOTE --> SSC
    
    %% Styling
    classDef groupStyle fill:#e3f2fd,stroke:#1976d2,stroke-width:2px,color:#000
    classDef areaStyle fill:#fff3e0,stroke:#f57c00,stroke-width:2px,color:#000
    classDef subStyle fill:#e8f5e8,stroke:#388e3c,stroke-width:2px,color:#000
    classDef sscStyle fill:#f3e5f5,stroke:#7b1fa2,stroke-width:3px,color:#000
    classDef noteStyle fill:#fff9c4,stroke:#f9a825,stroke-width:1px,color:#000
    
    class G1A,G2A,G3A,G1B,G2B,G3B,G4B,G1C,G2C,G1D,G2D,G1E,G2E groupStyle
    class AREA1,AREA2,AREA3,AREA4,AREA5 areaStyle
    class SUB1,SUB2,SUB3,SUB4,SUB5 subStyle
    class SSC sscStyle
    class NOTE noteStyle
```

### Regional Service Modal

```mermaid
flowchart TD
    %% Groups for each area
    G1A[G] 
    G2A[G]
    G3A[G]
    G4A[G]
    
    G1B[G]
    G2B[G]
    G3B[G]
    
    G1C[G]
    G2C[G]
    G3C[G]
    
    G1D[G]
    G2D[G]
    G3D[G]
    
    G1E[G]
    G2E[G]
    G3E[G]
    
    %% Areas and their subcommittees
    AREA1[AREA]
    AREA2[AREA]
    AREA3[AREA]
    AREA4[AREA]
    AREA5[AREA]
    SUB4[SUB]
    SUB5[SUB]
    
    %% Metro Committee
    METRO[METRO COMMITTEE]
    
    %% Regional Service Committee
    RSC[REGIONAL SERVICE COMMITTEE]
    
    %% Note
    NOTE["no subcommittees, but<br/>resource assignments"]
    
    %% Groups to Areas
    G1A --> AREA1
    G2A --> AREA1
    G3A --> AREA1
    G4A --> AREA1
    
    G1B --> AREA2
    G2B --> AREA2
    G3B --> AREA2
    
    G1C --> AREA3
    G2C --> AREA3
    G3C --> AREA3
    
    G1D --> AREA4
    G2D --> AREA4
    G3D --> AREA4
    
    G1E --> AREA5
    G2E --> AREA5
    G3E --> AREA5
    
    %% Areas to Metro Committee (some areas)
    AREA1 -.-> METRO
    AREA2 -.-> METRO
    AREA3 -.-> METRO
    
    %% All areas and metro to Regional Service Committee
    AREA1 -.-> RSC
    AREA2 -.-> RSC
    AREA3 -.-> RSC
    AREA4 -.-> RSC
    AREA5 -.-> RSC
    METRO -.-> RSC
    
    %% Note connection
    NOTE --> RSC
    
    %% Styling
    classDef groupStyle fill:#e3f2fd,stroke:#1976d2,stroke-width:2px,color:#000
    classDef areaStyle fill:#fff3e0,stroke:#f57c00,stroke-width:2px,color:#000
    classDef subStyle fill:#e8f5e8,stroke:#388e3c,stroke-width:2px,color:#000
    classDef metroStyle fill:#e1f5fe,stroke:#0277bd,stroke-width:2px,color:#000
    classDef rscStyle fill:#f3e5f5,stroke:#7b1fa2,stroke-width:3px,color:#000
    classDef noteStyle fill:#fff9c4,stroke:#f9a825,stroke-width:1px,color:#000
    
    class G1A,G2A,G3A,G4A,G1B,G2B,G3B,G1C,G2C,G3C,G1D,G2D,G3D,G1E,G2E,G3E groupStyle
    class AREA1,AREA2,AREA3,AREA4,AREA5 areaStyle
    class SUB4,SUB5 subStyle
    class METRO metroStyle
    class RSC rscStyle
    class NOTE noteStyle
```

### Regional Committee

```mermaid
flowchart TD
    %% Groups for each area
    G1A[G] 
    G2A[G]
    G3A[G]
    G4A[G]
    
    G1B[G]
    G2B[G]
    G3B[G]
    
    G1C[G]
    G2C[G]
    G3C[G]
    
    G1D[G]
    G2D[G]
    G3D[G]
    
    G1E[G]
    G2E[G]
    G3E[G]
    
    %% Areas and their subcommittees
    AREA1[AREA]
    SUB1[SUB]
    
    AREA2[AREA]
    SUB2[SUB]
    
    AREA3[AREA]
    SUB3[SUB]
    
    AREA4[AREA]
    SUB4[SUB]
    
    AREA5[AREA]
    SUB5[SUB]
    
    %% Regional Service Committee and subcommittees
    RSC[REGIONAL SERVICE COMMITTEE]
    RSO[RSO]
    CONV[CONV.]
    HI[H&I]
    PI[PI]
    
    %% Regional Assembly
    RA[REGIONAL ASSEMBLY]
    
    %% Note
    NOTE["Event attended<br/>by all GSRs, RCMs"]
    
    %% Groups to Areas
    G1A --> AREA1
    G2A --> AREA1
    G3A --> AREA1
    G4A --> AREA1
    
    G1B --> AREA2
    G2B --> AREA2
    G3B --> AREA2
    
    G1C --> AREA3
    G2C --> AREA3
    G3C --> AREA3
    
    G1D --> AREA4
    G2D --> AREA4
    G3D --> AREA4
    
    G1E --> AREA5
    G2E --> AREA5
    G3E --> AREA5
    
    %% Areas send RCMs to Regional Service Committee
    AREA1 -->|RCM| RSC
    AREA2 -->|RCM| RSC
    AREA3 -->|RCM| RSC
    AREA4 -->|RCM| RSC
    AREA5 -->|RCM| RSC
    
    %% Regional subcommittees
    RSO --> RSC
    CONV --> RSC
    HI --> RSC
    PI --> RSC
    
    %% Regional Assembly connection
    RSC --> RA
    NOTE --> RA
    
    %% Styling
    classDef groupStyle fill:#e3f2fd,stroke:#1976d2,stroke-width:2px,color:#000
    classDef areaStyle fill:#fff3e0,stroke:#f57c00,stroke-width:2px,color:#000
    classDef subStyle fill:#e8f5e8,stroke:#388e3c,stroke-width:2px,color:#000
    classDef rscStyle fill:#f3e5f5,stroke:#7b1fa2,stroke-width:3px,color:#000
    classDef raStyle fill:#ffebee,stroke:#c62828,stroke-width:3px,color:#000
    classDef noteStyle fill:#263238,stroke:#37474f,stroke-width:1px,color:#fff
    
    class G1A,G2A,G3A,G4A,G1B,G2B,G3B,G1C,G2C,G3C,G1D,G2D,G3D,G1E,G2E,G3E groupStyle
    class AREA1,AREA2,AREA3,AREA4,AREA5 areaStyle
    class SUB1,SUB2,SUB3,SUB4,SUB5 subStyle
    class RSC,RSO,CONV,HI,PI rscStyle
    class RA raStyle
    class NOTE noteStyle
```

### Regional Shared Services Committee

```mermaid
flowchart TD
    REGION1[REGION]
    REGION2[REGION]
    REGION3[REGION]

    SSC[SHARED SERVICES COMMITTEE]

    NOTE["Shared services committee<br/>fulfills generally one or<br/>two specific functions"]

%% Regions to Shared Services Committee
    REGION1 --> SSC
    REGION2 --> SSC
    REGION3 --> SSC

%% Note connection
    NOTE --> SSC

%% Styling
    classDef regionStyle fill:#e3f2fd,stroke:#1976d2,stroke-width:3px,color:#000
    classDef sscStyle fill:#f3e5f5,stroke:#7b1fa2,stroke-width:3px,color:#000
    classDef noteStyle fill:#fff9c4,stroke:#f9a825,stroke-width:1px,color:#000

    class REGION1,REGION2,REGION3 regionStyle
    class SSC sscStyle
    class NOTE noteStyle
```
