Are you ["frequently switching between directories that are in totally unrelated paths"](https://unix.stackexchange.com/questions/31161/quick-directory-navigation-in-the-bash-shell)?! Then PEVs (Personal Environment Variables) are for you.



### **example**:

Let's add a pev variable first:
```
$ pev add longpath '/A/very/very/long/path/I/frequently/need'

# environment variable "pev_longpath" added successfully. "pev show" to see the list of pev variables.
```
Now let's see a list of pev variables defined so far:
```
$ pev show

   |   NAMES          VALUES
   |   ----------     ----------
   |   pev_longpath   "/A/very/very/long/path/I/frequently/need"
```
To only print the value of a pev variable easily write:
```
$ pev longpath
```
Now let's change directory to that long path, it could be either done using command substitution or __the complete pev variable's name preceded by the dollar sign__:
```
$ cd $(pev longpath)

# OR alternatively:

$ cd $pev_longpath

# there's no difference, use whichever you're happier with.
```
Obviously the command you use your pev variable in, does not necessarily need to be a "cd" command, it can be any other commands as well.
```
$ cp somefile $pev_longpath
```
Or you can go deeper too:
```
$ cp somefile $pev_longpath/and/deeper/than/that
```
---
## Notice:

 Of course pev is not only limited to keeping paths, it might be used for any other purposes as well where quick access to frequently needed values is a need.

# **Usage**:


        pev <NAME>:
                echoes the value of the Personal Environment Variable named <NAME>

        pev add <NAME> <VALUE>:
                Adds a Personal Environment Variable

        pev remove <NAME>:
                Removes a Personal Environment Variable

        pev show:
                Shows a list of Personal Environment Variables

        pev edit <NAME> <NEW-VALUE>:
                Change the value of a predefined pev variable to a <NEW-VALUE>

        pev edit:
                Edit the list of Personal Environment Variables manually(NOT RECOMMENDED)


---
### _Please email me at [ aderchox[ at ]gmail[ dot ]com ] for any feedback._
