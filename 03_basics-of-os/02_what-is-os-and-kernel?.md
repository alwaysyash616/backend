# What is OS and Kernel?
```mermaid
flowchart LR
    Q2[" "]

    OS["OS"]

    Q2 -->  |#1<br/>What is?| OS

    OS -->|"#4<br/>1 Line"| Software(["A Software"])

    Software -->|"#6<br/>specialized to manage"| Hardware(["Hardware Resources"])

    %% Examples of Operating Systems
    OS -.->|#2<br/>like as| OSExamples["Windows<br/>Mac<br/>Linux"]
    OSExamples -.-> |#3<br/>just<br/> OS examples| Q1["Not, what an OS is?"]

    %% Examples of software/applications
    Software -->|"#5<br/>is it like?"| Apps["Browsers<br/>VS Code<br/>❌"]

    %% Applications use/request hardware resources
    Software -.->|"#7<br/>decides which<br/>application use..."| Hardware2["how much of<br/>hardware"]

    %% Hardware resources are available to applications
    Hardware2 -.->|"for all"| OtherApps(["Other Applications"])

    %% Types of hardware resources
    Hardware2 --> RAM["RAM"]
    Hardware2 --> Disk["Disk Memory"]
    Hardware2 --> CPU["CPU Time"]

    style Q2 fill:none, stroke:none
    style Q1 stroke:none
    style Hardware2 stroke:none
```
## Kernel
```mermaid
flowchart LR
    OS["OS"]
    Kernel["Kernel"]
    Hardware["Hardware"]

    Window["Window"]
    UI["UI"]
    Button["Button"]
    Screen["Screen"]

    Kernel -. "#1<br/>part of" .-> OS
    Kernel -->|"#2<br/>especially<br/>(to manage)"| Hardware

    Hardware -. "for" .-> OS

    OS -.-> |has many| OT["other<br/>things"] 
    OT --> Window
    OT --> UI
    OT --> Button
    OT --> Screen

    Kernel -->|"like a"| Program(("Program"))
```
## Single Core
- does it mean
- 1 application at a time?
<!-- ![Processor with 2 Cores](./.assets/02-01.svg) -->

<div style="display: flex; gap: 20px;">
  <div style="flex: 1;"><img src="./.assets/02-01.svg" width="500" alt="Processor with 1 cores"></div>
  <div style="flex: 1;"><img src="./.assets/02-02.svg" width="500" alt="Processor with 2 cores"></div>
</div>

> Task Manager ➜ Performance Tab  
> ➜ 6 Cores (physical)  
> ➜ 12 Cores (logical)  

```mermaid
flowchart LR
    A(["12 Applications"])
    B[" "]
    C["Hundreds of 'em"]
    D["Thousands"]
    E["Single Core"]
    F["that's not true"]

    B --> |"We can't<br/>run more<br/>than"| A

    A -->|"already running"| C
    C --> |"or<br/>maybe"| D
    C -.->|"also on"| E

    A -->|"we know"| F

    style B fill:none, stroke:none;
    style F stroke:none
```

> it's true (1 core CPU)  
> can run  
> only 1 application at a time  
> it's not true that (1 core CPU) can run  
> multiple applications at the same time  

- _think how it happens_ then,
- `Screen recording`
- `Excel`
- `VsCode`
- `Clock App`
- `background Applications`
- `browser`
+ MANY (in background)

> OS tells the applications to execute on CPU for a fraction (very small) each
  (in some repeated order)

> but

> this happens frequently

> so, at a time (instant)

> only 1 application (at a time) 

> does't mean 1 application (all the time)

> for dual core → two applications at an instant (time)

> doesn't mean only 2 apps all the time.

> _this whole stuff is called_ `Context Switching`  

```mermaid
flowchart LR
    B["Context Switching"]

    B --> |"#1<br/>thousands<br/>or more times"| D(("in a single second"))

    B --> |"#2<br/>Can we see it?"| F["Yes"]
    F --> |"We can"| G["see it"]

    style F stroke:none
```

### Next Video: Process