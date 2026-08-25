# Configuring our Terminal using .bashrc File
```mermaid
flowchart LR
    A["to overwrite"] -->|permanently| B["Array.prototype.filter"]

    B -->|write in| C["JS file"]

    C -->|connected to| D["Webpage"]

    C -.->|runs everytime<br/>when Reload| D
```

## Similarly,
`.bashrc`
```mermaid
flowchart LR

    WU(("We'll use"))
    TOUCH["touch"]
    BASHRC[".bashrc"]
    HOME(("home<br>directory"))
    CREATE(("We need to<br>create"))
    DIFF(("different<br>use"))
    BOTH(("Use both<br>for same"))

    WARNING["WARNING<br>• .bash_profile<br>• .bash_login<br>• .profile"]

    TERMINAL["Terminal"]
    NOTE["creates<br>too"]

    WU -->|"now only"| BASHRC
    TOUCH --> BASHRC

    BASHRC -->|"in"| HOME
    HOME -.->|"sometimes"| CREATE

    DIFF -.-> BASHRC
    DIFF -.-> WARNING
    DIFF -->|"but we<br>can"| BOTH

    TERMINAL -->|"starts<br>(run)"| BASHRC
    BASHRC -->|"terminal"| WARNING

    WARNING --- NOTE
```

- cd ~/
- explorer . `opens home directory`
- touch .bashrc  
`open .bashrc in VsCode`
> `paste:`  
<details>
<summary><strong>.bashrc</strong></summary>
<div style="display: inline-block;">
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">num1=5
num2=4
echo $((num1+num2))
echo End</pre>
</div>
</details>

> `open new terminal`   
> `WARNING: Found ~/.bashrc but no ~/.bash_profile, ~/.bash_login or ~/.profile.`  
> `open new terminal`   

- echo $num2
- echo $num3
- echo $num36
> `paste:`  
<details>
<summary><strong>.bashrc</strong></summary>
<div style="display: inline-block;">
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">num1=5
num2=4
num3=42
echo $((num1+num2))
echo End</pre>
</div>
</details>

> `open new terminal`  
- echo $num3
> `paste`  
<details>
<summary><strong>.bashrc</strong></summary>
<div style="display: inline-block;">
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">echo running .bashrc</pre>
</div>
</details>

> `open new terminal`  
> `open .bash_profile in VsCode`  
> `paste`  
<details>
<summary><strong>.bash_profile</strong></summary>
<div style="display: inline-block;">
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">echo running .bash_profile</pre>
</div>
</details>

> `open new terminal`  
> _you may think `.bashrc` runs earlier than `.bash_profile`_  
> _but it's not_  
> write the line `echo running .bash_profile` at the top in `.bash_profile`  

> `paste` in .bashrc
<details>
<summary><strong>.bashrc</strong></summary>
<div style="display: inline-block;">
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">PS1="=> "</pre>
</div>
</details>

> `open new terminal`  
- echo $PS1
> copy value  

## ChatGPT
> `paste` PS1 value  
> Use ChatGPT to generate something beautiful prompt.  

> `open new terminal` is very irritating  
> alternatively we can use - `source ~/.bashrc` command  

- _use of `.bash_profile` is out of our scope_
- 2 types of shells
- `login shells` & `non-login shells`
