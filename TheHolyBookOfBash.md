[Source](https://www.gnu.org/software/bash/manual/bash.html#Shell-Parameter-Expansion)

[//]: # (
Format:
## Name
### Syntax
<!-- Bash script block -->
```bash
# Example here
```
- Notes
)

# Contents:
<details> <summary> <a href="#data-types">Data Types</a> </summary>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#numbers">Numbers</a><br>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#strings">Strings</a><br>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#arrays">Arrays</a>
</details>
<details> <summary> <a href="#operators">Operators</a> </summary>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#maths">Maths</a><br>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#string-manipulation">String Manipulation</a><br>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#comparisons">Comparisons</a>
</details>
&nbsp;&nbsp;&nbsp;<a href="#variables">Variables</a>
<details> <summary> <a href="#conditional-constructs">Conditional Constructs</a> </summary>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#case">Case</a><br>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#if">If</a><br>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#-h3-iddouble-parenthesish3">((…))</a><br>
  &nbsp;&nbsp;&nbsp;&nbsp;<a href="#-h3-iddouble-bracketsh3">[[...]]</a>
</details>




# Data Types:
In Bash, variables are used to store values that can be referenced and manipulated throughout the script. Bash variables are untyped, which means they can hold values of any data type, including numbers, strings, arrays, and even other variables.

[//]: # (TODO: Proof read that ^ and add the appropriate sections)

## Numbers
[//]: # (TODO:)
Only raw numbers can do maths\
$((...))
<!-- Bash script block -->
```bash
echo $((1+2))
```
Questions:
- [ ] ((OPTIND++)) Why do I need the '(())'? Is it cause all math operations need to me in a '(())'?

## Strings
[//]: # (TODO: Format)
[//]: # (
Strings are surrounded in double &#40;"&#41; or single &#40;'&#41; quotes
If a data item is to be treated like a string contain it with quotes!
When dealing with numbers use quotes to ensure that any numbers are treated as strings
more deets abt strings
)
[//]: # (
my_var="Hello, World!"
echo ${my_var,} # Outputs "hello, World!"
echo ${my_var^^} # Outputs "HELLO, WORLD!"
echo ${my_var//o/a} # Outputs "Hella, Warld!"
)

## Arrays
### array=(element1 element2 element3...)
[//]: # (TODO:)
[//]: # (element 1+2 are strings and element3 is a variable)
[//]: # (The [@] is used to index all the elements of an array.IS THIS TRUE?)

[//]: # (I believe the reason that the double quotes &#40;"&#41; are required when calling the array in the for loop is because every time the array is indexed the quotation marks encapsulateIS THIS TRUE?)
[//]: # (
my_array=&#40;"apple" "banana" "orange" "grape"&#41;
Loop through the array and print each element
for i in "${my_array[@]}"
do
  echo "$i"
done
)


# Operators:
## Maths:
[//]: # (TODO: Format)
[//]: # (Math can only be done with raw integers not string integers)
[//]: # ($&#40;&#40;operations&#41;&#41;)
[//]: # (Understand why the syntax works like that)
[//]: # (addition &#40;+&#41;)
[//]: # (subtraction)
[//]: # (/ division)
[//]: # (Returns the answer rounded down to the whole number)
[//]: # (ex: $&#40;&#40;5/3&#41;&#41;; >>> 1 )
[//]: # (multiplication &#40;*&#41;)
[//]: # (% divides then returns the remainder)
[//]: # (ex: $&#40;&#40;5%3&#41;&#41;; >>> 2)
[//]: # (Functions)
[//]: # (Include some essential maths functions use link as a jumping point)
[//]: # ([link]&#40;https://unix.stackexchange.com/questions/40786/how-to-do-integer-float-calculations-in-bash-or-other-languages-frameworks&#41;)
[//]: # (x++ = x = x+1)

## String manipulation:
[//]: # (TODO:)

## Comparisons:
[//]: # (TODO: Format)
[//]: # (6.4 Bash Conditional Expressions)
[//]: # (Conditional expressions are used by the [[ compound command &#40;see Conditional Constructs&#41; and the test and [ builtin commands &#40;see Bourne Shell Builtins&#41;. The test and [ commands determine their behavior based on the number of arguments; see the descriptions of those commands for any other command-specific actions.)
[//]: # (Expressions may be unary or binary, and are formed from the following primaries. Unary expressions are often used to examine the status of a file. There are string operators and numeric comparison operators as well. Bash handles several filenames specially when they are used in expressions. If the operating system on which Bash is running provides these special files, Bash will use them; otherwise it will emulate them internally with this behavior: If the file argument to one of the primaries is of the form /dev/fd/N, then file descriptor N is checked. If the file argument to one of the primaries is one of /dev/stdin, /dev/stdout, or /dev/stderr, file descriptor 0, 1, or 2, respectively, is checked.&#41;''[//]: # &#40;When used with [[, the ‘<’ and ‘>’ operators sort lexicographically using the current locale. The test command uses ASCII ordering.)
[//]: # ([//]: # &#40;Unless otherwise specified, primaries that operate on files follow symbolic links and operate on the target of the link, rather than the link itself.&#41;'')
[//]: # (-a file)
[//]: # (True if file exists.)
[//]: # (-b file)
[//]: # (True if file exists and is a block special file.)
[//]: # (-c file)
[//]: # (True if file exists and is a character special file.)
[//]: # (-d file)
[//]: # (True if file exists and is a directory.)
[//]: # (-e file)
[//]: # (True if file exists.)
[//]: # (-f file)
[//]: # (True if file exists and is a regular file.)
[//]: # (-g file)
[//]: # (True if file exists and its set-group-id bit is set.)
[//]: # (-h file)
[//]: # (True if file exists and is a symbolic link.)
[//]: # (-k file)
[//]: # (True if file exists and its "sticky" bit is set.)
[//]: # (-p file)
[//]: # (True if file exists and is a named pipe &#40;FIFO&#41;.)
[//]: # (-r file)
[//]: # (True if file exists and is readable.)
[//]: # (-s file)
[//]: # (True if file exists and has a size greater than zero.)
[//]: # (-t fd)
[//]: # (True if file descriptor fd is open and refers to a terminal.)
[//]: # (-u file)
[//]: # (True if file exists and its set-user-id bit is set.)
[//]: # (-w file)
[//]: # (True if file exists and is writable.)
[//]: # (-x file)
[//]: # (True if file exists and is executable.)
[//]: # (-G file)
[//]: # (True if file exists and is owned by the effective group id.)
[//]: # (-L file)
[//]: # (True if file exists and is a symbolic link.)
[//]: # (-N file)
[//]: # (True if file exists and has been modified since it was last read.)
[//]: # (-O file)
[//]: # (True if file exists and is owned by the effective user id.)
[//]: # (-S file)
[//]: # (True if file exists and is a socket.)
[//]: # (file1 -ef file2)
[//]: # (True if file1 and file2 refer to the same device and inode numbers.)
[//]: # (file1 -nt file2)
[//]: # (True if file1 is newer &#40;according to modification date&#41; than file2, or if file1 exists and file2 does not.)
[//]: # (file1 -ot file2)
[//]: # (True if file1 is older than file2, or if file2 exists and file1 does not.)
[//]: # (-o optname)
[//]: # (True if the shell option optname is enabled. The list of options appears in the description of the -o option to the set builtin &#40;see The Set Builtin&#41;.)
[//]: # (-v varname)
[//]: # (True if the shell variable varname is set &#40;has been assigned a value&#41;.)
[//]: # (-R varname)
[//]: # (True if the shell variable varname is set and is a name reference.)
[//]: # (-z string)
[//]: # (True if the length of string is zero.)
[//]: # (-n string)
[//]: # (string)
[//]: # (True if the length of string is non-zero.)
[//]: # (string1 == string2)
[//]: # (string1 = string2)
[//]: # (True if the strings are equal. When used with the [[ command, this performs pattern matching as described above &#40;see Conditional Constructs&#41;.)
[//]: # (‘=’ should be used with the test command for POSIX conformance.)
[//]: # (string1 != string2)
[//]: # (True if the strings are not equal.)
[//]: # (string1 < string2)
[//]: # (True if string1 sorts before string2 lexicographically.)
[//]: # (string1 > string2)
[//]: # (True if string1 sorts after string2 lexicographically.)
[//]: # (arg1 OP arg2)
[//]: # (OP is one of ‘-eq’, ‘-ne’, ‘-lt’, ‘-le’, ‘-gt’, or ‘-ge’. These arithmetic binary operators return true if arg1 is equal to, not equal to, less than, less than or equal to, greater than, or greater than or equal to arg2, respectively. Arg1 and arg2 may be positive or negative integers. When used with the [[ command, Arg1 and Arg2 are evaluated as arithmetic expressions &#40;see Shell Arithmetic&#41;.)


# Variables:
[//]: # (TODO: Format)
[//]: # (Defined by a single '=')
[//]: # (ex: things_i_love="cats")
[//]: # (ONLY global and shell variables should be all uppercase)
[//]: # (ex: PWD vs things_i_love)
[//]: # (Local variables should be lowercase)
[//]: # (To call a variable use a single '$')
[//]: # (ex: $PWD or $things_i_love)
[//]: # (When calling a variable the {} are used to isolate the variable to ensure correct syntax.)
[//]: # (EX: echo "${Hello}World" vs echo -n "$Hello"; echo "World" because echo "$HelloWorld" returns something different)
[//]: # (The [@] is used to index all the elements of a variable. IS THIS TRUE?)

[//]: # (TODO: why use this: ${!OPTIND} instead of this: ${${OPTIND}})


# Conditional Constructs:
- Statements are a form of high level logic operations (like an if statement).
- They are a feature of a language that allows customized inputs and outputs.

[//]: # (TODO: The above line 'customized inputs and outputs' doesn't make any sense.
               This is also a feature of a function.
               So what is the essence, what makes a statement unique?)

## case
[//]: # (TODO: Format)
### case \<variable> in; \<pattern>); \<code>;; esac
[//]: # (In a way case acts as a set of nested if statements)
<!-- Bash script block -->
```bash
variable=pattern

case $variable in
  pattern)
    echo "pattern";;
esac
```
[//]: # (broken down:)
[//]: # (case $variable in)
[//]: # (Initiates the case statement)
[//]: # (The value of $variable will be checked against all the below value)
[//]: # (The 'in' keyword encapsulates the variable being matched and is followed)
[//]: # (by the patterns being matched)
[//]: # (pattern&#41;)
[//]: # (This is the first pattern being matched)
[//]: # (Case automatically treats the $variable and pattern&#41; as strings)
[//]: # (So if $variable=pattern then the code below pattern&#41; will execute)
[//]: # (If not nothing will happen and the statement tries the other patterns)
[//]: # (The close parentheses '&#41;' indicates the end of the pattern)
[//]: # (echo "pattern" ;;)
[//]: # (This is the code that is executed if $variable matches pattern)
[//]: # (This section is highly customizable)
[//]: # (The double semicolon is a control operator)
[//]: # (This specific control operator ';;' ends the case statement and)
[//]: # (stops trying to match $variable to other patterns)
[//]: # (If there is another pattern that will match $variable it will)
[//]: # (never execute)
[//]: # (ex: )
[//]: # (case $variable in)
[//]: # (pattern&#41;)
[//]: # (echo "pattern 1")
[//]: # (;;)
[//]: # (pattern&#41;)
[//]: # (echo "pattern 2")
[//]: # (;;)
[//]: # (esac)
[//]: # (esac)
[//]: # (This keyword signals the complete end of the case statement)
[//]: # (Nothing super special just case backwards)

## if
[//]: # (TODO: Format)
[//]: # (Comprised of CONDITION and STUFF commandsIS THIS TRUE?)
[//]: # (When CONDITION is executed it leaves behind an exit statusIS THIS TRUE?)
[//]: # (If this exit status is 0 then the CONDITION evaluated to true and if not it's falseIS THIS TRUE?)
[//]: # (STUFF is only executed if CONDITION exits with a status of 0IS THIS TRUE?)
[//]: # (ex: if CONDITION IS THIS TRUE?)
[//]: # (do STUFF IS THIS TRUE?)
[//]: # (fiIS THIS TRUE?)

## select
[//]: # (TODO:)

## ((…)) <h3 id="double-parenthesis"></h3>
[//]: # (TODO:)

## [[…]] <h3 id="double-brackets"></h3>
[//]: # (TODO:)


# Looping constructs:

## while
### while [\<command>]; do; \<code>; done
<!-- Bash script block -->
```bash
i=0
while [ "${i}" -lt 10 ] 
do
  echo "${i}"
  i++
done  # ends the loop
```
'-lt' is equivalent to '<' see: [Comparisons](#comparisons) for more

Executes &lt;code&gt; as long as &lt;command&gt; has an exit status of 0


## for

[//]: # (TODO:)

## until

[//]: # (TODO:)


# Bourne Shell Built-ins:

## exit

[//]: # (TODO:)

## :

[//]: # (TODO:)

## .

[//]: # (TODO:)

## break

[//]: # (TODO:)

## cd

[//]: # (TODO:)

## continue

[//]: # (TODO:)

## eval

[//]: # (TODO:)

## exec

[//]: # (TODO:)

## export

[//]: # (TODO:)

## getopts
### getopts \<optsting> \<name> [arg1 arg2 argX]
- Use by a script to parse positional parameters 
- Each time getopts is called the next argument from the execution of the script is accessed and assigned to \<name>
- \<optstring> contains the option characters to be recognized
- if a character is followed by a colon (;) the option is expected to have an argument, which should be separated from it by whitespace 
- The colon ':' and question mark '?' may not be used as option characters 
- The index of the last argument accessed is stored in $OPTIND 
- $OPTIND is only reset or initialized to 1 every time a script is executed 
- By default, processes args passed on script execution but can process builtin args [arg 1 arg2 argX]
- If the first character of \<optstring> is a colon, silent error reporting is used 
- In normal operation, diagnostic messages are printed when invalid options or missing option arguments are encountered

<!-- Bash script block -->
```bash
getopts ":hrvklpsui" opt
```
- Reads the first argument (arg1) passed when the script was executed
- This is the first time getops is called, so it initializes $OPTIND and sets it to 1
- Runs in silent mode because <optstring> starts with a ':'
- Checks the value of arg1 against h, r, v, k, l, p, s, u, or i
- The value of arg1 is assigned to $opt
- Why does it work in a while loop?
  - I believe it works cause the  exit status remains 0 until all args are passed or there is an error
- Can I allow any character to be processed and passed to $opt? This would leave the error reporting and logic to the case statement (which I feel is more efficient)
  - hello

[//]: # (TODO: Understand how the returned logic works)
[//]: # (TODO: what happens to the arguements that are passed when they aren't in <optsting>?)

## hash

[//]: # (TODO:)

## pwd

[//]: # (TODO:)

## readonly

[//]: # (TODO:)

## return

[//]: # (TODO:)

## shift

[//]: # (TODO:)

## test

[//]: # (TODO:)

## umask

[//]: # (TODO:)

## unset

[//]: # (TODO:)

# Passing arguments to a function:
### IS THIS TRUE?

[//]: # (TODO:)
Update with the while and case rombo combo
When a function is called special sheet variables are used to assign what arguments have been passed
These variables are $0 through $9
$0 is always fixed to the function (or executable) name
$1 $9 are all the arguments
$# is the number of arguments passed
EX. In "ScriptKitty -h" $# will evaluate to 1

# Syntax:

[//]: # (TODO:)
Use "man bash" as a jumping off point
Control operators
A token that performs a control function.
||
&
&&
;
Semicolons (;) can be used to make lines of code denser it is signifies a new line of code to the interpreter
;;
( )
|
|&
<newline>

Metacharacters 
A character that, when unquoted, separates words.
|
&
;
( )
IS THIS ▼ VALID?
Allow the user to execute the enclosed code in a subshell
This subshell acts similar to a function in python and will keep any variable assignments or redirection isolated
< >
space
tab

## Where do I put these?? ▼ 

[//]: # (Parenthesis with a leading dollar sign $&#40;&#41;)

[//]: # (This is a 'command substitution')

[//]: # (Executes the nested command in a subshell)

[//]: # (Useful for getting the output of a command and substituting it)

[//]: # (ex: VAR=$&#40;Command arg1 arg2&#41;)

[//]: # (Double brackets [[]])

[//]: # (These surround conditional expressions)

[//]: # (There MUST be spaces between every element '[[ -e $file ]]' is good but '[[-e$file]]' is bad)

[//]: # (Some logic operators)

[//]: # (https://www.gnu.org/software/bash/manual/bash.html#Bash-Conditional-Expressions)

[//]: # (Is equal to)

[//]: # ([[ $var1 == $var2 ]])

[//]: # (Is not equal to)

[//]: # ([[ $var1 != $var2 ]])

[//]: # (sort )

[//]: # ([[ $var1 > $var2 ]] true if var1 sorts before var2 lexicographically &#40;the way a dictionary is sorted use an ascii table&#41;)

[//]: # (Single brackets [])

[//]: # (A legacy way to use conditional expressions)

[//]: # (This syntax can be used but may be funky)

[//]: # (Best only for use when a script is to be used by multiple different shells)

# Portability

[//]: # (TODO:)
Use [] and = for conditional expressions (replaces [[]] and == respectively)
What are the main differences between shells?

# Exit status of a command
### IS THIS TRUE?
Every time a command is run an exit status is outputted
This status is stored in$? For the last command executed
If the command is successful then exit status of 0 is assigned if there is a failure any number between 1 and 255 can be assigned
Extremely useful for error handling and debugging

# Passing an argument to a script (flags)
### IS THIS TRUE?
example: 
script:
echo -e "Function name: $0\nArg 1: $1\nArg 2: $2\nTotal args: $#"
user input: 
./TestRange -a balloon
output:
Function name: ./TestRange
Arg 1: -a
Arg 2: balloon
Total args: 2

# Special Characters
#### [Source](https://stackoverflow.com/questions/3005963/how-can-i-have-a-newline-in-a-string-in-sh)

[//]: # (TODO: Find a place to put me. I'm thinking under Datatypes > strings)
[//]: # (Words of the form $'string' are treated specially. The word expands to)
[//]: # (string, with backslash-escaped characters replaced as specified by the)
[//]: # (ANSI C standard. Backslash escape sequences, if present, are decoded)
[//]: # (as follows:)
[//]: # (      \a     alert &#40;bell&#41;)
[//]: # (      \b     backspace)
[//]: # (      \e)
[//]: # (      \E     an escape character)
[//]: # (      \f     form feed)
[//]: # (      \n     new line)
[//]: # (      \r     carriage return)
[//]: # (      \t     horizontal tab)
[//]: # (      \v     vertical tab)
[//]: # (      \\     backslash)
[//]: # (      \'     single quote)
[//]: # (      \"     double quote)
[//]: # (      \nnn   the eight-bit character whose value is the octal value)
[//]: # (             nnn &#40;one to three digits&#41;)
[//]: # (      \xHH   the eight-bit character whose value is the hexadecimal)
[//]: # (             value HH &#40;one or two hex digits&#41;)
[//]: # (      \cx    a control-x character)
[//]: # ()
[//]: # (The expanded result is single-quoted, as if the dollar sign had not)
[//]: # (been present.)
[//]: # ()
[//]: # (A double-quoted string preceded by a dollar sign &#40;$"string"&#41; will cause)
[//]: # (the string to be translated according to the current locale. If the)
[//]: # (current locale is C or POSIX, the dollar sign is ignored. If the)
[//]: # (string is translated and replaced, the replacement is double-quoted.)

# Positional Parameters (Builtins?)
### $1, $2, ... $n:
These variables represent the values of individual positional parameters. $1 is the first argument, $2 is the second argument, and so on.
### $#:
The variable $# holds the total number of positional parameters.
### $@:
$@ represents all the positional parameters as a list. It's often used in loops or when you need to reference all the arguments.
### $*:
Like $@, $* represents all the positional parameters as a single string, with each parameter separated by the first character in the $IFS (Internal Field Separator) variable (usually a space).
### Shift:
The shift command is used to shift positional parameters to the left. It's often used to process or remove arguments after they've been used.
### $OPTIND:
$OPTIND is a variable used by getopts to keep track of the index of the next argument to be processed.
### $opt:
$opt is a variable used with getopts to hold the currently processed option character. It's not a system variable; it's automatically set by getopts for convenience.
### $OPTARG:
$OPTARG is used with getopts to hold the argument associated with the currently processed option.
### IFS (Internal Field Separator):
IFS is an environment variable that determines how Bash splits words into fields when interpreting unquoted strings. By default, it includes whitespace characters (space, tab, newline).
You can access the current value of IFS using $IFS.
### Unset:
The unset command can be used to unset (delete) a specific positional parameter or variable.
### $_ 
the last argument to the last command
### $?
the exit status of the last executed command
[//]: # (TODO: other Special Parameters)


# Positional Param Commands
### Shift


# Sort Me
### &gt;&gt;
#### command &gt;&gt; file
- Appends the output of command to file

### &gt;
#### command &gt; file
- Overwrites file with the output of command ($stdout)


### |
#### command1 | command2
- transfers the output of command 1 to the input of command 2

[//]: # (TODO:$stdout and $stdin)

