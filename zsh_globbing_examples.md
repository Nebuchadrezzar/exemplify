# zsh globbing it operators and qualifiers 
references:
https://zsh.sourceforge.io/Doc/Release/Expansion.html
https://reasoniamhere.com/2014/01/11/outrageously-useful-tips-to-master-your-z-shell/


### list files only: (.)
```bash
ls **/*(.)
```

### list folders only: (/)
``` bash
ls **/*(/)
```

### list all but only two directories down: 
```bash
ls top_folder/*/*
```

### Search for changed files in the last five days: (.cd-5)
```bash
ls -l **/*(py|xml|xq|html)(.cd-5)
```
#### Qualify by time when files are (c)reated, (m)odified, or (a)ccess. 
c, m, a stand for file inode change time, the file modification time, files accessed. 
s, m, h, d, w, and M stand for seconds, minutes, hours, days, weeks, and Months.

### Search for top fifteen changed files ordered by latest modifications: (om[1,15])
```bash
ls -l **/*(py|xml|xq|html)(om[1,15])
```

### Search for files larger than 3MB: (Lm+3)
```bash
ls -l **/*(Lm+3)
```
#### Qualify by file size 
when files are (+) larger or (-)smaller
when sizes are (k) Kilobytes, (m) megabytes 

### Combine Quailifers: no spaces!
```bash
ls -l **/*(py|xml|xq|html)(Lm-3om[1,15])
```
note: the size limit (less than 3mb) and the ordered by modification qaulifiers are combined in the example. 

### Print only the file name: (:t)
```bash 
print -l **/*(*.xq)(:t)
```

### Print the file name without its extension: (:t:r)
```bash 
print -l **/*(*.xq)(:t:r)
```

### Print the file name extensions: (:e)
```bash 
print -l **/*(:e) | uniq 
```
note: printing the unique set of file extentions in dirs. 














