### Useful Ubuntu Commands

Query-1:  **Find all files containing specific text (string) on Linux ?**

Solution: 
```
grep -rnw '/path/to/somewhere/' -e 'pattern'
```
where

    -r or -R is recursive,
    -n is line number, and
    -w stands for match the whole word.
    -l (lower-case L) can be added to just give the file name of matching files.
    -e is the pattern used during the search

[Extra Info Link](https://stackoverflow.com/questions/16956810/how-to-find-all-files-containing-specific-text-string-on-linux)
