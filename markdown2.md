# Need to take notes in order to pass. Hard to memorize everything especially from only seeing it one time.

Install `atom` or `vscode` on students machine and open it.

It's just a text editor by default.

### What is markdown.

So, we want to take our notes in a easy clean way but want to render them as something easy to read and comprehend. So markdown is the go to currently.

We can write markdown in Atom/VScode and preview it as well.


### Sharing is caring

We have a place to generate notes but what if I want to share them with my team?

Well lets use `GIT` to keep track of our notes or code and it also keeps a running
log of who, what, and when it was changed. Also it gives us the ability to revert
any changes we may not want or accidently lost.

Lets tell `atom` or `vscode` about our `project` we are working on and connect it `github`. This can also be connected to other tools like `gitea` or `gitbucket`.

##### Connecting and adding projects to vscode
Easiest way is to use the command line to clone your project first.  
In `vscode` select `terminal` -> `new terminal` and mkdir or cd into a directory you want to work in.  
`git clone <github url>`

in vscode select `file` -> `open folder` Then navigate to the directory
that you just downloaded via git.

On success you should see that the directory to the top left in vscode looks like a
notebook with a book mark. Then under it all the folders and or files that exist
for that project.

  - `NOTE: If in teams only have 1 person per team add new content`
  - Fixing merge conflicts is not very fun, but it happens.
  - This is why branches exist. (best practice is never commit directly to master)
We can now add new files, folders or content to existing files locally with atom.
However, this isn't going to change what is in github......... yet. We need to save
our changes, stage, commit, then push them up to github.

Now that we have a project folder added, vscode will have noticed the .git folder and
will use it for connecting to the repo.

`git add .`  
`git commit -m "message"`

You will then need to add a commit message before you can click the button which
is basically like saying I am ready to generate a new hash and save point in time
for this data locally on this box.

Commit messages should be descriptive of what you are accomplishing in this
save. Having lots of mini saves is totally ok, you don't have to do big commits.
`examples:`
  - Initial commit
  - Updated install notes
  - Fixed typo in PFsense notes

Last thing you need to do is push to github.  
`git push`

If you are working in teams and want to be able to work on the project at the same time, best way is to create separate branches in Github to work out of and then
do pull requests against the master branch. Best practice here is after you
commit your code/notes to `Github` Open a `pull request` from your branch to the
master branch. After accepting this delete the branch. Then rebase or clone
from master and create another branch to work out of. These branches are known
as feature branches which allow you to work on a feature with out breaking
the already working code.

It is key to remember to delete your branch because working from it locally
after the pull request was accepted will cause a branch in time. Think endgame
when Hulk is trying to get the time stone.


# This is a heading
`# This is a heading`
## heading 2  
`## heading 2`
### heading 3
`### heading 3`
#### heading 4
`#### heading 4`
##### heading 5
`##### heading 5`
###### heading 6 
`###### heading 6`

---
## **Bold**
`**BOLD** `    
`__BOLD__`  

---
## *Italic*
`*Italic*`  
`_Italic_`

---
##  ***Bold and Italic***
`***BOLD and ITALIC*** `   
`**_BOLD and ITALIC_** `   
`__*BOLD and ITALIC*__ `   
`___BOLD and ITALIC___ `  

---
## ~~Strike through~~  
`~~strike though~~`

---
## Quotes
> This is a quote, useful for calling attention  
`> This is a quote`

---
## Bulleted Lists
If you start your line with `*` or `-` you will create a bulleted item. If you want to create a sub bullet, indent with 2 spaces.  

- bullet 
  - sub bullet   
    - sub sub bullet  

```
- bullet 
  - sub bullet   
    - sub sub bullet
```
---
## Numbered List
Markdown doesn't care what the number is
1. one
1. two
1. three

```
1. one
1. two
1. three
```
---
## Links
Use square brackets and put what text you want to be displayed on the content page, and then in the normal brackets you put the website url that it should link to.

1. online link - [elastic](https://elastic.co)

`[elastic.co](https://elastic.co)`  

2. local link - [front door to this repo](../README.md)

`[front door to this repo](../README.md)`  

The above example can just be a copy paste of the url while editing the test
markdown.

This is usually most helpful by allowing you to link to other parts of your code or documentation.  

---
## Code Blocks
1. Code highlighting:

To call out attention to specific notes or code you can highlight items. To do
this wrap the text with the backtick character (above the TAB key).

`Hightlighed things`

```
`Highlighted things`
```

2. Code Blocks

```
This is a code block
Lots of stuff
format specific
```

```
    ```
    This is a code block
    Lots of stuff
    format specific
    ```
```
---
## Tables
You can also create tables in markdown.

Start it with a Pipe `|` The space is not required but I think it's easier
to read with it. Followed by the first column title, Pipe, and repeat for
as many columns as you need ending with a `pipe` The second row
requires it to start with a pipe and each column needs a minimum of 3 dashes
`-`. Finally the row of text you start with a `pipe` as well add all the data/text you want in that cell of the table. Then end it with a `Pipe` and add data to the
next cell as well.

Example:
|Column 1|Column 2| Column 3 | Column 4 |
| --- | --- | --- | --- |
| Data1| Data2| Data3| Data4 |
| Data5 | Data6 | Data7 | Data8 |

```
|Column 1|Column 2| Column 3 | Column 4 |
| --- | --- | --- | --- |
| Data1| Data2| Data3| Data4 |
| Data5 | Data6 | Data7 | Data8 |
```
---
## Commenting things out

```
<!-- This entire section of text is commented out and will be invisible until uncommented. -->
```

<!-- This entire section of text is commented out and will be invisible until uncommented. -->

---

## Usage

I start out each of major sections with a header. If there are multiple steps
that are related to it I use sub headers to further organize or break out the
different subjects. Next I make heavy use of normal text, code blocks and
highlighting.

My rule of thumb is if its information for myself to read I write in normal text
if it is code or a command I need to run I highlight it. If it is a file
I need to modify I do a code block.

Example:
```
  ...
  ... # random number of lines above
  ...
   # Installing Nginx

   ### Initial Install
   To install nginx we need a yum repo setup. If it isn't setup refer to the
   [yum repo documentation](http://this.doesnt.exist).

   ### Configure NGINX
  After nginx is installed we need to setup our website and the reverse proxy by
  editing the main config file:  
  `sudo vi /etc/nginx/nginx.conf`

      ```
      server {
        listen 80;
        default_;
      ```
  ...
  ... # random number of lines below
  ...
```


   # Installing Nginx

   ### Initial Install
   To install nginx we need a yum repo setup. If it isn't setup refer to the
   [yum repo documentation](http://this.doesnt.exist).

   ### Configure NGINX
  After nginx is installed we need to setup our website and the reverse proxy by
  editing the main config file:  
  `sudo vi /etc/nginx/nginx.conf`

```
      ...

      server {
        listen 80;
        default_;
    
      ...
```



