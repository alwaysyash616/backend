# Viewing and Editing files with Commands
- cat app.js
- cat test.sh
- nano app.js
- vim app.js
- vim -v
- vi -v

> `cat` means _concatenate_ (to read files)  
> if file is very large  
> it does't print in one go  
> it prints in small amount  
> and  
> goes concatenating  

## Vim & Nano
> there are not just `commands`  
> they are editors  
```mermaid
flowchart TD
    CTRL["Ctrl + X"]

    CTRL -.->|"#3<br/>Save modified"| BUFFER["Buffer"]

    NANO["Nano"] --> Basic(("basic<br/>editing"))
    NANO -.->|"#1 loads in"| BUFFER
    NANO -.->|"#2 "| CTRL

    BUFFER -->|"#4<br/>Y/N + rename"| OPTION["✅"]

    style OPTION fill:none, stroke:none
    style Basic fill:none, stroke:none
```

> `vim` or `vi`  
> _more powerful then VsCode_  
> `vim` made on top of `vi`

```mermaid
flowchart TD
    UNIX(["UNIX<br/>Era"])
    VI["Vi"] -.-> |#2| UNIX
    Syntax(("syntax<br/>highlighting"))
    Hackers(("hacker type<br/>developers"))
    Server(("Remote<br/>Server"))
    Project["Project"]
    Deployment["deployment"]


    VI -->|"#1<br/>improved"| VIM["Vim"]

    VIM -->|"has"| MODES(["3 modes"])

    VIM -->|"used to <br/>(edit) files<br/>in a"| Project
    Project -->|"hosted on"| Server

    MODES -. "#1" .-> NORMAL(["Normal mode"])
    MODES -. "#2" .-> INSERT(["Insert Mode"])

    VIM -->|"press<br/>I"| INSERT
    VIM -->|"<br/>does"| Syntax
    VIM -->|"we use<br/>while"| Deployment
    Hackers --> |use| VIM

    VIM -->|"#7<br/>to save & exit<br/>Esc"| NORMAL
    VIM -->|"#5<br/>to exit<br/>Esc"| NORMAL
    VIM -->|"#3<br/>to save<br/>Esc"| NORMAL
    VIM -->|"#9<br/>to exit<br/>without saving"| NORMAL

    NORMAL -->|"#8<br/>:wq"| ENTER["ENTER"]
    NORMAL -->|"#6<br/>:q"| ENTER
    NORMAL -->|"#4<br/>:w"| ENTER
    NORMAL -->|"#10<br/>:q!"| ENTER
```


### Mac & Linux are based on UNIX
`nano` comes preinstalled with `bash`  