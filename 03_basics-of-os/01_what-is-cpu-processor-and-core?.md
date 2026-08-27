# Why OS?
<div style="display: flex; gap: 20px;">
  <div style="flex: 1;">

```mermaid
flowchart TD
    B["Javascript<br/>(browser)"]
    R["Browser<br/>Resources"]
    T["new Tabs"]

    B -->|access to| R

    R -.->|document| D["document"]
    R -.->|local storage| LS["local storage"]
    R -.->|cookies| C["cookies"]
    R -.->|session storage| SS["session storage"]

    R -.->|many| T
```

  </div>
  <div style="flex: 1;">

```mermaid
flowchart TD
    N["Node JS"]
    OS(("OS resources"))
    None[" "] -.-> |#2<br/>unaware of| OS
    N -->|#1<br/>access to| OS

    OS -.-> NC["Networking Capabilities"]
    OS -.-> FS["FS"]
    OS -.-> ENVS["ENVs"]

    OS -->|#3<br/>unable to use<br/>properly| N2["Node JS"]
    style None fill:none, stroke:none
```

</div>
</div>

> we'll not master OS  
> just OS basics  
> components & resources  
> not an `OS course`  

```mermaid
flowchart TD
    C["Cores"] -.-> |can run a task| I["independently"]

    C -->|processing| U(["Unit"])
    C -->|logical ??| LC["Logical<br/>Cores"]

    LC -.-> |are| D(["double"])
    D -->|of| C

    C -.->|not visible| E(["EYES"])
```

- example, if
- _physically:_ 4 Cores  
- modern technology (by processor manufacturers)
- 8 _logical cores_

> Task manager  
> ➜ Performance tab  
> _at bottom:_ cores, logical processors  
> In **Node REPL**  
> ➜ `os.availableParallelism()`  
  12  
> 12 different application (simultaneously)

```mermaid
flowchart TB
    A["1 Core"] -.- B["CPU<br/>(earlier)"]
    None[" "] -->|only 1 program on| B

    P1(["Program 1"]) --> C["CPU"]
    P2(["Program 2"]) --> C
    P3(["Program 3"]) --> C
    P4(["Program 4"]) --> C

    D["modern<br/>(4 Cores)"] -.- C

    style None fill:none, stroke:none
    style A stroke:none
    style D stroke:none
```