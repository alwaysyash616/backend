# A brief History of Node.js
```mermaid
flowchart TD

    Apache["Apache Server"]
    EveryRequest(("every request"))
    Blocking["blocking"]

    Apache --> |#1 creates new thread for| EveryRequest
    EveryRequest -.-> |#2| Blocking

    Apache -.-> |#3<br/>frustrated, &<br/> made him| Ryan["Ryan Dahl"]

    Ryan --> |#4<br/>in 2009| NodeJS["Node.js"]

    V8["V8 Engine (Chrome)"]
    Ryan --> |#5<br/>used| V8
    V8 --> |#6 for| NodeJS

    Joyent["Joyent"]
    Joyent -.-> |#9<br/>APPROACHED<br/>in 2012| Ryan
    Ryan --> |#10<br/>asked to join<br/>them, &<br/>offered| Resources(("Job, salary,<br/>team, resources,<br/>facilities"))

    Resources --> |#11<br/>made development<br/>fast| NodeJS

    Joyent -.-> |#7<br/>working in 2011,<br/>on| Similar["something similar"]
    Similar --> |#8<br/>they came to<br/>know about| NodeJS

    style Resources stroke:none;
```

- _Ryan Dahl accepted the offer from **Joyent**_
- _later_
- _the Company started controlling_
- _bound developers from adding features in Node.js_

```mermaid
flowchart TD

    Y2010["2010"] --> NPM["npm"]
    NPM --> Powerful["Very powerful thing"]

    NPM -.-> Platform["Platform for Packages<br/>(open source)<br/>(for developers)"]

    Y2011["2011"] --> Windows["Windows Support"]
    Windows --> Community(("COMMUNITY"))
    NPM --> Community

    Community -.-> |Popularity ↑<br/>increased| Node["NodeJs"]

    style Node stroke:none;
    style Platform stroke:none;
    style Powerful stroke:none;
    style Community stroke:none;
```

```mermaid
flowchart TD

    Joyent["Joyent"]
    Controlling(("controlling"))
    NodeJS(("Node.js"))
    IOJS(("io.js"))
    Developers["Some developers"]

    Joyent --> |#1<br/>later started| Controlling
    Controlling --> |#4<br/>parallel| NodeJS
    Controlling -.-> |#2<br/>therefore| Developers
    Developers --> |#3<br/>parallel| IOJS

    NodeJS --> |+| Node4["Node.js 4.0 LTS"]
    IOJS --> |+| Node4

    NodeFoundation(("Node.js Foundation<br/>(in 2015)"))
    Freedom["FREEDOM"]
    JSFoundation(("JS Foundation<br/>(for Browser JS)"))
    OpenJS["OPEN JS FOUNDATION"]

    NodeFoundation --> |#6<br/>made to<br/>provide enough| Freedom
    NodeFoundation --> |+| OpenJS
    JSFoundation --> |+| OpenJS

    NodeFoundation -.-> |#5<br/>in 2015<br/>merger| Node4
    OpenJS -.-> |#8<br/>in| Y2019["2019"]

    Freedom -.-> |#7<br/>to| Developers
```

> Atwood's Law  
> Any application that can be written in JavaScript, will eventually be written in JavaScript.  
> --Jeff Atwood, 2009.  

> The **merger** of `Node.js Foundation` and `Js Foundation` to form  
> ➜ `OpenJs Foundation` in 2019.  
> was another step toward's **Atwood's Law**.

- _because_
- _now, Javascript can be used on -_
- _a vast number of fields in software engineering._