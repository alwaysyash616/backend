# Why do we need Node.js & How is it different from Javascript in Browser?
```mermaid
flowchart TD

    NodeJS["Node.js"]

    NodeJS --> |#1| FS["Access to File System"]

    FS --> Read["read"]
    FS --> Write["write"]
    FS --> Delete["delete"]

    FS --> Manipulates(("manipulates"))
    Read --> Directories["files + directories"]
    Write --> Directories["files + directories"]
    Delete--> Directories["files + directories"]
    Manipulates--> Directories["files + directories"]

    NodeJS --> |#2| Networking["Networking Capabilities"]
    NodeJS --> |#3| Process["Process Management"]
    NodeJS --> |#4| OS["Interact with OS"]

    Networking --> |it can start| Servers["Servers"]

    Servers --> |"any IP address:port"| URL["localhost:something"]
    Servers -.-> TCP["TCP"]
    Servers -.-> UDP["UDP"]
    Servers -.-> HTTP["HTTP"]

    NormalJS(("Normal JS")) --> |"can't start"| Servers
    NormalJS -.- |has| FETCH["fetch,<br/>XMLHttpRequest"]
    FETCH --> |"can only fetch data from"| Servers
    NormalJS -.-> |can't| OS

    Process --> |open/close<br/>applications or processes<br/>using| NodeJS
    OS --> |set| ENVs(("ENVs and more..."))

    style Manipulates stroke:none;
    style Read fill:none, stroke:none;
    style Write fill:none, stroke:none;
    style Delete fill:none, stroke:none;
    style TYPE fill:none,stroke:none;
    style FETCH stroke:none;
```

## ChatGPT
<details>
<summary>1. shortest code to write to a file using node.js</summary>
<div style="display: inline-block;">
    <div style="text-align: center;">
        <strong>script.js</strong>
    </div>
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">const fs = require('fs');
fs.writeFileSync(
    'C:\\Users\\alwaysyash\\OneDrive\\Desktop\\text.txt',
    'MySirG Education Services Private Limited'
);
const text = fs.readFileSync('C:\\Users\\alwaysyash\\OneDrive\\Desktop\\text.txt');
console.log(text.toString());
console.log("End");</pre>
</div>
</details>

<details>
<summary>2. to change filename</summary>
<div style="display: inline-block;">
    <div style="text-align: center;">
        <strong>script.js</strong>
    </div>
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">const fs = require('fs');
fs.renameSync(
    'C:\\Users\\alwaysyash\\OneDrive\\Desktop\\text.txt',
    'C:\\Users\\alwaysyash\\OneDrive\\Desktop\\hello.txt'
);
console.log("End");</pre>
</div>
</details>

<details>
<summary>3. delte file</summary>
<div style="display: inline-block;">
    <div style="text-align: center;">
        <strong>script.js</strong>
    </div>
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">const fs = require('fs');
fs.unlinkSync('C:\\Users\\alwaysyash\\OneDrive\\Desktop\\hello.txt');
console.log("End");</pre>
</div>
</details>

<details>
<summary>4. open an application (eg. chrome)</summary>
<div style="display: inline-block;">
    <div style="text-align: center;">
        <strong>script.js</strong>
    </div>
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">const { exec } = require('child_process');
exec('start chrome');
// exec('start firefox');
// exec('start msedge');
// exec('start code');
// exec('"C:\\Program Files\\Mozilla Firefox\\firefox.exe"');</pre>
</div>
</details>  

- _after writing to file,_
- _navigate to the file (windows explorer/finder)_
- _try to read using `earlier code` (previous lecture)_
- _also_
- _try to view the file in `another application` eg. notepad_

> notepad (windows 11) saves file before closing  
> it can save the `earlier content`  
> if the file were already opened in it  
> so reopening can mislead  (frustating)  
> **this happened in the lecture**

```mermaid
flowchart TD
    B["Browser"]
    C["User"]
    JS["Normal JS"] -->|"can't do"| A["all those above"]

    JS -.->|"sandboxed in &<br/>asks"| B

    C -->|"drag & drop"| B
    B -->|"asks user to"| F(("choose from Files"))

    style A fill:none, stroke:none;
    style C fill:none, stroke:none;
    style F stroke:none;
```

- eg. _this site want's to open Whatsapp Y/N?_

- _`exec` function executes the command in terminal_
- _commands are OS specific (differs)_
- _`Mac: open -a google-chrome`_
- _we can close applications too (we'll see how to start, close in OS in more detail)_
- _and many more..._

> `unlinkSync` permanently deletes   
> **windows store apps** (some problem) | _I'will find how to open using terminal or code_  
> **other apps** ✅
> **powershell:** `start 'FullPath'`  
> **bash:** `FullPath`

```mermaid
flowchart LR
    A["Node.js"] -->|"can"| B(("start itself"))

    B --> |however<br/>➜| Code["exec('node')"]
    Code --> |it freezes<br/>अटक जाता है| Stop(("➜ ctrl + C to stop"))
    C(("process"))
    C --> D["child process"]
    C --> E["parent process"]

    F["Later"] -.->|"we'll study"| C

    style Code stroke:none;
```

> In terminal (section), we'll install `bash`  
> for now `powershell`  

## Create server using Node.js
<details>
<summary>code to create server</summary>
<div style="display: inline-block;">
    <div style="text-align: center;">
        <strong>server.js</strong>
    </div>
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">const { http } = require('http');
const server = http.createServer((req,res) => {
    res.end('Hello from Node.js server.)
});
server.listen(3000);</pre>
</div>
</details>

```mermaid
flowchart LR
    Run(("to Run"))
    Run -->|"#1 quickly"| Terminal["Terminal"]

    Terminal -.-> |#2| NodeServer["node server.js"]

    Terminal -->|"#3 freeze<br/>(अटक गया)"| Looks["it looks as"]

    Looks -->|"but<br/>it's listening"| Requests(("for requests"))

    style NodeServer stroke:none;
    style Run stroke:none;
```

> add `console.log(req)` in the **callback** function  
> run again  
> try to send `request` from browser  
> and see the request object in terminal 

### Analyse in more detail (run & debug)
```mermaid
flowchart LR

    Debug["Run and Debug"]

    Debug -.-> |#1 when it needs/<br/>more effectively| Execution(("to analyse<br/>execution in detail"))

    Debug -.-> |#4<br/>add<br/>breakpoint on| Function["res.end() function"]

    Debug -.-> |#2 <br/>change <br/>entrypoint in| Launch[".vscode/launch.json"]
    Launch -.-> |#3 to| Server["server.js"]

    Inspect(("We'll see these<br/>request/response<br/>in very detail")) -.-> |in| Networking["networking section"]

    Function --> |run F5| Hover["➜ hover on `req` in console.log<br/>➜ to see request object<br/>➜ see 'req' in local scope"]
    Hover --> Inspect 

    style Inspect stroke:none;
```