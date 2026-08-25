# Introduction to Terminal and Shell
```mermaid
flowchart TD
    V.Imp(("V.Imp"))
    terminal["Terminal"]
    backend(("backend"))
    backendApp(("backend<br/>Application"))
    application["Application"]
    server1["Server"]
    server2["Server"]

    basics(("basics"))
    master(("master"))
    void1[" "]

    void1 -. "#1 this<br/>section" .-> terminal

    void2[" "] -- "#4<br/>as a" --> backend
    backend -- "#5 developer" --> terminal

    terminal -- "#2" --> basics
    terminal -- "not #3" --> master

    backend -- "#7" --> application

    backendApp -- "on" --> server1

    application -- "#8/#11<br/>hosted on" --> server2

    server2 -- "#9 provides" --> terminal

    terminal -. "#6 basic understanding" .-> V.Imp

    %% Large original dashed relationship
    V.Imp -. "#10 used in / build & deploy" .-> application

    %% Terminal and CLI shells
    terminal -- "#17<br/>shells as diff. tabs" --> cliTools

    cliTools["Windows PowerShell<br/>CMD<br/>Bash<br/>Azure"]


    %% VS Code terminal
    vscodeTerminal -. "#12 to open" .-> terminal

    vscodeTerminal["in VS Code<br/><br/>Ctrl + J<br/>Ctrl + `"]


    %% Terminal / application
    terminal -- "#13 like an" --> app

    app["App"]


    %% Application / browser
    app -. "#14 like" .-> browser

    browser["Browser"]


    %% Browser can have many
    many(("there can<br/>be many"))

    many -.-> |#16| browser
    many -.-> |#16| terminal


    %% Browser-accessed sites / tools
    browser -- "#15 tabs (like sites)" --> webSites

    webSites["google.com<br/>procodrr.com<br/>..."]

    terminal -- "basics" --> application

    style void1 fill:none, stroke:none;
    style void2 fill:none, stroke:none;
```

**Linux:** bash  
**Mac:** zsh (default), bash  
_can be switched_

### Install `bash` on Windows
- download and install `Git`
- default editor - `vim`
- _restart VsCode_

### In VsCode (switch between terminals) -
- powershell
- command prompt
- bash
- `Javascript Debug Terminal` is powershell (not any different)

```mermaid
flowchart TD

    VSCode["VSCode"]

    VSCode --> |terminal inside<br/>called| Integrated["Integrated Terminal"]
    VSCode --> |#1<br/>terminal| Profile["Select Default Profile"]

    VSCode --> |#3 new terminal| Bash(("bash"))
    Bash -->  |#4| Prompt["username@PC-Name"]

    Profile --> |#2| GitBash["Git Bash"]

    style Prompt stroke:none;
    style Profile stroke:none;
```

```mermaid
flowchart TD

    Windows["Windows OS"]
    Terminal(("Dedicated terminal"))
    Users(("Users"))
    Each(("each"))
    Path(("C:\\Users\\"))

    Windows --> |terminals run<br/>on OS| Terminal
    Windows --> |"can have many"| Users
    Users --> |"can be created in"| Windows

    Users -. "separate directory for" .-> Each
    Each --> |"at path"| Path

    Notes["We'll see in detail in OS."]
    Notes --> Users
    Notes --> Permissions["User permissions"]
```


> We'll see about Users (in detail) in Operating System  
- user, user permissions  

> Integrated browser ➜ browser inside an app, _same for_ `integrated terminal`  
- `❌` Edge (by default installed), in Windows
- `✅` Chrome
- `❌` Terminal
- `✅` VsCode integrated terminal