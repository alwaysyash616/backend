# Creating, Copying, Moving, and Deleting Files and Directories
> touch  
> mkdir  
> cp  
> mv  
> rm  
> rmdir  

- touch index.html
- touch style.css app.js test.txt
- touch src
- mkdir src
- mkdir src1 src2
- pwd
- cp app.js src
- cp script.js src
- `delete all files in src`
- mv script.js src
- mv style.css src
- mv test.txt "C:\\Users\\alwaysyash\\OneDrive\\Desktop"
- mv app.js server.js
- mv server.js "C:\Users\alwaysyash\OneDrive\Desktop\index.js"
- `drag and drop the file on desktop ➜ here`
- rm index.js
- `create a file as.js using VsCode`
- rm index.html as.js
- rm src `❌ is a directory`
- rmdir src `❌ Directory not empty`
- rmdir src1
- rm src `❌ again`
- rm -r src
- rm -r src2
- 

> on remote server,  
> you'll have to face `terminal`  
> `mv` is also used to _rename_  
> also _move + rename_ at the same time (can't be done on UI)  
> files moved, renamed or deleted (by command in terminal)  
> can't be recovered by (ctrl + z)  
> they are't in Recycle Bin   
> `-r` is _recursive flag_ deletes all the files and folder inside, _recursively_  
> `rmdir` is very limited command  
> `-f` flag (अभी नहीं समझ आएगा)  
> we'll see it, after we study _file permission_ in **OS**  

### ChatGPT
> give me bash command to generate 1000 js files named -  
> app1.js app2.js and so on  

<details>
<summary><strong>test.sh</strong></summary>
<div style="display: inline-block;">
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">for i in {1...1000}; do touch "app$i.js; done</pre>
</div>
</details>

- `./test.sh`

<details>
<summary><strong>test.sh (to delete)</strong></summary>
<div style="display: inline-block;">
    <pre style="display: inline-block; text-align: left; padding: 12px 20px;">for i in {1...1000}; do rm "app$i.js; done</pre>
</div>
</details>

- `./test.sh`

> if you know something can happen  
> then, you can use ChatGPT _(generate)_  
> to  
> save your time  