# Useful Scripts

This repo contains useful scripts that I wanted to save and instructions on
how to use them.

## src2pdf

This script will recursively convert all source code files in a directory to
a pdf file with a table of contents.

### Dependencies

- texlive-latex-extra
- latex-xcolor
- texlive-latex-recommended

### Running the Script

The language option needs to be added to the lstdefinestyle options depending
on the language you are trying to convert to a pdf. This creates some 
complications for things like config files being included, but it is still 
pretty useful.

```bash
./src2pdf
```

### Credits

This script was originally found on StackExchange from author terdon. The 
original post can be found [here](https://superuser.com/questions/601198/how-can-i-automatically-convert-all-source-code-files-in-a-folder-recursively/601412)

