# PCRE examples (ag uses Perl Common Regular expressions) #
https://help.dyalog.com/13.2/Content/Language/Appendices/PCRE%20Regular%20Expression%20Details.htm

### positive lookahead: (?<=pattern)
```bash
$ echo "test this" | ag -o "(?<=test.)\w+"
this
```

### negative lookahead: (?<!pattern)
```bash
echo "testing this" | ag -o "(?<\!foo.).*"
testing this
```
note: escaping the exclamation is need on some shells: \\!

### Reset match start: \K
```bash
echo "test this" | ag -o "test\K.*"
this
```
note: any matched characters before \\K are not included in the final match

### mutlilines search: (?s) or the pattern (\n|.)
```bash
$cat test_newlines.txt
another
test
that
spans
over
newlines
$ag '(?s)another.*test' test_newlines.txt
1:another
2:test
```
note: this will not work with streams. 



