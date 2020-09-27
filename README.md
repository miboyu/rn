# Rename files with regex.

---------------
***Contents:***

> *[1. Introduction](#1)* <br>
> *[2. Examples](#2)* <br>
> *[3. Install](#3)* <br>
> *[4. Change Log](#4)* <br>
> *[5. License](#5)* <br>
> *[6. TODO](#6)* <br>
> *[7. Author](#7)*

---------------
<h2 id="1">1.Introduction</h2>

Use extended regular expression to rename files.

    Usage:
        rn [<options>] <old_pattern> <new_pattern> [<files>]

    Options:
        -r | --run          run mode, execute the renaming process
        -q | --quiet        quiet mode, show least information
        -v | --verbose      verbose mode, show most information
        -f | --force        force mode, overwrite existing target
        -l | --lower        to lower case, add -f if the name is case insensitive
        -u | --upper        to upper case, add -f if the name is case insensitive
        -n | --number=[ch]  'ch' will be replaced by a serial number in new_pattern,
                            the default 'ch' is '#'
             --nbegin #     beginning number when -n is used, defaulted as 1
             --nstep #      step number when -n is used, defaulted as 1
             --nwidth #     least width of the serial number when -n is used,
                            defaulted as 2 (eg: 1 will be 01)
        -A | --all          all types of file will be renamed
        -F | --file         regular file will be renamed
        -D | --dir          directory will be renamed
        -B | --block        block device file will be renamed
        -C | --char         character device file will be renamed
        -S | --socket       socket file will be renamed
        -P | --pipe         pipe file will be renamed
        -L | --link         symbolic link file will be renamed
             --help         show this help information
             --version      show version information
             --regex        show quick reference of regex
             --example      show examples
             --return-code  show return codes

    The command runs in TEST mode by default, add --run option to take effects.

    Wildcards(*?) are supported in <files>. If there are spaces in filenames, the
    <files> with wildcards should be quoted in '' or \"\". If <files> is omitted,
    it is the same as '*', which means all files in current working directory.
    If the <files> has parent path (contains '/'s), only the last part would be
    renamed, leaving parent path unchanged, and the last part could be file, dir,
    and so on.

    Quiet mode will print no information except for the error messages. Verbose mode
    will print as much information as possible, which can be used to check the inner
    status. If there is no --quiet or --verbose option, the normal mode will only
    print necessary information.

    Some options might conflict, like --quiet & --verbose, --lower & --upper, only
    the last one takes effect. For example, '$rn -u -l' means 'to lower case'.

    The file type options (-FDBCSPL) are used to filter unexpected files. It can
    also be accomplished by user in argument <files> before passing it in. If no
    file type option is given, the default types (file, dir, and link) are used.

--------------
<h2 id="2">2.Install</h2>

    git clone https://github.com/miboyu/rn
    (or git clone https://gitee.com/miboyu/rn)
    cd rn
    make install

--------------
<h2 id="3">3.Change Log</h2>

    1.0.5 (2020/09/27)
        Remove the --origin and --substi options, use position arguments.
        Remove --test option, defaulted as test mode.

    1.0.4 (2019/11/21)
        Fix the filename-with-space problem, see help for details.
        Remove "--space" option.

    1.0.3 (2019/09/19)
        Make the prompted command name dynamic.
        Add "makefile" to install the command.

    1.0.2 (2019/09/14)
        Change to extended regex "sed -E ...".
        Support more escape characters \d \D etc.
        Add option --regex to show quick reference of regex.

    1.0.1 (2019/09/13)
        Fix some bugs.
        Add more verbose information.

    1.0.0 (2019/09/12)
        Initial version.

--------------
<h2 id="4">4.License</h2>

This bash script is under license of GPLv3.

---------------
<h2 id="5">5.TODO</h2>
- Write renaming log, and add option --roll-back to roll back from the log.

--------------
<h3 id="6">Author: Boyu Mi (miboyu@yeah.net)</h3>

Thanks for using the script. If you feel good about it, a recommendation to your
friends will be appreciated. Any bugs or suggestions, please contact the author
(_miboyu@yeah.net_). Your feedback will help improving the script ^o^

--------------

