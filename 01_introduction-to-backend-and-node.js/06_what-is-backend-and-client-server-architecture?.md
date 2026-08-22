# What is **Backend?**
We see frontend on UI. But, the video comes from backend (for example and just one example, there are more).

```mermaid
flowchart LR

    V["VIDEO"]
    NODE["Node.Js"]
    H["http server"]
    J["vanilla javascript\nin frontend"]

    F["frontend<br/>(client)"]

    B["backend\n(server)"]

    API["Example, API"]

    U(("Like a URL<br/>eg.<br/>http://jsonplaceholder.<br/>typicode.com/todos/1"))

    N(("We'll make like<br/>this using node.js"))


    V -.-> |through http network<br/>using API| F

    V -.-> |stored in| B

    F --> |request| B

    B --> |response| F

    B --> |provides many things| API

    API -.-> U

    U --> N

    NODE --> |can create| H
    J --> |can't create| H
    H --> |is| B
```

> While learning frontend we use **nodejs**, to create a server (unknowingly).

```mermaid
flowchart TD

    A["Live Server<br/>(check GitHub)"]

    B["Node.js"]

    C["777.4% TS<br/>2.03% JS<br/>and<br/>Runs outside browser<br/>(in VSCode)"]

    D(("package.json<br/>&<br/>lib/live-server/index.js"))

    E(("<br/>http.createServer(...)<br/>server.listen(port,...)<br/>use of<br/>http module"))

    F["http://127.0.0.1/index.html<br/>Js can't<br/>Node can"]

    

    A -->|#1<br/>uses| B

    A -.-> |#2 ⇒<br/>It's a node.js project| C

    A -.-> |#3<br/>see| D

    D -.-> |index.js contains| E

    E -->|creates URL like| F

    

    style A fill:none,stroke-width:1px
    style B fill:none,stroke:none
    style C fill:none,stroke:none
    style D fill:none,stroke-width:1px
    style E fill:none,stroke-width:1px
    style F fill:none,stroke:none
```
> similarly, react uses node.js
> react uses http.createServer() under the hood, to start a server.
> means, there should be a backend to run a frontend application too.
> but that would be a simple server that only serves files.