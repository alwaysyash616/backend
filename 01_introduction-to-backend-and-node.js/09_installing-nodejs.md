# Installing Node.js
- download & install VsCode  
<div style="display: inline-block;">
    <div style="text-align: center;">
        <strong>index.js</strong>
    </div>
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">let a = 5;
let b = 4;
console.log(a + b);</pre>
</div>

```mermaid
flowchart TB

    LINK["LINK"]

    HTML["index.html"]
    JS["script.js"]

    LINK --> HTML
    LINK --> JS

    JS -->|"output"| CONSOLE["browser's<br/>console"]
    HTML --> |open with live-server<br/>http://127.0.0.1:5500/index.html<br/>| CONSOLE
```
- _127.0.0.1 is localhost_

- _before 2008 (Node.js), there was no other way to run Js outside Browser._

<div style="display: inline-block;">
    <div style="text-align: center;">
        <strong>index.js</strong>
    </div>
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">&nbsp; let a = 5;
*&nbsp;let b = 4;
&nbsp; console.log(a + b);</pre>
</div>

- _notice, the index.js has breakpoint on "let b = 4;"_

```mermaid
flowchart TD
    TDZ["TDZ"]

    BNOT["b variable<br/>not shown"]

    BNOT -.-> |#7 in| TDZ

    VSC["VS Code"]

    PORT(("must be ✅<br/>5500 port"))

    WEB(("WebApp<br/>Chrome"))

    LAUNCH(("Launch<br/>Chrome"))

    VSC -. "#1 live server" .-> PORT

    VSC -. "#2 run & debug" .-> WEB

    WEB -. "#3 edit launch.json<br/>Port: 5500" .-> LAUNCH

    LAUNCH -->|"#5 we can debug like<br/>browser in"| VSC


    %% ─────────────────────────────────────
    %% Browser observations
    %% ─────────────────────────────────────

    CHROME["• Chrome (new tab)<br/>• no output (in console), paused<br/>• b in TDZ<br/>• value unavailable<br/>before initialization<br/>(not accessible)"]

    LAUNCH --> |#4| CHROME

    VSC --> |#6 script scope &<br/>global scope| BNOT

    BNOT --> |#8 browser shows<br/>b| CHROME

    style VSC fill:none,stroke-width:2px
    style BNOT fill:none,stroke-width:1px
    style PORT fill:none,stroke-width:1px
    style WEB fill:none,stroke-width:1px
    style LAUNCH fill:none,stroke-width:1px
    style CHROME fill:none,stroke-width:1px
```
- _#2 run & debug creates .vscode/launch.json_  
- _forward the code (f9) like you do while debugging_  
- _and, **b** will become visible, after initialization_  
- _**b** comes out of **Temporal Dead Zone** (TDZ)._  

> add a line console.log(document), to see document object in (VsCode)  
> add breakpoint, somewhere  
> hover on '**document**' to see it's contents  
> '**document**' object is provided by **WebAPI**  
> use defer attribute to see body content in **document** object  

<div style="text-align: center;">

`delete html file`<br/>
and<br/>
`.vscode/launch.json`
</div>

```mermaid
flowchart LR
    R(("Restart<br/>VsCode"))

    V["VS Code"]

    PATH(("can't find nodejs<br/>binary...PATH..."))

    CMD(("bash: command not<br/>found"))

    V -->|"terminal (bash)<br/>node -v<br/>node"| CMD

    V -->|"run and debug<br/>➔ (nodejs)"| PATH

    PATH -.->|"Download & install<br/>Node.js"| R
    CMD -.->|"Download & install<br/>Node.js"|R

    style R fill:none,stroke-width:1px
    style V fill:none,stroke-width:1px
    style PATH fill:none,stroke-width:1px
    style CMD fill:none,stroke-width:1px
```

- **VS Code**
  - **Terminal**
    - `node -v`
    - `node`
      - `> 5 + 6`   
      - `> document`  
        `❌`
      - `> window`  
        `❌`

```mermaid
flowchart BT

    V["JavaScript code"]
    R(("Node REPL"))

    V -.->|"paste"| R

    %% Remove node rectangles
```

- _the above prompt '>' is provided by node.js application_  
- _it's called Node REPL_  
- _it can run Js code_  
- _**document** and **window** objects are not available_  
- `browser's console has document and window`  
- because they are provided by WebAPI  
- we'll see the global variables in node.js (next lecture)
- alternatives or similar to document and window

> node script.js  
    `❌` _(because of 'document')_  

also

> _this way does't provide debugging facility_  
> _&_  
> `without that kinda debugging facilities anyone can't learn Node.js (deeply)`

```mermaid
flowchart LR

    VS["VS Code"]

    WS["we see"]
    DEBUG(("variables<br/>call stack<br/>breakpoints"))

    WS -.- DEBUG

    LOCAL(("local<br/>scope"))

    LAUNCH[".vscode/launch.json<br/>➔ created"]


    VS -->|"run & debug<br/>➔ (nodejs)"| DEBUG

    DEBUG -->|"very interesting<br/>that variables"| LOCAL

    %% Styling
    style VS fill:none,stroke-width:1px
    style DEBUG fill:none,stroke-width:1px
    style LOCAL fill:none,stroke-width:1px
    style LAUNCH fill:none,stroke:none
    style WS fill:none,stroke:none
```

We defined variables in global scope, but they are shown in local scope.  
We'll see why?  
in the nodejs fundamentals [section-4](./04_fundamentals-of-node.js)  

## Next video
we'll execute some nodejs code  
(that was not in javascript)  

> Notice, the output in `debug console` and not in `terminal`.
