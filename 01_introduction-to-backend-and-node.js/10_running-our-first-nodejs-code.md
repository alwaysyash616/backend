# Running our first Node.js Code
```mermaid
flowchart LR

    N["Node.js"]

    CODE["let a = 5;<br/><br/>let b = 4;<br/><br/>console.log(a + b);"]

    JS["JS<br/>(browser)"]

    ADD(("add"))


    CODE -->|"#1 what's so special<br/>in"| N

    JS -->|"#2 can run<br/>this too"| CODE

    JS -->|"#3 can<br/>also"| ADD


    %% Styling
    style N fill:none,stroke-width:1px
    style CODE fill:none,stroke-width:1px
    style JS fill:none,stroke-width:1px
    style ADD fill:none,stroke-width:1px
```
- _don't try to understand the (below) code for now_
- _we'll understand in full detail_

<div style="display: inline-block;">
    <div style="text-align: center;">
        <strong>script.js</strong>
    </div>
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">const fs = require('fs');
const text = fs.readFileSync('./text.txt');
console.log(text);</pre>
</div>

```mermaid
flowchart LR

    VS["VS Code"]
    DEBUG(("debug<br/>console"))
    OUT["Output"]

    VS -->|"run & debug<br/>➜ nodejs"| DEBUG
    OUT -.->|"on"| DEBUG
    

    style VS fill:none,stroke-width:1px
    style OUT fill:none,stroke-width:0px
```

- _notice that the output comes as a buffer_
- _we'll study **buffer** and **streams**, later in this course_

## shortcut
> create a `launch.json` file, `➜ nodejs`  
> then, you can use  
> F5 (to )  
> Ctrl + Shift + F5 (to )  
> use F5 at least for a time to run your code  

<div style="display: inline-block;">
    <div style="text-align: center;">
        <strong>script.js</strong>
    </div>
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">const fs = require('fs');
const text = fs.readFileSync('./text.txt');
console.log(text);
console.log("End";)</pre>
</div>

```mermaid
flowchart LR

    F5["F5"]
    HELLO(["Hello World"])
    BUFFER(["buffer"])
    OUTPUT["Output / Data<br/>0=72<br/>1=101<br/>2=108<br/>..."]
    LOCAL["Local<br/>Scope"]
    HEX["Hex Editor<br/>Extension"]
    DECODED(["decoded<br/>text<br/>+<br/>hexadecimal<br/>values"])

    F5 -->|"#1 we wrote"| HELLO
    F5 -->|"#2 output<br/>as a"| BUFFER
    BUFFER -.-> OUTPUT

    LOCAL -->|"text variable's<br/>value"| OUTPUT

    OUTPUT -->|"view<br/>binary data<br/>button"| HEX
    HEX -->|"after installation"| DECODED

    style OUTPUT stroke:none;
```

- _add breakpoint on last line `console.log("End")`_
- _to see the buffer contents_
- _in **debug console**_

- _change `console.log(text)` ➜ `console.log(text.toString())` and
- _hit `ctrl + shift + F5`_
- _to see the actual string_
- _in **debug console**_

```mermaid
flowchart LR

    NodeJS["Node.js"]
    ReadFile["Read file"]

    TRY["try to"]

    Windows["\\<br/>Windows<br/>Paths<br/>(problems)"]
    Escape(("escape<br/>\<br/>sequence"))

    JS["JavaScript"]

    NodeJS -->|#5 can| ReadFile
    TRY -->|#1| ReadFile

    ReadFile -->|#2<br/>on desktop| Windows
    Windows -.-|#3| Escape

    JS -->|#4 can't do this<br/>read local FS| ReadFile

    style TRY fill:none, stroke:none;
    style Escape stroke:none;
```

> nodejs can read, write, delete (and many things...)  
> that's a big thing.  

```mermaid
flowchart TD

    Node["Node.js"]
    Check["✓"]
    Cross["✗"]    

    subgraph G["global scope"]
        Global["global"]
    end

    Node -->|global variable here| Global

    Node --> |document| Cross

    Node -->|window| Cross

    Node --> |globalThis| Check
    Node -->|global| Check

    style G stroke:none;
    style Global fill:#333,stroke:none;
```

- _globalThis is universal_
- _works in `browser` and `nodejs` both_
- _**In browser:** globalThis ➜ window_
- _**In nodejs:** globalThis ➜ global_

```mermaid
flowchart TD

    Browser["browser's console"]
    Check["✓"]
    Cross["✗"]

    Browser --> |document| Check

    Browser -->|window| Check

    Browser --> |globalThis| Check
    Browser -->|global| Cross

    style Check stroke:none;
    style Cross stroke:none;
```