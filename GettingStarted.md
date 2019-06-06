# Getting Started with Java SE 11
This repository is meant to give a quick run-down of all the features of Java SE 11 (including the concepts of Java 8)
<!--##Pre-Setup-->
### Installing JDK on Windows / Mac
The JDK is a development environment for building applications, and components using the Java programming language. The JDK includes tools useful for developing & testing programs in Java. 
Oracle's OpenJDK (Java Development Kit) version 11 is available for free and can be downloaded from their [website](https://www.oracle.com/technetwork/java/javase/downloads/jdk11-downloads-5066655.html)

Both Mac and Windows require administrator privileges to install the JDK.  

The JDK is installed in the directory `C:\Program Files\Java\jdk-11.i.u` on Windows or  on Mac, where `i` and `u` denote interim and update (followed by a patch number, if any)

### Setting Environment Variables
Environment variables are dynamic and global, they are accessible by all processes of an Operating System, and thus are used in Java store the directories of the executable files like `java.exe` and `javac.exe` to avoid repetition of long commands.
The variables required are: 
* JAVA_HOME
* PATH
* CLASSPATH


#### On Windows
1. `⊞ Win` + `R` opens the Run Window
2. Type `sysdm.cpl` and `Enter↵` or click *OK*
3. Go to *System Properties > Advanced > Environment Variables*
4. Click *New* and Enter the Variable Name as `JAVA_HOME` and set Variable value to `C:\Program Files\Java\jdk-11.i.u`
5. Create new variables named `PATH` and `CLASSPATH` with values `%JAVA_HOME%\bin` and `%JAVA_HOME%\lib` respectively.
<!--https://stackoverflow.com/questions/26864662/the-system-cannot-find-the-file-c-programdata-oracle-java-javapath-java-exe-->
> If you are installing a new version of Java (e.g. Migrating from Java 8 to 11), make sure that you completely uninstall the previous jdk versions and delete the folder `ProgramData/Oracle/..` since this could cause the error `The system cannot find the file C:\ProgramData\Oracle\Java\javapath\java.exe`
#### On Mac
##### Temporary - Set for current session
1. `Shift ⇧` + `⌘ Command` + `U` opens the Terminal
2. Type `export JAVA_HOME=/Library/Java/Home` in the Terminal to set `JAVA_HOME`
3. Type `echo $JAVA_HOME` to finalize set path 
##### Permanent - Make path persist
1. Open Terminal *(Applications > Utilities > Terminal)*
2. Type `emacs .profile` and add the following at the end of the `.profile` file
`
JAVA_HOME=/Library/Java/Home 
`
`
export JAVA_HOME;
`
3. Save & Exit `emacs` (`Ctrl`+`X`, `Ctrl`+`S`; `Ctrl`+`X`, `Ctrl`+`C`)

<!--http://www.sajeconsultants.com/how-to-set-java_home-on-mac-os-x/-->
### Confirming Installed version of Java 

Run the Command Prompt (on Windows) or Open the Terminal (on Mac), and enter `java -version` and your output should look similar to the following:
```
   java version "11.i.u" 20yy-mm-dd LTS
   Java(TM) SE Runtime Environment 18.9 (build 11.i.u+12-LTS)
   Java HotSpot(TM) 64-Bit Server VM 18.9 (build 11.i.u+12-LTS, mixed mode)
```
>If the version shown is a version existing prior to 11, you will need to [set the Environment Variables](#setting-environment-variables) to the directory of the jdk-11 folder

If the CMD or Terminal output is similar to the above, Congratulations on successfully installing JDK on your machine!
For any further clarification regarding the installation read through this once more or refer to the official Oracle [documentation](https://docs.oracle.com/en/java/javase/11/install/overview-jdk-installation.html#GUID-8677A77F-231A-40F7-98B9-1FD0B48C346A)
