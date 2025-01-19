nCtrl + F search text
Ctrl + H to replace text 
Ctrl + P to search File
Ctrl + , for settings shortcut
Ctrl + / to make/undo a comment in an html file
Right click on a file and split up/down or left/right
Press F2 to rename a file
Alt + up/down (to move a line up or down)
Alt + left/right (to move cursor 1 tab unit without highlighting text)
Shift + left/right (to move cursor 1 tab unit while highlighting text)

CLI commands
    code . (to open a project in CS Code) (NOTE: cd first to the project directory)
    cd ~ (to return to root directory)
    cd - (to return to previous directory whether up or down)
    cd .. (to move one directory above)
    pwed (print working directory)
    ls (sees the contents of a directory)
    ls -F (lists and describes the contents)
    ls -F 0a or ls -Fa (to include ..)
    man ls OR ls --help (for more info)
    nano somefile.txt (to launch a text file)
    touch somefile.txt (to create a text file without opening)
    mv oldname.txt newname.txt (to rename a text file)
    mv somefile.extension somedirectory/ (to move a file in somedirectory)
    rm -i somefile.extension (to remove a file with a prompt)
    rm -ri somedirectory (to recursively reome a directory with a prompt)
    mkdir -p newdir/subdir1/subdir2 (-p forces mkdir to create intermiediate subdir as req'd)
    grep (???)

Installing GIt
    sudo add-apt-repository ppa:git-core/ppa
    sudo apt update
    sudo apt install git

GIT commands
    git clone (ssh key or url of repo)
    git config --global user.name (or user.email) some_username (or some_email)
    git config --get user.name (or user.email)
    git remote -v (to get the remote url of the remote repo)
    git add somefile.extension (or git add . to add alfiles in the staging area)
    git status
    git commit -m "any message describing the changes you made"
    git log or git log --pretty="- %s" (more readable log)
    git push remotename branchname (i.e. git push origin main)
    git config --global core.editor "code --wait" (to set code as keyword to start VS Code)
    git revert HEAD (to refert to previous commit)
    git commit --amend (another way to edit previous commit message)
    git branch <branchn_name> **omit the argument <branch_name> to see all branches**
    git checkout <branc_name>  **to change to your newly created branch**
    git checkout -b <branch_name> **one-liner to create a new branch and transfer to that branch**
    git merge <branch_name>
    git branch -d <branch_name> **to delete a branch has already been merged with main, otherwise use below**
    git branch -D <branch_name> 
    git push origin --delete <branch_name> **delete the remote branch on GitHub**

Installing NVM and NPM
    sudo apt install curl (first install curl)
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
    export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
    nvm install --lts 
    nvm use --lts (to use the latest long-term support stable version)
    node (to open Node terminal) .exit (to exit Node terminal)
    npm install (inside a repository to install JEST)


Downloading Chrome
    wget https://dl.google.com/linxu/direct/google-chrome-stable_current_amd64.dfeb
    sudo dpkg -i google-chrome-stable_current_amd64.deb
    sudo apt-get install -r
    google-chrome somefile.html (to open an html file)

Git commit messages
    "If applied, my commit will ____."
    <type>[optional scope]: <description>
    [optional footer(s)]
    [optional body]

    common <type>
    -build, fix, feat, chore, ci, docs, style, refactor, test

    optional scope 
        -must be a noun
        -should end with ! before : if a breaking change

Working with Chromedev tools
    Ctrl + Shift + C (to open Chromedev tools)
    Ctrl + Shift + J (to open console in chrome browser)
    Ctrl + Shift + F (to open Search Panel)
    F12 or Ctrl + Shift + I (to open the last most recent panel from CXhrome devtools)
    google-chrome --auto-open-devtools-for-tabs (to automatcially open devtools for every webpage you visit)
    Ctrl + Shift + P (to open command line in devtools)
    Ctrl + F (to search text or element in the DOM Or elements page of the Devtools)
    Esc + type $0 (to find the currenly selected node and inspect/edit it)
    Esc + type $1 (previously selected node)
    Right Click and select EDIT as HTML (to add attributes to an element)

    Go to Sources, and on the top left, click Snippets for creating js code you want to check often
    To check the datatypes, go to Sources and on the right pane, go to Watch and click "+" icon to add watch expression. (typeof(somevariable))


HTML elements
    <input type="text" required pattern="Any text">

CSS attributes
    animation: rainbow 10s linear infinite;
    box-sizing: border-box (sets the box-model to include padding and border value in the height & width declaration)
    use margin-(top/bottom/left/right) to manipulate the placing of two elements from each other (negative values is accepted)
    color: inherit can be used if you want a chilren to inherit the color of its parent
    when flex-wrap is enabled and the primary axis is divided to more than 1 due to insufficident container size,
        you can use align-items to adjust every item's position and align-content to adjust the collective position of the
        items.
    background: linear-gradient(to right, red, blue);
        
    If we put position: relative; on the parent element, anything inside of it with position: absolute; will be placed absolutely, relative to that containing unit!

ZIP commands
unzip file.extension -d somedirectory (extracts all zip files to somedirectory)

JS with HTML manipulation
    someElement.querySelector(selector)
    someElement.querySelectorAll(selectors)
    document.createElement(tagname, [options]) **options is optional and tagname is like <div>**
    parentNode.appendChild(childNode) **appends childNode as the list child of parentNode**
    parentNode.insertBefore(childNode, referenceNode) **inserts childNode to parentNode before referenceNode**
    parentNode.removeChild(childNode) **removes childNode and returns a reference to that node**
    someNode.remove() //removes a node without referencing a parent **not supported in all browsers**
    someHtmlTag.setAttribute("style", "any css syntax"); **adds multiple styles in a single string**
    someHtmlTag.style["any attribute"]; **to access any multi-worded style attribute e.g. div.style["background-color"]**
    someHtmlTag.set/get/removeAttribute("id") **for set, ("id","id value")**
    someHtmlTag.classList.add/remove("classname");
    someHtmlTag.classList.toggle("classname"); **if div doesn't have class "classname" then add it, or if it does, then remove it**
    **referencing a css Class selector on setAttribute**
        const para = document.querySelectorAll("p");
        para.setAttribute("class", "highlight"); **where highlight is set in CSS as .highlight { style...};**
k
JAVASCRIPT
    Events 
        <!-- The e parameter in that callback function contains an object that references the event itself.  -->
        <!-- Within that object you have access to many useful properties and methods  -->
        <!-- (functions that live inside an object) such as which mouse button or key was pressed,  -->
        <!-- or information about the event’s target - the DOM node that was clicked. -->
        btn.addEventListener("click", function (e) {
        console.log(e.target);
        e.target.style["background"] = "blue"; <!--sets the btns bg color to blue -->
        });

    using map() function
        const arr = [1, 2, 3, 4, 5];
        const mappedArr = arr.map((num) => num + 1);
        console.log(mappedArr); // Outputs [2, 3, 4, 5, 6]

    using filter() function
        function isOdd(num) {
            return num % 2 !== 0;
        }
        const arr = [1, 2, 3, 4, 5];
        const oddNums = arr.filter(isOdd);
        console.log(oddNums); // Outputs [1, 3, 5];
        console.log(arr); // Outputs [1, 2, 3, 4, 5], original array is not affected

    using reduce() function
        const arr = [1, 2, 3, 4, 5];
        const productOfAllNums = arr.reduce((total, currentItem) => {
            return total * currentItem;
        }, 1);
        console.log(productOfAllNums); // Outputs 120;
        console.log(arr); // Outputs [1, 2, 3, 4, 5]

    TOD ACTIVITY
        const arr = [1,2,3,4,5];
        const filteredArr = arr.filter( (num) => num % 2 === 0);
        const mappedArr = filteredArr.map((num) => num * 3);
        const sumOfAllEven = mappedArr.reduce((total, currentItem) => total + currentItem; ) 
        //no second argument after callback because we want our initial total value to be the first element of the mappedArr
        // callback simply means the function to be passed as an argument

    const arr = Array.from({length: n}, (_,index) => index + 1) //to instantiate an array based of a length input
    Math.floor(Math.random()*8**8).toString(16) **/2/8/10** - generate random numbers which I used for color
    put <script src="someJsFile.js" defer></script> at the <head> of html file to run the js script after the html file for DOM manipulation
    parseInt(someVar);
    someString.concat(someString2); 
    somedigit.push(somedigit2); 
    use `` instead of '' if ${} will be used
    someArray.push("anyitem"); (to add an element to an array and returns the new arraylength)
    someArray[someArray.length] = someItem; (another way of adding)
    someArray.toString() (converts an array to a string of comma separated values)
    Array.isArray(someArray); (returns true if someArray is an array)
    someArray instanceof Array; (alternative to above method of)
    someArray.pop() (removes the last item and returns it)
    someArray.shift() (removes the first item and returns it)
    someArray.unshift() (adds new element to index 0 and shifts all other elements, returns new arraylength)
    someArray.at(-1) (accepts negative indexing and an alternative to [])
    someArray.concat(someOtherArray,...,...,); (joins two or more arrays together and returns it as a new array)
    someArray.flat(); ( [[1,2],[1,2], [1,2]] becomes [1,2,1,2,1,2]  )
    someArray.flatMap(do somethin with each element)
        const arr = [1,2,3,4,5,6]
        const newArr = arr.flatMap( x => [x, x*10] );
    someArray.splice(0, 0, item1, item2, ...) (add/delete new items to an array in any position)
        const fruits = ["Banana", "Orange", "Apple", "Mango"];
        fruits.splice(2, 2, "Lemon", "Kiwi");
        <!-- The first parameter (2) defines the position where new elements should be added (spliced in). -->
        <!-- The second parameter (0) defines how many elements should be removed. -->
        <!-- The rest of the parameters ("Lemon" , "Kiwi") define the new elements to be added. -->
        <!-- The splice() method returns an array with the deleted items: -->
    someArray.toSpliced(0,0, item1, item2, ...) (same as splice but creates a new array keeping the original unaltered)
    someArray.slice(position, end) (creates a new array strating from position index up to (but not including) end index)
    Accessing arrays within arrays
        let x = '';
        const myObj = {
            name: "John",
            age: 30,
            cars: [
                {name:"Ford", models:["Fiesta", "Focus", "Mustang"]},
                {name:"BMW", models:["320", "X3", "X5"]},
                {name:"Fiat", models:["500", "Panda"]}
            ]
        }   

        for (let i in myObj.cars) {
            x += "<h2>" + myObj.cars[i].name + "</h2>"; 
            for (let j in myObj.cars[i].models) {
                x += myObj.cars[i].models[j] + "</br>";
            }
        }
        document.getElementById("someID").innerHTML = x;

    Using forEach() method instead of for-loop
        const fruits = ["Apples", "Oranges", "Tomatoes"];
        function sample(value) {
            console.log(value + "ss");
        }
        fruits.forEach(sample); //output is Applesss/nOrangesss/nTomatoesss

    Assigning a function to a variable
        function add(a,b) {
            return a+ b;
        }
        
        let sum = add;
        let result = sum(10,20); //or add(10,20);
        let another_result = average(10,20,sum) //for a function that needs a function as an argument

    Returning a function from another function 
        function compareBy(propertyName) {
            return function (a, b) {

                /*multiple declarations using a single let
                a[] is used to return a value that does/doesn't have whitespaces in between
                a.propertyname is an alternative*/
                let x = a[propertyName],
                y = b[propertyName];

                if (x > y) {
                return 1;
                } else if (x < y) {
                return -1;
                } else {
                return 0;
                }
            };
        }

    Anonymous functions are functions that have no name and generally expectx another function as a parameter.

            textBox.addEventListener("keydown", function (event) {
                console.log(`You pressed "${event.key}".`);
                });

    Using an arrow function,

            textBox.addEventListener("keydown", (event, event2) => {
                console.log(`You pressed "${event.key}".`);
                });

            textBox.addEventListener("keydown", event => {
                console.log(`You pressed "${event.key}".`);
                }); //omit the parenthesis if the anonymous function only takes one parameter//


            const doubled = originals.map(item => item * 2); //omit the braces if function is one liner 
            //function above doubles each item of a list 'originals' and stores it in a string// 


            /*A complete example 
                in html:
                    <input id="textbox" type="text"/>
                    <div id="output"></>

                in JS:
                    const textbox = document.querySelector("#textbox);
                    const output = document.querySelector("#output");

                    textbox.addEventListener("keydown", (event) => {
                        output.textContent = "You pressed "${event.key}".";
                    });*/

    An example of a callback function:
        console.log('Start script');

        setTimeout ( () => {
            task('Download a file');
        }, 1000); //even if timeout is 0 instead of 1000, callback function is called only if call stack is empty
                  //callback functions are put in callback queue while others are in call stack

        console.log('Done!'); /* output is Start script\nDone!\nDownload a file */




