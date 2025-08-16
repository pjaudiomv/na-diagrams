# Diagrams

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
