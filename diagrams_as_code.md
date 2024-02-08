This document stores the mermaid syntax used by the repository to create graphs. 

Actual images of the graphs rendered in ideal conditions are used on the repository pages; this step was taken because the rendering failed responsive design tests.

## Self-directed career process

```
graph LR

    subgraph learn[Experiential Learning]
        style learn fill:#34495E,stroke:#333,stroke-width:2px;
        
        subgraph Experience[3. Get hands on]
          Cloud[Big Cloud]
          Containers
          APIs 
          Niche[Niche that interests you]
        end

        subgraph Network[4. Network]
          Mentors
          Meetups
        end
    end

    subgraph brainstorm[Reflect]
        style brainstorm fill:#2ECC71,stroke:#333,stroke-width:2px;
        
        subgraph Identify[1. Identify]
          Interests
          Passions
        end

        subgraph Goals[2. Set goals]
          Quarterly
          Yearly
        end
    end

    Identify --> Goals
    Experience --> Network
    learn --> brainstorm
    brainstorm --> learn



```
