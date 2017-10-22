# Vim

### Reload .vimrc from editor
```
:so $MYVIMRC
```

### Search word under the cursor:
 - `*` Move Forward
 - `#` Move Backward

### * Search among all files to open
```
:tabe **/<file_to_search>
```

### Open a new files
```
:tabe <filepath>    # New tab
:new <filepath>     # Split the window horizontally
:edit <filepath>    #  close current window before opening
```

### Search in directory
```
:e <directory>
# In current directory
:e.
# replace the current file or split horizontally with change not save
:E
```
#### Note
_INF Error E464_ after a shortcut command result that another command begins with the same letters (Example -- :E pour :Explore)

Solution: force command by changing conf file "command! E Explore"

## Javascript

### Jsdoc.vim: add jsdoc before a function
 1.   Move cursor on function keyword line.
 2.   Type :JsDoc to insert JSDoc.
 3.   Insert JSDoc above the function keyword line.
