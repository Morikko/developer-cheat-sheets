# Linux Commands

## Packages

### Search a command
```bash
dnf provides <command>
```

### Install old package
```bash
dnf --showduplicates list <package>
dnf install <package-with-spec-version> # Overwrite the previous one
```

### Find the installation path
```bash
rpm -ql <tool>
```

## Execution

### Execute command on another display
```bash
$> DISPLAY=:0 <cmd>
```

### Start process independently of the terminal
```bash
nohup script-file </dev/null >/dev/null 2>&1
```

## Libraries

### Print necessary shared libraries
```bash
ldd <lib>
```

### Print library version
```bash
ident <lib>
```

## System

### Memory - Memory (RAM), from high to low
```bash
ps aux --sort -rss
```

#### List disks
```bash
lsblk
```

## Images

### Resize pictures
```bash
mogrify -resize 1200 *.jpg
mogrify -resize x1200 *.jpg
```

## Search

### Search multiple words with grep
```bash
grep 'pattern1\|pattern2' file1 file2 # Use single quotes in the pattern
egrep 'pattern1|pattern2' *.py # Use extended regular expressions
```

## Text processing

### Split text with word delimiter
```bash
echo "onewordtwowordthreewordfour" | awk -F"word" '{print $1}'   
```  

### Cut: select part of info
```bash
# Extract characters
cut -c1 # Only 1
cut -c1-3 # 1 to 3
cut -c3- # 3 to end
# Extract field
cut -f1 # Only 1
cut -f1,6 # 1 and 6
cut -f1-4,6 # 1 to 4 and 6
```

### Sed: reformat info
```bash
sed '1d' # Remove 1st line
sed 's/bla/blabla/g' # Replace bla with blabla
sed 's/1/0/g;s/0/1/g' # Double replacement
```
### Awk: process info
```bash
# Compute sum
awk '{SUM +$1} END { print SUM/10}' # $1: column 1
```

## Arguments Parser
[Project argbash](https://argbash.io/generate) is a code generator for bash scripts.

## Screen 
 [Keep Your Processes Running Despite A Dropped Connection (Source)](https://www.howtoforge.com/linux_screen)

### Multiple session independent of the current shell terminal
```bash
screen
```

### Showing all the screen sessions
```bash
screen -ls
```

### Reconnect to the session
```bash
screen -r 2477.pts-0.server1
```

### To close a session
```bash
exit
```

## Bash syntax

### Boolean test
```bash
if [ "$_arg_boolean" = on ]
```
