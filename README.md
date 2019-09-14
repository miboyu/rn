# Rename files with regex.

> ***rn [options] [-o origin -s substitute] [files]***

Use extented regular expression to rename files. If the "origin" and 
"substitute" are not given, you can still change the letter case and/or
add serial number at the beginning of the filename.

See ***rn --help*** for details.

See ***rn --example*** for examples.

See ***rn --regex*** for quick reference of **regex**

-----------
#### Example 1: Add "-" between "*year*" "*month*" and "*day*" in filenames

- Files at the beginning 

![](example/ls-1.png)

- Rename **TEST MODE**

![](example/rn-1-t.png)

- Rename **VERBOSE TEST MODE**

![](example/rn-1-tv.png)

......

![](example/rn-1-tv2.png)

- Rename **RUN MODE**

![](example/rn-1.png)

- Files after renaming

![](example/ls-2.png)


#### Example 2: Add serial number
-
![](example/rn-2.png)

--------------
## Change Log:

    1.0.2 (2019/09/14)
        Change to extended regex "sed -E ...".
        Support more escape characters \d \D etc.
        Add option --regex to show quick reference of regex.

    1.0.1 (2019/09/13)
        Fix some bugs.
        Add more verbose information.

    1.0.0 (2019/09/12)
        Initial version.

---------------

### **Author  : Boyu Mi (miboyu@yeah.net)**
