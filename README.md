# Poor-file-name-finder
Bash script to find files that have "poor names" as specified by the script regular expression.

Usage:
`poornames [directory to search] [-r]`

If no directory to search is provided, then poornames will search the working directory it is in.

The use of the -r flag will enable recursive running: poornames will enter any directory it finds in the directory it is searching and look for poor name violations in these directories as well.

Currently, the implementation of the script is to find files that violate the following naming rules:
- A file name component must contain only ASCII letters, ‘.’, ‘-’, and ‘_’. A file name component is a nonempty part of a file name that is a maximal sequence of characters other than ‘/’; for example, the file name ‘/usr/lib64/libstdc++.so.6’ has the three components ‘usr’, ‘lib64’, and ‘libstdc++.so.6’, where the second component violates this guidline due to the digits ‘6’ and ‘4’ and the last component’s two ‘+’ characters and the ‘6’ digit violate this guideline
- A file name component cannot start with '-'
- Except for ‘.’ and ‘..’, a file name component cannot start with ‘.’
- A file name component must not contain more than 14 characters
- No two files in the same directory can have names that differ only in case - e.g. the two files, "apoorname" and "aPooRNamE" cannot exist together
