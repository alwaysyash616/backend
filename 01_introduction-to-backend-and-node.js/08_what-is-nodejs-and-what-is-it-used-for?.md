# What is Node.js? | What is it used for?
> Js in browser has very limited access.  
> **Node.js** runs on OS.  
> has access to OS resources.  
> very powerful applications.

```mermaid
flowchart TD

    %% ─────────────────────────────────────
    %% GitHub / Node.js project identification
    %% ─────────────────────────────────────

    CHECK["observe anything<br/>which proves<br/>it's a node.js project - <br/>package.json<br/>node_modules<br/>devDependencies"]

    %% ─────────────────────────────────────
    %% Main Node.js concept
    %% ─────────────────────────────────────

    N["Node.js"]


    %% GitHub inspection → Node.js

    %% ─────────────────────────────────────
    %% CLI applications
    %% ─────────────────────────────────────

    CLI["npm, Ts, webpack, babel, prettier, ESLint, Yarn, Vue CLI, Angular CLI, CreateReactApp and many more ..."]

    CLI --> |#7 Check GitHub<br/>each| CHECK

    N --> |#6 CLI applications| CLI

    %% ─────────────────────────────────────
    %% Application made using C++ and JS
    %% ─────────────────────────────────────

    N -->|"#1 application made<br/>using"| CPP["C++ and JS"]

    %% ─────────────────────────────────────
    %% **JavaScript** outside browser
    %% ─────────────────────────────────────

    N -->|"#2 can run"| JS(("JS<br/>(outside browser)"))
    CHECK --> |all are| JS

    JS -->|"#3 on OS"| OS(("access to<br/>OS resources"))

    JS --> |very powerful| A["applications"]
    OS --> |very powerful| A


    %% ─────────────────────────────────────
    %% Web servers
    %% ─────────────────────────────────────

    N -->|"#5 not limited to (backend)"| WEB(("Web Servers<br/>using Node.js"))

    WEB --- FOCUS["(backend)<br/>OUR MAIN FOCUS<br/>+<br/>but we'll make<br/>a CLI app too."]

    OS --> |#4 that's why we make| WEB

    N --> |also| IoT["IoT"]


    %% ─────────────────────────────────────
    %% Styling
    %% ─────────────────────────────────────

    style N fill:none,stroke-width:2px

    style CPP fill:none,stroke-width:1px
    style JS fill:none,stroke-width:1px
    style OS fill:none,stroke-width:1px
    style WEB fill:none,stroke-width:1px

    style FOCUS fill:none,stroke:none

    style CLI fill:none,stroke-width:1px
```

> npm, Ts, webpack  
> babel, prettier, ESLint   
> Yarn, Vue CLI, Angular CLI  
> CreateReactApp, _and many more ..._  
- _Check GitHub of each_  
- _package.json (and other things that prove it's a nodejs project or npm project)_


## TypeScript
- 98% **TypeScript** is made in Typescript.
- **TypeScript** originally made using **JavaScript**.
- Later, **TypeScript** evolved and it's support become available in many IDE's.
- They, used their **JavaScript** code (which was the **TypeScript** Language), in **TypeScript** itself.
- Because, **JavaScript** code works in **TypeScript**.

- but, at the end, we know everything translates back to ****JavaScript****.
- because, neither **Node.js** nor the **browser** understands ****TypeScript****.