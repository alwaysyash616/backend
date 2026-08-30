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
> not an `OS course` (Node.js course)  
> Imagine (picture)  
> CPU, Processor & Core  
> _In daily life we use the term `CPU` for the Cabinet_ but that's not true  
> CPU and Processor are same  
> fan for cooling on top of processor  
> CMOS (battery) for maintaining time, while system is off  
> `Anurag sir built their pc on 4 Nov, 2020`  

```mermaid
flowchart TD
    C["Cores"] -.-> |can run a task| I["independently"]

    C -->|processing| U(["Unit"])
    C -->|logical ??| LC["Logical<br/>Cores"]

    LC -.-> |are| D(["double"])
    D -->|of| C

    C -.->|not visible| E(["EYES"])
```

> in earlier days  
> CPU (single core)  
> only 1 program on 1 CPU at a time  
- example, if
- _physically:_ 4 Cores  
- modern technology (by processor manufacturers)
- 8 _logical cores_

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

### To see processor (specs, company), cores(physical, logical)
> Task manager  
> ➜ Performance tab  
> _top right:_  Processor name and some details  
> _at bottom:_ cores, logical processors  
> In **Node REPL** (_only_ logical cores can be seen)  
> ➜ `os.availableParallelism()`  
  12  
> 12 different application (simultaneously)  

`Anurag sir used the workspace (directory), he created for chapter-3 (Process), in VsCode, in this lecture to show os.availableParallelism()`