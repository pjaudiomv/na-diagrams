# Diagrams

### Fund Flow

```mermaidjs
flowchart TD
    GROUP[GROUP]
    AREA[AREA]
    METRO[METRO]
    REGION[REGION]
    WORLD[WORLD SERVICES]
    
    %% Direct donations from groups
    GROUP -->|Direct donation| AREA
    GROUP -->|Direct donation| METRO
    GROUP -->|Direct donation| REGION
    GROUP -->|Direct donation| WORLD
    
    %% Fund flow through hierarchy
    AREA -->|Funnel for metro services| METRO
    METRO -->|Return excess funds| AREA
    AREA -->|Donate excess funds| REGION
    AREA -->|Donate excess funds| WORLD
    REGION -->|Donate excess funds| WORLD
    
    %% Styling
    classDef groupStyle fill:#e1f5fe,stroke:#01579b,stroke-width:2px
    classDef areaStyle fill:#f3e5f5,stroke:#4a148c,stroke-width:2px
    classDef metroStyle fill:#e8f5e8,stroke:#1b5e20,stroke-width:2px
    classDef regionStyle fill:#fff3e0,stroke:#e65100,stroke-width:2px
    classDef worldStyle fill:#fce4ec,stroke:#880e4f,stroke-width:2px
    
    class GROUP groupStyle
    class AREA areaStyle
    class METRO metroStyle
    class REGION regionStyle
    class WORLD worldStyle
```
